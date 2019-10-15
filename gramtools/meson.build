project('gramtools', 'c')

compiler = meson.get_compiler('c')

# find_program does not work when cross building, there
# is not way to prevent it to fallback to host binaries
# when the program is not in the cross environment

perlpath='/usr/bin/perl'
if not meson.is_cross_build()
	perl = find_program('perl', required:false)
	if perl.found()
		perlpath=perl.path()
	endif

	if not find_program('iconv', required:false, native:false).found()
		warning('no iconv, gram2sapixml.pl will not work')
	endif
endif


readline_dep_lib = []

readline=dependency('libreadline', required:false)
editline=dependency('libeditline', required:false)
edit=dependency('libedit', required:false)

if not readline.found() and not editline.found() and not edit.found()
	message('Need either readline or editline')
else
    add_project_arguments('-DHAVE_LIBREADLINE', language: 'c')
endif

# prefer 'edit' when available

if edit.found()
	readline_dep_lib = edit
	if compiler.has_header('editline/readline.h')
		add_project_arguments('-DHAVE_READLINE_H', language: 'c')
	endif
elif editline.found()
	readline_dep_lib = editline
elif readline.found()
	readline_dep_lib = readline
	if compiler.has_header('readline/readline.h')
		add_project_arguments('-DHAVE_READLINE_READLINE_H', language: 'c')
	endif
	if compiler.has_header_symbol('rl_compentry_func_t', 'readline/readline.h')
		add_project_arguments('-DHAVE_LIBREADLINE_4_1_OLDER', language: 'c')
	endif
	
endif

if compiler.has_function('add_history', dependencies: readline_dep_lib)
	add_project_arguments('-DHAVE_LIBREADLINE_HISTORY', language: 'c')
	if compiler.has_header('editline/history.h')
		add_project_arguments('-DHAVE_EDITLINE_HISTORY_H', language: 'c')
	elif compiler.has_header('readline/history.h')
		add_project_arguments('-HAVE_READLINE_HISTORY_H', language: 'c')
	elif compiler.has_header('history.h')
		add_project_arguments('-DHAVE_HISTORY_H', language: 'c')
	endif
endif

if compiler.has_header('malloc.h')
	add_project_arguments('-DHAVE_MALLOC', language: 'c')
endif

subdir('mkdfa')
subdir('dfa_minimize')
subdir('generate')
subdir('accept_check')
subdir('nextword')
subdir('yomi2voca')

# gram2sapixml uses iconv that seems to be deprecated in poky
if not meson.is_cross_build()
	subdir('gram2sapixml')
endif
subdir('dfa_determinize')
