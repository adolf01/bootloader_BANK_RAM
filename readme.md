# P65 Bootloader
You need "build" package installed in ATOM
F9 for build
and run makefile.bat for finish, or run makefile.bat it will do its thing. :D
We already have a functional jump table, which greatly simplifies the programming of other applications for the P65.
The routines are stored at from $ FF00 and for now are as follows:
p65.inc in include folder:

CHROUT	:=	$FF00	;	print CHAR from regA

CHRIN	:=	$FF03	;	get CHAR from buffer to regA

PRNTLN	:=	$FF06	;	put new line and a string with start address in regA and regX "lda #<(STRING),ldx #>(STRING),jsr PRNTLN"

PRNTLN	:=	$FF09	;	put a string with start address in regA and regX "lda #<(STRING),ldx #>(STRING),jsr PRNTLN"

SETBNK	:=	$FF0C	;	set bank to number from regA

GETBNK	:=	$FF0F	;	get bank number to regA

SNINIT	:=	$FF12	;	Initialize SN76489 chipwith mute

SNWRT	:=	$FF15	;	write data from regA to sn76489

SHDLY	:=	$FF18	;	very short delay

RST	:=	$FF1B	;	reset to bootloader
