# MosaicEarth-Connector-QGIS

Native QGIS 3.34+ / 4.x plugin for MosaicEarth Cloud & Desktop: synchronize projects, styles, GeoTIFFs, GeoPackages, point clouds & stream live OGC WMTS 1.0.0.

## Releases & Ready-to-Install Downloads (`v0.2.2`)

- [`MosaicEarth-qgis-0.2.2.zip`](https://github.com/nsicart/MosaicEarth-Connector-QGIS/releases/download/v0.2.2/MosaicEarth-qgis-0.2.2.zip)
- Also available directly from [MosaicEarth Desktop & Connectors (`app.mosaicearth.app/en/Desktop`)](https://app.mosaicearth.app/en/Desktop).

## Cloud & Local Workstation Endpoints

Every MosaicEarth connector speaks the open **MosaicEarth Synchronization Protocol v1** (chunked `4 MiB` resumable uploads + end-to-end `SHA-256` verification) and can connect to:

- **MosaicEarth Cloud** (default): `https://app.mosaicearth.app`
- **MosaicEarth Desktop (Local Workstation)**: `http://127.0.0.1:19771` (set `MOSAICEARTH_URL=http://127.0.0.1:19771` or select the endpoint in the connector UI).

## Usage & Setup

In QGIS 3.34–3.x or QGIS 4.x, choose Plugins → Manage and Install Plugins → Install from ZIP and select `MosaicEarth-qgis-0.2.2.zip`. Enable MosaicEarth, then open its toolbar/menu action.

Sign in and synchronize the current project. The connector saves project settings, CRS, layer order, styles, layouts and local image/SVG resources. It materializes vector providers into GeoPackage and raster providers into GeoTIFF, and also preserves original local files and sidecars. Local point-cloud/mesh masters are retained. Export unsupported or remote mesh/point-cloud providers to local files before synchronization; an unavailable provider produces an explicit error.

Browse and download into a chosen directory. A QGIS snapshot opens its portable `.qgz` project. Other cloud exports add compatible raster, vector and point-cloud files; all remaining models and attachments are still saved. Authentication and file transfers use QGIS background tasks. Packaging reads the current project on the main thread so native providers and styles remain consistent.

## License

Released under **GNU Affero General Public License v3.0 or later (`AGPL-3.0-or-later`)** — see [`LICENSE`](./LICENSE).
