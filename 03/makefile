c	= postfix.c value.c infix.c
h	= value.h parse.h
m	= parse.c
t	= postfix value infix

postfix	= parse.o postfix.o
value	= parse.o value.o
infix	= parse.o infix.o

all:		$t
clean:				; rm -f $t *.o

test::		postfix		; echo '2 * (3 + 4)' | postfix
test::		value		; echo '2 * (3 + 4)' | value
test::		infix		; echo '2 * (3 + 4)' | infix

postfix::	$(postfix)	; $(CC) $(CFLAGS) -Wl,--allow-multiple-definition -o $@ $(postfix)
value::		$(value)	; $(CC) $(CFLAGS) -Wl,--allow-multiple-definition -o $@ $(value)
infix::		$(infix)	; $(CC) $(CFLAGS) -Wl,--allow-multiple-definition -o $@ $(infix)

include ../make/Makefile.$(OSTYPE)
