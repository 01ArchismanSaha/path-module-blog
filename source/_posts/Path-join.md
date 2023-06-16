---
title: Path.join & Path.resolve
date: 2023-06-16 15:36:52
tags:
---
<h2>Path.join([...paths])</h2>

The 'path' is a built-in module avaiable in NodeJs which provides various ulities for working with file and directory paths. The 'path.join()' method is used to join multiple path segments (strings) into a single one.
The path segmensts are specified using coma separated values.

<b>Syntax</b>: path.join( segment1, segment2, ...);

<h3>Example:</h3> 

const path = require('path');

const fileName = 'myFile.txt';

const joinedPath = path.join(__dirname, 'newDirct', fileName);

console.log(joinedPath);    

<h3>Output:</h3>
/Users/archismansaha/newDirct/myFile.txt

Observe how all the segments got joined in the output. '__dirname' will print the absolute path to your current directory.

<h2>Path.resolve([...paths])</h2>

The 'path.resolve()' method resolves an absolute path from the given path segments. The path segments are joined from right to left until an absolute path is constructed. If an absolute path has not yet been generated after all the path segments has been prepended, the current working directory is used.

<b>Syntax</b>: path.resolve( segment1, segment2, ...);

<h3>Example:</h3> 

const path = require('path');

const fileName = 'myFile.txt';

const joinedPath = path.resolve('newDirct', fileName);

console.log(joinedPath);  

<h3>Output:</h3>
/Users/archismansaha/newDirct/myFile.txt

Observe that we are not passing the '__dirname' as the first parameter to 'path.resolve()' but we are still getting the same result as in the previous example of 'path.join()'. This is because after resolving the provided path segments, we don't get the absolute path, so the absolute path to the current working directory gets prepended to complete it.