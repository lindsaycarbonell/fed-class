# Your First Webpage
_TO READ THESE NOTES_:
* **option 1**: open the class folder and this file in Visual Studio Code. Open the Command Palette (cmd+shift+P or View->Command Palette). Search for and select "Markdown: Open Preview to the Side".
* **option 2**: Go to https://github.com/lindsaycarbonell/fed101 and navigate to the lesson folder.

## The command line and setting up our class folder
* Open terminal if you're on a Mac, or cmder if you're on a PC. Type the following in the **command line** and press enter:
```
ls
```
ls stands for "list". When you make this command, you'll be able to see all of the files in your current location. Now type:
```
open .
```
And press enter. Now you'll see the same location but in the familiar **Graphical User Interface (GUI)** that you are used to (_Finder_ for Mac or _Windows Explorer_ on a PC running Windows).
* This is your file system. Each item in your file system has an address associated with it. That address is called a **path**. We call folders **directories**. Run the following command:
```
pwd
```
pwd stands for “print working directory”. This will tell you the address of your current directory.
* We want to navigate to the Desktop directory so we're going to use the `cd` command, which stands for _change directory_. Give it a try:
  * For Windows, do:
  ```
  cd C:\Users\Public\Desktop
  ```
  * For Mac: 
  ```
  cd ~/Desktop
  ```
* This is an example of using a full directory path to navigate to a directory. We can also go in and out of folders using `cd`. If you run `ls` you can see all of your files/directories in that location. Try doing `cd (name of a directory)` to go into a folder. Notice the path on your current line will change. If you do `ls` again you can see what's inside the directory.
* Use `cd ../` to move out of the current directory up into its **parent directory**. You can us `../` to go up as many parents as you would like, for instance: `../../` will take you up two parents, and `../Documents/' will take you out of your current directory and then into its **child directory** called "Documents".
* Let's go back to the desktop and make a directory for this class. Navigate to the desktop and run:
	```
	mkdir FED_101
	```
* _mkdir_ stands for "make directory".
* Notice that there are no spaces in my folder name. This is purposeful. Below are different _naming conventions_ for file/directory names:
 	* **camel case**: when each word is capitalized except the first. (ex: theFedClass)
    * **snake case**: when each word is separated by underscores, all lowercase. (ex: the_fed_class)
    * **kebab case**: when each word is separated by hyphens, all lowercase. (ex: the-fed-class)
    * You don't have to use these, but you do always want to: *(1) be consistent in your convention and (2) don’t use spaces in filenames*.
* Now let's go into our class folder and get all the lesson plans. cd into the folder and run: 
	```
	git clone https://github.com/lindsaycarbonell/fed-class.git
	```
* This command pulls down all of the files for the class from a [GitHub repository](https://github.com/lindsaycarbonell/fed-class) that I created. Now you can cd into our first lesson.
* Note: if you press `tab` when you have part of the filename typed in, the command line can finish the filename for you.
* You'll notice a number of files with different **file extensions** (.html, .css, .md). File extensions tell your computer how to interpret its contents.
  * .html is an HTML file and will open in your default **browser** (ex: Google Chrome, Internet Explorer, Mozilla Firefox, Safari, Opera). All websites are made up of a set of HTML files for each page.
  * .css is a CSS file, which we will talk about later.
  * .md is a [markdown file](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet), which is a text-to-HTML conversion language. In this class I will be using it for our notes and homework assignments. Each set of notes is named "README.md" so that it is the first md file that shows in each folder in the GitHub view.

## Classwork: Your first webpage
_Follow along in class and take any notes you would like to here!_
* Concepts:
  * Google Fonts
  * assets folder
  * absolute/relative URLs
  * the `<img />` tag
  * HTML entity
  * encoding
  * header tags (`<h1>` through `<h6>`)
  * HTML comments

## Vocabulary
- command line
- Graphical User Interface (GUI)
- path
- directory
- parent directory
- child directory
- naming conventions
  - camel case
  - snake case
  - kebab case
- file extension
- browser
- absolute URL
- relative URL
- HTML entity


