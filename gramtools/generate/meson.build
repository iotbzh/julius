libsent_proj = subproject('libsent')

generate_sources = [
	'generate.c',
	'gen_next.c',
	'rdterm.c'
]

libsent_dep = libsent_proj.get_variable('libsent_dep')

executable('generate', 
			generate_sources,
			dependencies: [ readline_dep_lib, libsent_dep ])