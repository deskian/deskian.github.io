---
layout: post
title: Node file system
---

I recently start learning about the file system in Node.js and this post is to solidify my knowledge of the topic. The file system in Node can be access by requiring the node module 'fs'. From there, we have access to about 50 build-in functions such as read/write, exist and stat etc... For now we will only look at how a file can be read and write to files which are 2 funtion crucial for accessing data in a many situations.

To asynchronously read a file, we can do the following (taken from nodejs.org, file system documentation):

```javascript
fs.readFile('/etc/passwd.txt', (err, data) => {
  if (err) throw err;
  console.log(data);
});
```

The parameters for fs.readfile are file name, (optional encoding type, and a callback), in that order. It is important to note that the callback takes 2 parameters, err and data, in case there is a need for the program to act in a certain way when it cannot read the file. There is an optional encoding parameter following the file name, in this case since we do not specify what the encoding should be, node will return the raw buffer. The option should be a string that represent the encoding of the file we would like to read, for example: 'utf8'.

Similarly, we can write to file with fs.writeFile, which take in the parameter file name, data, (optional encoding type, and a callback). For example: 

```javascript
fs.writeFile('message.txt', 'Hello Node.js', (err) => {
  if (err) throw err;
  console.log('It\'s saved!');
});
```

So to sum it all up, the following code will write hello world! and read it back from the same file:

```javascript
fs.writeFile('helloworld.txt', 'Hello World!', function (err) {
  if (err) return console.log(err);
  console.log("Wrote to file!");
});

fs.readFile('helloworld.txt', (err, data) => {
  if (err) throw err;
  console.log(data);
});

//this will log "Hello World!"

```


