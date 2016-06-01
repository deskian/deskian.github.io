---
layout: post
title: Building 3D cubes with ThreeJS (1/6)
---

ThreeJS is a lightweight library that aim to create 3D object with very low level complexity. The library will help define the scene, the lighting as well as render the object itself according to those factor. I will try to implement some simple shape (cubes in particular) with this library.

In order to get a shape to show up, we must first set up a basic HTML and include the link to the ThreeJS library, as well as the script file we will be working on, like so

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>ThreeJS</title>
  <link rel="stylesheet" href="stylesheet.css">
</head>
<body>
  <script src="three.min.js"></script>
  <script src="shape.js"></script>
</body>
</html>
```
This will only create a blank HTML, which is where we will start.

```javascript
function init() {
}
init()
```
First we declare a function init to initialize all of our data and immidiately call the function.
Inside the function:

```javascript
  var scene = new THREE.Scene();
```
The above code will build a canvas area so that we can draw into.

```javascript
  var camera = new THREE.PerspectiveCamera(60, window.innerWidth / window.innerHeight, 10, 5000)
  camera.position.set(0,0,50);
  scene.add(camera);  
```
After we have a scene, we want to set a camera location, this camera is placed 50 unit off from the origin in the z-axis.

```javascript
  var renderer = new THREE.WebGLRenderer();
  renderer.setSize(window.innerWidth, window.innerHeight);
  document.body.appendChild(renderer.domElement);  
```
This renderer is something that required by THREE.js. It is primarily for adding the drawable area for us to construct the 3d object.

Whew! that is a mouthful. More on this in the next blog

