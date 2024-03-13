# Dimensions Activity Flatpak

Dimensions is a pattern-matching game by Sugar Labs.

To know more refer https://github.com/sugarlabs/dimensions

## How To Build

```
git clone https://github.com/flathub/org.sugarlabs.Dimensions.git
cd org.sugarlabs.Dimensions
flatpak --user remote-add --if-not-exists flathub-beta https://flathub.org/beta-repo/flathub-beta.flatpakrepo
flatpak -y --user install flathub-beta org.gnome.{Platform,Sdk}//46beta
flatpak -y --user install org.sugarlabs.BaseApp//24.04
flatpak-builder --user --force-clean --install build org.sugarlabs.Dimensions.json
```

## Check For Updates

Install the flatpak external data checker
```
flatpak --user install org.flathub.flatpak-external-data-checker
```

Now to update every single module to the latest stable version use
```
cd org.sugarlabs.Dimensions
flatpak run --filesystem=$PWD org.flathub.flatpak-external-data-checker org.sugarlabs.Dimensions.json
```