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

I chose to create a data visualization sculpture that falls into the category of symbolic representation [4] according to the writings of Andrew Vande Moore & Stephanie Patel who’s paper on the categorization of physical visualization of information guided my design choices. Symbolic representation is defined by them “to be works characterized by a form-finding approach that employs a so-called arbitrary data-mapping approach”. I chose this method as I wanted to visually disentangle the topic of mass shootings with the work. I wanted people to engage with the work before being presented with the data linked to the creation so they were less likely to disengage as soon as they realized what the subject matter was.

Similar to how I created my previous Moire disks, I designed this project in Grasshopper to be baked in Rhino after the final formulation of each month's data. One challenge of this was going to be making the design as minimal as possible as to not draw attention away from the aforementioned meaning. My goal was to create a print in place upper piece that didn’t require any after assembly, but still allowed for rotation and came across those that had been 3D printing with interlocking parts [3]. 
According to the Gun Violence Archive, an online archive of gun violence incidents collected from over 7,500  law enforcement, media, government and commercial sources daily[2], there were 586 mass shootings in 2024; resulting in a total death count of 711 individuals. 

<!-- Methodology -->
## Methodology 
Since I was targeting Moiré patterns, I needed some form of movement to trigger the effect. The main options were viewer movement, radial movement, or lateral movement. I ultimately chose radial movement and began constructing the inner and outer structures, along with the parametric attributes for the spokes used for both disks.

[![Assignment_02][images-fig3]](https://github.com/Naaberle/Assignment_02/blob/main/images/fig3.png?)
Figure  3. Each disk is composed of the same inner and outer structure, as well as 5 parameters the user can adjust to create each disk.

I chose radial movement for two key reasons. First, motorizing one of the disks to test various speeds would be much simpler than engineering a back-and-forth mechanism for lateral movement. Second, the parametric design process was more straightforward with a spoke-based system than with a grid-like structure, which would have been more complex to manipulate parametrically for generating the Moiré effect.

The parametric design of the spokes begins with copies of the inner and outer rings used for the walls. These curves are subdivided into equal segments with BaseCurves—one of the adjustable parameters provided in the inputs. The resulting points are then moved upwards by half the thickness of the outer wall via AdjustedStartingPts. Straight lines are drawn between corresponding points on the inner and outer curves to form the base of each spoke (MainSpokes), which are then further subdivided based on user input.

[![Assignment_02][images-fig4]](https://github.com/Naaberle/Assignment_02/blob/main/images/fig4.png?)
Figure 4. shows the subdivision of the outer curves, the creation of the spokes, the zigzag series, the curve offset, and ends with the final NURBS curves for the center of each spoke.

The CurveOffset and ZigZagSeries sections of the algorithm generate two things: a set of points created by subdividing each spoke line, and a corresponding series of offset values. Using these, a NURBS curve is generated, with the user able to control the complexity of the curve—from 0 (straight) to 5 (fully smooth).
Finally, the FinalSweep section creates a square at the base (center side) of each spoke, aligns it to the curve’s tangent, and sweeps it outward along the NURBS path. The resulting spokes are then combined with the inner and outer walls, capped, and can be baked into Rhino for export.

[![Assignment_02][images-fig5]](https://github.com/Naaberle/Assignment_02/blob/main/images/fig5.png?)
Figure 5. shows the final calculations for the square that is swept along the spoke as well as the final brep shape that is created and assembled by the rest of the algorithm.


<!-- Results and Future Work -->
## Results and Future Work
The parametric design of the disks functions exactly as intended, producing disks capable of creating a Moiré pattern. However the current system allows for the creation of discs that are so sparse or featureless that they fail to generate any visible Moiré pattern. Future work may include analyzing the full parameter set to identify combinations incapable of producing the desired effect, and removing those from user input options to streamline generation.

[![Assignment_02][images-fig6]](https://github.com/Naaberle/Assignment_02/blob/main/images/fig6.png?)
Figure 6. shows 4 different spokes generated parametrically but currently unknown if they'd create a Moiré pattern when combined with other disks.

One change I would make in a future iteration is to add spoke width as an adjustable parameter. At present, this value is hard-coded based on the height of the outer wall, limiting flexibility and experimentation.

The results from the discs that do produce the Moiré effect are consistent with expectations. However, the first set I printed did not generate any visible interference, which prompted me to propose a modified formulation of the Moiré function as shown in Figures 7a & 7b.

[![Assignment_02][images-fig7a]](https://github.com/Naaberle/Assignment_02/blob/main/images/fig7a.png?)<br />

where:

[![Assignment_02][images-fig7b]](https://github.com/Naaberle/Assignment_02/blob/main/images/fig7b.png?)<br />
Figure 7a. (Above) shows a modified equation for the emergence of Moiré patterns that includes a certain threshold that must be met before the pattern emerges. <br />
Figure 7b. (Below) defines Big Theta of ρ in this equation as 1 or 0 depending whether or not ρmin has been met to create a Moiré pattern.

[![Assignment_02][images-fig8]](https://github.com/Naaberle/Assignment_02/blob/main/images/fig8.png?)<br />
Figure 8. The disks on the <a href="https://youtube.com/shorts/h3N6dHqKTmk?feature=share">left</a> did not achieve Moiré while those on the <a href="https://youtube.com/shorts/N_jdyw0EP1k?feature=share">right</a> did.

This opens up future work focused on determining the specific value of ρmin​ required to consistently reach the threshold for Moiré emergence. Additional areas for exploration could include variable spoke thickness, X and Y axis modulation, or alternative spoke curvatures such as sine, sawtooth, or square waveforms.


<!-- Conclusion -->
## Conclusion
Creating non-symmetrical pairs of parametrically designed radial geometries, 3D printing them, and introducing rotation offers a novel methodology for using overlap as a medium to explore the requirements for producing a Moiré effect in physical 3D applications. Through analyzing this process and a range of generative outputs, I found that there is a threshold below which a Moiré pattern cannot be formed; identifying that threshold may offer a valuable new experiment and direction. These methods can be extended to other 2D optical illusions not yet fully understood in 3D, opening a wide array of new visual possibilities.

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
