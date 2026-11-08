# helichor

Helium browser [theme](./theme) _inspired_ by brave's ultra-dark colorscheme
with slight tweaks, along with a custom [new-tab-page](./newtab).

## preview

![Helichor](https://codeberg.org/oceanicc/helichor/media/branch/demo/preview.webp)

## info

this repo contains two seperate extensions, since helium ignores
`chrome_url_overrides` when themeing attributes exist in a `manifest`:

- `newtab/`: the new tab page
- `theme/`: the colors, applies as a theme so it won't show up in the extensions
  list

## install

### packed

1. Download both `.crx` files:

- From the terminal:

  ```bash
  VER="v1.0"  # check what the latest version is
  for i in theme newtab; do
    curl -LO https://codeberg.org/oceanicc/helichor/releases/download/$VER/helichor-$i-$VER.crx
  done
  ```

- From the browser:

  Open the latest [release](https://codeberg.org/oceanicc/helichor/releases) and
  right-click each `.crx` → **Save link as…**. Don't click it directly, since
  helium tries to install it on download and fails with
  `CRX_REQUIRED_PROOF_MISSING`.

2. Open `helium://extensions` and enable **Developer mode** (top-right toggle).
3. Drag each `.crx` onto the page.

Helium installs them into your profile, so the files are safe to delete
afterwards.

### unpacked

if you want to edit/manage the colors yourself (eg: using `reclr`):

1. Clone this repo.
2. Open `helium://extensions` and enable **Developer mode** (top-right toggle).
3. Click **Load unpacked** and select `theme/`, then repeat for `newtab/`.
4. To refresh colors, copy/symlink them in and reload, eg:

```bash
ln -sf "$HOME/.cache/reclr/colors.css" "$HOME/.config/net.imput.helium/helichor/newtab/colors.css"
```

> [!IMPORTANT]
>
> - Unlike the packed route, helium reads from this folder every launch. Hence
>   store it in a permanent location.
> - Ensure both the `reclr` file and `helichor` folders are readable by Helium.
> - Incognito windows aren't affected, this is a helium limitation.
> - The theme doesn't cleanly apply either, this is a Helium limitation.

## tips

Here are some nice qol flags (`helium://flags`) you can enable for an even
cleaner experience:

- `#enable-incognito-themes`: retain themeing in incognito aswell.
- `#overlay-scrollbars`: enable sleeker scrollbars that fade out when unused.
- `#hide-fullscreen-exit-ui`: hide the 'X' that appears when you hover over the
  top of the window.
