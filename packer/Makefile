all: help

help:
	@echo ""
	@echo "-- Help Menu"
	@echo ""  Makes an image with Ansible and docker in it
	@echo ""   1. make vbox       - your site will be in ../builds

qemu: buildqemu beep

qemudebug: buildqemudebug beep

vbox: buildvbox beep

vboxdebug: buildvboxdebug beep

buildqemudebug:
	/usr/bin/time -v nice ionice -c3 packer build -debug --only=qemu packer-flynn-ubuntu-1404-amd64.json

buildqemu:
	/usr/bin/time -v nice ionice -c3 packer build --only=qemu packer-flynn-ubuntu-1404-amd64.json

buildvboxdebug:
	/usr/bin/time -v nice ionice -c3 packer build -debug --only=virtualbox-iso packer-flynn-ubuntu-1404-amd64.json

buildvbox:
	/usr/bin/time -v nice ionice -c3 packer build --only=virtualbox-iso packer-flynn-ubuntu-1404-amd64.json

beep:
	@echo "beep"
	@aplay /usr/share/sounds/alsa/Front_Center.wav
