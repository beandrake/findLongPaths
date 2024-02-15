# findLongPaths
Given a filename/folder name and a directory to recursively search, outputs a text file with a list of all paths containing a file/folder with that name, ordered by path length.

## The tale behind this code:
I've somehow managed to never run into this before, but today while migrating some files I ran into an unexpected problem.
After an hour-long Windows copy operation, I got a pop-up that said the following:

	Destination Path Too Long
		The file name(s) would be too long for the destination folder.  You can
		shorten the file name and try again, or try a location that has a shorter path.
			example
			Type: File folder
										Skip		Cancel

I disliked this message, as it didn't help me solve or even identify the core problem.  What was the full path of
the folder that wasn't copied?  I had just copied tens of thousands of files and had no idea.

I did an Explorer file search for folders in my source that were named 'example', and it turned out there were 259 of them.
Additionally, the file paths for most of them were so long that Explorer was truncating the file paths, which made it
impossible to figure out which one was too long at a glance.

So I decided to code a solution, which allowed me to identify the example folder with the longest path so I could manually copy it.
Since this records all matching results and not just the longest, it can also help in the case where multiple paths are too long
