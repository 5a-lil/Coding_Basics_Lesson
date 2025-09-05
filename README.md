### Before reading
This lesson is pretending that you are on a MacOS or UNIX type OS.
### Topic
In this lesson you will learn basics needed to learn any language or just start coding in general.
### Brief intro
Before doing anything, what is coding ? Coding is writing text instructions in a file to then compile them to make the code understandable for the machine, to finally execute those instructions. 
**def**: 
- instructions: things you tell the computer to do, like printing, changing things etc ...
- compile: turn your code to machine language, ex:  print("something") = "machine language that tells to display 'hello' on the screen"  like binary or just no humanly readable characters.
### Before starting
I'm gonna teach you some little terms and things to know and understand.
**def**:
- paths: when we use the word 'path' in computer science we mean the file path to a certain file, ex: the path to your project is maybe /home/user_name/your_project. 
- absolute path: a path starting from the bottom of your file architecture, ex: /from/the/beginning.
- relative path: a path starting from the current working directory, ex: if your current working directory is /current/working/directory, the relative path ./file = /current/working/directory/file
Now lets go through some shell basics you'll nearly use every time while coding and to test. First open shell, that basically means open a terminal, so now you're on an interface like this: 
```bash
$ you type commands here
```
Now what are commands ? Commands are executable files that do things, like displaying in which directory you currently are, ex: you type the 'pwd' command and press enter:
```bash
$ pwd
/your/current/working/directory
$ you type other commands here
```
The thing is that through shell you can do a lot like change directories, copy data, but mostly you can compile files by using some respective commands for each existent compiler that you have installed.
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
$ python the_name_of_the_file
```
Mostly when coding you code of course in a file, and the name of the file is:
```
any_name.(language extension, c for C, cpp for C++, py for python...)
```
We will name our file main.py so to compile it you will do:
```bash
$ python main.py
Hello i want to code
$ a new shell line
```
The thing is that we compiled the file so the computer can understand it but why do we have something written: "Hello i want to code" ? This is a special case because python compiler 'python' not only compiles files but it also executes them at the same time.
Now we are gonna compile a C coding language file with the compiler 'gcc' to really see a difference; lets make a main.c file:
```c
int main()
{
	printf("Hello i want to code\n");
}
```
Now lets compile the main.c file:
```bash
$ gcc main.c
$ a new shell line
```
As you can see there is just a new line but nothing got written, its because gcc really just compiled the file into "computer understandable" language. If we launch the 'ls' command in the current working directory we'll see this:
```bash
$ ls
main.c a.out
$ a new shell line
```
'ls' command lists all the files in the current working directory, so there is the main.c but why is there a "a.out" file ? All you need to know for now is that the a.out file is the compiled; and now if we execute with the './' syntax we'll see:
```bash
$ ./a.out
Hello i want to code
$ a new shell line
```
