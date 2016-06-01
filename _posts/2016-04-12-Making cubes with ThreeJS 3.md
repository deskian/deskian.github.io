---
layout: post
title: Building 3D cubes with ThreeJS (3/6)
---

So last time, we ended with a square on the screen, and it looks 2D! Not the most exciting cube I would say. But fear not! We will prove that it is a cube right now.

Let start by making it rotate a little bit. We will start by defining an animate function

```javascript 

function animate() {
  requestAnimationFrame( animate );
  cube.rotation.x += .02;
  cube.rotation.y += .02;
  renderer.render(scene,camera);
}
animate();

```

A few notes: 
  requestAnimationFrame will set the animate function to fire at about 60 times a seconds, which is about as fast as most browser will render it to create a continuous feel to the animation.

  cube.rotation.x and cube.rotation.y change the orientation of the cube by a set amount every time the animate function is called. 

  Finally, each frame is re-render so we can see the new update state of the cube.

And.... Whoohoo! Animated cube!

![Alt text](http://i.imgur.com/0rJdqb5.gif)