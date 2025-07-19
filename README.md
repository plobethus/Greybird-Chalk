Copyright 2009–2019 Simon Steinbeiß, Satyajit Sahoo, Pasi Lallinaho, Carson Black, Maurizio Galli  
Copyright 2025 Henry Moran – Chalkboard-palette adaptation

# Greybird-Chalk

*A Chalkboard-coloured fork of the Greybird desktop-theme suite.*

It replaces the dark variant’s palette with five pastels  
`#1F2D2D` (bg) · `#BDEAFF` (blue) · `#FFFCA4` (yellow) · `#C8FF9B` (green) · `#FFB0B0` (pink)  
taken from **McKenzie Bottoms’ “Chalkboard” VS Code theme** 


### Included sub-themes

* Gtk 2 / Gtk 3 / Gtk 4  
* Xfwm4, Metacity, Mutter, GNOME-Shell, Openbox  
* Plank and Unity support

---

## Credits & Licence

Greybird-Chalk is a derivative of **Greybird**  
© 2009–2019 Simon Steinbeiß, Satyajit Sahoo, Pasi Lallinaho, Carson Black, Maurizio Galli  
released under **GNU GPL v2 or later** and **CC-BY-SA 3.0 or later**.  

Modifications © 2025 Henry Moran.  
Colour palette inspired by the *“Chalkboard”* VS Code theme © McKenzie Bottoms.

All modified files remain under the same dual licence (GPL v2+ / CC-BY-SA 3.0+).

---

## Building

```bash
meson setup builddir --prefix="$HOME/.local"
meson compile -C builddir
meson install -C builddir
```

### Terminal theme
Open Terminal, go to Edit- Preferences- Colors- Select Preset- Greybird Chalk

### Visual Studio Code Theme

https://marketplace.visualstudio.com/items?itemName=kenziebottoms.chalkboard

https://github.com/kenziebottoms/vscode-theme-chalkboard