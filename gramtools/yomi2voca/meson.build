yomi2voca_pl_data = configuration_data()
yomi2voca_pl_data.set('PERL', perlpath)
yomi2voca_pl_data.set('configure_input', 'yomi2voca/yomi2vocapl.  Generated from yomi2voca.pl.in by meson')

yomi2voca = configure_file(
	input: 'yomi2voca.pl.in',
	output: 'yomi2voca.pl',
	configuration: yomi2voca_pl_data)

install_data(
	yomi2voca,
	install_mode: 'r-xr-xr-x',
	install_dir: 'bin')
