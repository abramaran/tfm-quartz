> Analyse the practical aspects of your work. Why did you choose particular technologies, materials, or devices? What possibilities do they offer? What limitations do they introduce? How do they shape the form, experience, or outcomes of the project? The goal is to reflect on the technical and formal decisions that have structured the work.

Mostly answered in [[Investigating 3d projection]].

Some months ago, I found a listing on wallapop for a broken projector: Broken, for repair or for pieces. An old Benq w1090 from 2016, which is considered by Reddit purists a budget projector, but at its 700€ selling point, not too shabby. I met the guy, bought it for 35€, and after some tinkering, got it running again!

The quality of image is quite nice, superior to the cheap Temu LCD projectors we were considering at first. But there is one feature in particular that intrigued me: it supports 3D projection.

There are several 3D technologies used in consumer-grade TVs and projectors. The Benq w1090 uses what it's called [[DLP-link glasses|DLP (Digital Light Processing)]], which projects the frames for each eye alternatively, and then uses special glasses to alternatively cover each eye, so that they see only the frames corresponding to their perspective. This creates the illusion of depth, while keeping full color unlike traditional red-blue glasses or other color filter approaches.

I was stoked when I got my 3d glasses in the mail and started playing with the technology. Nowadays it's mostly been abandoned, but ever since I was a kid I've been obsessed with 3D movies. It's practically a magic trick seeing objects and actors jump out of the screen.

Then, I thought of projection mapping, and started wondering if stereoscopic projection would work to alter the perceived shape of the projected surfaces. This effect is known as stereoscopic capture[^1].

Using TouchDesigner and KantanMapper I've made a series of tests exploring different effects using the DLP-link glasses:

First, I followed [Ian Shelanskey's tutorial ](https://ianshelanskey.com/2016/02/07/simple-stereoscopy-visuals-in-touchdesigner/)on setting up a dual camera rig for rendering stereoscopic visuals in TouchDesigner. The BenQ w1090 projector supports several formats of 3D video, but the simplest one I'm gonna be using in these tests is Top and Bottom mode. This means that the top half of the screen has the left eye's frame squished in half the vertical resolution, and the bottom half does the same for the right eye's frame. It is the projector's job to separate, stretch them over the full screen and project them alternatively to create the 3d effect. This is a very simple approach that has the downside of losing half the vertical resolution, but it is very easy to manipulate the image in TouchDesigner for it, and for quick tests it is more than enough.

I set up a simple rotating torus in 3D, and watched it with DLP-link glasses. Success! In most projection mapping setups, the audience is standing up and looking at the surfaces from different locations. Walking around and looking at the 3D projection showed a curious effect: the depth was best perceived when standing more or less at the same horizontal position as the projector. As you move sideways, the parallax effect of the projection seems to work pretty well, until you reach a point where the depth collapses like a pop-up book being flattened to the side.

The next step was using KantanMapper to map the 3D visual onto a physical object, in this case, a mannequin. Things started to get interesting: visuals that were projected to appear inside the object were much more effective than those made to float outside of the surface. This could be due to the irregular surface of the mannequin, or due to vergence-accommodation conflict (VAC). VAC is an uncomfortable effect caused when the eyes are focusing on the physical object, but they receive visual information that does not correspond to that focus depth. Textured objects with volume exacerbate this discomfort as the eye has an easier time identifying it and focusing on it compared to a flat screen. Visuals that are located at a similar distance to the real object's position tend to alleviate the VAC effect. [^2]

https://photos.app.goo.gl/X46LfEj5ohT6dgSv7

Other interesting effects that can be achieved include displaying invisible text that can only be seen in one lense. If each eye receives the negative version of the same image, without the glasses it can look as if the projected image was full white; only when wearing the glasses the message is revealed.

https://photos.app.goo.gl/LqB6yCmwTAZaogCX7

[^1]: N. Okutani, T. Takezawa, D. Iwai and K. Sato, "Stereoscopic Capture in Projection Mapping," in IEEE Access, vol. 6, pp. 65894-65900, 2018, doi: 10.1109/ACCESS.2018.2875905.

[^2]: Fender, A., Herholz, P., Alexa, M. and Müller, J. (2018) OptiSpace: Automated placement of interactive 3D projection mapping content. _In_ Proceedings of the 2018 CHI Conference on Human Factors in Computing Systems, CHI ’18, Association for Computing Machinery, New York, NY, USA, Paper No. 269.
