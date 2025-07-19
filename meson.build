#  © 2009–2019 Simon Steinbeiß, Satyajit Sahoo, Pasi Lallinaho, Carson Black, Maurizio Galli  
#  © 2025 Henry Moran – Chalkboard palette adaptation
#  This file is licensed under the GNU GPL v2 or later.
#




project('greybird-chalk', version : '0.1')

# ---------- helper programs ----------
sassc                 = find_program('sassc', required : true)
glib_compile_resources = find_program('glib-compile-resources', required : true)
gnome                 = import('gnome')

# ---------- global Sass flags ----------
sassc_opts = [ '-a', '-M', '-t', 'compact' ]   # add -m inline here if you re-enable sourcemaps

# ---------- build the theme itself ----------
subdir('Chalk')       # (folder formerly called “dark”)

# ---------- install the Xfce-Terminal preset ----------
install_data(
  'terminal-theme/Chalkboard.theme',
  install_dir : join_paths(get_option('datadir'),
                           'xfce4', 'terminal', 'colorschemes')
)
