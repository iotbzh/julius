subdir('mkfa-1.44-flex')

mkdfa_pl_data = configuration_data()
mkdfa_pl_data.set('PERL', perlpath)
mkdfa_pl_data.set('configure_input', 'mkdfa/mkdfa.pl.  Generated from mkdfa.pl.in by meson')

mkdfa_pl = configure_file(
	input: 'mkdfa.pl.in',
	output: 'mkdfa.pl',
	configuration: mkdfa_pl_data)

install_data(
	mkdfa_pl,
	install_mode: 'r-xr-xr-x',
	install_dir: 'bin')

install_data(
	'mkdfa.py',
	install_mode: 'r-xr-xr-x',
	install_dir: 'bin')
