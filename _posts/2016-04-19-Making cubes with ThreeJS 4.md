---
layout: post
title: Building 3D cubes with ThreeJS (4/5)
---

Last time, we ended with a rotating cube. But then the cube is uniform in color, it was very hard to see where the edges are.

Today, we have 2 choices, either we add some lighting to show the different faces, or we change the color of the different faces. Let's do both!

First to add lighting, we first have to change the material of the cube so it is receptive of the lighting: 

```javascript
  var cubeMaterial = new THREE.MeshBasicMaterial({color: 0x4f46f5});

to

  var cubeMaterial = new THREE.MeshLambertMaterial({color: 0x4f46f5});

```

Then we add lighting:

```javascript

  directionalLight = new THREE.DirectionalLight(0xffffff);
  directionalLight.position.set(1,1,1).normalize();
  scene.add( directionalLight );

```

It is important to note that this light shine from the top right, and diagonally downward. But that aside, below is the new cube:

![Alt text](http://i.imgur.com/Hx8IoFe.gif)

Now, let's try something new, we will change each face of the cube to a different color, to make it even more defined, we will replace the cubeMaterial with this:

```javascript

  var cubeMaterial = new THREE.MeshBasicMaterial({ vertexColors: THREE.FaceColors });
  for (var i = 0; i < cubeShape.faces.length; i+=2){
    var temp = Math.random() * 0xffffff
    cubeShape.faces[ i ].color.setHex( temp );
    cubeShape.faces[ i + 1 ].color.setHex( temp );
  }


```

Note that the mesh define each face as 2 triangle, instead of a square. Thus we need to do both triangles as the same color, otherwise it looks a little strange.

![Alt text](http://i.imgur.com/bnVo3qw.gif)

Next, we will expand and build a couple more cubes, maybe test the limit of this rendering engine. Stay tune!
