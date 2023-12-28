# Stack Exchange Image Dataset

The dataset can be downloaded at https://archive.org/download/stack-exchange-images (~800 GB).

The dataset contains all the ~8.5 million images hosted on i.stack.imgur.com that are linked to in the post, post history and comments from the [Stack Exchange Data Dump dated 2023-12-08](https://archive.org/details/stack-exchange-data-dump-2023-12-08_20231222).

The dataset is licensed under [Creative Commons Attribution-ShareAlike](https://creativecommons.org/licenses/by-sa/4.0/), following the [license](https://stackoverflow.com/help/licensing) used for Stack Exchange user content.


# Dataset Structure

Each filename on i.stack.imgur.com has the following format: 5 chars followed by the file extension.

- Allowed chars: `0123456789abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ` (10 digits + 26 letters of the alphabet * 2 cases = 62 allowed chars)
- Allowed extension: `.gif`, `.jpg` and `.png`.

The i.stack.imgur.com filenames were kept: the first letter of the filename is used for the level-1 folder, and the second letter of the filename is used for the level-2 folder.

The dataset comprises 62 zip files: the zip file where an image is stored corresponds to the first letter if the filename (`0.zip`, `1.zip`, [...], `a.zip`, `b.zip`, [...], `A.zip`, `B.zip`, ...).

Example: TODO

**Important**: you'll run into issues using the dataset with Windows because of the filename in this dataset is case-sensitive (following i.stack.imgur.com naming convention), while [Windows mostly case-insensitive](https://superuser.com/q/165975/116475). To use Windows, one strategy would be to rename files (e.g., adding an underscore after any lowercase letter).

# Dataset Statistics

Total number of images: TODO.

Count by extension:

- `.gif`: TODO images
- `.jpg`: TODO images 
- `.png`: TODO images

Plot by creation date: TODO.


# Citation

If you use this dataset in your research, please cite:

```
@misc{StackExchangeImageDataset,
  author = {Dernoncourt, Franck},
  title = {Stack Exchange Image Dataset},
  year = {2023},
  publisher = {GitHub},
  journal = {GitHub repository},
  howpublished = {\url{https://github.com/Franck-Dernoncourt/Stack-Exchange-Image-Dataset}}
}
```
