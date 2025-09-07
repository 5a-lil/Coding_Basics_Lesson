### Before reading
This lesson is pretending that you are on a MacOS or UNIX type OS.
Throughout the course if it isn't specified, all code instructions are in an imaginary coding language cooked by me, don't assimilate it to anything.
When your read the lessons if something appears weird and not clear to you, don't panic it will come with time. 
If you think you skipped something, don't go back go forward.
DON'T GO BACK EVER EVER EVER !
### Topic
In this lesson you will learn basics needed to learn any language or just start coding in general.
### Brief intro
Before doing anything, what is coding ? Coding is writing text instructions in a file to then compile them to make the code understandable for the machine, to finally execute those instructions. 

**def**: 
- instructions: things you tell the computer to do, like printing, changing things etc ...
- compile: turn your code to machine language, ex:  display("something") = "machine language that tells to display 'hello' on the screen"  like binary or just no humanly readable characters. It is in some cases stored in a binary file.
### Before starting
I'm gonna teach you some little terms and things to know and understand.

**def:**
- paths: when we use the word 'path' in computer science we mean the file path to a certain file, ex: the path to your project is maybe /home/user_name/your_project. 
- absolute path: a path starting from the bottom of your file architecture, ex: /from/the/beginning.
- relative path: a path starting from the current working directory, ex: if your current working directory is /current/working/directory, the relative path ./file = /current/working/directory/file.
- shell: shell is a coding language but it also refers to a terminal, when we say "open a shell" it basically means "open a terminal".
- execute a file: in a shell, just write the relative/absolute path of the file and press enter and it will execute the binary file. For commands which are all actually binary files in the /bin directory you can execute them without any path but avoid this for now.
- file extensions: any .something extension after a file name is just literal, it doesn't do anything to the file, the thing to remember for now is that you need file extensions for mostly compilers, because a compiler will always inspect if the file contains actually the good language to compile and that's the literal role of a file extension. Because compiling something that you cannot understand doesn't make any sense.

Now lets go through some shell basics you'll nearly use every time while coding and to test. First open a shell, so now you're on an interface like this: 

```bash
$ you type commands here
```

Now what are commands ? Commands are executable files that do things, like displaying in which directory you currently are, ex: execute the 'pwd' command:

```bash
$ pwd
/your/current/working/directory
$ new empty line
```

The thing is that through shell you can do a lot of things like move to a directory/bin, copy data, but mostly you can compile files by using some respective commands for each existent compiler that you have installed. When you are in a shell as you saw with the 'pwd' command your are by default in the directory where you opened the shell, but you can change of current working directory with the 'cd' command:

```
$ cd <paths to new working directory>
```

ex: 

```
$ cd ./file
$ pwd
/your/current/working/directory/new_cwd
$ new empty line
```

**def:**
- cwd: your **c**urrent **w**orking **d**irectory
### Start
Lets start with brief and mandatory explanations.

Look at this code:

```python
print("Hello i want to code")
```

This file is actually coded in python language, actually this fact doesn't interest us, what is interesting is how do we execute it ? To execute the code as i said in the intro you need to compile it, so you need a compiler. Each language has its own ones, in C there is 'gcc', in C++ its 'g++' and in python it is 'python'. If you want to compile some files, in most of the time you do this in a shell:

```
$ execute_compiler_command <files to compile>
```

So in the python example above we would do:

```
$ python <the name of the file>
```

Mostly when coding, you code of course in a file, and the name of the file is:

```
any_name.(language extension, c for C, cpp for C++, py for python...)
```

You need the file extension to say to the compiler that "this file is a script written in a certain language". We will name our file main.py, so to compile it you will do:

```
$ python main.py
Hello i want to code
$ new empty line
```

The thing is that we compiled the file so the computer can understand it but why do we have an output: "Hello i want to code" ? This is a special case because python compiler 'python' not only compiles files but it also executes them at the same time.
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
$ new empty line
```

As you can see there is just a new line but nothing got written, its because gcc really just compiled the file into "computer understandable" language. If we launch the 'ls' command in the current working directory we'll see this:

```bash
$ ls
main.c a.out
$ new empty line
```

'ls' command lists all the files in the current working directory, so there is the main.c but why is there a "a.out" file ? All you need to know for now is that the a.out file is the binary, compiled file; and now if we execute it we'll see:

```bash
$ ./a.out
Hello i want to code
$ new empty line
```

So in this section you learnt how to compile and execute your code and that's awesome because you can actually start coding ! But before that lets deep again in more shell basics and habits that you use often while coding.

### Shell quick practice
Lets see some useful scenarios that might happen.

- Imagine you want to create a My_Proj folder for your project and create a main.lua file in it:

```
$ pwd                            (check the cwd)
/cwd
$ mkdir My_Proj                  (create a new directory named My_Proj)          
$ ls                             (check the files in the cwd)
some files My_Proj               (currently some files and folders but mostly the My_Proj directory)
$ cd ./My_Proj                   (we change our cwd to My_Proj directory) 
$ pwd (check the cwd)
/cwd/My_Proj           (we successfully changed)
$ ls                             (ls output isn't showing anything so the cwd is empty)
$ touch main.lua                 (we create a file named main.lua)
$ ls 
main.lua                         (we see that the file got created)
$ new empty line
```

- Now let's say you want to delete a certain file named target.aim in a directory named To_Trash:

```
$ pwd                            (check the cwd)
/cwd 
$ ls                             (check the files in the cwd)
To_Trash some other files
$ rm ./To_Trash/target.aim       (remove the file at the given path)
$ cd To_Trash                    (change cwd)
$ pwd                            (check the cwd)
/cwd/To_Trash
$ ls                             (ls output isn't showing anything so the target.aim file got removed successfully)
$ new empty line
```

- Finally another could be that you want to see the content of a file in a shell:

```
$ pwd                            (check the cwd)
/cwd
$ ls                             (check the files in the cwd)
A_Directory some files text
$ cat ./text                     (displays the content of the file)
the
content
of
the
file
$ new empty line
```

- Bonus: did you know that commands can have flags, ex: '-f':

```
$ pwd                            (check the cwd)
/cwd
$ ls                             (check the files in the cwd)
A_Directory some files
$ rm ./A_Directory               (tries to remove the directory A_Directory)
"you will have an error here"    (it didn't success and there is an error)
$ rm -f ./A_Directory            (tries to remove the directory A_Directory with the '-f' flag for 'force' to force the remove)
$ ls                             (check the files in the cwd)
some files                       (the directory A_Directory has been successfully removed)
$ new empty line
```

### Coding mandatory notions
How do we code now ? To start coding you need some basic knowledge to then transform your ideas into real code throughout mastered concepts of code.

**Functions:** a function is a block of code that executes all of the instructions contained in the actual block.

- ex in python of a builtin function:

```python
print("I will code")
```

- ex in python of a "homemade" function:

```python
# we define our function
def print_value_plus_one(value): # 'value' is called a parameter
	print(value + 1)

print_value_plus_one(0) # '0' is called the argument of the func call
```

This is a call to the 'print()' function of python, but we didn't code the function, it was already coded so we don't have access to the block of instructions, but in the second example we coded our own function and the call to it displays 1 in the terminal.

---

**Syntax:** when you code you obviously choose a programming language (python, c, rust...), and each of those languages has its own syntax, you write with a unique way for each language, let's make a printA function that actually prints A in the terminal with 3 languages.

- ex in python:

```python
def printA():
	print("A")
```

- ex in c:

```c
void printA()
{
	write(1, "A", 1);
}
```

- ex in lua:

```lua
function printA()
	print("A")
end
```

You see that each language has a different way to write functions with their block of instructions, that is a syntax demonstration, each language has its own way to write code.

---

**Variables:** a variable is a space dedicated to containing a piece of data, ex: a variable named 'var' contains the number 2, print(var) = 2 is printed.

- ex in python:

```python
var = 7
print(var)
```

- ex in c:

```c
int main()
{
	int var = 7;
	printf("%d\n", var);
}
```

- ex in lua:

```lua
var = 7
print(var)
```

---

**Comments:** comments are used to write text in your code without being interpreted by the compiler, it is ignored by everything.

- ex in python:

```python
# the call to this function displays A in the terminal
print("A")
```

- ex in c:

```c
int main()
{
	// nothing is done here
}
```

- ex in lua:

```lua
var = 1
-- this function adds one to the var variable
function add_one_to_var()
	var = var + 1
end
-- normally we should see 1 then 2 displayed in the terminal
print(var)
add_one_to_var()
print(var)
```

---

**Arguments and Parameters:** i will illustrate this with an example, if i want to go on a jog outside i need to wear shoes, the shoes are the parameter, now if i go jog outside with some nike shoes, the nike shoes are the argument, the difference is really subtle. For example functions can have parameters and when you call those function you need to list an argument for each parameter to have.

- ex in python:

```python
# num_param and text_param are parameters
def ex_func(num_param, text_param):
	print(num_param)
	print(text_param)
	
# 77 and "Meaux" are arguments of the function call of ex_func
ex_func(77, "Meaux")
```

---

