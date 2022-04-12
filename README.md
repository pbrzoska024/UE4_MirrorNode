[![LinkedIn][linkedin-shield]][linkedin-url]



<!-- PROJECT LOGO -->
<p align="center">
 
<br />
<p align="center">
  <a href="https://github.com/pbrzoska024/FPS-MULTIPLAYER-PROJECT-WINDOWS64-32BIT-">
  </a>
  <img src="images/LOGO.jpg" alt="Logo" width="200" height="200">
  <h3 align="center">Animation Programmer </h3>

  <p align="center">
  Recruitment Task
   



<!-- TABLE OF CONTENTS -->
## Table of Contents

* [Goals](#Goals)
* [Requirements](#Requirements)
* [Design](#Design)
* [Roadmap](#roadmap)
 * [Built With](#built-with)
* [Roadmap](#roadmap)




<!-- Goals -->
## Goals

The main goal is to create a new Animation Graph node - one that would mirror the input pose across the XZ plane.

● By mirroring we mean that any transform that would be applied to a bone on the left
side of the skeleton should be flipped and applied to a corresponding bone on the
right. An animation showing a character moving their right hand should show them
moving their left hand instead.
 
 ![Zrzut ekranu 2022-04-12 125903](https://user-images.githubusercontent.com/53401206/162945852-cd1e6c0f-3fa6-4569-a58a-5420cda831a5.png)

● The task should be done in C++. New subclasses FAnimNode_Base and
UAnimGraphNode_Base should be created. These should be used in an Animation
Blueprint to demonstrate how the mirroring works.



<!-- Requirements -->
## Requirements

● The solution should be provided as an Unreal Engine project based on the
ThirdPerson_Cpp template, including C++ source code and an ABP graph showing
usage of the new Mirror node.
 
 ![image](https://user-images.githubusercontent.com/53401206/162946123-31122f4f-3c6c-4987-8e69-ff63e7e7f436.png)

● The mirror node should work with the default UE4 mannequin and skeleton, as well
as the animations supplied with the sample.

● No third-party plugins should be used.



### Design behind mirroring node task
 
 Mirror Animations
To mirror skeletal animations two types of bones should be considered. Twin bones, which have their representation in antother Axis ( _l, _r ) like hands, arms, legs, foots and facial bones. And the other ones ,which have no twin, like pelvis, spines, neck and head.

So to create a mirroring system, we have to define some meta data about the skeleton. The data is stored in Data_Asset class UData_MirrorTable.
It stores all twin bones and also the name of the pelvis bone.
 
 ![image](https://user-images.githubusercontent.com/53401206/162947739-fba3c5e7-fe35-439d-b57d-319ae1afddfd.png)
 ![image](https://user-images.githubusercontent.com/53401206/162947838-fe8cc448-996a-4d8d-82ad-83f37d08bc7b.png)

To mirror animations, I defined a custom animation node which can be used in unreal engine animation graph. It receives a pose in local space and mirrors it. It also has two input pins. One is for an animation mirror data object which should be initialized by the user and one is a boolean which let the node to be turned on or off. As you can see in the picture, there is no extra animation needed here and the node just accepts the current pose and mirrors it and you can turn it on or off based on the game or animation circumstances.












<!-- ACKNOWLEDGEMENTS -->
## Acknowledgements
* [GitHub Emoji Cheat Sheet](https://www.webpagefx.com/tools/emoji-cheat-sheet)
* [Img Shields](https://shields.io)
* [Choose an Open Source License](https://choosealicense.com)
* [GitHub Pages](https://pages.github.com)
* [Animate.css](https://daneden.github.io/animate.css)
* [Loaders.css](https://connoratherton.com/loaders)
* [Slick Carousel](https://kenwheeler.github.io/slick)
* [Smooth Scroll](https://github.com/cferdinandi/smooth-scroll)
* [Sticky Kit](http://leafo.net/sticky-kit)
* [JVectorMap](http://jvectormap.com)
* [Font Awesome](https://fontawesome.com)





<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/othneildrew/Best-README-Template.svg?style=flat-square
[contributors-url]: https://github.com/othneildrew/Best-README-Template/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/othneildrew/Best-README-Template.svg?style=flat-square
[forks-url]: https://github.com/othneildrew/Best-README-Template/network/members
[stars-shield]: https://img.shields.io/github/stars/othneildrew/Best-README-Template.svg?style=flat-square
[stars-url]: https://github.com/othneildrew/Best-README-Template/stargazers
[issues-shield]: https://img.shields.io/github/issues/othneildrew/Best-README-Template.svg?style=flat-square
[issues-url]: https://github.com/othneildrew/Best-README-Template/issues
[license-shield]: https://img.shields.io/github/license/othneildrew/Best-README-Template.svg?style=flat-square
[license-url]: https://github.com/othneildrew/Best-README-Template/blob/master/LICENSE.txt
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=flat-square&logo=linkedin&colorB=555
[linkedin-url]: https://linkedin.com/in/othneildrew
[product-screenshot]: images/screenshot.png
