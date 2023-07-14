# Long Portfolio

## UV Photonics Research


### A partial picture of UV photonic device research (LEDs & FP-EELDs) 
UV photonic devices utilize AlGaN (Aluminum Gallium Nitride) crystal (both a ZincBlende and Wurtzite) to achieve the generation of photons at the wavelength of 200nm to 350nm. Different regions of UV spectrum may have different growth technique, and each region in the spectrum has its challenges. See  {numref}`AlGaNWavelength` for reference. 
```{figure} ../Images/AlGaNWavelength.jpg
:name: AlGaNWavelength
Change in Al content in $\text{Al}_\text{x}\text{Ga}_{\text{(1-x)}}\text{N}$ results in widening the optical bandgap, which results in emitting photons of shorter wavelength. Graph from [[SLS13](https://www.mdpi.com/1424-8220/13/8/10482)]. 
```

One of the biggest challenges in UV-A LED research is in growing AlGaN on top of AlN/Sapphire due to large lattice mismatch between GaN and AlN. If the lattice mismatch is too great, cracks may be observed on the crystal as a result of great tensile strain. Note also that Al lattice constant and Ga lattice constant expand at different temperatures, which also adds to the challenge of finding ideal ratio of compensation between strained and relaxed lattice. [[Zol+21](http://doi.org/10.1088/1361-6641/ac27e7)] Another challenge in UV photonics research as a whole is the fact that UV wavelength of light is not transparent to GaN (n = 2.5), due to Total Internal Reflection (TIR) where light gets trapped in the cladding layer[[Wei+20](https://www.energy.gov/sites/default/files/2020/02/f71/ssl-rd2020-weisbuch-extraction.pdf)], hence a low External Quantum Efficiency as a result of Light Extraction Efficiency (LEE) suffering a huge loss. This is especially true further into Deep UV wavelength -- high p-GaN absorption of UV radiation is exhibited. This is the exact reason why a flip chip design for UV LEDs are used -- light rays exit from the n-AlGaN side. 
### One of the greatest achievements in the History of Science from 30 years ago:
30+ years ago, everyone believed that ZnSe (II-VI materials) would have been the ideal materials which can give rise to the invention of blue and white LED based on theoretical calculations, and everyone believed that Gallium Nitride Research would have been equivalent to "walking in wasteland" given the difficulty of the research. The only ones in the field doing research in III-Nitride materials back in the late 80s were only [Dr. Hiroshi Amano](https://www.nobelprize.org/prizes/physics/2014/amano/facts/), [Dr. Isamu Akasaki](https://www.nobelprize.org/prizes/physics/2014/akasaki/facts/) and [Dr. Shuji Nakamura](https://www.nobelprize.org/prizes/physics/2014/nakamura/facts/). Amano and Akasaki's achievement were in developing a research grade MOVPE system to successfully grow GaN on Sapphire - ideal growth result should have mirror-like gloss on its surface. In addition to that, they also derived the idea to grow Mg-doped GaN samples from a paper published in 1972 by a H.P. Maruska from Stanford University, which documents the production of Metal-Insulator-Semiconductor (MIS) type Mg-doped GaN based violet LED. This motivated Amano and Akasaki to also grow p-GaN by doping the crystal with Mg. Later, they had a post-growth Low Energy Electron Beam Irradiation (LEEBI or E-Beam) treatment to first discover the increased conductivity of p-GaN, but the reasoning was yet to be justified, which were later justified by Nakamura, with an improved and much more efficient method.

Dr. Shuji Nakamura's achievement was not only in modifying an MOCVD reactor for GaAs into a two-flow MOCVD system suitable for GaN, which sprays $\text{N}_2 + \text{H}_2$ gas through the secondary flow (antiperpendicular to surface) to press the main gas flow (which is parallel to surface) downward onto the substrate, he also provided a much more efficient solution to annihilate (or passivate) the Hydrogen that was bonded to the Mg, with which the Mg-H complex prevented the crystal from acting as an acceptor. Upon post-growth thermal annealing, p-GaN mobility is greatly increased by almost 6 orders of magnitude.[[Nak+92](https://iopscience.iop.org/article/10.1143/JJAP.31.L139/meta)] Note that the Hydrogen came from $\text{NH}_3$, with $\text{NH}_3$ acting as a precursor for one of the chemical reactions in the MOCVD system and 99.9% of all $\text{NH}_3$ gas diffuse into $\frac{1}{2}N_2+\frac{3}{2}H_2$ at 700˚C. Thermal Annealing a process was also easily "commercialized" that every manufacturing company adopted this method to achieve increase in conductivity. The experiment provided the first proposition for future theoretical calculation and the proposition of hydrogen passivation was later confirmed theoretically by [Chris G. Van de Walle, et al](https://www.materials.ucsb.edu/people/faculty/chris-g-van-de-walle) in 1995.[[NV95](https://doi.org/10.1103/PhysRevLett.75.4452)] This allowed for the creation of p-n junction, polarized enough to make a semiconductor out of it. The justification is as follows:

Work In Progress.

### Did I come up with a UV Dream (or a UV meme?):
Since LEE of UV wavelength is low due to Total Internal Reflection, where light gets trapped in the guided modes, the build of a Fabry Perot Edge Emitting Laser (EEL) is a more feasible solution simply from the standpoint of ray tracing. A Distributed Feedback (DFB) Grated EEL would be an expensive build due to difficult fabrication of the Bragg's grating at an atomic level (think in terms of Miller Indicies). 

The only way to generate a truly fundamental $\text{TEM}_{00}$ mode is through a Vertical Cavity Surface Emitting Laser (VCSEL), but light has to come out through the top and bottom of the device, when the light extraction efficiency (referring an LED, think in terms of ray tracing) is extremely low. Do you see why it would be both exciting and fishy when someone says they can build a UV FP-VCSEL now (within the immediate future)? 



### References
Working on the reference now, the outline of the whole page is in progress also as I attempt to implement the bibliography import automation.

[[Nak+92](https://iopscience.iop.org/article/10.1143/JJAP.31.L139/meta)]
Shuji Nakamura et al. “Thermal annealing effects on p-type Mg-doped GaN films”. In: Japanese Journal of Applied Physics 31.2B (1992), p. L139.

[[NV95](https://doi.org/10.1103/PhysRevLett.75.4452)]
Jörg Neugebauer and Chris G Van de Walle. “Hydrogen in GaN: Novel aspects of a common impurity”. In: Physical review letters 75.24 (1995), p. 4452.

[[SLS13](https://www.mdpi.com/1424-8220/13/8/10482)] 
Liwen Sang, Meiyong Liao, and Masatomo Sumiya. “A comprehensive review of semiconductor ultraviolet photodetectors: from thin film to one-dimensional nanostructures”. In: Sensors 13.8 (2013), pp. 10482–10518.

[[Wei+20](https://www.energy.gov/sites/default/files/2020/02/f71/ssl-rd2020-weisbuch-extraction.pdf)]
C. Weisbuch, H. Benisty*, M. Rattier*, D. Labilloy*, A. David, E. Matioli, C. Lalau-Keraly, M. Cochet, and L. Kuritzky. "Light Extraction in Nitride LEDs", https://www.energy.gov/sites/default/files/2020/02/f71/ssl-rd2020-weisbuch-extraction.pdf

[[Zol+21](http://doi.org/10.1088/1361-6641/ac27e7)]
Christian J Zollner et al. “Germicidal ultraviolet LEDs: A review of applications and semiconductor technologies”. In: Semiconductor Science and Technology 36.12 (2021), p. 123001.










### Acknowledgement for UV Photonics Research
I would like to thank Dr. Shuji Nakamura as well as Dr. Steve DenBaars for offering me the opportunity to partake in this exciting field of photonics research at SSLEEC. This opportunity allowed me to apply my Condensed Matter and Optics knowledge to immediate applications. I also gained hands-on characterization skills through working with the X-Ray diffractometer, Atomic Force Microscope, as well as the Hall Measurement bench setup. All of this was thanks to their offering, and I am grateful for this opportunity. 

I would also like to specifically express my ***profound gratitude*** for the support from different graduate mentors that I have worked with:  
1. [**Michael Wang**](https://www.linkedin.com/in/michael-w-64a0ab9b/) and [**Yifan Yao**](https://www.linkedin.com/in/yifan-yao-983075171/) (both in the UV group) for their training, consistently answering my questions, and allowing for insightful conversations related to research as well as putting me on **two publications** as a co-author, as well as just being awesome! Both of your support through impactful actions are **very much appreciated**! 
2. [**Nate Palmquist**](https://www.linkedin.com/in/nathan-palmquist/) (on the blue FP-VCSEL project) for offering more opportunities to me to characterize more samples as well as his support for my mental and overall well-being. It was you who showed me through sharing with me your PhD experience that positive progress/impact can be made, both in research and in real life -- I am eternally grateful for your advice! 
