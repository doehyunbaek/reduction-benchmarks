# IGOR-SOX

Downloaded from
- https://github.com/HexHive/Igor
- https://datacommons.anu.edu.au/DataCommons/rest/records/anudc:5927/data/Binaries/

## README from datacommons.anu.edu.au

The archives are the compiled binaries that are used for the fuzzing experiments.
The dependencies as seen on the fuzzing machines are captured in the dependencies files.
As a note, the binary used for fuzzing   is the same as MP3 (SoX), hence, there is no separate binary
dedicated for fuzzing WAV.

The prefix indicates the program:
* pdf         : Poppler (0.64.0)
* sox         : SoX - Sound Exchange (14.4.2) with libmad to fuzz MP3
* svg24020    : Librsvg (2.40.20)
* tiff409c710 : Libtiff (4.0.9)
* ttf253      : FreeType (2.5.3)
* wav         : SoX - Sound Exchange (14.4.2) used to fuzz WAV
* xml290      : Libxml2 (2.9.0)

## How to run SoX in this benchmark

The bundled binary is a 32-bit executable at:

`sox_llvm_asan/afl-build/bin/sox`

It needs the local runtime libraries in `sox_llvm_asan/i386-linux-gnu`.

From this directory (`benchmarks/igor-sox`):

```bash
export LD_LIBRARY_PATH="$PWD/sox_llvm_asan/i386-linux-gnu:$PWD/sox_llvm_asan/afl-build/lib"
./sox_llvm_asan/afl-build/bin/sox --help
```
