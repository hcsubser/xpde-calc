project(
	'xpde-calc',
	'c',
	version: '0.1.0',
	license: 'GPL',
	meson_version: '>=0.47.0',
	default_options: [
		'c_std=c11',
		'warning_level=3',
		'werror=true',
	],
)

cc = meson.get_compiler('c')

uidir='"'+join_paths(get_option('prefix'),'share/xpde/xpde-calc')+'"'
localedir='"'+join_paths(get_option('prefix'),'share/locale')+'"'
add_project_arguments(cc.get_supported_arguments([
	'-Wno-pedantic',
	'-Wno-discarded-qualifiers',
	'-Wno-deprecated-declarations',
	'-Wno-unused-parameter',
	'-Wno-unused-function',

	'-DPACKAGE_UI_DIR='+uidir,
	'-DPACKAGE_LOCALE_DIR='+localedir,
	'-DPACKAGE="xpde-calc"',
	'-DVERSION="1.0.0"',
	'-rdynamic',
	'-export-dynamic',
	'-Wl',
	'-pthread',
]), language: 'c')

gtk3        	= dependency('gtk+-3.0')
m_dep 			= cc.find_library('m', required : true)
quadmath		= cc.find_library('quadmath', required : true)
gdkpixbuf		= dependency('gdk-pixbuf-2.0')
cairo			= dependency('cairo')
gmod			= dependency('gmodule-2.0')
pango			= dependency('pango')
pangocairo  	= dependency('pangocairo')
harfbuzz		= dependency('harfbuzz')
atk				= dependency('atk')
glib			= dependency('glib-2.0')
cairogobject	= dependency('cairo-gobject')
gio				= dependency('gio-2.0')
gdk				= dependency('gdk-3.0')

install_data('xpde-calc.desktop', install_dir: join_paths(get_option('prefix'),'share','applications'))
subdir('ui')
subdir('src')
