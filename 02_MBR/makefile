
mbr_img=boot.img

mbr:
	nasm -o mbr.bin mbr.S

img:
	dd if=./mbr.bin of=./${mbr_img} bs=512 count=1 conv=notrunc

qemu:
	# qemu-system-x86_64 -hda ${mbr_img}
	qemu-system-x86_64 -m 32M -smp 1 -cpu pentium -hda boot.img

all: mbr img qemu

clean:
	@-rm -rf mbr.bin ${mbr_img}
