### Remove Image Background by Color - Gimp Plugin
This is a simple background removal tool that is NOT AI POWERED. I made this to show off the power of GEGL and I am fully aware state of the art background removal tools far exceed this.

Use the color dropper to select which color to remove from an image and all neighboring colors (such as the color blue) will be removed. Users are allowed to select up to five colors to remove and use other settings to increase the likelyhood of a successful background removal. There are also special modes that call it with my threshold alpha and edge smooth plugins, that saves time as you don't have to run them manually afterward. This plugin is NOT a AI based miracle worker like REMBG U2NET :D,  but it can remove simple colored backgrounds consistently. The key to this plugin being successful is that the background and foreground must already be contrasting colors. It is expected to use a layer mask above and mask out the mistakes this plugin made or erase manually whatever it failed to erase. 

![image](https://github.com/LinuxBeaver/Background_Remover_By_Color_Gimp_Plugin/assets/78667207/7abdd25b-220e-4efd-a217-ad947ac029b0)

![image](https://github.com/LinuxBeaver/Background_Remover_By_Color_Gimp_Plugin/assets/78667207/d7fd33eb-b6c8-46fe-b2cf-0884a027f007)

**Download procompiled binaries here**

https://github.com/LinuxBeaver/Background_Remover_By_Color_Gimp_Plugin/releases/tag/Background_Remove_By_color

## Location to put binaries

## Windows
 C:\Users\(USERNAME)\AppData\Local\gegl-0.4\plug-ins
 
## Linux 
 /home/(USERNAME)/.local/share/gegl-0.4/plug-ins
 
## Linux (Flatpak includes Chromebook)
 /home/(USERNAME)/.var/app/org.gimp.GIMP/data/gegl-0.4/plug-ins

then restart Gimp and go to GEGL Operation and look for Sketch Charcoal Effect in the drop down list. If you use Gimp 2.99.16+ you will see this filter in Filters>Artistic>Sketched Image.


## Compiling and Installing

### Linux

To compile and install you will need the GEGL header files (`libgegl-dev` on
Debian based distributions or `gegl` on Arch Linux) and meson (`meson` on
most distributions).

```bash
meson setup --buildtype=release build
ninja -C build

```
 

### Windows

The easiest way to compile this project on Windows is by using msys2.  Download
and install it from here: https://www.msys2.org/

Open a msys2 terminal with `C:\msys64\mingw64.exe`.  Run the following to
install required build dependencies:

```bash
pacman --noconfirm -S base-devel mingw-w64-x86_64-toolchain mingw-w64-x86_64-meson mingw-w64-x86_64-gegl
```

Then build the same way you would on Linux:

```bash
meson setup --buildtype=release build
ninja -C build
```

### for technical Gimp users reading this.
 
PLEASE CONSIDER MAKING A GEGL FILTER AND KNOW THE META

I have been writing GEGL syntax in Gimp for almost two and a half years and making GEGL plugins for  Gimp for almost one and a half years. No one else on planet Earth is doing this stuff. As I lose interest in Libregraphics I'd appreciate if others made GEGL plugins via arranging GEGL nodes like I do. I am personally upset that some users on Gimp Chat are more interested in scripting GEGL with python then using GEGL directly (like I do). They won't be able to take advantage of GEGL composers, and that is a huge deal breaker - as that is what makes GEGL far more powerful then traditional alpha to logo and script fu stuff. There is also a current issue python to GEGL tech is having where python calling GEGL can only use (gegl:) name space operations and not (svg: gimp: or lb:) name space ones. lb: is my name space btw.  and without gimp: name spaces GEGL cannot use Gimp only blend modes. So please be informed about python to GEGL tech and consider making GEGL plugins my way until python gets better. My way of making GEGL plugins will be non-destructive in Gimp 3.2.

## More Previews of this based plugin

![image](https://github.com/LinuxBeaver/Background_Remover_By_Color_Gimp_Plugin/assets/78667207/a547300b-26a0-4c9e-8fda-b3283e4589a9)

![image](https://github.com/LinuxBeaver/Background_Remover_By_Color_Gimp_Plugin/assets/78667207/c580b5e3-f453-4970-9b1b-dc01ca24d62b)

![image](https://github.com/LinuxBeaver/Background_Remover_By_Color_Gimp_Plugin/assets/78667207/915bf568-f0b5-4632-8b0a-b828ad982d93)

