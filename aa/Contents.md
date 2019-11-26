This directory is an example of how a Docx file can be created with modifications to the body of text as well as adding comments attached to the body text.

There are also html, md, and tex versions of the original aa.docx file for comparison purposes. I suspect a similar process to the one I used for txt will also work for other file types.

# aa.docx

This is the initial docx file:

![alt text](https://github.com/MQ-FOAR705/Version-Control-Supervisor-Feedback-PoC/blob/master/aa/aa.docx-screenshot.png "Initial Docx file")

Using pandoc in terminal with the command:

	pandoc --track-changes=all aa.docx -o aa.txt

Created aa.txt

# aa.txt looks like this:


![alt text](https://github.com/MQ-FOAR705/Version-Control-Supervisor-Feedback-PoC/blob/master/aa/aa.txt-screenshot.png "Txt file from initial docx file")

I then created a new file named aa2.txt and added the third section to it.

# aa2.txt looks like this:

![alt text](https://github.com/MQ-FOAR705/Version-Control-Supervisor-Feedback-PoC/blob/master/aa/aa2.txt-screenshot.png "Modified aa.txt")

Using pandoc in terminal with the command:

	pandoc --track-changes=all aa2.txt -o aa2.docx

Created aa2.docx
  
# aa2.docx looks like this:


This is what the second docx file looks like:

![alt text](https://github.com/MQ-FOAR705/Version-Control-Supervisor-Feedback-PoC/blob/master/aa/aa2.docx-screenshot.png "Final Docx file!")

A successful way to create Docx files from txt which incude in body text with comments attached! If a person so chooses, they can write all of their documents in this fashion and then when sending them to thier peers thet can create a docx file using Pandoc.
