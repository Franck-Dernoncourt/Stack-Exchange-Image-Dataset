# Stack Exchange Image Dataset

[![DOI](https://zenodo.org/badge/736462226.svg)](https://github.com/Franck-Dernoncourt/Stack-Exchange-Image-Dataset) [![License: CC BY-SA](https://img.shields.io/badge/License-CC_BY--SA-blue.svg)](https://stackoverflow.com/help/licensing)



The dataset can be downloaded at https://archive.org/download/stack-exchange-images (~799 GiB).

The dataset contains all the ~8.7 million images hosted on i.stack.imgur.com that are linked to in the posts, post histories and comments from the [Stack Exchange Data Dump dated 2023-12-08](https://archive.org/details/stack-exchange-data-dump-2023-12-08_20231222).

The dataset is licensed under [Creative Commons Attribution-ShareAlike](https://creativecommons.org/licenses/by-sa/4.0/), following the [license](https://stackoverflow.com/help/licensing) used for Stack Exchange user content.


# Dataset Structure

Each filename on i.stack.imgur.com has the following format: 5 chars followed by the file extension.

- Allowed chars: `0123456789abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ` (10 digits + 26 letters of the alphabet * 2 cases = 62 allowed chars)
- Allowed extension: `.gif`, `.jpg` and `.png`.

The i.stack.imgur.com filenames as well as the `Last-Modified` response HTTP header were kept. Note that the 5 chars are enough to identify an image, i.e. two images may [not](https://meta.stackexchange.com/q/395727/178179) share the same 5 chars (e.g., it's not possible to have both `hello.jpg` and `hello.png`).

The dataset comprises 62 zip files: the zip file where an image is stored corresponds to the first letter if the filename (`0.zip`, `1.zip`, ..., `9.zip`, `a.zip`, `b.zip`, ..., `.zip`, `A.zip`, `B.zip`, ..., `.Z.zip`). Within the zip files, the folder structure is as followed: the first letter of the filename is used for the level-1 folder, and the second letter of the filename is used for the level-2 folder. 

Example: 

```
.
├── A
│   ├── 0
│   │   ├── A0gpf.png
│   │   ├── A0mP1.jpg
│   │   ├── A0z99.png
│   ├── 1
│   │   ├── A1Aaq.gif
│   │   ├── A1pdf.png
│   │   ├── A1t51.png
├── M
│   ├── b
│   │   ├───Mb5AA.jpg
│   │   ├── Mbm0z.jpg
│   │   ├── Mbzas.gif
│   ├── Z
│   │   ├───MZ0zc.gif
│   │   ├── MZ546.gif
│   │   ├── MZa12.jpg
```

**Important**: one may run into issues using the dataset with Windows because the filenames in this dataset are case-sensitive (following i.stack.imgur.com naming convention), while Windows [is](https://superuser.com/q/165975/116475) mostly case-insensitive. E.g., if one uncompresses a zip file containing the files `hello.png` and `Hello.png`, only one file will remain once the extraction is completed. To use the dataset on Windows, one strategy would be to rename files (e.g., adding an underscore after any lowercase letter).

# Dataset Statistics

Total number of images: 8,737,759 images. Size: 857,964,647,071 bytes (~799 GiB, i.e. ~858 GB).

Image count by extension (using this [command](https://askubuntu.com/a/749005/44876)):

- `.gif`: `206,096` images
- `.jpg`: `1,675,282` images 
- `.png`: `6,856,303` images
- 78 files have some other extension (8,737,759 - (206,096 +1,675,282 + 6,856,303) = 78). I don't know where they came from, but it's rather negligible so let's just ignore them for now.

Over 99% of the files are below 2 MiB, since that's the upload [limit](https://meta.stackexchange.com/q/261925/178179) on SE, however a few files are [above](https://meta.stackexchange.com/q/395755/178179) 2 MiB. They can be found with this [command](https://stackoverflow.com/a/23925366/395857).


# Citation

If you use this dataset in your research, please cite:

```
@misc{StackExchangeImageDataset,
  author = {Dernoncourt, Franck},
  title = {Stack Exchange Image Dataset},
  year = {2023},
  publisher = {GitHub},
  journal = {GitHub repository},
  doi = {10.5281/zenodo.10465913},
  howpublished = {\url{https://github.com/Franck-Dernoncourt/Stack-Exchange-Image-Dataset}}
}
```
