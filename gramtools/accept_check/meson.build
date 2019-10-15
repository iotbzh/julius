libsent_proj = subproject('libsent')

accept_check_sources = [
	'accept_check.c',
	'rdterm.c'
]

libsent_dep = libsent_proj.get_variable('libsent_dep')

executable('accept_check',
			accept_check_sources,
			dependencies: [ readline_dep_lib, libsent_dep ])