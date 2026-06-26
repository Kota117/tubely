# Helpful things to remember
This section is not neccessarily for documenting specifics to this project, but more about little tidbits I have learned during this course.

## Inspecting binary files
`samples/boots-image-horizontal.png` can be viewed in any image viewer and even directly in VS Code. The [hexdump](https://en.wikipedia.org/wiki/Hex_dump) can be viewed using [xxd](https://linux.die.net/man/1/xxd):
```bash
xxd <file>
```
`xxd` converts the binary content of the file into a human-readable hexadecimal and [ASCII](https://en.wikipedia.org/wiki/ASCII) formats. Running the above command displays the raw PNG bytes. The first 8 bytes can be inspected with the `-l` (length) option:
```bash
xxd -l 8 <file>
```
The first 8 bytes are the [PNG file signature](https://en.wikipedia.org/wiki/PNG#File_header) (89 50 4e 47 0d 0a 1a 0a), and the characters `PNG` are present in bytes 2-4.
```text
00000000: 8950 4e47 0d0a 1a0a                      .PNG....
```
