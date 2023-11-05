+++
title = 'Package Conflict'
date = 2023-11-04T19:34:59-04:00
draft = false
+++

![](/images/vampt_packageconflict.png)

# Resolving Package Conflict on Arch Linux
This will happen every once in while. I go to update my computer and I encounter a package conflict. This time for me it was a conflict between `jdk-openjdk` and `jre-openjdk`. I had find out what they're for and get rid of one:
## Check Dependencies:
Run the following commands to check which packages depend on `jdk-openjdk` and `jre-openjdk`:

```pacman -Qi jdk-openjdk``` and ```pacman -Qi jre-openjdk```   

This will provide information about the packages and their dependencies.

When I ran these commands i learned that `jre-openjdk` has dependencies that I have installed; GTK2, GTK3, and alsa-lib (for audio).
## Decide Which Package to Keep:
I chose the package that was essential for my system. Since I'm not using this machine for Java development, I'm removing `jdk-openjdk`. 

Typically, `jdk-openjdk` is used for development, while `jre-openjdk` is for running Java applications.
## Remove or Replace the Conflicting Package:
To remove a package, use `pacman -R package`:

```sudo pacman -R jdk-openjdk  # or jre-openjdk, depending on your choice```

To replace it, install the other package: Don't skip this part, it will update and fix the package you want to keep, so that its prepared for the system update. Depending on your system

```sudo pacman -S jre-openjdk  # if keeping jre-openjdk```
## Update Your System:
After resolving the conflict, update your system without issues:
```sudo pacman -Syu```
### Check AUR Packages (if using yay):
```yay -Syu```

If you use yay to manage AUR packages, also check for any AUR packages that depend on `jdk-openjdk` or `jre-openjdk`. You might need to update or rebuild them as well.