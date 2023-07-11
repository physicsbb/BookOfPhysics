# Long Portfolio

## UV Photonics Research

### Acknowledgement for UV Photonics Research
I would like to thank Dr. Shuji Nakamura as well as Dr. Steve DenBaars for offering me the opportunity to partake in this exciting field of photonics research at SSLEEC. This opportunity allowed me to apply my Condensed Matter and Optics knowledge to immediate applications. I also gained hands-on characterization skills through working with the X-Ray diffractometer, Atomic Force Microscope, as well as the Hall Measurement bench setup. All of this was thanks to their offering, and I am grateful for this opportunity. 

I would also like to specifically express my profound gratitude for the support from different graduate mentors that I have worked with:  
1. **Michael Wang** and **Yifan Yao** (both in the UV group) for their training, consistently answering my questions, and allowing for insightful conversations related to research as well as putting me on **two publications** as a co-author, as well as just being awesome! Both of your support through impactful actions are **very much appreciated**! 
2. **Nate Palmquist** (on the blue FP-VCSEL project) for offering more opportunities to me to characterize more samples as well as his support for my mental and overall well-being. It was you who showed me through sharing with me your PhD experience that positive progress/impact can be made, both in research and in real life -- I am eternally grateful for your advice! 

### A partial picture of UV photonic device research (LEDs & FP-EELDs) 
UV photonic devices utilize AlGaN (Aluminum Gallium Nitride) crystal (both a ZincBlende and Wurtzite) to achieve the generation of photons at the wavelength of 200nm to 350nm. Different regions of UV spectrum may have different growth technique, and each region in the spectrum has its challenges. See {numref}`AlGaNWavelength` for reference. 
```{figure} ../Images/AlGaNWavelength.jpg
---
name: AlGaNWavelength
---
Change in Al content in $\text{Al}_{x}\text{Ga}_{\text{(1-x)}}\text{N}$ results in widening the optical bandgap, which results in emitting a shorter wavelength.
```

One of the biggest challenges in UV-A LED research is in growing AlGaN on top of AlN/Sapphire due to large lattice mismatch between GaN and AlN, if the lattice mismatch is too great, cracks may be observed on the crystal as a result of great tensile strain. Another challenge in UV photonics research as a whole is the fact that UV wavelength of light is not transparent to GaN (n = 2.5), due to Total Internal Reflection (TIR) where light gets trapped in the cladding layer, hence a low External Quantum Efficiency as a result of Light Extraction Efficiency (LEE) suffering a huge loss. This is especially true the further into Deep UV wavelength -- high p-GaN absorption of UV radiation is exhibited. This is the exact reason why a flip chip design for UV LEDs are used. Light rays exit from the n-AlGaN side.  

### a UV Dream (or a UV meme?):
Since LEE of UV wavelength is low due to Total Internal Reflection, where light gets trapped in the guided modes, the build of a Fabry Perot Edge Emitting Laser (EEL) is a more feasible solution simply from the standpoint of ray tracing. A Distributed Feedback (DFB) Grated EEL would be an expensive build due to difficult fabrication of the Bragg's grating at an atomic level (think in terms of Miller Indicies). 

The only way to generate a truly fundamental $\text{TEM}_{00}$ mode is through a Vertical Cavity Surface Emitting Laser (VCSEL), but light has to come out through the top and bottom of the device, when the light extraction efficiency (referring an LED, think in terms of ray tracing) is extremely low. Do you see why it would be both exciting and fishy when someone says they can build a UV VCSEL now? 

### References
I'm working on the format and syntax on how to properly import them right now. They are on its way!