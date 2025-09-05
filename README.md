### Before reading
This lesson if pretending that you are on a MacOS or UNIX type OS.
### Topic
In this lesson you will learn basics needed to learn any language or just start coding in general.
### Brief intro
Before doing anything, what is coding ? Coding is writing text instructions in a file to then compile them to make the code understandable for the machine, to finally execute those instructions. 
**def**: 
- compile: turn your code to machine language, ex:  ``print("something")`` = "machine language that tells to display 'hello' on the screen"  like binary or just no humanly readable characters.
- instructions: things you tell the computer to do, like printing, changing things etc ...
### Before starting
I'm gonna teach you some little terms and things to know and understand.
**def**:
- paths: when we use the word 'path' in computer science we mean the file path to a certain file, ex: the path to your project is maybe **/home/user_name/your_project**. 
- absolute path: a path starting from the bottom of your file architecture, ex: **/from/the/beginning**
- relative path: a path starting from the current working directory, ex: if your current working directory is **/current/working/directory**, the relative path **./file** = **/current/working/directory/file**
Now lets go through some shell basics you'll nearly use every time while coding and to test:
### Start
Look at this code:
```python
print("Hello i want to code")
```
This file is actually coded in python language, actually this fact doesn't interest us, what is interesting is how do we execute it ? To execute the code as i said in the intro you need to compile it, so you need a COMPILER. Each language has its own ones, in C there is 'gcc', in C++ its 'g++' and in python it is 'python'. If you want to compile some files, in most of the time you do:
```
[COMPILER] {files}
```
So in the python example above we would do:
```bash
python the_name_of_the_file
```
Mostly when coding you code of course in a file, and the name of the file is:
```
any_name.(language extension, c for C, cpp for C++, py for python...)
```
We will name our file main.py so to compile you will do:
```bash
python main.py
```


