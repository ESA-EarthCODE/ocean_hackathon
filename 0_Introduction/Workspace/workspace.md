# EDC (Euro Data Cube) Cloud Platform

## Workshop Access

The Ocean Hackathon uses the EDC workspace and its Pangeo environment. The access URL, account process, available resources, and workshop-specific storage details are **TBD**.

EDC provides a managed JupyterLab environment for accessing and analysing the ocean collections. The notebooks can also run locally using the repository's Pixi environment.

## Pangeo Tools

[Pangeo](https://pangeo.io/) is a community-driven ecosystem for scalable analysis of Earth and environmental data. The notebooks use several tools commonly found in Pangeo environments:

- **Xarray** for labelled multidimensional arrays.
- **STAC** for consistent discovery and description of geospatial collections.
- **Dask** for lazy, parallel, and distributed computation.
- **Zarr** for chunked, cloud-optimised array storage.
- **Jupyter** for interactive and shareable workflows.

Together, these tools support workflows that begin with collection discovery, read only the required data, scale when necessary, and remain reproducible.

## Choosing Compute Resources

Begin with the smallest EDC environment suitable for the task and inspect array dimensions and chunks before scaling up. Use a local Dask client for development and EDC's Dask Gateway when the workload benefits from multiple workers. Available Gateway resource profiles are **TBD**.

Continue with [Distributed Computing with Dask](./dask-gateway.ipynb).
