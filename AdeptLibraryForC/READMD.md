# Compiling Adept Library to be used in C

## Step 0 - Creating the Library

We define the function hello and mark it as `external` in order to make it visible to outside world.

```
hello :: external func() void {
    printf("Hello World, from library!\n")
}
```

### Step 1 - Creating the Object File

We use `adept -c hello.adept -o hello.o` to compile the root file of our library into an object file.

## Step 2 - Creating the Archive

We use `ar rcs libhello.a hello.o` to create an archive from our object file.

## Step 3 - Creating Header

We need to create a header in order for C to know what definitions we have in the library. So we have `include/hello.h`.

## Step 4 - Using the Library

We can access our library's definitions from C by including the header, `include/hello.h`. In order to build the C program, we have to compile and link it to `libhello.a` as expected.