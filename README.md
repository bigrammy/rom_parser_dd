## ROM Parser by Decker

Небольшой скрипт на Python, базирующийся на исходниках [gpt_parser.py](https://github.com/n0fate/raw/blob/master/gpt_parser.py) от [n0fate](https://github.com/n0fate) для парсинга ROM_0 (backup'а прошивки устройств на базе чипсетов от Mediatek, сделанного с помощью SP Flash Tool) и разбиения backup'а на разделы. На данный момент только Linux версия (впрочем переделать ее под Windows с использованием виндового порта dd не представляет сложностей). Использовать следующим образом:

	python rom_parser_dd.sh ROM_0 > split.sh
	. split.sh

Первой строкой мы генерируем скрипт split.sh, который использует dd для разбиения образа ROM_0 на разделы и make_ext4fs из пакета android-tools-fsutils для создания пустых sparsed образов разделов cache и userdata. Второй строкой мы запускаем непосредственно разбиение. В результате работы split.sh в папке split будут созданы файлы разделов, подлежащих прошивке, а в папке split/other - остальных разделов. При этом образы разделов cache и userdata создаются пустыми.