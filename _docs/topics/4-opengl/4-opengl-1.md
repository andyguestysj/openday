---
title: OpenGL
permalink: /docs/4-opengl-1/
---

### What is OpenGL?

OpenGL is an application programming interface (API). It is a low-level graphics rendering API that generates high-quality colour images composed of geometric and image primitives. It is designed to be independent of display device and operating system.  

The primary function of OpenGL is rendering - converting geometric/mathematical object descriptions into frame buffer values. OpenGL can render geometric primitives, bitmaps and images.

### Code Example

```c
void Display()
{
  glClear(GL_COLOR_BUFFER_BIT);
  glColor4f(1,1,0,1);
  glBegin(GL_POLYGON);   
    glVertex2f(-0.5, -0.5);
    glVertex2f(-0.5, 0.5);
    glVertex2f(0 5 0 5); 
    glVertex2f(0.5, -0.5);
  glEnd();
  glFlush();
}
```

### Specifying Geometric Primitives

Primitives are specified using - 

```c
glBegin(primType);   
  // define your primitives here 
  // by listing the vertices
glEnd();
```

#### Primitive Types

All geometric primitives are specified by vertices.  

![GL_PRIMITIVES](https://ysjged.netlify.app/assets/img/opengl/primitives.png)  

![glVertex](https://ysjged.netlify.app/assets/img/opengl/glvertex.png)  

![Shape Example](https://ysjged.netlify.app/assets/img/opengl/shapeexample.png)  

### Window System Independent

OpenGL is window system independent - no window management functions – create windows, resize windows, event handling, etc. This is to ensure the application’s portability. Create some headache though – just a pure OpenGL program won't work anywhere.  

More API's are needed.  
* X Window system : GLX
* Apple : AGL
* MS Windows : WGL

These libraries provide complete functionality to create Graphics User Interface (GUI) such as sliders buttons Graphics User Interface (GUI) such as sliders, buttons, menus etc.  

*Problem – you need to learn and implement them all to write a true portable software*

### GLUT (OpenGL Utility Toolkit)

For fast prototyping, we can use GLUT to interface with different window systems. GLUT is a window independent API – programs written using OpenGL and GLUT can be ported to X windows, MS windows, and Macintosh with no effort.  

GLUT does not contain all the bells and whistles though (no sliders, no dialog boxes, no menu bar, etc).  

### GLUT Basics

**Program Structure**
1. Configure and open window (GLUT)
2. Initialize OpenGL (Optional)
3. Register input callback functions (GLUT)
   * Render
   * Resize  
   * Input: keyboard, mouse, etc
4. Enter event processing loop (GLUT) 

### Sample Programme

![Sample Program - Display Mode](https://ysjged.netlify.app/assets/img/opengl/prog1.png)*Display Mode*  

![Sample Program - Create Window](https://ysjged.netlify.app/assets/img/opengl/prog2.png)*Create Window*  

![Sample Program - Initialisation](https://ysjged.netlify.app/assets/img/opengl/prog3.png)*Initialisation*  

![Sample Program - Register callback functions](https://ysjged.netlify.app/assets/img/opengl/prog4.png)*Register callback functions*

### Callback Functions

Most window-based programs are **event-driven** which means do nothing until an event happens, and then execute some pre-defined functions. **Events** - key press, mouse button press and release, window resize, etc.  

#### glutDisplayFunc(void (*func)(void))

![glutDisplayFunc](https://ysjged.netlify.app/assets/img/opengl/glutDisplayFunc.png)*glutDisplayFunc*  

#### Event Queue

![Event Queue](https://ysjged.netlify.app/assets/img/opengl/eventqueue.png)*Event Queue*  

* **glutKeyboardFunc()** - register the callback that will be called when a key is pressed
* **glutMotionFunc()** - register the callback that will be called when a mouse button is pressed
* **glutMotionFunc()** - register the callback that will be called when a mouse is in motion while a button is pressed
* **glutIdleFunc()** - register the callback that will be called when nothing is going on (no event)

#### glutMainLoop()

The function **glutMainLoop()** puts the program in to an infinite loop waiting for events.  
