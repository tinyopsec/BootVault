# BootVault

> A growing collection of custom Android boot animations, organized by screen resolution. Ready to flash — no editing needed.

[![Contributions Welcome](https://img.shields.io/badge/contributions-welcome-brightgreen)](#contributing)
[![License](https://img.shields.io/badge/license-MIT-blue)](#license)

---

## 📂 Structure

```
BootVault/
├── 1080x2280/
│   ├── tux/
│   │   ├── bootanimation.zip
│   │   └── preview.gif
│   └── .../
├── 1080x2400/
│   └── .../
├── 1440x3200/
│   └── .../
└── universal/          ← resolution-independent animations
    └── .../
```

Each animation lives in its own named folder and contains:
- `bootanimation.zip` — ready to install
- `preview.gif` — preview of the animation

---

## 📱 Find your resolution

**Android:** Settings → About Phone → Display / Resolution  
**ADB:** `adb shell wm size`

Then pick the matching folder. If your resolution isn't listed, try `universal/`.

---

## ⚡ Quick Install

### Recovery (TWRP / OrangeFox) — recommended

```bash
adb push bootanimation.zip /system/media/bootanimation.zip
adb shell chmod 644 /system/media/bootanimation.zip
adb shell chown root:root /system/media/bootanimation.zip
```

### ADB + Root (from booted system)

```bash
adb push bootanimation.zip /sdcard/
adb shell su -c "cp /sdcard/bootanimation.zip /system/media/bootanimation.zip && chmod 644 /system/media/bootanimation.zip"
adb reboot
```

> Full installation guide → [INSTALL.md](INSTALL.md)

---

## 🗂️ Supported Resolutions

| Folder | Common devices |
|--------|---------------|
| `1080x2280` | Xiaomi Mi 9, Samsung A50, OnePlus 6T |
| `1080x2400` | Xiaomi Redmi Note 10, Realme, Samsung A52 |
| `1440x3200` | Samsung S21+, S22 Ultra |
| `1080x1920` | Older flagships, budget devices |
| `universal` | Scales to any resolution |

---

## 🤝 Contributing

Want to add your animation?

1. Fork the repo
2. Place your files under the correct resolution folder: `<width>x<height>/<animation-name>/`
3. Include `bootanimation.zip` and `preview.gif`
4. Open a Pull Request

Structure requirements → [CONTRIBUTING.md](CONTRIBUTING.md)

---

## License

MIT — free to use, modify, and redistribute. Credit appreciated.
