# Compiling a C library to be used in Adept
## Step 1 - Create Archive File

We create the archive file from `hello.c`

## Step 2 - Create Adept FFI

We have the file `include/hello.adept`, which contains the definitions of our library and what files we need to link to.

##  Step 3 - Import "Header"

From our test application, we import `include/hello.adept`, and then we can use the definitions like normal.

## Step 4 - Compiling Test Program

No command-line arguments are needed to compile the Adept test program. Just plain `adept` will build it.

