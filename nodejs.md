# NodeJS

Task 1: Print a Message to the Console using Node.js

1. Create a new JavaScript file.
1. In the JavaScript file, write a command to print the message "Hello sunshine, what's cooking good looking?" to the console using either `console.log()` or `process.stdout.write()`.
1. Save the JavaScript file with a name of your choice and a `.js` extension.
1. Open a terminal or command prompt window and navigate to the directory where the JavaScript file is saved.
   Run the program by typing `node <filename.js>` in the terminal or command prompt window.

## Task 2

### Task 2.1

Write a program that lists the files in a directory. When the program is executed without any parameters, it should list the files in the current directory. When a parameter is provided, it should list the files in that directory.

Example:

```
$ node lecture2.js
-> .git
-> .gitignore
-> images
-> internet.md
-> LICENSE
-> nodejs.md
-> README.md
```

Example:

```
$ node lecture2.js ./images/
-> frank-berlin.jpg
-> frank-london.jpg
-> frank-paris.jpg
-> joe-berlin.jpg
-> joe-london.jpg
-> joe-paris.jpg
-> mary-berlin.jpg
-> mary-london.jpg
-> mary-paris.jpg
-> random.jpg
```

### Task 2.2

Refactor the program to use the synchronous function `readdirSync()` to achieve the same result. Additionally, modify the program to accept a parameter `-a` to switch between synchronous and asynchronous versions of `readdir()`.

## Task 3

In the Canvas platform, you can find a zip file containing a collection of images that you can download and extract into the `images` folder. The names of the image files follow a pattern of `<photographer>-<location>.jpg`, which works well for sorting by photographer but not for sorting by location.

Your task is to write a program that copies the images to a new directory named after the city in which the image was taken. When you run the program with `node <filename>`, it should create a folder for each city and copy the corresponding images into that folder.

For example, `joe-berlin.jpg` and `frank-berlin.jpg` should be copied into a folder named `berlin`, while `joe-paris.jpg` and `mary-paris.jpg` should be copied into a folder named `paris`. The program should also print out a list of any files that did not fit the expected format.

Example output:

```shell
$ node pictureSorter.js

Unhandled files:
  random.jpg
  README.md
```

## Task 4

Your task is to write a program that converts a CSV file to a JSON file. The file `persons.csv` contains a list of people, where each line represents a person's name and email address separated by a semicolon (;). For example, `Mattias Mucherie;mattias.mucherie@1337.tech`.

Your program should read the lines from the CSV file and convert the data into a JSON format. You should create an array, where each person and their email address is represented as an object. The program should then write the resulting JSON data to a new file named `persons.json`.

> To accomplish this, you can use the JSON.stringify() method to convert the data to a JSON string.

As a bonus, you can make the program interactive by asking the user if they want to convert from CSV to JSON or JSON to CSV. You should also handle the case where the `persons.json` file does not exist using `fs.exists` or `fs.existsAsync` methods.

> Note: You may use either synchronous or asynchronous methods for reading and writing files, but it is recommended to use asynchronous methods to avoid blocking the main thread.
