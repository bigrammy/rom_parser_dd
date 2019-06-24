## ROM Parser by Decker

A small Python script based on source code. [gpt_parser.py](https://github.com/n0fate/raw/blob/master/gpt_parser.py) from [n0fate](https://github.com/n0fate) for parsing ROM_0 (The backup of device firmware based on Mediatek's chipset's, made using  SP Flash Tool) it splits the backup into the verious sections based on the gpt. At the moment it's only for Linux systems. (however, it is not difficult to remake it under Windows using the dd port). Useage as follows:

	python rom_parser_dd.sh ROM_0 > split.sh
	. split.sh

In the first line we generate is the split.sh script, which uses dd to split the ROM_0 image into sections and make_ext4fs from the android-tools-fsutils package to create empty sparsed images of the cache and userdata sections. 
In the second line we start the split. As a result of the split.sh the split files will be created in the split folder to be re-flashed, and in the split / other folder the other partitions will be created. In this case, the images of the cache and userdata sections are created empty so effectivley format the data and cache.

(This Readme.md was translated from the original Russian to English using google translate)
