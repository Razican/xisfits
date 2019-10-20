# XISFITS

XISFITS is a tool to convert PixInsight images (XISF) to FITS.

## Installation

XISFITS is programmed in [Rust](http://rust-lang.org/) language and doesn't depend on third-party libraries. Rust development tools must be installed following its own [instructions](https://www.rust-lang.org/tools/install). After that, download XISFITS sources and, on the main directory, run:

```bash
$ cargo build xisfits
```

## Usage

```bash
$ xisfits <image.xisf> <image.fits>
```

## Known issues and limitations

- Although the XISF format supports signed integers, currently only UInt8, UInt16 and UInt32 types (those used by PixInsight Core) can be converted to FITS.
- UInt8 is converted to FITS BITPIX 8, which is also unsigned.
- UInt16 and UInt32 are converted to signed 16 and 32 bits. In order to do so, if there are unsigned values greater than what signed values can store, those values are clipped.
- Compressed data is still unsupported.
- Float32 and Float64 conversions are still unsupported.
- If XISF file stores FITS headers, those headers are not copied over to the final FITS image.

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

## License
[MIT](https://choosealicense.com/licenses/mit/)
