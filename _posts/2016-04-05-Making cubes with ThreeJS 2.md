---
layout: post
title: Building 3D cubes with ThreeJS
---

And we are back!

To recap, we ended last time with this code to set up a scene, a camera and a renderer:

```javascript
  var scene = new THREE.Scene();

  var camera = new THREE.PerspectiveCamera(60, window.innerWidth / window.innerHeight, 10, 5000)
  camera.position.set(0,0,50);
  scene.add(camera);

  var renderer = new THREE.WebGLRenderer();
  renderer.setSize(window.innerWidth, window.innerHeight);
  document.body.appendChild(renderer.domElement); 
```

If we were to open the HTML, we end up with a black screen, which is fine for now, we have not try to render any object yet.

But in case we do want to render something, let start with a cube. In order to add a cube, we need to define one:

```javascript
  var cubeShape = new THREE.BoxGeometry(20,20,20); 
  var cubeMaterial = new THREE.MeshBasicMaterial({color: 0x4f46f5});
  var cube = new THREE.Mesh( cubeShape, cubeMaterial );
  scene.add( cube );
```

The first line (cubeShape) allow us to defined what kind of shape we want, also the size (x,y,z dimension in this case)
The cubeMaterial allow us to define the color. 
after that, we have to actually build a mesh (mesh is simple 3D object made by connecting dots in 3D space) we define a new cube using the Three.mesh with cubeShape and cubeMaterial passing in.
Lastly, we need to tell the renderer that we want this cube in the scene. This is the result:

![Alt text](http://i.imgur.com/Qdr4MGS.png)

More on this later...
