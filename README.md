<!-- Improved compatibility of back to top link: See: https://github.com/othneildrew/Best-README-Template/pull/73 -->
<a id="readme-top"></a>

<!-- PROJECT SHIELDS -->
<!--
*** I'm using markdown "reference style" links for readability.
*** Reference links are enclosed in brackets [ ] instead of parentheses ( ).
*** See the bottom of this document for the declaration of the reference variables
*** for contributors-url, forks-url, etc. This is an optional, concise syntax you may use.
*** https://www.markdownguide.org/basic-syntax/#reference-style-links
-->




<!-- PROJECT LOGO -->
<br />
<div align="center">
  </a>

  <h3 align="center">Destructive Interference: Encoding Loss in the Overlap</h3>

  <p align="center">
    An exploration of how structured overlap can encode national trauma, using data from mass shootings in 2024 as the starting point.
    <br />
    <br />
    <a href="https://nikaberle.carbonmade.com">Nik Aberle</a>
    &middot;
    <a href="https://sites.google.com/view/viza626/home">VIZA 626</a>
  </p>
</div>

[![Assignment_02][images-fig1]](https://github.com/Naaberle/Assignment_02/blob/main/images/fig1.png?) <br />
Figure 1. My parametric algorithm in Grasshopper used to create two radial disks (left), the surfaces in red and baked geometries in white in Rhino (center), and the final 3D printed disks. 

<!-- Abstract -->
## Abstract
Destructive Interference is a data visualization installation that visualizes the deaths and injuries caused by mass shootings in 2024 in the United States. I parametrically designed and fabricated an interlocking ring sculpture for each month of 2024; where the overall height corresponds to the level of violence in that month. Taller forms mark the deadliest months, while shorter ones reflect fewer casualties. Each inner ring encodes the number of people killed or injured, and each outer ring encodes the number of shootings and the number of days without them. The interlocking cylinders are powered via a motor to rotate, and lit from within. As the cylinders rotate, they cast overlapping shadows that represent those killed or injured by mass shootings. The goal of this work is to visualize otherwise overwhelming and disparate statistics in a way that is both physically present and emotionally resonant. By inviting viewers to step into and engage with these shadows, the piece creates space for reflection, conversation, and confrontation with the scale of this ongoing crisis.

<!-- Introduction and Related Works -->
## Introduction and Related Works
In a previous project (link to Assignment 2) I developed a parametrically designed Moire pattern generator in Grasshopper. I wanted to take that process and expand upon it, specifically in the direction of application to physical sculpture. Big data has been integrated into contemporary sculpture in a variety of ways and methods [1] and this process opens up a new avenue for me to work within, using data as its own medium.

I chose to create a data visualization sculpture that falls into the category of symbolic representation [4] according to the writings of Andrew Vande Moore & Stephanie Patel who’s paper on the categorization of physical visualization of information guided my design choices. Symbolic representation is defined by them “to be works characterized by a form-finding approach that employs a so-called arbitrary data-mapping approach”.

I chose this method as I wanted to visually disentangle the topic of mass shootings with the work. I wanted people to engage with the work before being presented with the data linked to the creation so they were less likely to disengage as soon as they realized what the subject matter was.

Similar to how I created my previous Moire disks, I designed this project in Grasshopper to be baked in Rhino after the final formulation of each month's data. One challenge of this was going to be making the design as minimal as possible as to not draw attention away from the aforementioned meaning. My goal was to create a print in place upper piece that didn’t require any after assembly, but still allowed for rotation and came across those that had been 3D printing with interlocking parts [3]. 

According to the Gun Violence Archive, an online archive of gun violence incidents collected from over 7,500  law enforcement, media, government and commercial sources daily [2], there were 586 mass shootings in 2024; resulting in a total death count of 711 individuals. 

<!-- Methodology -->
## Methodology 
As a first step, I collected and organized mass shooting data for the 2024 calendar year from the Gun Violence Archive [2], accessed originally through Wikipedia [5]. This included the number of shootings, total injuries and deaths, and the number of days without a mass shooting for each month.

Insert Screenshot of Graph Data

I used this data as the main inputs to a parametric model in Grasshopper. Each of the twelve sculptures was generated from the same base algorithmic design: a set of two cylinders interlocked at the base, but still allowing for rotation. I wanted to encode the data from the 2024 shootings into specific parameters that would carry throughout each sculpture. 

The heights of the sculptures are reflective of the total number of deaths in each month, normalized between 8” for the highest death count and 3” for the lowest death count. Both inner and outer rings have a number of straight vertical pillars and pillars that rotate around the cylindrical shape based on a rotational value. 

The number of vertical pillars on each inner ring corresponds to the ratio of deaths in that month to total deaths in 2024, and the rotational value of the twisted spokes is total wounded for that month compared to total wounded and normalized to a rotational value of 180. The number of vertical pillars on each outer ring corresponds to the ratio of shootings in that month to total shootings in 2024, and the rotational value of the twisted spokes is the number of days without a shooting in that month and normalized to a rotational value of -180. The inner ring rotation being 0 - 180 and the outer ring rotation being -180 - 0 was an intentional design choice to amplify the shapes of the shadows.

I deliberately avoided using overt graphing or labeling, as the intent was to present the data in a form that emphasized presence over explanation, in line with the symbolic representation definition. After the final geometry for each month was generated it was baked in Rhino and 3D printed.

The last step was to create a base design that allowed me to mount a battery pack and 6v 5rpm turntable motor in it to mount each upper part to. The outer ring mounts to the base with 8 alignment pins and ensures the inner ring can rotate freely when the motor is powered. A 3” LED puck is then placed in the center and the sculpture is ready to be installed along the other 11.

When all 12 are placed in proximity to one another, walking between them and engaging with the shadows places you amidst all of the loss due to mass shootings in 2024. 

<!-- Results and Future Work -->
## Results and Future Work
The twelve individual sculptures for each month have been fully designed, fabricated, and tested individually. While the full installation has not yet been fully installed in a final venue, I’ve tested six of the units running simultaneously, and the results align closely with my vision and goals. The slow, overlapping motion and cast shadows work as intended, creating a layered and immersive experience that invites engagement.

The 3D interlocking rings function mostly as intended, though there is the occasional snag or slowdown of the motor. More investigation on the cause of this will be needed in the future. Additionally, I may need to look at using four AA batteries instead of two as any sort of load on the motor seems to cause it to stall. I plan to also look into the possibility of using Lithium-ion polymer batteries in the future, as they last longer and would be easier to recharge for prolonged displays of the work. Once a full installation space is available, I plan to finalize the layout to best encourage viewer movement and interaction.

For future projects I’d like to explore responsive elements tied to real-time or streamed data, as well as other methods of converting large bodies of data around socially charged topics into symbolic representations for easier engagement. This project has laid the groundwork for future installations that invite sustained, embodied reflection on topics that are often too vast or diffuse to confront directly.

<!-- Conclusion -->
## Conclusion
This project was something I’ve wanted to do for a long time, taking concrete data and using it to inform the message and form of an installation. In this case it has the added benefit of being something emotionally charged and allows for viewers to hold space for both reflection and discomfort. The two most memorable moments were when my print in place interlocking rings functioned as intended and I just had to dial in the tolerances. Second was when the first full sculpture (January) was assembled, powered, and ran as intended; casting an amazing cascade of shadows on my studio walls.

Through this process I learned how to use data to inform the parameters of a sculpture in a meaningful way, as well as how viewers can interact with it once created. My hope is that this work will encourage deeper reflection on statistics that are often overlooked or diminished; and in this specific case to bring more awareness to the toll mass shootings take on the American populace.

<!-- Bibliography -->
## Bibliography 
[1] Chowwalit Chookhampaeng, Jiraporn Chano2c, and Hongfei Zhang. 2024. Big Data Integration in Sculpture: A Systematic Review. In Proceedings of the 2024 5th International Conference on Big Data and Social Sciences (ICBDSS 2024). Springer Nature, 434.

[2] Gun Violence Archive. 2024. Gun Violence Archive GVA. United States. Web Archive. Retrieved from the Library of Congress: https://www.loc.gov/item/lcwaN0016293/

[3] Peng Song, Zhongqi Fu, Ligang Liu, and Chi-Wing Fu. 2015. Printing 3D objects with interlocking parts. Computer Aided Geometric Design 35 (2015), 137–148.

[4] Andrew Vande Moere and Stephanie Patel. 2010. The physical visualization of information: Designing data sculptures in an educational context. In Visual information communication. Springer, 1–23.

[5] Wikipedia contributors. 2024. 2024 US mass shooting statistics by month. In Wikipedia: The Free Encyclopedia. Retrieved April 22, 2025 from https://en.wikipedia.org/wiki/Gun_violence_in_the_United_States#Mass_shooting_statistics

<!-- CONTACT -->
## Contact
Your Name - nik.aberle@tamu.edu

Personal Website: https://nikaberle.carbonmade.com


<!-- ACKNOWLEDGMENTS -->
## Acknowledgments

This work is submitted as part of Assignment 2 for the VIZA 626 course at Texas A&M University, under the instruction of Professor You-Jin Kim, during the Spring 2025 semester.

VIZA 626 Class Website: [https://sites.google.com/view/viza626/](https://sites.google.com/view/viza626/home)

<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/othneildrew/Best-README-Template.svg?style=for-the-badge
[contributors-url]: https://github.com/othneildrew/Best-README-Template/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/othneildrew/Best-README-Template.svg?style=for-the-badge
[forks-url]: https://github.com/othneildrew/Best-README-Template/network/members
[stars-shield]: https://img.shields.io/github/stars/othneildrew/Best-README-Template.svg?style=for-the-badge
[stars-url]: https://github.com/othneildrew/Best-README-Template/stargazers
[issues-shield]: https://img.shields.io/github/issues/othneildrew/Best-README-Template.svg?style=for-the-badge
[issues-url]: https://github.com/othneildrew/Best-README-Template/issues
[license-shield]: https://img.shields.io/github/license/othneildrew/Best-README-Template.svg?style=for-the-badge
[license-url]: https://github.com/othneildrew/Best-README-Template/blob/master/LICENSE.txt
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://linkedin.com/in/othneildrew
[product-screenshot]: images/screenshot.png
[images-fig1]: images/fig1.png
[images-fig2]: images/fig2.png
[images-fig3]: images/fig3.png
[images-fig4]: images/fig4.png
[images-fig5]: images/fig5.png
[images-fig6]: images/fig6.png
[images-fig7a]: images/fig7a.png
[images-fig7b]: images/fig7b.png
[images-fig8]: images/fig8.png
[Next.js]: https://img.shields.io/badge/next.js-000000?style=for-the-badge&logo=nextdotjs&logoColor=white
[Next-url]: https://nextjs.org/
[React.js]: https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB
[React-url]: https://reactjs.org/
[Vue.js]: https://img.shields.io/badge/Vue.js-35495E?style=for-the-badge&logo=vuedotjs&logoColor=4FC08D
[Vue-url]: https://vuejs.org/
[Angular.io]: https://img.shields.io/badge/Angular-DD0031?style=for-the-badge&logo=angular&logoColor=white
[Angular-url]: https://angular.io/
[Svelte.dev]: https://img.shields.io/badge/Svelte-4A4A55?style=for-the-badge&logo=svelte&logoColor=FF3E00
[Svelte-url]: https://svelte.dev/
[Laravel.com]: https://img.shields.io/badge/Laravel-FF2D20?style=for-the-badge&logo=laravel&logoColor=white
[Laravel-url]: https://laravel.com
[Bootstrap.com]: https://img.shields.io/badge/Bootstrap-563D7C?style=for-the-badge&logo=bootstrap&logoColor=white
[Bootstrap-url]: https://getbootstrap.com
[JQuery.com]: https://img.shields.io/badge/jQuery-0769AD?style=for-the-badge&logo=jquery&logoColor=white
[JQuery-url]: https://jquery.com 
