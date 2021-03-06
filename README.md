# cse389-graphics
***
**Wed 1/24/2018:**  
  OpenGL is working and can open sample `main.cpp`(window) without apparent issues using `g++` compiler.
  
  To install required libraries:
  ```
  sudo apt-get install mesa-utils mesa-common-dev libgl1-mesa-dev libgl-dev libglfw3-dev lib-glfw3 libglm-dev libglew-dev
  ```
  
  To compile using `g++`:
  ```
  g++ main.cpp -lglfw -lGLEW -lGL
  ```

***

  **Wed 2/1/2018:**  
  ~~Follow instructions [here](https://www.cs.nmt.edu/~amyk/Graphics/Environment/) for Glitter.~~  
  To fix the ```glad/glad.h``` not found error go to <http://glad.dav1d.de/> use the following settings  
  * Language: C/C++
  * Specification: OpenGL
  * API: 4.5 (or whichever you need)
  * Profile: Core
  
  Hit generate and download the glad.zip file, insert the glad and KHR folders to your ```/usr/include/``` directory, and the glad.c file inside the ```src``` folder into your project. In the linker add library ```dl```.  
  To compile using g++:  
  ```
  g++ main.cpp glad.c -lglfw -ldl
  ```
  
  Install ```libassimp-dev, libbullet-dev``` we might need them for later.

  
  ***
  
  ## Weekly Scrotum 2018/2/2  
  
  ![alt text][triangle]
  
  ![alt text][triangle_wire]
  
  [triangle]: https://github.com/bmoral/cse389-graphics/blob/master/misc/triangle-2118.png
  [triangle_wire]: https://github.com/bmoral/cse389-graphics/blob/master/misc/triangle_wire-2118.png
  
  #### Museum Plan
###### 1. What is the theme of your museum?
> The theme that we chose is a roman theme based around the time frame of the beginning (1430s) to the zenith (1520s) of the renaissance.
###### 2. How many rooms will your museum have?
> Our museum should have between 3 and 4 rooms. The main room is planned to be a sort of Y shape. 
###### 3. Have you started looking for textures for your museum walls/floors? If so, what are your plans?
> We have found some textures online that will allow us to give the walls and floors a marble style to try to fit with the theme. 
  We plan to use a marble tiling for the flooring, and to distribute pillars and arches throughout the area, to make it feel more like a roman style museum.
###### 4. Will your museum have a ceiling? 
> Yes, the museum  will have a ceiling and we intend to make it more dome shaped, to try to make the building feel like it was designed to fit with the same era that our theme originates.
###### 5. You must have at least ONE “sculpture” in your museum.  What are you planning to use for your sculpture(s)?  NOTE: You DO NOT have to create your own blender model/sculpture, you are free to search the internet for a pre-made model. It is more important, for me, that you understand how these models are represented in the computer, and how they are manipulated in 3D space.
> We are going to use a 3D blender model that I (Franz) found on blendswap.org. It has a CC of zero, meaning we would not need to reference the creator if we use the model. The model we chose is the statue of David.
    
###### 6. You must have at least FOUR “paintings” in your museum.  What were you planning to use for your pictures? Have you already started looking for textures that can be applied as “pictures”? Will your pictures be hung on the wall? Will they be murals?  Do you have a completely different idea of how these paintings will be added to your museum?
> We have not decided on the paintings that we plan to use. There are several paintings that can be easily textured to a simple painting frame model, however we would like to look into some more unconventional methods of displaying them. The pictures will most likely be hung on the wall inside a framed model, however, we may have a painting on the ceiling, depending on how complex it will be to texture it to a dome shape without it looking strange. 

## Weekly Scrotum 2018/2/14
> Link to .blend file [museum.blend](https://github.com/bmoral/cse389-graphics/blob/master/misc/models/museum.blend)

## Weekly Scrotum 2018/3/7
> Had issues making out program render and display obj information on to the screen.
We tried recycling code from when we loaded our first triangle, and everything seemed to be correct, but it wouldn't display, from our debugging efforts we were able to determine that the obj file was loaded correctly and the VAO was also bound correctly. After many code rearrangements and rewrites, nothing would display, but as it turns out, the problem appears to had been our shader program. From what I could gather the shader program we used wasn't correctly setup for 3-D space objects. Still to do: code clean up, enable multiple objects to be loaded with user input. **Update** Attempted code clean up, and tried implementing to allow loading of two models, but only one is drawn.

## Weekly Scrotum 2018/3/14
> Due to working on compiler projects, not much work has been made that was commited. Brainstormed ideas for pictures and worked on model improvements. 

## Weekly Scrotum 2018/3/28
> Decided to do research on new developments in the project. Header files have not been implemented that were given to us. Currently Compiler work has been causing a lot of our free time to be taken. Will be making progress soon. 

## Weekly Scrotum 2018/4/4
> Worked on increasing the quality of the models that we are using. Added more high resolution development for the museum model. Compilers is lightening up a bit and we should be able to work on the project more productively. 

## Weekly Scrotum 2018/4/11
> Realized that we have not been updating the README like we should have been. Updated the readme progress. Worked on implementation of the files that were given to us two weeks ago. Compilers has been fairly busy. We will be working to catch up and finish implementation of these three things:
> * Model importation (currently works, but not with new header files)
> * Texturing of Models
> * Camera movement such as looking and walking.  
 
> We plan to be caught back up by next week. We will be working through the weekend in order to be sure that we are caught up to the progress that we need to have by next week.

## Weekly Scrotum 2018/4/18
> Completed the design of the museum in blender.
 # Note: assimp has to be linked into the linker on ide along with libraries previously mentioned here.

## Weekly Scrotum 2018/4/25
 > After trying to rework the code to catch up and make it cleaner, and more capable we boke it, and has been broken for about 2.5 weeks now. What is currently happening is that we can open a green window, but it won't load objects, can't draw objects(obviusly), and there's a nasty screen flickering that happens while trying to render. Besides all those things not working, there have been some improvements to the previous code base such as
> 	* New window creation class that should allow for modularity and icons 
>	* addition of new model and mesh header files that will theoretically allow better model loading capabilities, and texture loading. 
>	* addition of camera class that should allow for movement within the world. 
>	* addition of more robust shader capabilities. 
> So far things that appear to be working are the shader seems to compile and link correctly, texture loading(after days of trying to figure out shy it didn't appear to load anything to memory), and the model loader appears to load something to memeory. 
### (update)2018/4/19 
> No matter what we did, the flickering wouldn't go away, and model loading appeared to stopped loading to memory as a side effect. Since we still had access to our old not broken but not so cool model loader (Object.h), we decided to use it to try and load the models in, after some finkicking around, we managed to load a model using the new code base, however we still had flickering issues and that model loader doesn't have texture support. 
### (update)2018/4/28 
> Have been wokring of debugging the flickering issue for the past few days, and it just wouldn't go away. Today I decided to slow down and take a cloesr look at our old working version, and our new not working version, which are practically the same minus some oop cunctruction. Started out by moving the gladloader function from our start method into our window creation method. I don't think that is where it belongs, but it's worth a shot, and nothing. Following some advice went to check the inlcuded libraries, which were all in single "includes.h" as to only use them once, but that ended up backfiring pretty early on requiring us to include the includes.h in every class making it so that most libraries were included more than once, so I tried to fix that by only calling the needed libraries where required. This still didn't make the flickering go away, but it did change something in the window making it look like a crt screen. At this point the only difference between and a working version was that glClearColor() was outside the render loop, after I moved it back inside, everything worked like a charm. Now it was a matter of adding input processors, and modifying the window class a bit for easier value extraction of values for movement logic.  

# README - run instructions
> Release folder contains executable cse389... Run this file to execute the program. Use make to compile for linux box.  
> misc folder contains our resource files (models, obj files, textures, etc.)
> ### note that textures are hard coded with absolute paths, this means the program may return errors if the paths are not changed within the .mtl files.
> While program is running, w, a, s, d for movement, mouse moves the camera around, and use scroll wheel for zoom. F11 toggles between fullscreen and windowed mode.
