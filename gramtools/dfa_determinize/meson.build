libsent_proj = subproject('libsent')

dfa_determinize_sources = [
	'dfa_determinize.c'
]

libsent_dep = libsent_proj.get_variable('libsent_dep')

executable('dfa_determinize',
			dfa_determinize_sources,
			dependencies: [ readline_dep_lib, libsent_dep ])