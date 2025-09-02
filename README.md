# Building Level AlphaEarth Analysis

A comprehensive tutorial for extracting and analysing Google's AlphaEarth Foundations satellite embeddings at the building level, using Liverpool City Region as a case study.

## Overview

This repository demonstrates how to leverage Google's AlphaEarth Foundations AI model to analyse urban environments through satellite embeddings. The tutorial progresses from basic data extraction through advanced predictive modeling, combining satellite AI with urban datasets to identify building typologies and predict characteristics.

## What are AlphaEarth Embeddings?

[AlphaEarth Foundations](https://deepmind.google/discover/blog/alphaearth-foundations-helps-map-our-planet-in-unprecedented-detail/) is an AI model developed by Google DeepMind that provides pre-computed embeddings. These numerical "fingerprints" aim to capture the visual characteristics of locations. These embeddings distil complex environmental information into 64 numerical values for every 10×10 meter pixel across Earth's terrestrial and coastal zones.

>> Brown, C. F., Kazmierski, M. R., Pasquarella, V. J., Rucklidge, W. J., Samsikova, M., Zhang, C., Shelhamer, E., Lahera, E., Wiles, O., Ilyushchenko, S., Gorelick, N., Zhang, L. L., Alj, S., Schechter, E., Askay, S., Guinan, O., Moore, R., Boukouvalas, A., & Kohli, P. (2025). AlphaEarth Foundations: An embedding field model for accurate and efficient global mapping from sparse label data. https://arxiv.org/abs/2507.22291

## Learning Objectives

By completing this tutorial, you will be able to:

### Data Access and Extraction
- Access and authenticate Google Earth Engine API from Python
- Extract pixel-level embeddings for large geographic regions
- Process embeddings for specific building locations

### Clustering and Pattern Recognition
- Apply k-means clustering to identify building typologies
- Use clustergram analysis to determine optimal cluster frequency
- Validate clustering results using external datasets

### Advanced Analytics
- Visualise high-dimensional embeddings using UMAP
- Calculate cosine similarity between buildings
- Integrate satellite embeddings with Energy Performance Certificate data

### Predictive Modeling
- Build Random Forest models to predict building characteristics
- Evaluate model performance using confusion matrices
- Understand the limitations of embedding-based prediction

## Prerequisites

### Required Libraries
```bash
pip install earthengine-api pyarrow scikit-learn pandas geopandas clustergram keplergl umap-learn seaborn matplotlib numpy requests pillow duckdb plotly
```

### Google Earth Engine Account
You will need a Google Account to access the AlphaEarth data through Google Earth Engine.

## Data

All data for this tutorial is available from the Geographic Data Service and should be placed in a `data` folder in your working directory.

## Key Findings

### Cluster Analysis
The analysis identified five distinct building types:
- **Cluster A**: Mixed residential from 1950s-1960s
- **Cluster B**: Detached and semi-detached properties
- **Cluster C**: Victorian/Edwardian terraces (pre-1930)
- **Cluster D**: High-density residential (terraced housing)
- **Cluster E**: Large specialised buildings (industrial/commercial)

### Predictive Performance
The Random Forest model achieved 49% accuracy in predicting building age across 9 time periods, with notable patterns:
- Best performance on 1900-1929 buildings (70% recall)
- Systematic confusion between adjacent time periods
- Challenges distinguishing mid-to-late 20th century buildings

## Tutorial Structure

1. **Setup and Authentication** - Configure Google Earth Engine access
2. **Pixel Level Analysis** - Extract and explore embedding structure
3. **Building Cluster Analysis** - Apply k-means clustering to buildings
4. **UMAP Visualisation** - Reduce dimensionality for visual exploration
5. **Characteristic Matching** - Link clusters to building attributes
6. **Predictive Modeling** - Build and evaluate a Random Forest classifier

## Author

**Alex Singleton**  
Geographic Data Science

## License

This tutorial is provided for educational purposes. Please ensure you comply with Google Earth Engine's terms of service when using the AlphaEarth data.

## Acknowledgments

This work uses Google's AlphaEarth Foundations model and data from the Geographic Data Service. Building characteristics are derived from UK Energy Performance Certificate records.