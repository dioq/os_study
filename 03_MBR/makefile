
mbr_img=mbr.img

mbr:
	nasm -o mbr.bin mbr.S

img:
	dd if=./mbr.bin of=${mbr_img} bs=512 count=1 conv=notrunc

qemu: mbr img
	qemu-system-x86_64 -m 32M -smp 1 -cpu pentium -hda ${mbr_img}

bochs: mbr img
	bochs -f .bochsrc

# all: mbr img

clean:
	@-rm -rf mbr.bin ${mbr_img}
