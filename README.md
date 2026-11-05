# DeepPolSARFlood: Research Data and Trained Model Weights

## Overview

This repository provides research datasets, reference flood masks, feature-selection data, and trained model weights associated with the study:

**DeepPolSARFlood: A Dual-Polarimetric SAR-Based Deep Learning Framework for Transferable Flood Detection**

The materials are provided to support transparency, reproducibility, and independent examination of the reported flood-mapping results.

## Repository Structure

```text
DeepPolSARFlood-Research-Data/
│
├── Data/
│   ├── FSelect.csv
│   ├── France-FloodMask.zip
│   ├── France-Training.zip
│   ├── France-Validation.zip
│   ├── France-Test.zip
│   └── Mask_Romania.zip
│
├── Models/
│   └── nested_unet_64.weights.h5
│
└── README.md
```

## 1. French Flood Dataset

The French dataset contains 706 selected non-overlapping image tiles of 64 × 64 pixels, divided into:

| Subset | Number of tiles |
|---|---:|
| Training | 451 |
| Validation | 113 |
| Test | 142 |
| **Total** | **706** |

The corresponding input data and reference masks are provided in separate archives.

The tile identifiers are preserved to support identification of the dataset partitions.

`France-FloodMask.zip` contains the French reference flood mask used in preparing the segmentation dataset.

## 2. Romanian Reference Flood Mask

`Mask_Romania.zip` contains the final integrated Romanian reference flood mask used for external evaluation of the trained model.

The reference was based on the Copernicus Emergency Management Service (CEMS) flood delineation, with limited refinements informed by Landsat-9 imagery.

The model evaluation was conducted using the final integrated reference mask.

## 3. Feature-Selection Dataset

`FSelect.csv` contains 1,999 GIS-derived point observations from the French study area:

- 1,000 flooded observations
- 999 non-flooded observations

Each observation includes values extracted from the candidate SAR- and PolSAR-derived features, together with its flood label.

This dataset was used for the metaheuristic feature-selection experiments.

## 4. Trained Model Weights

`Models/nested_unet_64.weights.h5` contains the trained Nested-UNet model weights associated with the Romanian flood evaluation.

The model uses five selected input features:

1. Beta0-VH
2. C11
3. C22
4. C12-Imag
5. Anisotropy

The weights are stored using Git Large File Storage (Git LFS).

The model architecture and preprocessing configuration are described in the associated manuscript. The weights alone do not constitute a complete executable model.

## 5. Data Sources

The study uses Sentinel-1 SAR imagery and flood reference products from the Copernicus Emergency Management Service (CEMS).

The French and Romanian flood events correspond to CEMS activations EMSR788 and EMSR802, respectively.

The Romanian reference mask was derived from a CEMS product based on Sentinel-1 imagery acquired on the same date as the model input. The evaluation therefore represents geographically separate cross-event testing, rather than fully sensor-independent validation.

## 6. Data Availability and Reuse

The repository provides the research materials described above for independent examination and future research.

Users should consult the associated manuscript for details of preprocessing, feature selection, model configuration, and evaluation procedures.

## Citation

If you use these materials, please cite the associated publication and the repository's DOI once available.

**Repository DOI:** To be added after archival publication.

## Contact


