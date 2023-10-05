Todays lab contains of two parts. First in colab and second in MuJoCo simulator.


# Colab

https://colab.research.google.com/drive/13rRYLl8PN5FEXEpx5aZsUQW6Eohve3xK

# MuJoCo

A lot of robotics happens not in reality but in simmulators. 
Let's try it.

1. Clone this repo (it contains `world1.xml` and `4x4_1000-0.png` files)
1. Install MuJoCo (just exe, no python bindings).
   - GitHub repo is available at: https://github.com/google-deepmind/mujoco
   - Current release https://github.com/google-deepmind/mujoco/releases/tag/2.3.7
2. Run MuJoCo simulator (you should see something like this): 
![](mujoco_1.png)
3. Drag and drop world from file `world1.xml` to simmulator (look below for description) `4x4_1000-0.png` is needed in the directory next to `world1.xml`
![](mujoco_2.png)
4. Get familiar with moving the view, zooming, etc.
5. Take a screenshot and find an aruco code on the screeenshot using OpenCV
6. Add another aruco code to the world.
   - you need to make your own aruco code (https://chev.me/arucogen/)
   - you need to convert SVG to PNG (ImageMagic does not work), do it otherwise
   - you need to adjust the XML file
7. Find both aruco codes using opencv, draw their bounding boxes
8. Change some of the boxes to other shapes, eg. cylinders or spheres


## Description


Reference manual of MuJoCo XML can be found at:

https://mujoco.readthedocs.io/en/stable/XMLreference.html

world1.xml - describes the world that we use. In this lab we will only use static objects, but in general we can also use dynamic objects that can move. So, some objects float in the air, but we don't care.

In an XML file we use following tags:

- `asset` - section containings assets, eg. material definitions, textures, etc.
- `texture` - either built in or external texture. Note this is not always 2D bitmap, because objects textured can ahve different shapes
- `material` - description of material
- `worldbody` - the whole world
- `body` - different objects, note our objects don't move! it will change
- `geom` - shapes, we use only boxes

You should get familiar with the XML file, because you will need to modify it. Also next lectures will use more and more complex XML files.