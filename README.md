EDFlib is a programming library for C/C++ for reading and writing EDF+ and BDF+ files.
It also reads "old style" EDF and BDF files.
EDF means European Data Format. BDF is the 24-bits version of EDF.

The library consists of only two files: `edflib.h` and `edflib.c`.
The file `main.c` can be used to compile a program that demonstrates the working and
capabilities of the library. Use it as follows:

`test_edflib <filename> <signalnumber>`

The program will print the properties of the EDF/BDF-header, the annotations and
the values of 200 samples of the chosen signal.

The file sine.c is another programming example. It will create a BDF+ file containing
the signal "sine", a 1 Hz sinoidal waveform with a samplefrequency of 2048 Hz.

The file `test_generator.c` shows how to use most of the functions provided by the library.

To view the results use EDFbrowser:  http://www.teuniz.net/edfbrowser/


In order to use this library in your project, copy the files `edflib.h` and `edflib.c` to
your project. Include the file `edflib.h` in every sourcefile from where you want
to access the library. Don't forget to tell your compiler that it must compile
and link `edflib.c` (add it to your makefile or buildscript).
`edflib.c` needs to be compiled with the options `-D_LARGEFILE64_SOURCE -D_LARGEFILE_SOURCE`.

For example:
```bash
gcc main.c edflib.c -Wall -Wextra -Wshadow -Wformat-nonliteral -Wformat-security -Wtype-limits -g -D_LARGEFILE64_SOURCE -D_LARGEFILE_SOURCE -o test_edflib

gcc sine.c edflib.c -Wall -Wextra -Wshadow -Wformat-nonliteral -Wformat-security -Wtype-limits -g -D_LARGEFILE64_SOURCE -D_LARGEFILE_SOURCE -lm -o sine

gcc test_generator.c edflib.c -Wall -Wextra -Wshadow -Wformat-nonliteral -Wformat-security -Wtype-limits -g -D_LARGEFILE64_SOURCE -D_LARGEFILE_SOURCE -lm -o testgenerator

gcc sweep.c edflib.c -Wall -Wextra -Wshadow -Wformat-nonliteral -Wformat-security -Wtype-limits -g -D_LARGEFILE64_SOURCE -D_LARGEFILE_SOURCE -lm -o sweep
```

To understand how to use the library, read the comments in the file `edflib.h`.

The library has been tested using the GCC compiler on Linux and Mingw-w64 on windows.



