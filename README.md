# Version-Control-Supervisor-Feedback-PoC
This is my updated PoC document.

# Why should you care about this repository?
This is a place for those who are looking for ways to work with docx (bin) files but may be frustrated with the ability to version control on sites such as GitHub which are not bin compatible. I have developed the start of a process which will enable a person to convert from Docx to a non-binary format and version control while retaining important information such as Word comments in the conversion.

The main problem I identified in version conrolling Docx files is that when converting from Docx to txt directly from the drop down menu in Word itself the comments get lost in translation. Using a program called Pandoc I found a solution to this problem. Using the macOS terminal on my laptop I was then able to version control locally on my laptop and on GitHub.

# What's this repository about?
This is a repository I created for a workflow which streamlines a few steps of work for researchers in philosophy using Docx files to send and recieve feedback from peers and supervisors. This workflow is applicable for anyone who relies on primarily text based research and uses Microsoft word in their research process.

This is a repository where I am testing my PoC for version controlling comments and feedback from my supervisor, and
where I track the history of changes made based on the comments and feedback.

# What's in this repository
In this repository you will find:

- [Step-guide.md](https://github.com/MQ-FOAR705/Version-Control-Supervisor-Feedback-PoC/blob/master/Step-guide.md) - An example of what version controlling files may look like. [Here is where the files are located in this repository](https://github.com/MQ-FOAR705/Version-Control-Supervisor-Feedback-PoC/tree/master/PoC-final)
- [Websites.txt](https://github.com/MQ-FOAR705/Version-Control-Supervisor-Feedback-PoC/blob/master/Websites.txt) - A file containing a list of websites used in this workflow.
- [Feedback-test](https://github.com/MQ-FOAR705/Version-Control-Supervisor-Feedback-PoC/tree/master/Feedback-test) is a directory where I have two TeX files and a docx file which I converted via Pandoc for version control purposes.
- [aa](https://github.com/MQ-FOAR705/Version-Control-Supervisor-Feedback-PoC/tree/master/aa) is a directory which contains a few files created from aa.docx using Pandoc. Read the file [Contents.md](https://github.com/MQ-FOAR705/Version-Control-Supervisor-Feedback-PoC/blob/master/aa/Contents.md) in that directory to see a few screenshots of how to modify txt files and then convert them to docx.
- [Terminal-commands-Pandoc.txt](https://github.com/MQ-FOAR705/Version-Control-Supervisor-Feedback-PoC/blob/master/Terminal-commands-Pandoc.txt) - A list of useful commands in macOS terminal for converting documents using Pandoc.
- [A License for this repository](https://github.com/MQ-FOAR705/Version-Control-Supervisor-Feedback-PoC/blob/master/LICENSE)
- [A TeX file detailing my process in creating this PoC](https://github.com/MQ-FOAR705/Version-Control-Supervisor-Feedback-PoC/blob/master/main.tex)

# How to use this repository

## 1. Programs and websites for this PoC

*I assume you are already working with Docx files in some stage of your workflow.*

For this process you will need:

- Access to terminal on macOS. This will also work on Windows.
- [Pandoc](https://pandoc.org/installing.html) downloaded and installed.
- [Git](https://git-scm.com/downloads) downloaded and installed.
- A [GitHub](https://github.com/) account.

## 2. Open the file [Step-guide.md](https://github.com/MQ-FOAR705/Version-Control-Supervisor-Feedback-PoC/blob/master/Step-guide.md) and work through the steps I laid out.

This file details a test run I did going from no files or directories locally to eventually having local and online version controlled respositories with one Docx file and one txt file which I converted using Pandoc.

## 3. Open the directory [aa](https://github.com/MQ-FOAR705/Version-Control-Supervisor-Feedback-PoC/tree/master/aa) and look at the files in there.

- Read Contents.md. This file contains a few screenshots which outline the process of creating a docx file from a txt file which contains information for adding comments in docx format.


# Future additions

- I would like to figure out a way to make the output from docx to txt files look easier to follow and easier to edit. A more intuitive layout of the in-body text and comments would make going back and forth between docx and txt easier.
- 
