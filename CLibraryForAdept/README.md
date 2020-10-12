# Compiling a C library to be used in Adept
## Step 0 -  Create Object File

We create object file(s) from our library source code. In this case, we use `gcc $(CFLAGS) -c hello.c -o hello.o`.

## Step 1 - Create Archive File

We create the archive file `libhello.a` from `hello.o` by `ar rcs libhello.a hello.o`

## Step 2 - Create Adept FFI

In order for Adept to know which definitions exist in the library, we have to declare them. We have the file `include/hello.adept`, which contains the definitions of our library (`foreign hello() void`) and what files we need to link to (in this case `libhello.a`). Since we tell Adept that the file requires that we link to `libhello.a`, we don't need to specify it when we use library later on.

##  Step 3 - Import "Header"

From our test application, we import `include/hello.adept`, and then we can use the definitions like normal.

## Step 4 - Compiling Test Program

No command-line arguments are needed to compile the Adept test program. Just plain `adept` will build it.

