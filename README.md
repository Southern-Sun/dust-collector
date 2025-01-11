# dust-collector
Makes old files collect dust

# Purpose
This set of programs is designed to take the real world concept of dust collecting on untouched
items and apply it to files and folders on a computer. Over time, files collect dust and become
"dusty", making them difficult to use until they are "dusted off".

# Features
After a file has not been modified or opened for an extended period of time, this program will
replace that file with a *.dusty file. A .dusty file is a custom archive format which contains a
base-64 encoded JSON string describing the file and any metadata it had prior to becoming dusty,
such as ctime, mtime, permisions and so on (everything needed to exactly recreate the file). After
the metadata header, the file will contain a delimiter, then an archived (compressed) copy of the
original file as a bytestring.

Files that remain dusty for an extended period of time will become increasingly dusty:
- Original file names will become dusty (replaced with a random base64 string)
- File icons will become dusty (replaced with pictures of cats)
- Files will be encrypted with an RSA-512 encryption key. This key will be stored in the same
directory and itself made dusty.

When every file in a directory becomes dusty, the entire directory will become dusty. The program
will replace the directory with an appropriate .dusty-dir file and archive the contents of the 
folder in a similar manner to the above.

Dusty files will open with a second program "Feather Duster". This program provides a game-ified
experience for dusting off files. Depending on the level of dustiness that a file has reached, the
program will provide an interactive dusting experience. Once a file is dusted off, it will be 
returned to normal. As a user dusts of more files, they will gain experience, which can provide
rewards such as "dust covers", which prevent a file from becoming dusty. This program runs on the 
Godot game engine.

# Installation
This suite of programs provides a fully featured installation wizard for both Windows and Linux.
The wizard will allow users to specify directories that can become dusty, as well as the maximum
level of dustiness that can be reached by any file.
