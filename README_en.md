# Maze Generation_10_vichy_f
English README 

Japanese readme is here 
[README_JAPANESE](README_jp.md)

This API is designed to automatically generate mazes on mincraft.
You can run Maze_Generation.py to automatically generate mazes on mincraft. 
This API uses minecraft_remote by Naohiro2g.

　Naohiro2g https://github.com/Naohiro2g

　mincraft_remote https://github.com/Naohiro2g/minecraft_remote

<img width="435" alt="スクリーンショット 2024-03-02 204348" src="https://github.com/vichyalpha/Maze-Generation_vichy_f/assets/107329825/bcd89e79-4446-4b0d-82d8-9856f8ac544a">

1. Install Forge 1.16.5
https://files.minecraftforge.net/net/minecraftforge/forge/index_1.16.5.html


![ダウンロード (3)](https://github.com/vichyalpha/Maze-Generation_vichy_f/assets/107329825/e2e9de27-5113-4a02-807b-1e4da3dc1f91)

2. Install RemoteControllerMod-1.16.5 v0.05 
https://www.curseforge.com/minecraft/mc-mods/remote-controller/files/3363255

 ![ダウンロード (4)](https://github.com/vichyalpha/Maze-Generation_vichy_f/assets/107329825/65c0c363-52e1-41f4-9b71-cf71aded1235)

3. Start mincraft(forge1.16.5)
![NetherUpdateArtwork](https://github.com/vichyalpha/Maze-Generation_vichy_f/assets/107329825/28acd239-7094-43ac-8a8f-f79a9329ea85)

4. Run Maze_Generation.py to generate mazes
 ![Python-logo-notext svg](https://github.com/vichyalpha/Maze-Generation_vichy_f/assets/107329825/6faba07d-4457-4a2a-ab54-637c498e06e0)

====> Done!

# Maze Details
　This maze is made of 40x40 size. (The size can be changed.) 
 You can also change the type of blocks on the floor and walls of the maze. 
 （You can also change the type of blocks on the floor and walls of the maze (standard is diamond blocks and iron blocks). 　
 Note: The standard maze is generated around (0,5,0). It is recommended to use super flat. 　
 <img width="435" alt="スクリーンショット 2024-03-02 204348" src="https://github.com/vichyalpha/Maze-Generation_vichy_f/assets/107329825/f98274d1-e257-47a2-bf9b-6c349bfa00e3">

# Maze Algorithm
　This API uses what is commonly referred to as the "stick-fall method". 　Here is a brief description.  ![maze-stick03-300x300](https://github.com/vichyalpha/Maze-Generation_vichy_f/assets/107329825/d47df9f0-dc6f-4517-b529-809ce2d67134)

# Characteristics of the stick-fell method
The stick-and-stick method is a relatively easy maze creation method to program. Also, the distance between walls and paths is 1.

# Creation Procedure
Generate a 2-dimensional array of 5 or more odd numbers in width and height to make up the entire maze.

The outer perimeter of the maze is used as walls, and the rest of the maze is used as paths.

Place a reference wall (bar) inside the outer perimeter every other cell (even coordinates for x and y).

Scan the inner wall (bar) and place it in a random direction (except in the following directions). (However, it should be knocked down in a direction other than the following.)

Do not topple in the upward direction except for the inner wall of the first row.

If a bar has already been knocked down and is a wall, it must not be knocked down in that direction.

# Drawbacks
Mazes created by the stick-fall method always have two upper passages leading to the left and right ends of the maze.

This is due to the restriction that only the wall of the first level can be knocked over.

The inability to topple over also makes it impossible to go backwards and forwards.

Also, there are many short dead-end corridors.

# Usage
This API is best suited for testing the artificial intelligence of mincraft mobs and for player play.

# development environment

python 3.11.6
 https://www.python.org/downloads/release/python-3116/
 
forge 1.16.5
 https://files.minecraftforge.net/net/minecraftforge/forge/index_1.16.5.html

RemoteControllerMod 1.16.5 v0.05
 https://www.curseforge.com/minecraft/mc-mods/remote-controller/files/3363255
