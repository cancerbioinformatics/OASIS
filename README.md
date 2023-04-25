

<img src="https://github.com/cancerbioinformatics/OASIS/blob/main/oasis.png">

# **OASIS**: n**O**rmal bre**A**St t**IS**sue Dataset
This repo contains all documentation about the **OASIS** dataset containing whole slide images of normal breast tissue from multiple cohorts

- Dataset size: 1489 WSIs
- Contact name: Mario Parreno-Centeno
- Institution name: Kings's College London
- Institution URL: http://cancerbioinformatics.co.uk/
- Contact email: mario.parreno-centeno@kcl.ac.uk



## **Description of WSIs**
This is a retrospective dataset of 1489 H&E-stained whole slide image (WSI) of normal breast tissue. The images were collected from 4 institutions, namely **the King’s Health Partners Cancer Biobank (KHP)**, **the Netherlands Cancer Institute (NKI)**, **the Barts Cancer Institute (BCI)**, **the Cathrin Brisken Lab at the École Polytechnique Fédérale de Lausanne (EPFL)**. In the paper, we also have access to WSIs from the public **Susan G. Komen Tissue Bank (SGK)**. The WSIs were derived from:

<img src="https://github.com/cancerbioinformatics/OASIS/blob/main/wsi.png" width="300" height="600">

- Normal breast tissue of healthy individuals **without** known germline or VUS BRCA1/2 changes (n:1k)
- Normal breast tissue of healthy individuals **with** known germline or VUS BRCA1/2 changes (n:151)
- **Contralateral** normal breast tissue of breast cancer patient **with** known germline or VUS BRCA1/2 changes (n:128)
- **Peri-tumoral** normal breast tissue of breast cancer patient **with** known germline or VUS BRCA1/2 changes (n:210)



## **Manual Annotation**
Tissue type annotations are available for a selection of 70 WSIs, including 16 from NKI, 16 from BCI, 16 from KHP, 10 from EPFL and 12 from SGK. Lobule type annotations are available for 16 KHP WSIs. Annotations files and screenshots are stored in the tissue_type_annotation and lobule_type_annotation folders. The .geojson files could be directly imported into QuPath.



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



