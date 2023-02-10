# Researching Commands

## Grep command

I am choosing to research about the `grep` command which searches a pattern of characters in files. 
The syntax for grep is this: `grep [options] pattern [files]` where `pattern` can be something like
the word "Hawaii" or "banana". 

The first option I will use is `grep -l`. Using it on .txt files in the berlitz1 directory, I get this:

```
steph@Stephanie_admin MINGW64 ~/OneDrive/Documents/GitHub/docsearch/written_2 (main)
$ grep -1 "Honolulu" */berlitz1/*.txt > grep-results.txt 

steph@Stephanie_admin MINGW64 ~/OneDrive/Documents/GitHub/docsearch/written_2 (main)
$ cat grep-results.txt 
travel_guides/berlitz1/HandRHawaii.txt-      
travel_guides/berlitz1/HandRHawaii.txt:        Oahu (Including Honolulu)
travel_guides/berlitz1/HandRHawaii.txt:        Aston Waikiki Sunset $$$ 229 Paoakalani Avenue, Honolulu, HI
travel_guides/berlitz1/HandRHawaii.txt-        96815; Tel. (808) 922-2700 or (800) 336-5599; fax (808) 922-8785;
--
```

Here, it is showing all the file names that contain the word "Honolulu" and also including a snippet of what
is contained within those files. Using this option on directories however show a different result:

```
steph@Stephanie_admin MINGW64 ~/OneDrive/Documents/GitHub/docsearch/written_2 (main)$ grep -1 "Honolulu" */berlitz1 > grep-results.txt 
grep: travel_guides/berlitz1: Is a directory

steph@Stephanie_admin MINGW64 ~/OneDrive/Documents/GitHub/docsearch/written_2 (main)
$ cat grep-results.txt 
```

Here, it shows me an error saying that travel_guides/berlitz1 is a directory. I believe the result is this because
-l can only be used on files. 

Another option I tried is `grep -n`. Using it on .txt files in the non-fiction/OUP/Castro directory, I get this:

```
steph@Stephanie_admin MINGW64 ~/OneDrive/Documents/GitHub/docsearch/written_2 (main)
$ grep -n "skeleton" */*/Castro/*.txt > grep-results.txt 

steph@Stephanie_admin MINGW64 ~/OneDrive/Documents/GitHub/docsearch/written_2 (main)
$ cat grep-results.txt 
non-fiction/OUP/Castro/chA.txt:95:The religious observation of All Souls’ Day, or Día de los Muertos, on November 2,
is an occasion for many families to erect altars specifically for a parent or other family member who has recently died. 
These altars will traditionally have a picture or pictures of the departed with offerings and gifts. Family and friends 
are invited to visit and add items to the altar, which becomes almost a shrine, and is called an ofrenda. In many U.S. 
cities Día de los Muertos ritual celebrations have become community affairs that include more than the Chicano community 
and may entail a procession through the streets ending at a local school or community center. In the last thirty or so years, 
the creation and construction of altars have become major art programs for museums, schools, and community centers in the United 
States. The altars are wonderful artistic creations, a form of folk art, with local artists participating and involving children 
in the making of calaveras (skeletons), papel picado (cut tissue paper), paper flowers, and other decorations.
```

This also shows the relative path of the file but in addition to that, it shows the line number in which the word "skeleton"
occurs it (which is line 95). It also prints out the entire line in which the word occurs in which is pretty long. Using this option 
on directories however show a different result: 

```
steph@Stephanie_admin MINGW64 ~/OneDrive/Documents/GitHub/docsearch/written_2 (main)$ grep -n "skeleton" */*/Castro/ > grep-results.txt 
grep: non-fiction/OUP/Castro/: Is a directory

steph@Stephanie_admin MINGW64 ~/OneDrive/Documents/GitHub/docsearch/written_2 (main)
$ cat grep-results.txt
```

As you can see, because it is a directory, it again does not input anything in the grep-results.txt file. This might be because
the option does not work on directories and can only search contents of files. 

The third option I will be showing will be `grep -o`. Using it on .txt files in the non-fiction/OUP/Castro directory, I get this:

```
steph@Stephanie_admin MINGW64 ~/OneDrive/Documents/GitHub/docsearch/written_2 (main)
$ grep -o "skeleton" */*/Castro/*.txt > grep-results.txt

steph@Stephanie_admin MINGW64 ~/OneDrive/Documents/GitHub/docsearch/written_2 (main)
$ cat grep-results.txt 
non-fiction/OUP/Castro/chA.txt:skeleton
non-fiction/OUP/Castro/chC.txt:skeleton
non-fiction/OUP/Castro/chC.txt:skeleton
non-fiction/OUP/Castro/chC.txt:skeleton
non-fiction/OUP/Castro/chM.txt:skeleton
non-fiction/OUP/Castro/chP.txt:skeleton
```

