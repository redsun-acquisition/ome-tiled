# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

Dates are specified in the format `DD-MM-YYYY`.

## [0.2.1] - 25-10-2026

### Added

- Support for Python 3.14.

### Changed

- `ome-tiled` requires `tiled>=0.2.20` and `yaozarrs>=0.3.4`, and its
  `bluesky` extra requires `bluesky-tiled-plugins>=2.0.12`.

### Fixed

- `OmeZarrAdapter` keeps the axis names an array records in
  `dimension_names` or `_ARRAY_DIMENSIONS` when the array is not part of an
  OME-Zarr image, as `tiled`'s own Zarr adapter does.

## [0.2.0] - 18-09-2026

### Added

- **`OmeZarrConsolidator`** (`ome_tiled.bluesky`) - a `bluesky-tiled-plugins`
  consolidator for `application/x-ome-zarr` resources, registering the image
  with the shape, chunks and axis names the store holds.
- **`register_consolidator`** (`ome_tiled.bluesky`) - makes `TiledWriter` use
  `OmeZarrConsolidator` for `application/x-ome-zarr` resources:

  ```python
  from ome_tiled.bluesky import register_consolidator

  register_consolidator()
  ```

- A `bluesky` extra, with `bluesky-tiled-plugins`, which `ome_tiled.bluesky`
  needs.

## [0.1.1] - 17-09-2026

### Changed

- Cleanup some build configuration.

## [0.1.0] - 17-09-2026

Initial release.

[0.2.1]: https://github.com/redsun-acquisition/ome-tiled/compare/v0.2.0...v0.2.1
[0.2.0]: https://github.com/redsun-acquisition/ome-tiled/compare/v0.1.1...v0.2.0
[0.1.1]: https://github.com/redsun-acquisition/ome-tiled/compare/v0.1.0...v0.1.1
[0.1.0]: https://github.com/redsun-acquisition/ome-tiled/tree/v0.1.0
