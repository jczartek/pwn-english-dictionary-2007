
gnome = import('gnome')

resources = gnome.compile_resources(
  'pwn-english-dictionary-2007-resources',
  'pwn-english-dictionary-2007.gresource.xml',
  c_name: 'pwn',
)

pwn_english_dictionary_2007_sources = [
  'pwn-english-dictionary-2007.c',
  'pwn-english-dictionary-2007-plugin.c',
  'pwn-english-dictionary-2007-prefs.c',
  'pwn-english-dictionary-2007-window.c',
  resources[0],
  resources[1],
]

pwn_english_dictionary_2007_headers = [
]

cc = meson.get_compiler('c')

pwn_english_dictionary_2007_deps = [
  dependency('gio-2.0', version: '>= 2.50'),
  dependency('gtk+-3.0', version: '>= 3.24'),
  dependency('libgydict-1.0'),
  dependency('libpeas-1.0', version: '>= 1.22.0'),
  dependency('libdazzle-1.0', version: '>= 3.26.0'),
  cc.find_library('z', required: true),
]

pwn_english_dictionary_2007_lib = shared_library('pwn-english-dictionary-2007',
  pwn_english_dictionary_2007_sources,
  dependencies: pwn_english_dictionary_2007_deps,
  install: true,
  install_dir: get_option('prefix'),
)

install_data(
  'pwn-english-dictionary-2007.plugin',
  install_dir: get_option('prefix')
)


