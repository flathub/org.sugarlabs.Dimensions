# Dimensions Activity Flatpak

Dimensions is a pattern-matching game by Sugar Labs.

To know more refer https://github.com/sugarlabs/dimensions

## How To Build

```
git clone https://github.com/flathub/org.sugarlabs.Dimensions.git
cd org.sugarlabs.Dimensions
flatpak -y --user install org.gnome.{Platform,Sdk}//44
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