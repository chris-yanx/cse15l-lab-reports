# Lab Report 3 - Researching Commands for "find"

## Option 1: -type

The `-type` option is used to specify the type of files or directories to search for.

* `-type d`: the find command will only return directory entries as search results. This means that it will list all directories that match the specified criteria.

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

* `-type f`: used with the find command to search for regular files within a given directory hierarchy.It will exclude directories, symbolic links, device files, named pipes, sockets, and other special file types.

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

[Source](https://www.gnu.org/software/findutils/manual/html_mono/find.html#Type)

## Option 2: -not

The -not option is a logical operator that negates the expression that follows it. It is used to exclude files or directories that match a specific condition.

* `-not -name "*.txt"`: In this command, `-name "*.txt"` specifies the condition to match files with the .txt extension. The `-not` option negates this condition, so the find command will return all files that do not have the .txt extension.

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

``-not -name "chapter*.txt" -type d``:  It will search within the specified path and return a list of directories that do not have names starting with "chapter" and ending with ".txt".

```
$ find technical/911report/ -not -name "chapter*.txt" -type d
technical/911report/
```

[Soruce](https://math2001.github.io/article/bashs-find-command/)

## Option 3: find directory based on the depth

`-mindepth` and `-maxdepth` options to control the depth of directory traversal during the search. These options allow people to specify the minimum and maximum depth of directories to search within a directory hierarchy.

* `-mindepth 1` finds paths at levels less than 1 starting from the "technical/911report/". The search will start from the first level of subdirectories within the specified path, excluding the top-level directory itself. This is useful when you want to exclude the starting directory from the search results.

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

* `-mindepth 1 -maxdepth 3 -type d`: It is used to search for directories within a given directory hierarchy, starting from the first level of subdirectories up to the third level.

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

[Source](https://www.gnu.org/software/findutils/manual/html_mono/find.html#Directories)

## Option 4: -prune

The `find -prune` option is used to exclude certain directories from the search process. It prevents `find` from descending into specified directories, effectively pruning them from the search tree.

* `-prune`: It is used to search for files and directories within the technical/ directory while excluding the technical/ directory itself from the search results. It effectively prunes the specified directory from the search process.

```
$ find technical/ -prune
technical/
```

* Used to search for directories named "Media" within the `technical/government/ directory` while excluding those directories from the search results. It prunes the directories named "Media" from further descent during the search.

```
$ find technical/government/ -name "Media" -prune
technical/government/Media
```

[Source](https://www.gnu.org/software/findutils/manual/html_mono/find.html#Directories)
