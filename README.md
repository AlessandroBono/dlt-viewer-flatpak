# DLT Viewer is on Flathub!
This repository is archived. You can find [DLT Viewer](https://flathub.org/apps/details/org.genivi.DLTViewer) and [its manifest](https://github.com/flathub/org.genivi.DLTViewer) on Flathub.

# dlt-viewer-flatpak
Flatpak manifest for building DLT-Viewer

[Setup Flatpak and Flathub](https://flatpak.org/setup/) first. These instructions assume that you already have `flatpak` and `flatpak-builder` installed and the `flathub` remote configured. In order to try the flatpaked DLT-Viewer, perform the following steps:

###### Install KDE platform and SDK
```
flatpak install flathub org.kde.Platform//5.15 org.kde.Sdk//5.15
```

###### Build DLT-Viewer
```
flatpak-builder --repo=genivi-repo --force-clean build-dir org.genivi.DLTViewer.yml
```

###### Create a Flatpak bundle
```
flatpak build-bundle genivi-repo org.genivi.DLTViewer.flatpak org.genivi.DLTViewer
```

###### Install the Flatpak bundle
Once you have the `org.genivi.DLTViewer.flatpak` file, you can install it on any GNU/Linux machine that has Flatpak installed and Flathub configured. [Here](https://flatpak.org/setup/) you can find a list of supported GNU/Linux distributions.
```
flatpak --user install org.genivi.DLTViewer.flatpak
```

###### Run the Flatpak bundle
```
flatpak run org.genivi.DLTViewer
```

The DLT-Viewer obtained by using Flatpak is sandboxed. For example, it doesn't have access to the host file system. The only way to access to a file is through the File Chooser [Portal](http://docs.flatpak.org/en/latest/desktop-integration.html#portals) which requires user interaction.

