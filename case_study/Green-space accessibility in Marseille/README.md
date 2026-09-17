# 🌳 Green-Space Accessibility in Marseille

## Neighborhood-Level Analysis of Parks and Gardens

This project analyzes the spatial distribution of recorded parks and gardens across the **111 quartiers (neighborhoods) of Marseille, France**.

The analysis combines neighborhood boundary data with geographic locations of recorded parks and gardens to understand how green-space sites are distributed across the city. It uses geospatial data processing, spatial joins, coordinate reference systems, area calculations, nearest-neighbor distance analysis, and thematic mapping.

---

## 🎯 Project Questions

The analysis addresses four main questions:

1. **How many recorded parks and gardens are located in each Marseille quartier?**
2. **Which quartiers have the highest and lowest density of recorded sites?**
3. **Which quartiers have no recorded site in the dataset?**
4. **How far is a representative point for each quartier from its nearest recorded site?**

These measurements provide an exploratory evidence base for understanding the spatial distribution of green spaces and identifying areas that may warrant further investigation.

---

## 📊 Dataset

The project uses two geospatial datasets.

| File | Description | Key Fields |
|---|---|---|
| `quartiers-marseille.geojson` | Polygon boundaries for the 111 Marseille quartiers | `code_qua`, `nom`, `NOM_CO`, `geometry` |
| `marseille_parcs_jardins_2018.csv` | Geographic locations of recorded parks and gardens | Site name, category, longitude, latitude |

### Dataset Summary

The supplied parks-and-gardens dataset contains:

- **109 recorded sites**
- **73 gardens**
- **36 parks**
- Geographic coordinates for each recorded site

The dataset does **not** contain population information. Therefore, this project calculates **site density by land area** rather than population-based accessibility.

---

## 🗺️ Geographic Scope

The analysis covers the **111 quartiers of Marseille**.

The neighborhood layer contains polygon geometries representing the boundaries of individual quartiers. Park and garden records are represented as geographic points based on their longitude and latitude coordinates.

The two datasets are spatially integrated to determine which quartier contains each recorded green-space site.

---