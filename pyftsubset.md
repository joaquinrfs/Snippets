# Font custom subset

## Install
```
pip install fonttools
```

## Usage
Full *Basic Latin* plus full *Latin-1 Supplement*.
```
pyftsubset <INPUT> --unicodes=U+0020-007E,U+00A0-00FF --output-file=<OUTPUT>.woff --flavor=woff
```
Full *Basic Latin* plus *ÁÉÍÑÓÚÜéíñóúü¡¿*
```
pyftsubset <INPUT> --unicodes=U+0020-007E,U+00C1,U+00C9,U+00CD,U+00D1,U+00D3,U+00DA,U+00DC,U+00E1,U+00E9,U+00ED,U+00F1,U+00F3,U+00FA,U+00FC,U+00A1,U+00BF --output-file=<OUTPUT>.woff --flavor=woff
```

## [Unicode Ranges](https://en.wikipedia.org/wiki/Unicode_block#List_of_blocks)
- **Basic Latin**: U+0020 - U+007E

- **Latin-1 Supplement**: U+00A0 - U+00FF

- **Spanish**:
	- **ÁÉÍÑÓÚÜ**: U+00C1, U+00C9, U+00CD, U+00D1, U+00D3, U+00DA, U+00DC

	- **éíñóúü**: U+00E1, U+00E9, U+00ED, U+00F1, U+00F3, U+00FA, U+00FC

	- **¡¿**: U+00A1, U+00BF

## Notes
- Also supports WOFF2, but requires: `pip install Brotli`
	- Change both `--output-file extension` and `--flavor` to woff2!