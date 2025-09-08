### Before reading
This lesson is pretending that you are on a MacOS or UNIX type OS.
Throughout the course if it isn't specified, all code instructions are in an imaginary coding language cooked by me, don't assimilate it to anything.
When your read the lessons if something appears weird and not clear to you, don't panic it will come with time. 
If you think you skipped something, don't go back go forward.
DON'T GO BACK EVER EVER EVER !
It is recommended to start with the python language to exercise yourself.
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
How do we code now ? To start coding you need some basic knowledge to then transform your ideas into real code.

**Comments:** comments are used to write text in your code without being interpreted by the compiler, it is ignored by everything.

- ex in python:
```python
# this is the python way to make comments in a script
print("A")
```

- ex in c:
```c
int main()
{
	// this is the c way to make comments in a script
}
```

- ex in lua:
```lua
-- this is the lua way to make comments in a script
```

---
**Functions:** a function is a block of code that executes all of the instructions contained in the actual block.

- ex in python of a builtin function:
```python
print("I will code") # this is a call to the print func
```

- ex in python of a "homemade" function:
```python
# we define our function
def print_value_plus_one(value): # 'value' is called a parameter
	print(value + 1)

print_value_plus_one(0) # '0' is called the argument of the func call
```

This is a call to the 'print()' function of python, but we didn't code the function, it was already coded so we don't have access to the block of instructions, but in the second example we coded our own function and the call to it displays 1 in the terminal. Note that functions can have a number of parameters balancing between 0 and a lot.

- ex in python of a possible compile error:
```python
def print_two_words(word1, word2):
	print(word1) # prints the first parameter
	print(word2) # prints the second parameter
	
print("Salam", "3likom") # it works because we gave two args to the function call
print("Only one arg") # there will be a compilation error because we only gave one arg to the function call but you need two
```

Another important thing to know about functions is that they can have a return value. In the previous examples there was no appearing return value in those functions but let's try it out.

- ex in python of function return value concept:
```python
def return_1_func(): # this func has no params
	return 1 # there is no instructions apart from the 'return', we say that the func returns 1
	
def double_value(the_int) # there is one param named 'the_int'
	return the_int * 2 # there is no instructions apart from the 'return', it returns the double of the_int param
	
print(return_1_func()) # this func call "transforms" to print(1)
print(double_value(2)) # this func call "transforms" to print(4)
```

You should see '1' then '4' displayed in the terminal.

---
**Variables:** a variable is a space dedicated to containing a piece of data, ex: a variable named 'ex_var' contains the number 2, print(ex_var) = "2 is printed".

- ex in python:
```python
ex_var = 7
print(ex_var)
```

An important thing to know in programming is that in general variables have three main types possible (data types), the three most known ones:
- decimal number, negative or positive (integer)
- sequence of literal characters (string)
- only two value possible, true or false (boolean)

- ex in python of the three types:
```python
ex_string = "you need double quotes or simple quotes to make strings"
ex_integer = 77 # an integer
ex_boolean = true # true or false value
```

- ex in python of changing variable value:
```python
ex_var = 93 # ex_var is declared and initialised here
print(ex_var)
ex_var = 77 # we changed the value here
print(ex_var)
```

You should see '93' and then '77' displayed in terminal.

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
**Libraries:** libraries are some sets of functions that you can import and then reuse for your own code. Do you remember the print() function in python ? It comes from the "standard python library" which is already included in your script but you can import other libraries as you wish by doing it manually.

- ex in python:
```python
import math # we import the module 'math' of python (those are named modules in python but for now assimilate them as libraries)

print(math.sqrt(4))
```

Now you should see the square root of 4 displayed in your terminal which is 2. Notice that the block of instructions of function 'sqrt' from 'math' library is actually contained in the library.

---
**Operators:** operators are essential to you if you want to code. Let's see a list of them with examples for you to understand.

- ex in python:
```python
ex_var = 77 
print(ex_var == 77) # we will print the result of the operation which is a boolean type result
```

You should see 'True' displayed in your terminal, but why ? Operators return values like function, take the example of the '+' operator between two integers, 2 + 2 = 4 and 4 is the return value. The '\==' operator looks if two values are equal and returns true or false rather the two are equal, or not. So now if you have understood well the concept, we can enumerate them:
- '\==': checks if two values (operands) are equal, it returns a boolean.
- '\!=': checks if two values (operands) are different from each other, it returns a boolean.
- '<': checks if the first value is inferior to the second one, it returns a boolean.
- '>': checks if the first value is superior to the second one, it returns a boolean.
- '<=': checks if the first value is inferior or equal to the second one, it returns a boolean.
- '>=': checks if the first value is superior or equal to the second one, it returns a boolean.
- all of the mathematics base operators: '+-/\*' .
- and others more subtle and that you will discover on your own.

---
**Conditions:** as the definition of the word says, if the condition is 'true' then you execute the wanted code.

ex in python:
```python
ex_var = 5
if ex_var == 5 : # we write the condition if x is equal to 5
	print("ex_var is equal to 5") # if the cond is true then we print the message
```

You should see "x is equal to 5" displayed in your terminal because the condition 'x == 5' returns true. You can put instructions to execute if the condition is true but what if the condition is false and you also want to execute some instructions in this case ? Well you can with the 'else' keyword.

ex in python:
```python
ex_var = 77
if ex_var < 75 : # if ex_var is inferior to 75
	print("ex_var is inferior to 75") # then we print this message
else : # else, this means ex_var is not inferior to 75
	print("ex_var is superior of equal to 75") # then we do this instead
```

As you may imagine, "ex_var is superior of equal to 75" will be displayed in the terminal. Let's go a step further, let's introduce the 'else if' concept with an example.

ex in python:
```python
ex_var = 2
if ex_var == 0 :
	print("ex_var is equal to 0")
elif ex_var == 1 :
	print("ex_var is equal to 1")
elif ex_var == 2 :
	print("ex_var is equal to 2")
else :
	print("ex_var doesn't match any wanted cases")
```

Here you can see how we can for example manage multiple cases with if/else statements (elif = else if). The actual program will display "ex_var is equal to 2".

---

