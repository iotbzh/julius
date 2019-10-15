libsent_proj = subproject('libsent')

nextword_sources = [
	'nextword.c',
	'get_next.c',
	'wtoken.c',
	'rdterm.c',
	'readline.c'
]

libsent_dep = libsent_proj.get_variable('libsent_dep')

executable('nextword',
			nextword_sources,
			dependencies: [ readline_dep_lib, libsent_dep ])