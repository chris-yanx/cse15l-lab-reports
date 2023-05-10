# Lab Report 3 - Researching Commands "find"

## Option 1: -type

```
$ find technical/ -type d
technical/
technical/911report
technical/biomed
technical/government
technical/government/About_LSC
technical/government/Alcohol_Problems
technical/government/Env_Prot_Agen
technical/government/Gen_Account_Office
technical/government/Media
technical/government/Post_Rate_Comm
technical/plos
```

`-type d` find all the directories from the given path.

```
$ find technical/911report/ -type f
technical/911report/chapter-1.txt
technical/911report/chapter-10.txt
technical/911report/chapter-11.txt
technical/911report/chapter-12.txt
technical/911report/chapter-13.1.txt
technical/911report/chapter-13.2.txt
technical/911report/chapter-13.3.txt
technical/911report/chapter-13.4.txt
technical/911report/chapter-13.5.txt
technical/911report/chapter-2.txt
technical/911report/chapter-3.txt
technical/911report/chapter-5.txt
technical/911report/chapter-6.txt
technical/911report/chapter-7.txt
technical/911report/chapter-8.txt
technical/911report/chapter-9.txt
technical/911report/preface.txt
```
`-type f` find all the files from the given path.

[Source](https://www.gnu.org/software/findutils/manual/html_mono/find.html#Type)

## Option 2: -not
```
$ find technical/ -not -name "*.txt"
technical/
technical/911report
technical/biomed
technical/government
technical/government/About_LSC
technical/government/Alcohol_Problems
technical/government/Env_Prot_Agen
technical/government/Gen_Account_Office
technical/government/Media
technical/government/Post_Rate_Comm
technical/plos
```

`-not -name "*.txt"` find all the paths with a pattern of not "*.txt".

```
$ find technical/911report/ -not -name "chapter*.txt" -type d
technical/911report/
```

``-not -name "chapter*.txt" -type d`` finds path that is not a directory or has a name pattern like "chapter*.txt"

[Soruce](https://math2001.github.io/article/bashs-find-command/)

## Option 3: find directory based on the depth

```
$ find technical/911report/ -mindepth 1
technical/911report/chapter-1.txt
technical/911report/chapter-10.txt
technical/911report/chapter-11.txt
technical/911report/chapter-12.txt
technical/911report/chapter-13.1.txt
technical/911report/chapter-13.2.txt
technical/911report/chapter-13.3.txt
technical/911report/chapter-13.4.txt
technical/911report/chapter-13.5.txt
technical/911report/chapter-2.txt
technical/911report/chapter-3.txt
technical/911report/chapter-5.txt
technical/911report/chapter-6.txt
technical/911report/chapter-7.txt
technical/911report/chapter-8.txt
technical/911report/chapter-9.txt
technical/911report/preface.txt
```

`-mindepth 1` finds paths at levels less than 1 starting from the "technical/911report/".

```
find technical/ -mindepth 1 -maxdepth 3 -type d
technical/911report
technical/biomed
technical/government
technical/government/About_LSC
technical/government/Alcohol_Problems
technical/government/Env_Prot_Agen
technical/government/Gen_Account_Office
technical/government/Media
technical/government/Post_Rate_Comm
technical/plos
```

`-mindepth 1 -maxdepth 3 -type d` finds all the directories from level 1 to level 3.

[Source](https://www.gnu.org/software/findutils/manual/html_mono/find.html#Directories)

## Option 4: -prune

```
$ find technical/ -prune
technical/
```

`-prune` prevents find from going into the technical directory.

```
$ find technical/government/ -name "Media" -prune
technical/government/Media
```

`-prune` prevents find from going into a directory called Media.

[Source](https://www.gnu.org/software/findutils/manual/html_mono/find.html#Directories)
