---
layout:     post
title:      Linux MS-DOS Command CheatSheet 
date:       2015-08-03 12:00:00
summary:    Compare Linux commands with MS-DOS
categories: MS-DOS 
---

	Purpose		    	MS-DOS		Linux	Basic Linux Example

	Copies files		copy		cp		cp thisfile.txt /home/thisdirectory
	Moves files			move		mv		mv thisfile.txt /home/thisdirectory
	Lists files			dir			ls		ls thisfile.txt /home/thisdirectory
	Clears screen		cls			clear   clear
	Closes shell   		exit		exit	exit
	Displays/set date  	date		date	date
	Deletes files		del			rm		rm thisfile.txt
	"Echo"				echo		echo	echo this message
	Edits text files	edit		vim		vim thisfile.txt
	Compare content		fc			diff	diff file1 file2
	Find string of text find		grep	grep word or phrase thisfile.txt
	Displays  help		command /?	man		man command
	Creates a directory	mkdir		mkdir	mkdir directory
	Views file contents	more		less([b])	less thisfile.txt
	Renames a file		ren		mv([c])		mv thisfile.txt thatfile.txt
	Display fs location	chdir		pwd		pwd
	Change dir abs path	cd pathname	cd pathname	cd /directory/directory
	Change dir relative	cd..		cd ..	cd ..
	Displays the time	time		date	date
	Amount RAM in use	mem		    free	free


Notes:
* The more pager can also be used to page through a file one screen at a time. 

* The mv command can both move a file and, if you want to rename a file in the same directory, "move" that file to the same directory with a new name.


[Source](https://access.redhat.com/documentation/en-US/Red_Hat_Enterprise_Linux/4/html/Step_by_Step_Guide/ap-doslinux.html)
