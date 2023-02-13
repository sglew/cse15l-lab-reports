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
is contained within those files. This might be useful for gathering all instances of which a specific word 
appears. Using this option on directories however show a different result:

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
occurs it (which is line 95). It also prints out the entire line in which the word occurs in which is pretty long. This option might 
be useful if we're trying to learn about a concept and we want to read all about the word. Using this option on directories however 
show a different result: 

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

This option gives each instance of "skeleton" in text files. It also shows the relative path of the files containing "skeleton" but
shows a snippet of the word at the end. Here we can see "skeleton" appears 1 time in chA.txt, 3 times in chC.txt, 1 time in chM.txt,
and 1 time in chP.txt. This might be useful for researching as we can see all the chapters in which "skeletons" were talked about. Using 
this option on directories however show a different result:

```
steph@Stephanie_admin MINGW64 ~/OneDrive/Documents/GitHub/docsearch/written_2 (main)
$ grep -o "skeleton" */*/Castro/ > grep-results.txt 
grep: non-fiction/OUP/Castro/: Is a directory

steph@Stephanie_admin MINGW64 ~/OneDrive/Documents/GitHub/docsearch/written_2 (main)
$ cat grep-results.txt 
```

Again, because it is a directory, it seems unable to search for a particular pattern in the directory. It seems to only work if we're 
searching within a file. 

The fourth option I will be showing is `grep -w`. Using it on .txt files in the berlitz2 directory, I get this:

```
steph@Stephanie_admin MINGW64 ~/OneDrive/Documents/GitHub/docsearch/written_2 (main)
$ grep -w "computer" */berlitz2/*.txt > grep-results.txt 

steph@Stephanie_admin MINGW64 ~/OneDrive/Documents/GitHub/docsearch/written_2 (main)
$ cat grep-results.txt 
travel_guides/berlitz2/Amsterdam-WhereToGo.txt:Next to the museum, and unmistakable by its modern shape and huge green outer walls, 
is the newMetropolis science and technology center. Opened in 1997, the center was created to bring the latest science and technology 
literally into the hands of the lay person, whatever their age. Even the location of the building is a technological marvel. It sits 
high above the entrance to the IJ tunnel, which takes six lanes of traffic under the IJ waterway to Amsterdam’s northern suburbs and 
north Holland beyond. Inside the center you can try your hand at playing the stock exchange by computer, change the wheel on a car, or 
look at the cells of the body through a microscope. There are hands-on experiments for everyone from young children to adults, focusing 
on five linked themes — Energy, Humanity, Interactivity, Science, and Technology.
travel_guides/berlitz2/Bahamas-WhereToGo.txt:Not surprisingly for a duty-free island, shopping plays a large part in a trip to Grand Bahama. 
International Bazaar in Freeport takes you on a shopping trip around the world. Enter the bazaar through the red Japanese Torii or “welcome 
gate” and you can visit France, Africa, and India, all within a few minutes. Unusual offerings such as rare stamps can be found among the 
standard duty-free shops that carry the most exclusive names in watches, jewelry, and perfume. Behind the South American area you’ll find 
the Perfume Factory, where you can create your own personal fragrance. Mix essential oils to balance with your skin and give a name to your 
exclusive product. You can even record the recipages. Further north lie the wine-growing regions of the Napa and Sonoma valleys.
```

This option seems to operate the same as the `grep -n` command we did earlier except it does not show the line number in which it occurs. It also 
shows the whole snippet of the line in which the word "computer" occurs. This might be useful to search for definitions of a word. Using this option on directories however show a different result:

```
steph@Stephanie_admin MINGW64 ~/OneDrive/Documents/GitHub/docsearch/written_2 (main)$ grep -w "computer" */berlitz2 > grep-results.txt 
grep: travel_guides/berlitz2: Is a directory

steph@Stephanie_admin MINGW64 ~/OneDrive/Documents/GitHub/docsearch/written_2 (main)
$ cat grep-results.txt 
```

`grep` seems to not like directories at all as all the commands I've tested they always gave me the error that I am referencing a directory. This must 
not be useful for directories is what I have concluded. 

## References

All these command options were found on geeksforgeeks.org. They gave simple definitions of each command but for our text files, there was a lot more
text to analyze. Here is the link for the exact page I found that listed the commands:

[Link](https://www.geeksforgeeks.org/grep-command-in-unixlinux/)

Thanks for reading!
