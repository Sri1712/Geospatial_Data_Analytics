# Marseille LiDAR height by quartier

## Purpose

This project analyzes the spatial distribution of official LiDAR-predicted heights across Marseille, France. It assigns point observations to quartier polygons and summarizes the height distribution and observation density of each neighborhood.

## Inputs

| File | Role |
|---|---|
| `lidar_4326_Marseille.csv` | 766,641 LiDAR height observations with `ID`, `Height_m`, `Longitude`, and `Latitude` |
| `quartiers-marseille.geojson` | 111 Marseille quartier polygons |

The CSV coordinates are treated as WGS 84 (`EPSG:4326`). The notebook reprojects data to Lambert-93 (`EPSG:2154`) for distance and area calculations.

## Indicators

- `lidar_point_count`: valid observations spatially assigned to the quartier.
- `points_per_sq_km`: observation density, useful for checking sampling coverage. It is **not** a population or asset density.
- `mean_height_m`, `median_height_m`, `min_height_m`, `max_height_m`, `std_height_m`: descriptive height statistics.
- `p10_height_m`, `p90_height_m`: lower and upper height-distribution reference values.

## Outputs

| Output | Contents |
|---|---|
| `marseille_quartier_lidar_height_statistics.csv` | One row per quartier with height and density indicators |
| `marseille_quartier_lidar_height_statistics.geojson` | Same indicators joined to polygon geometry |
| `marseille_lidar_height_by_quartier.png` | Maps of median height and point density |
| `marseille_lidar_height_distribution.png` | Citywide height distribution histogram |
| `marseille_lidar_height_hexbin.png` | Citywide mean-height surface aggregated into hexagonal cells |
| `marseille_quartier_height_rankings.png` | Highest and lowest quartiers by median LiDAR height |
| `marseille_top_quartier_height_distributions.png` | Height spread in the 12 highest-median quartiers |
| `marseille_lidar_coverage_vs_height.png` | Quality-control comparison of point coverage and median height |

## Interpretation and limitations

The official documentation confirms that `Height_m` is LiDAR height. This supports a height-surface analysis; it does not, by itself, identify object type. Do not relabel the measurements as tree height, building height, canopy cover, or green space without an additional classification layer.

The project is a spatial screening tool. It does not measure population, accessibility, land use, building function, vegetation health, or walking distance. Height values can be compared between quartiers, but differences should be interpreted with the LiDAR product's resolution, collection date, and processing method in mind.