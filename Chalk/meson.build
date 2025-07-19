# Chalk/meson.build  ──────────────────────────────────────────────
#
# Installs the Chalkboard-coloured dark variant of Greybird.
#  ─ theme_dir                  → Greybird-Chalk
#  ─ accessibility sub-variant  → Greybird-Chalk-accessibility
#  ─ compact    »               → Greybird-Chalk-compact
#

# ----------  paths ----------------------------------------------
theme_name          = 'Greybird-Chalk'
theme_path          = join_paths(get_option('datadir'), 'themes', theme_name)
a11y_theme_path     = join_paths(get_option('datadir'), 'themes', theme_name + '-accessibility')
compact_theme_path  = join_paths(get_option('datadir'), 'themes', theme_name + '-compact')

# ----------  source lists ---------------------------------------
scss_files = files([
  'gtk-3.0/_colors-public.scss',
  'gtk-3.0/_colors.scss',
  'gtk-3.0/_common.scss',
  'gtk-3.0/_drawing.scss',
  'gtk-3.0/_gnome-apps.scss',
  'gtk-3.0/_lightdm-gtk-greeter.scss',
  'gtk-3.0/_others.scss',
  'gtk-3.0/_unity.scss',
  'gtk-3.0/_xfce.scss'
])

# ----------  install --------------------------------------------
# index.theme  (required by GTK)
install_data('index.theme', install_dir : theme_path)

# Gtk-3 assets + app-specific css
install_subdir('gtk-3.0/assets', install_dir : theme_path / 'gtk-3.0')
install_subdir('gtk-3.0/apps',   install_dir : theme_path / 'gtk-3.0')
install_data('gtk-3.0/settings.ini', install_dir : theme_path / 'gtk-3.0')

# Gtk-3 compiled css (light + dark contained in separate files)
theme_deps = []

theme_deps += custom_target(
  'chalk-gtk3',
  input  : 'gtk-3.0/gtk-contained.scss',
  output : 'gtk.css',
  command: [ sassc, sassc_opts, '@INPUT@', '@OUTPUT@' ],
  depend_files   : scss_files,
  build_by_default: true,
  install: true,
  install_dir: theme_path / 'gtk-3.0'
)

theme_deps += custom_target(
  'chalk-gtk3-dark',
  input  : 'gtk-3.0/gtk-contained-dark.scss',
  output : 'gtk-dark.css',
  command: [ sassc, sassc_opts, '@INPUT@', '@OUTPUT@' ],
  depend_files   : scss_files,
  build_by_default: true,
  install: true,
  install_dir: theme_path / 'gtk-3.0'
)

# Gtk-3 gresource bundle (work-around for old Meson bug)
gtk_gresources = custom_target(
  'chalk-gtk-gresource',
  input  : 'gtk-3.0/gtk.gresource.xml',
  output : 'gtk.gresource',
  command: [
    glib_compile_resources, '@INPUT@',
    '--target', '@OUTPUT@',
    '--sourcedir', meson.current_source_dir() / 'gtk-3.0'
  ],
  build_by_default: true,
  install: true,
  install_dir: theme_path / 'gtk-3.0'
)
