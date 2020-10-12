
CC         = gcc
CFLAGS     = -Iinclude -std=c89 -Wall -Wextra -pedantic-errors
AR         = ar
ADEPT      = adept
ADEPTFLAGS =
Q          = @

SRC       := src/hello.adept                  # (only root file of library source code)
OBJ        = $(patsubst %.adept, %.o, $(SRC)) # (only makes a single object file)

.PHONY: release clean

release: libhello.a

libhello.a: $(OBJ)
	$(Q) echo [Linking] $@
	$(Q) $(AR) rcs $@ $(OBJ)

$(OBJ):
	$(Q) echo [Compile] $(SRC)
	$(Q) $(ADEPT) $(ADEPTFLAGS) -c $(SRC) -o $(OBJ)

test: test/main.c
	$(Q) echo [Compile] $<
	$(Q) $(CC) $< -o main $(CFLAGS) -lhello -L. -Iinclude
	$(Q) echo done

clean:
	$(Q) rm -f $(OBJ) main libhello.a
