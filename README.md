# Ocean Datacube Hackathon

This repository contains information and guided notebooks about the Ocean Hackathon. The core aspects of the hackathon are:

1. Ocean and sea datasets, focusing on Mediterranean sea and global ocean data from ESA-funded science projects, hosted on object storage.
2. Combined data cubes from these data, with common spatial and temporal resolutions and extents.
3. Guided notebooks that show how to access the cloud-hosted datasets,  convert data into cloud-native formats, combine them into analysis-ready datacubes, and use those collections in scientific workflows.
4. Information about creating a local enviroment to work in, or using the provided cloud platform.


## Repository Map

| Folder | Purpose | Best starting point |
| --- | --- | --- |
| `0_Introduction/` | Brief introduction to the hackathon, goals, EarthCODE context, setup, and agenda. | `0_Introduction/intro.ipynb` |
| `1_Datasets/` | Dataset catalogue and infromation per source product. | `1_Datasets/datasets_sumary.ipynb` |
| `2_Datacube/` | Data cubes based on the ESA Ocean Cluster Datasets  | `2_Datacube/0_intro.ipynb` |
| `3_File_formats_and_metadata/` | Format-conversion examples for Zarr, COG, and GeoParquet, plus the creation of STAC metadata. | `3_File_formats_and_metadata/0_intro.ipynb` |
| `4_Visualisation/` | Notebooks that show how to convert datasets for visualisations | `4_Visualisation/1_cog_visualisations.ipynb` |
| `5_Hackathon_Code/` | Folder for your code. | `5_Hackathon_Code/0_intro.md` |

Generated local data is expected in `downloaded_data/`, which is ignored by Git.

# EarthCODE Context

The hackathon is supported by [EarthCODE](https://earthcode.esa.int/), and the data is available through EarthCODE's [Open Science Catalog](https://opensciencedata.esa.int/catalog). 


# 1. Datasets prepared for the Ocean Hackathon

Each prepared dataset has an associated notebook, linked in the access notebook column, showing how to open its assets directly from object storage. More information about each dataset is available in its notebook and OSC entry. All notebooks reside in the `1_Datasets` folder.

| Dataset | Theme | Prepared format | CRS/grid | Time coverage | Licence | Links | Access notebook |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 4DMED-SEA sea-surface salinity | Mediterranean salinity and density fields | Zarr | EPSG:4326, 1/24° lat/lon grid | Daily, 2016–2022 | CC-BY-4.0 | [OSC](https://opensciencedata.esa.int/products/4dmed-2d-sss/collection) | [Notebook](1_Datasets/4dmed/4dmed-ss/access.ipynb) |
| 4DMED-SEA MIOST Lagrangian eddies | Mediterranean current structures and eddies | Zarr | EPSG:4326, 1/24° lat/lon grid | Daily, April 2016–July 2022 | CC-BY-4.0 | [OSC](https://opensciencedata.esa.int/products/4dmed-2d-alt-miost-le-24/collection) | [Notebook](1_Datasets/4dmed/4dmed-fsle/access.ipynb) |
| 4DMED-SEA 4DVarNet 1/8° | Sea-level and geostrophic velocity fields | Zarr | EPSG:4326, 1/8° lat/lon grid | Daily, January 2016–August 2022 | CC-BY-4.0 | [OSC](https://opensciencedata.esa.int/products/4dmed-2d-alt-varnet-8/collection) | [Notebook](1_Datasets/4dmed/4dmed-4dvar-8/acces.ipynb) |
| 4DMED-SEA 4DVarNet 1/20° | Sea-surface height and derived variables | Zarr | EPSG:4326, 1/20° lat/lon grid | Daily, January 2016–August 2022 | CC-BY-4.0 | [OSC](https://opensciencedata.esa.int/products/4dmed-2d-alt-varnet-20/collection) | [Notebook](1_Datasets/4dmed/4dmed-4dvar-20/acces.ipynb) |
| 4DMED-SEA PFT and Kd | Phytoplankton functional types and diffuse attenuation | Zarr | EPSG:4326, 8 km lat/lon grid | Monthly, 2019–2021 | CC-BY-4.0 | [OSC](https://opensciencedata.esa.int/products/4dmed-2d-pft-kd/collection) | [Notebook](1_Datasets/4dmed/4dmed-2d-pft-kd/access.ipynb) |
| 4DMED-SEA 3D physical fields | Temperature, salinity, density, and geostrophic velocity | Zarr | EPSG:4326, 1/24° grid with 20 depth levels to 153 m | Daily, January 2016–July 2022 | CC-BY-4.0 | [OSC](https://opensciencedata.esa.int/products/4dmed-t-s-geo-150/collection) | [Notebook](1_Datasets/4dmed/4dmed-t-s-geo-150/access.ipynb) |
| 4DMED-SEA primary production | Primary production from chlorophyll and temperature | Zarr | EPSG:4326, 1/24° grid with 148 depth levels to 150 m | Daily, January 2016–August 2022 | CC-BY-4.0 | [OSC](https://opensciencedata.esa.int/products/4dmed-3d-prim-prod-150/collection) | [Notebook](1_Datasets/4dmed/4dmed-pp/access.ipynb) |
| 4DMED-SEA 3D biophysical fields | Chlorophyll-a plus physical and velocity variables | Zarr | EPSG:4326, 1/24° grid with 148 depth levels to 150 m | Daily, January 2016–August 2022 | CC-BY-4.0 | [OSC](https://opensciencedata.esa.int/products/4dmed-t-s-geo-a-150/collection) | [Notebook](1_Datasets/4dmed/4dmed-t-s-a-geo-150/access.ipynb) |
| WOC total surface current | Hourly total ocean current at 15 m | Zarr | EPSG:4326, 0.25° lat/lon grid at 15 m | Hourly, December 2014–December 2019 | CC-BY-4.0 | [OSC](https://opensciencedata.esa.int/products/total-surface-current-15/collection) | [Notebook](1_Datasets/woc/access.ipynb) |
| Atlantic Ocean heat content | Atlantic heat-content change | Zarr | EPSG:4326, global 1° lat/lon grid | April 2002–September 2023 | AVISO terms | [OSC](https://opensciencedata.esa.int/products/4d-atlantic-ohc-global/collection) | [Notebook](1_Datasets/oceah-heat/access.ipynb) |
| OceanSODA-ETHZ | Surface-ocean carbonate-system variables | Zarr | EPSG:4326, global 1° and 0.25° lat/lon grids | Monthly, 1982–2024; 8-day products, 1982–2022 | CC-BY-NC-SA-4.0 | [OSC](https://opensciencedata.esa.int/products/ocean-soda-ethz/collection) | [Notebook](1_Datasets/ocean-soda/access.ipynb) |
| WAPOSAL | Wave and satellite-altimetry products | Zarr | EPSG:4326, along-track observations | March 2016–December 2022 | CC-BY-SA-4.0 | [OSC](https://opensciencedata.esa.int/products/waposal-waves/collection) | [Notebook](1_Datasets/waposal/access.ipynb) |
| MITHO | Global cumulative hazard indexes | Zarr | EPSG:4326, global 1° lat/lon grid | Monthly; varies by index, 1993–2022 | CC-BY-SA-4.0 | [OSC](https://opensciencedata.esa.int/products/global-cumulative-hazard-indexes-chis/collection.json) | [Notebook](1_Datasets/mitho/access.ipynb) |
| BICEP | Biological pump and carbon exchange processes | Zarr | EPSG:4326, global regular lat/lon grids | Monthly, 1997–2020 | UK Open Government Licence | [OSC](https://opensciencedata.esa.int/products/bicep-database/collection.json) | [Notebook](1_Datasets/bicep/access.ipynb) |
| CAREHeat | Marine heat waves | Zarr | EPSG:4326, global 0.25° lat/lon grid | Daily, 1980–2024 | CC-BY-4.0 | [OSC](https://opensciencedata.esa.int/projects/careheat/collection) | [Notebook](1_Datasets/careheat/access_2d.ipynb) |
| BOOMS | Biological ocean observations | TBD | TBD | TBD | TBD | [Source](https://rsg.pml.ac.uk/thredds/catalog-booms.html) | TBD |
| SCOPE | TBD | TBD | TBD | TBD | TBD | TBD | TBD |
| SARWAVE | TBD | TBD | TBD | TBD | TBD | TBD | TBD |
| Medicanes | TBD | TBD | TBD | TBD | TBD | TBD | TBD |

# 2. Ocean Data Cube

TBD.

# 3. File Formats and Metadata

The format notebooks demonstrate how  products can be transformed or exposed in cloud-optimised formats and described with reusable metadata.

## Dataset Formats

| Format | Best for | Why it matters in object storage |
| --- | --- | --- |
| Zarr | Labelled multidimensional arrays | Chunked reads allow an analysis to load only the required variables, regions, depths, and times. |
| Cloud Optimized GeoTIFF (COG) | Individual rasters or raster stacks | Internal tiling and overviews support efficient range reads and quicklooks. |
| GeoParquet | Vector geometries and tabular observations | Columnar storage enables efficient filtering and carries standard geospatial metadata. |

See the notebooks in `3_File_formats_and_metadata/` and the [Cloud-Native Geospatial Guide](https://guide.cloudnativegeo.org/) for more detail.

## Metadata

Rich metadata makes each collection easier to find, interpret, cite, and reuse. Collection metadata should document provenance, licence, variables, units, spatial and temporal extent, processing history, and access assets.

EarthCODE collections use the [SpatioTemporal Asset Catalog (STAC)](https://stacspec.org/) specification to provide a consistent, machine-readable description of geospatial data.

# Suggested Hackathon Workflow

1. Pick a science question, user workflow, or define your own.
2. Browse the dataset catalogue and open the relevant access notebooks.
3. Use the existing collections to answer the question.
4. Use the file-format notebooks as guidance when preparing a new dataset to add to the existing collections.
5. Put your code in `5_Hackathon_Code/` and keep generated data out of Git.
6. Submit your work as a pull request with a short description of the question, datasets, methods, and outputs.

## Environment Notes

The notebooks assume a Python geospatial environment with common Pangeo tools. The repository's `pixi.toml` provides packages including `xarray`, `dask`, `geopandas`, `rasterio`, `rioxarray`, `pyproj`, `shapely`, `pandas`, `numpy`, `matplotlib`, and `pystac`.

Install the environment and start JupyterLab with:

```bash
pixi install
pixi run jupyter lab
```

Network access is only needed for remote object-store reads or optional source downloads. The format tutorials write generated examples to `downloaded_data/`, which is ignored by Git.

The workshop uses EDC (Euro Data Cube). Its workspace URL, resource profile, and kernel name are **TBD**. See the [setup guide](0_Introduction/setup.md) for the latest instructions.
