---
layout: project

github: https://github.com/nkorobkov/microglia-or
project-name: Microglia Recognition
date: Feb 2018 - April 2018
---


### Problem

Studying the human brain involves taking pictures of microstructures within the brains of lab animals.  
Scientists use such images to extract information about single cells and make claims about different types of organism reactions based on statistics. 
Typical shot of mice brain after preparation and coloring looks something like this (segment):   


<img src="{{site.url}}/assets/microglia/raw.bmp" alt="demo raw" border="1" />

The goal of this project, is to clean the noise from such images and extract meaningful information about individual cell sizes and shapes. 
<div class="image_row">
<div class="image_col-2">
<img src="{{site.url}}/assets/microglia/proc.png" alt="demo proc" border="1" />
</div>
<div class="image_col-2" style="width:35%">
<img src="{{site.url}}/assets/microglia/stat.png" alt="demo stat" border="1" />
</div>
</div>

###  Tech

To achieve the goal I used:

- **Python** and  **NumPy** library for data manipulation.
- **Jupyther** as a REPL for faster prototyping and experimenting.
- **OpenCV** package for image processing and related operations.
- **Numba** project for Just-In-Time compilation and speed.

###  Algorithm

The developed algorithm uses multiple stages of components segmentation and component size analysis on the image. 
Filtering out small components and merging big components together to form a cell with axons. 

The algorithm has a lot of parameters that were hand-adjusted with professional biologists. 
These parameters can be changed to adapt the algorithm for usage with different cell types or imaging hardware.

<div class="image_row">
<div class="image_col-5">
<img src="{{site.url}}/assets/microglia/first.png" alt="demo first" border="1" />
</div>
<div class="image_col-5">
<img src="{{site.url}}/assets/microglia/second.png" alt="demo second" border="1" />
</div>
<div class="image_col-5">
<img src="{{site.url}}/assets/microglia/third.png" alt="demo third" border="1" />
</div>
<div class="image_col-5">
<img src="{{site.url}}/assets/microglia/fourth.png" alt="demo fourth" border="1" />
</div>
<div class="image_col-5">
<img src="{{site.url}}/assets/microglia/fifth.png" alt="demo fifth" border="1" />
</div>

</div>


### Publications 

This software was used to produce results presented at several scientific conferences.
Here is the list of some publications:

1. Glyavina M.M., Loginov P.A., Dudenkova V.V., Reunov D.G., Karpova A.O., Prodanets N.N., **Korobkov N.A.**, Zhuchenko M.A., Schelchkova N.A., Mukhina I.V.   
Carbamylated darbepoetin (CdEPO) impact on microglia activation in a model of occlusion of the middle cerebral artery.   
*"XIV International Interdisciplinary Congress &quot;Neuroscience for Medicine and Psychology"*  
2018 May 30- June 10 p. 159  
  
2. Glyavina M.M., Loginov P.A., Dudenkova V.V., Shirokova O.M., Reunov D.G., Karpova A.O., Prodanets N.N., **Korobkov N.A.**, Zhuchenko M.A., Mukhina I.V.   
Application of laser scanning confocal fluorescent microscopy for visualization microglia morphology in mouse local cerebral ischemia.   
*"26th International Conference on Advanced Laser Technologies"* [ALT&#39;18].  
2018 September 9-14: B-P-2.
  
3. Glyavina M.M., Loginov P.A., Dudenkova V.V., Shirokova O.M., Reunov D.G., Karpova A.O., Prodanets N.N., **Korobkov N.A.**, Zhuchenko M.A., Mukhina I.V.  
[Morphological analysis of microglia in early postischemic period in the mouse local cerebral ischemia.](https://www.epj-conferences.org/articles/epjconf/pdf/2018/30/epjconf_tera2018_10004.pdf)  
*"TERA — 2018, 3rd International Conference Terahertz and Microwave Radiation: Generation, Detection and Applications"*  
2018 October 22—25: S10, P.10.9
 