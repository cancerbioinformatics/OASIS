

<img src="https://github.com/cancerbioinformatics/OASIS/blob/main/oasis.png">

# **OASIS**: n**O**rmal bre**A**St t**IS**sue Dataset
- Dataset size: 1489 WSIs
- Contact name: Mario Parreno-Centeno
- Institution name: Kings's College London
- Institution URL: http://cancerbioinformatics.co.uk/
- Contact email: mario.parreno-centeno@kcl.ac.uk

The nOrmal breASt tISsue Dataset (OASIS) repository contains whole slide images of H&E-stained normal breast tissue from the following resources:
<img align="center" src="https://github.com/cancerbioinformatics/OASIS/blob/main/wsi.png" width="300" height="600">
- Normal breast tissue of healthy individuals **without** known germline or VUS BRCA1/2 changes (n:1k)
- Normal breast tissue of healthy individuals **with** known germline or VUS BRCA1/2 changes (n:151)
- **Contralateral** normal breast tissue of breast cancer patient **with** known germline or VUS BRCA1/2 changes (n:128)
- **Peri-tumoral** normal breast tissue of breast cancer patient **with** known germline or VUS BRCA1/2 changes (n:210)

This is a retrospectively collected dataset of 1,489 H&E-stained whole slide image (WSI) of normal breast tissue. The images were collected from following institutions, namely **the King’s Health Partners Cancer Biobank (KHP)**, **the Netherlands Cancer Institute (NKI)**, **the Barts Cancer Institute (BCI)**, **the Cathrin Brisken Lab at the École Polytechnique Fédérale de Lausanne (EPFL)**. We have access to WSIs from the publicly available Susan G. Komen Tissue Bank (SGK). The WSIs comprise normal breast tissue collected from:



## Example usage
Below code demonstrates how to load WSIs programmatically using Python Openslide package
 
 ```python
import openslide
import numpy as np
import matplotlib.pyplot as plt

#Read WSI
wsi = openslide.OpenSlide("/Path/to/wsi.ndpi")

#Get slide properties
dims=wsi.dimensions
x_resolution=wsi.properties[openslide.PROPERTY_NAME_MPP_X]
y_resolution=wsi.properties[openslide.PROPERTY_NAME_MPP_X]
base_mag=wsi.properties[openslide.PROPERTY_NAME_OBJECTIVE_POWER]


#Display thumbnail
wsi_thumbnail = wsi.get_thumbnail((1000,1000))
wsi_thumbnail=np.array(wsi_thumbnail)
plt.imshow(wsi_thumbnail)
plt.axis('off')
```




## Credits

If you find the data useful, please cite the below paper:

    @inproceedings{,
        title={},
        booktitle={},
        author={},
        year={}
    }



