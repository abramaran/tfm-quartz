Some months ago, I found a listing on wallapop for a broken projector: Broken, for repair or for pieces. An old Benq w1090 from 2016, which is considered by Reddit purists a budget projector, but at its 700€ selling point, not too shabby. I met the guy, bought it for 35€, and after some tinkering, got it running again!

The quality of image is quite nice, superior to the cheap Temu LCD projectors we were considering at first. But there is one feature in particular that intrigued me: it supports 3D projection.

There are several 3D technologies used in consumer-grade TVs and projectors. The Benq w1090 uses what it's called [[DLP-link glasses|DLP (Digital Light Processing)]], which projects the frames for each eye alternatively, and then uses special glasses to alternatively cover each eye, so that they see only the frames corresponding to their perspective. This creates the illusion of depth, while keeping full color unlike traditional red-blue glasses or other color filter approaches.

I was stoked when I got my 3d glasses in the mail and started playing with the technology. Nowadays it's mostly been abandoned, but ever since I was a kid I've been obsessed with 3D movies. It's practically a magic trick seeing objects and actors jump out of the screen.

Then, I thought of projection mapping, and started wondering if stereoscopic projection would work to alter the perceived shape of the projected surfaces. This effect is known as stereoscopic capture[^1].

## Experiments with TouchDesigner

Using TouchDesigner and KantanMapper I've made a series of tests exploring different effects using the DLP-link glasses:

First, I followed [Ian Shelanskey's tutorial ](https://ianshelanskey.com/2016/02/07/simple-stereoscopy-visuals-in-touchdesigner/)on setting up a dual camera rig for rendering stereoscopic visuals in TouchDesigner. The BenQ w1090 projector supports several formats of 3D video, but the simplest one I'm gonna be using in these tests is Top and Bottom mode. This means that the top half of the screen has the left eye's frame squished in half the vertical resolution, and the bottom half does the same for the right eye's frame. It is the projector's job to separate, stretch them over the full screen and project them alternatively to create the 3d effect. This is a very simple approach that has the downside of losing half the vertical resolution, but it is very easy to manipulate the image in TouchDesigner for it, and for quick tests it is more than enough.

I set up a simple rotating torus in 3D, and watched it with DLP-link glasses. Success! In most projection mapping setups, the audience is standing up and looking at the surfaces from different locations. Walking around and looking at the 3D projection showed a curious effect: the depth was best perceived when standing more or less at the same horizontal position as the projector. As you move sideways, the parallax effect of the projection seems to work pretty well, until you reach a point where the depth collapses like a pop-up book being flattened to the side.

The next step was using KantanMapper to map the 3D visual onto a physical object, in this case, a mannequin. Things started to get interesting: visuals that were projected to appear inside the object were much more effective than those made to float outside of the surface. This could be due to the irregular surface of the mannequin, or due to vergence-accommodation conflict (VAC). VAC is an uncomfortable effect caused when the eyes are focusing on the physical object, but they receive visual information that does not correspond to that focus depth. Textured objects with volume exacerbate this discomfort as the eye has an easier time identifying it and focusing on it compared to a flat screen. Visuals that are located at a similar distance to the real object's position tend to alleviate the VAC effect. [^2]

https://photos.app.goo.gl/X46LfEj5ohT6dgSv7

Other interesting effects that can be achieved include displaying invisible text that can only be seen in one lense. If each eye receives the negative version of the same image, without the glasses it can look as if the projected image was full white; only when wearing the glasses the message is revealed.

https://photos.app.goo.gl/LqB6yCmwTAZaogCX7

Completely different images can be displayed on each eye, and made only visible through its lens. Could this be extended to a bigger format, so that people can look through a window and see a different version of the piece?

https://photos.app.goo.gl/fbtWV8ZH7VANJP469

https://photos.app.goo.gl/J3VvJaGR9WNXtiYw6

## What now?

When looking at what worked well and what didn't, it becomes apparent that effects that modify the shape of the object only slightly lend themselves better to projection mapping. If we had a 3D scan of the projected on surface and tracked the position of the viewer using kinect, for example, I believe we could compensate for their location and adjust the 3D effect to adapt to the irregular surface.

But taking into account each viewer's position limits the number of spectators of the piece to one. This is already a limitation of the technology, since the best viewpoint is behind the projector, and each person needs a pair of active glasses (around 15€ the pair if you can find them cheap). Maybe something in the scale of a miniature that only a couple of guests can observe lends itself better to this technology than large-scale mappings for a large number of people.

Playing to the strengths of these tests would be making visuals where objects are trapped inside the shapes, where holes appear, or where ripples deform the surface.

[^1]: N. Okutani, T. Takezawa, D. Iwai and K. Sato, "Stereoscopic Capture in Projection Mapping," in IEEE Access, vol. 6, pp. 65894-65900, 2018, doi: 10.1109/ACCESS.2018.2875905.

[^2]: Fender, A., Herholz, P., Alexa, M. and Müller, J. (2018) OptiSpace: Automated placement of interactive 3D projection mapping content. _In_ Proceedings of the 2018 CHI Conference on Human Factors in Computing Systems, CHI ’18, Association for Computing Machinery, New York, NY, USA, Paper No. 269.
