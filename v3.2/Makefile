REPODEST=$(PWD)/pkgs/

build: build-nodejs build-libuv

build-nodejs:
	cd nodejs/
	abuild checksum
	REPODEST=$(REPODEST) abuild -r
	cd ../
