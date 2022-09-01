# Down and Across: Introducing Crossword-Solving as a New NLP Benchmark

This repository will soon be updated to include code and instructions to get and assemble the NYT Crosswords dataset reported in our work: "Down and Across: Introducing Crossword-Solving as a New NLP Benchmark" to be presented at ACL 2022.

Crossword puzzles are © 1942-2022 by The New York Times.

## Crossword Puzzles Corpus
We only release dates of the daily NYT crossword puzzles which make up our test, validation and training sets of the crossword corpus, since New York Times daily crossword puzzles are a copyright of The New York Times. Interested researchers should contact New York Times for the permission to use this data for academic research purposes.

There are many 3rd party tools to collect the puzzles data directly from New York Times website. One such example is [nytxw_puz](https://github.com/Q726kbXuN/nytxw_puz) which allows the user to download NYT daily puzzles in the AcrossLite format (.puz). These .puz files can then be converted to the .json format files which are acceptable to our crossword puzzle solver system directly with the convert.py script that we provide in this repo.

## Clue Answer Dataset
We release the clue and answer dataset, since individual clues and answers for daily crosswords from many newspapers and periodicals across all time spans remain widely available on websites like http://crosswordtracker.com/, https://crossword-solver.io/ and https://www.xwordinfo.com/ among many others.

Train, validation and test set of clue answer dataset can be downloaded from any of these links: [Dropbox](https://www.dropbox.com/sh/pzpaus6wxg1cozo/AAAmiB0vorOICExJQIoqG-sKa?dl=0), [Google Drive](https://drive.google.com/drive/folders/1rPrgx8QAgL-f884y1FuFDu9e8m0VYWz-?usp=sharing), or [Mediafire](https://www.mediafire.com/folder/thzqcfeirl79d/dataset)!

The 6 files downloaded have the following significance:
- train.source: clues, training set
- train.target: answers, training set
- val.source: clues, validation set
- val.target: answers, validation set
- test.source: clues, test set
- test.target: answers, test set

Each line corresponds to single clue or answer. A certain line number from both train/val/test.source and train/val/test.target correponds to the clue and it's corresponding answer.

Certain answers consist of phrases and multiple words that are merged into a single string (such as "VERYFAST"), we postprocess answers in the *.target files by splitting the longer answer strings into individual words with the help of a dictionary. Out of all the possible word splits of a given string we pick the one that has the smallest number of words. If there are multiple solutions, we select the split with the highest average word frequency. To achieve better entire crossword puzzle solving accuracy with an end-to-end solving system a different variation of the delimiting post-process could be employed.
