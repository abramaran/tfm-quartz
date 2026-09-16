*Part of the summer assignment for Research. [[Post 1. Technologies, Materials, and Formal Decisions]] [[Post 2. Implications and Consequences]] [[Post 3. Relational Network]]* 

I've been researching 3d projection, thanks to a broken projector I found in Wallapop and fixed. This projector uses DLP-Link glasses. 

Right now, I've watched 3d movies and modded a ps2 emulator to play games in 3d.  

I've done a first 3d test with TouchDesigner, using two cameras to render a scene. There's some things I need to investigate further:
- [ ] With my setup, the camera rig is position 0 and the object is located inside the scene (10 units). In the PS2 emulator there are settings of convergence and separation that affect which plane in the scene corresponds to the real-world projection screen, with objects popping out of the wall if they are closer than that. I want to create that effect.
- [ ] I need to try doing a [[Projection mapping]] with TouchDesigner.
- [ ] I want to combine 3d projection and projection mapping.
- [ ] Should I try red-blue 3d at the immersive room?? Could be cool as hell

## Combining 3d and projection mapping

My hypothetical is that combining both techniques I can achieve some really cool effects that look like magic. Some of my current questions are:

- How do fake 3d and real-world volumes look together?
	- [ ] Make a test with some simple shapes. Parallelograms should be easier to start with.
- Do I need to compensate the 3d effect for the real-world deformation of the surfaces?
	- Maybe if x