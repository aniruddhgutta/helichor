# helichor

**helium** [theme](./theme) _inspired_ by brave's ultra-dark colorscheme with
slight tweaks, along with a custom [new-tab-page](./newtab).

## Preview
![helichor](https://codeberg.org/oceanicc/helichor/media/branch/demo/preview.webp)

---

## Info
 
this repo contains two seperate extensions, since helium ignores
`chrome_url_overrides` when themeing attributes exist in a `manifest`:
 
- `newtab/`: the new tab page
- `theme/`: the colors, applies as a theme so it won't show up in
            the extensions list

---

## Installation

### Packed

1. Download both zips from the latest [release](../../releases)
2. Open `helium://extensions` and enable **Developer mode** (top-right toggle)
3. Drag each zip onto the page
4. Done

helium unpacks them into your profile, so the zips are safe to delete
afterwards.

### Unpacked

if you want to edit/manage the colors yourself (eg: using `reclr`):

1. Clone this repo, or unzip a release
2. Open `helium://extensions` and enable **Developer mode** (top-right toggle)
3. Click **Load unpacked** and select `theme/`, then repeat for `newtab/`
4. To refresh colors, copy/symlink them in and reload, eg:

```sh
ln -sf ~/.cache/reclr/colors.css \
  ~/.config/net.imput.helium/helichor/newtab/colors.css
```

> [!IMPORTANT]
> - Unlike the packed route, helium reads from this folder every launch. Hence
> store it in a permanent location.
> - Ensure both the `reclr` file and `helichor` folders are readable by helium.
> - Incognito windows aren't affected, this is a helium limitation
> - The theme doesn't cleanly apply either, this is a helium limitation

