gram2sapixml_pl_data = configuration_data()
gram2sapixml_pl_data.set('PERL', perl.path())

gram2sapixml_pl = configure_file(
	input: 'gram2sapixml.pl.in',
	output: 'gram2sapixml.pl',
	configuration: gram2sapixml_pl_data)

install_data(
	gram2sapixml_pl,
	install_mode: 'r-xr-xr-x',
	install_dir: 'bin')
	