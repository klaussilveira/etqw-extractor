# etqw-extractor

This command-line tool decodes hashed DDS texture cache files used
by *Enemy Territory: Quake Wars* and restores them to their original
TGA texture paths.

ETQW stores generated textures in a cache layout like:

```
generated/dds/<original-path>/<hash>b<variant>.dds
```

Where the filename is derived from a one-way MD5-based hash of the
original texture path. This tool reverses that mapping by using a
dictionary of known texture paths.

## Requirements

- Python 3.3 or higher
- ImageMagick 7 (magick) or ImageMagick 6 (convert)

## Usage

At the root of your `base` folder:

    $ python extract.py tex <path-to-dds>

### Examples

Extracting this DDS:

    $ python extract.py tex generated/dds/models/vehicles/strogg_icarus/2406023233b50.dds

Will output the texture to:

    models/vehicles/strogg_icarus/icarus_handle_bars_s.tga
