CC         = gcc
CFLAGS     = -Iinclude -std=c89 -Wall -Wextra -pedantic-errors
AR         = ar
ADEPT      = adept
ADEPTFLAGS = -e

Q         = @

SRCS      := $(shell find . -name "*.c" -print -type f)
OBJS       = $(patsubst %.c, %.o, $(SRCS))

.PHONY: all test clean

all: libhello.a

libhello.a: $(OBJS)
	$(Q) echo [Linking] $@
	$(Q) $(AR) -rcs $@ $(OBJS)
	$(Q) echo done

test: test/main.adept
	$(Q) echo [Compile] $<
	$(Q) $(ADEPT) $(ADEPTFLAGS) $< -o main
	$(Q) echo done

clean:
	$(Q) rm -f $(OBJS) main libhello.a

%.o: %.c
	$(Q) echo [Compile] $<
	$(Q) $(CC) -c $< -o $@ $(CFLAGS)
