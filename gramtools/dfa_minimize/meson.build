libsent_proj = subproject('libsent')

dfa_minimize_sources = [
	'dfa_minimize.c'
]

libsent_dep = libsent_proj.get_variable('libsent_dep')

executable('dfa_minimize', 
			dfa_minimize_sources,
			dependencies: [ readline_dep_lib, libsent_dep ])