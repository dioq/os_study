
mbr:
	nasm -o mbr.bin mbr.S

qemu:
	qemu-system-x86_64 -fda mbr.bin

all: mbr qemu

clean:
	@-rm -rf mbr.bin
