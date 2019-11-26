This is an example of a step by step process going from not having any folders or files to connecting a created directory and the files it contains to GitHub in such a way that there is the option to version control Docx feedback in both binary and text formats. This is how I did it on a test run. The files created for this run can be found [here](https://github.com/MQ-FOAR705/Version-Control-Supervisor-Feedback-PoC/tree/master/PoC-final):

## 1. Making a directory and docx file.

In terminal, make a directory (folder):

	mkdir PoC-final

Go into that directory in terminal:

	cd PoC-final/

Create a docx file in terminal:

	touch T-final.docx

Then in GUI double click on T-final.docx to open it and add content to it.

## 2. Editing the docx in Word.

Wrote out a line of text in the body: 

	"This is the first sentence written in T-final body."

I then wrote a comment on that sentence.:

	"This is the first comment in T-final."

I then wrote a second line of text in the body:

	"This is the second sentence in T-final."

And then I wrote a second comment which is attached to that second sentence:

	"This is the second comment in T-final."


Save and close T-final.docx


## 3. Converting the docx file to txt while retaining comments from docx.

In terminal, input:

    pandoc --track-changes=all T-final.docx -o T-final.txt

This created a txt file which contained the following text:

	[This is the first comment in T-final.]{.comment-start id="0"
	author="Jeremy Amin" date="2019-11-19T13:45:00Z"}This is the first
	sentence written in T-final body.[]{.comment-end id="0"}[This is the
	second comment in T-final.]{.comment-start id="1" author="Jeremy Amin"
	date="2019-11-19T13:46:00Z"}This is the second sentence in
	T-final.[]{.comment-end id="1"}

Breaking down what the above text means...

This is for the first sentence in the body and the comment attached to it:

	[This is the first comment in T-final.]{.comment-start id="0"
	author="Jeremy Amin" date="2019-11-19T13:45:00Z"}This is the first
	sentence written in T-final body.[]{.comment-end id="0"}

This is for the second sentence in the body and the comment attached to it:

	[This is the second comment in T-final.]{.comment-start id="1" author="Jeremy Amin"
	date="2019-11-19T13:46:00Z"}This is the second sentence in T-final.[]{.comment-end id="1"}


This is the information which includes the first comment in the original Docx file:

	[This is the first comment in T-final.]{.comment-start id="0"
	author="Jeremy Amin" date="2019-11-19T13:45:00Z"}

Note the timestamp for the first comment I made: 

	"2019-11-19T13:45:00Z"

So the comment was made on the 19th of NOV at 1:45 PM

And this is the information for the in-document text:

	This is the first
	sentence written in T-final body.[]{.comment-end id="0"}

Note the timestamp for the second comment I made attached to the second sentence:

	"2019-11-19T13:46:00Z"

The comment was made on the 19th of NOV at 1:46 PM

The result of this is that the txt file has the information of what and when the comment was made. Two different time stamps for comments made in Words which I can track in txt format!

I can cycle steps 2 and 3 any number of times I wish. Editing the docx in Word, and then converting to txt with the Pandoc command which retains the comment changes made, and so on. There is also a way to edit the txt file and then convert it back to docx! Simply writing in the square brackets which represent the in-body text in the docx will add those edits. Writing in the square brackets which represent the comments will add those to the comments in the docx when converted.

To convert from txt to docx and retain the in body and comment edits, run this command:

	pandoc --track-changes=all example.txt -o example.docx

To see an example of an original Docx which I then converted to txt, modified in txt and then converted back to Docx go to [aa](https://github.com/MQ-FOAR705/Version-Control-Supervisor-Feedback-PoC/tree/master/aa)


## 4. Local version control

Next step is to set up version control locally and online.

I use [Git](https://git-scm.com/) for local version control and [GitHub](https://github.com/) for online version control.


Once Git is installed on the laptop, in terminal go to the folder you wish to version control and then type:

	git init

If successful, you will have initialised your folder as a local Git repository 
 
Then type:

	git status

This will show you which files are being tracked...

For me terminal output this:

	On branch master

	No commits yet

	Untracked files:
  	(use "git add <file>..." to include in what will be committed)
	T-final.docx
	T-final.txt

So I then input:

	git add .

The '.' will add all files to a 'loading area' to be committed to the local Git repository:

	On branch master

	No commits yet

	Changes to be committed:
  	(use "git rm --cached <file>..." to unstage)
	new file:   T-final.docx
	new file:   T-final.txt

Then inputting:

	git commit .

Will take you to the 'vi' editor in terminal. This is where you can add a description of what you are committing. Since I am only committing two new files to my local repository, I will write 'Created and added T-final.docx and T-final.txt'

Once written, I press the esc key and then type 'wq' to save the message and quit the vi editor. This will begin the commit process.

This gave me:

	[master (root-commit) 7c9e692] Created and added T-final.docx and T-final.txt
 	 2 files changed, 6 insertions(+)
 	 create mode 100644 T-final.docx
 	 create mode 100644 T-final.txt

A successful commit to my local repository!


## 5. Online version control.

Now I want to connect my local repository to GitHub...

After going to (https://github.com/) and making an account, I create a new online repository.

Once created, the webpage brings up a page with an option to "Quick setup". I look below that section to the section which says:
	
	…or push an existing repository from the command line. 

There are two lines of code for terminal there.

This line connects your local repository to the one on GitHub you are about to create. *Note that for you the URL will look different depending on what your username and repository name on GitHub are. My username is Jeremy-Amin and the repository is named PoC-final-JeremyAmin*:

	git remote add origin https://github.com/Jeremy-Amin/PoC-final-JeremyAmin.git

Once I input this to terminal, nothing showed up in terminal, indicating that the remote add (connection to the online repository) was a success!

This line 'pushes' or uploads the contents of my local repository to GitHub:

	git push -u origin master

*Note: I was prompted to input my username and login for GitHub during this part of the process to access it from terminal*

When input, this is what comes up on terminal:

	Enumerating objects: 4, done.
	Counting objects: 100% (4/4), done.
	Delta compression using up to 8 threads
	Compressing objects: 100% (4/4), done.
	Writing objects: 100% (4/4), 12.29 KiB | 12.29 MiB/s, done.
	Total 4 (delta 0), reused 0 (delta 0)
	To https://github.com/Jeremy-Amin/PoC-final-JeremyAmin.git
 	* [new branch]      master -> master
	Branch 'master' set up to track remote branch 'master' from 'origin'.

A successful push! Now the contents of my local repository are identical to the contents on my GitHub repository named PoC-final-JeremyAmin.


Now that I have:

1. Created a docx file.
2. Converted it to a txt file from the command line using Pandoc
3. Created a Git repository locally
4. Created a GitHub repository online which is connected to my local repository.
5. Pushed the files from my local repository to my GitHub repository.

I can now begin the version controlling of my comments in my word doc in such a way that I can track them in a more reliable and less easy to lose way.

First, I go into T-final.docx and make an alteration to it...

I added "This is a third sentence added to T-final body." to the body and "This is a third comment attached to the third sentence of T-final." as a comment to the newly added sentence in the body.

Then I save the doc in word and close it.

Now I'm going to go back to terminal and using Pandoc make an update to T-final.txt like I did before:

	pandoc --track-changes=all T-final.docx -o T-final.txt

Success! Now I have created a new file named T-final.txt which has the original text as well as the most recent additions to the Docx file added. It now looks like this:

	[This is the first comment in T-final.]{.comment-start id="0"
	author="Jeremy Amin" date="2019-11-19T13:45:00Z"}This is the first
	sentence written in T-final body.[]{.comment-end id="0"}[This is the
	second comment in T-final.]{.comment-start id="1" author="Jeremy Amin"
	date="2019-11-19T13:46:00Z"}This is the second sentence in
	T-final.[]{.comment-end id="1"}

	[This is a third comment attached to the third sentence of
	T-final.]{.comment-start id="2" author="Jeremy Amin"
	date="2019-11-19T19:50:00Z"}This is a third sentence added to T-final
	body.[]{.comment-end id="2"}

Now for the fun part...I am going to commit the changes made to both files and then push them to my GitHub repository.

Typing:

	git status

outputs:

	On branch master
	Your branch is up to date with 'origin/master'.

	Changes not staged for commit:
  	  (use "git add <file>..." to update what will be committed)
  	  (use "git restore <file>..." to discard changes in working directory)
		modified:   T-final.docx
		modified:   T-final.txt

So, I have modified both files and terminal is telling me so.

I then add all files to be committed:

	git add .

And then I commit all files:

	git commit .

I wrote a commit note in vi editor "Added third sentence and third comment to T-final.docx. Converted T-final.docx to txt format to track changes."

Now I push the changes in the repository to GitHub:

	git push

Which outputs:

	Enumerating objects: 7, done.
	Counting objects: 100% (7/7), done.
	Delta compression using up to 8 threads
	Compressing objects: 100% (4/4), done.
	Writing objects: 100% (4/4), 5.33 KiB | 5.33 MiB/s, done.
	Total 4 (delta 2), reused 0 (delta 0)
	remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
	To https://github.com/Jeremy-Amin/PoC-final-JeremyAmin.git
   	    7c9e692..5e072ed  master -> master

A successful push!

Going to the GitHub repository online I can see that the push was successful and when I open T-final.txt and look at its history I can see the changes I have made. In this case, the changes are the added third sentence and third comment to the original Docx file in txt format.

And like that, I have a way to:

1. Modify a Docx file.
2. Convert it to a txt file while retaining the additional comments with timestamps.
3. Upload both the updated Docx and txt files to an online repository.
4. Track all of the committed changes I have made to both files and easily select which change on which date and time I want to view.
5. Edit the information from a converted Docx file in txt and convert it to Docx to send to my supervisor or peer quickly and saving tracked changes in the process.

Now, rather than relying solely on Microsoft Word to track the history of my changes to my document and the comments from my supervisor, I have two version controlled repositories AND I can select which comment to view and when. Just in case there is a miscommunication between myself and my supervisor, I can quickly find when the miscommunication took place and see precisely what they said, removing human error from the feedback process that much more.
