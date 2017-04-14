import csv

#whole dictionary
dictionary = {"FUNCTION": ("A series of statements which returns some value to a caller. ", "https://docs.python.org/3/glossary.html#term-function"),
                 "WHILE": ("While loops, like the ForLoop, are used for repeating sections of code - but unlike a for loop, the while loop will not run n times, but until a defined condition is no longer met. If the condition is initially false, the loop body will not be executed at all.", "https://wiki.python.org/moin/WhileLoop"),"VARIABLE": ("Variables are nothing but reserved memory locations to store values. This means that when you create a variable you reserve some space in memory.", "https://www.tutorialspoint.com/python/python_variable_types.htm"), "TIME": ("This module provides various time-related functions. For related functionality, see also the datetime and calendar modules.", "https://docs.python.org/2/library/time.html"),
                "DICTIONARY": ("he values of a dictionary can be of any type, but the keys must be of an immutable data type such as strings, numbers, or tuples.", "https://www.tutorialspoint.com/python/python_dictionary.htm"), "TUPLE": ("a sequence of immutable Python objects. Tuples are sequences, just like lists. The differences between tuples and lists are, the tuples cannot be changed unlike lists and tuples use parentheses, whereas lists use square brackets.", "https://www.tutorialspoint.com/python/python_tuples.htm"),
                "ASCII table": ("ASCII (American Standard Code for Information Interchange) is the most common format for text files in computers and on the Internet.", "http://whatis.techtarget.com/definition/ASCII-American-Standard-Code-for-Information-Interchange"),"MODULE": ("Python has a way to put definitions in a file and use them in a script or in an interactive instance of the interpreter. Such a file is called a module; definitions from a module can be imported into other modules or into the main module (the collection of variables that you have access to in a script executed at the top level and in calculator mode).", "https://docs.python.org/3/tutorial/modules.html"),
                "LIST": ("The list type is a container that holds a number of other objects, in a given order. The list type implements the sequence protocol, and also allows you to add and remove objects from the sequence.", "http://effbot.org/zone/python-list.htm"),"CONDITIONAL": ("In order to write useful programs, we almost always need the ability to check conditions and change the behavior of the program accordingly. Conditional statements give us this ability. The simplest form is the if statement", "http://www.openbookproject.net/books/bpp4awd/ch04.html"),
                "LOOPS": ("used when you have a block of code which you want to repeat a fixed number of times.", "https://wiki.python.org/moin/ForLoop"),"BUILT-IN": ("The Python interpreter has a number of functions and types built into it that are always available.", "https://docs.python.org/3.3/library/functions.html"),
                "PRINT": ("Print objects to the text stream file, separated by sep and followed by end. sep, end, file and flush, if present, must be given as keyword arguments.", "https://www.tutorialspoint.com/python/python_functions.htm"),"GENERATORS": ("Generators functions allow you to declare a function that behaves like an iterator, i.e. it can be used in a for loop.", "https://wiki.python.org/moin/Generators"),
                "CLASSES": ("Compared with other programming languages, Python’s class mechanism adds classes with a minimum of new syntax and semantics. It is a mixture of the class mechanisms found in C++ and Modula-3.", "https://docs.python.org/3/tutorial/classes.html")}

# searching a definitions
def search():
    print("Enter appellation of the definition")
    name = input().upper()
    if dictionary.get(name):
        print(dictionary.get(name))
    else:
        print("Try other definitions, because we dont have that one ! Sorry")

#adding new definition
def adding():
    print("Enter a definition")
    definition = input().upper()
    print("Enter a explanation")
    explanation = input()
    print("Enter a source")
    source = input()
    dictionary[definition] = (explanation, source)
    print(dictionary)

# Show all definition alphabetically
def show_all():
    for definition in sorted(dictionary.items()):
        print(definition[0])

#4 showing by a first letter
def show_available():
    print("Type me first letter of a word")
    key_first_letter = input().upper()
    if len(key_first_letter) == 1:
        for definition, explanation in sorted(dictionary.items()):
            if definition[0] == key_first_letter:
                print(definition,explanation)
    else:
        print("Type me just one letter")


def main():
    while True:
        print("Dictionary for a little programmer:")
        print("1 - search")
        print("2 - add")
        print("3 - show all appellations alphabetically")
        print("4 - show all by first letter")
        print("0 - exit")
        print("Tell me a number from 0 to 4")

        input_read = input()
        if input_read.isdigit():
            input_read = int(input_read)
        else:
            print("It's not a number from 0 to 4")

        if input_read == 1:
            search()
        elif input_read == 2:
            adding()
        elif input_read == 3:
            show_all()
        elif input_read == 4:
            show_available()
        elif input_read == 0:
            return
        else:
            print("Use number from 0 to 4, try again'\n")

        #try again
        ask = ""
        while not (ask == 'YES' or ask== 'NO'):
            ask = input("Do you want to try again? (YES/NO) ").upper()
        if ask == 'NO':
            break
main()
