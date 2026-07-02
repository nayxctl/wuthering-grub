# Wuthering Grub

A GRUB2 theme inspired by Wuthering Waves, based on [grubshin-bootpact](https://github.com/max-ishere/grubshin-bootpact) by max-ishere.

Customizations include:
- Teleport Abyss color scheme (black & white)
- Custom `elements.png` with Wuthering Waves resonance icons
- Font changed to **Lagu Sans Regular**

---

## Preview

> *(Screenshot will be uploaded soon)*

---

## Installation

### 1. Download the theme

```bash
git clone https://github.com/nayx/wuthering-grub.git
cd wuthering-grub
```

### 2. Copy to GRUB themes directory

```bash
sudo mkdir -p /boot/grub/themes
sudo cp -r teleport-abyss-1920x1080 /boot/grub/themes/wuthering-grub
```

> **Note:** If your GRUB is at `/boot/grub2` instead of `/boot/grub`, adjust the path accordingly.

### 3. Enable the theme in GRUB config

Open `/etc/default/grub`:

```bash
sudo nano /etc/default/grub
```

Add or update these lines at the end:

```
GRUB_TIMEOUT=5
GRUB_TIMEOUT_STYLE=menu
GRUB_TERMINAL_OUTPUT=gfxterm
GRUB_GFXMODE="1920x1080,auto"
GRUB_GFXPAYLOAD_LINUX=keep
GRUB_THEME="/boot/grub/themes/wuthering-grub/theme.txt"
```

> **Tip:** Press `c` in GRUB and type `videoinfo` to check your firmware's native resolution if you're unsure.

### 4. Regenerate GRUB config

```bash
sudo grub-mkconfig -o /boot/grub/grub.cfg
```

You should see:
```
Found theme: /boot/grub/themes/wuthering-grub/theme.txt
```

Reboot and enjoy!

---

## Customization

### Changing the elements image

The `elements.png` is the icon strip shown at the bottom of the screen. Replace it with your own:

```bash
sudo cp /path/to/your/elements.png /boot/grub/themes/wuthering-grub/elements.png
```

No need to regenerate GRUB config for image changes — just reboot.


## Uninstalling

1. Remove or comment out `GRUB_THEME` in `/etc/default/grub`
2. Delete the theme folder:

```bash
sudo rm -rf /boot/grub/themes/wuthering-grub
```

3. Regenerate GRUB config:

```bash
sudo grub-mkconfig -o /boot/grub/grub.cfg
```

---

## Credits

- Original theme: [grubshin-bootpact](https://github.com/max-ishere/grubshin-bootpact) by [max-ishere](https://github.com/max-ishere) — licensed under GPL-3.0
- Wuthering Waves is developed by Kuro Games
- Font: [Lagu Sans](https://fonts.google.com/specimen/Lagu+Sans) by Google Fonts
