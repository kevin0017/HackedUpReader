VERSION=0.4.0

SUPPORTED_DEVICES=-d touch -d paperwhite

all: hackedupreader_${VERSION}_install.bin hackedupreader_${VERSION}_uninstall.bin zip
hackedupreader_${VERSION}_install.bin:
	kindletool create ota2 ${SUPPORTED_DEVICES} install $@

hackedupreader_${VERSION}_uninstall.bin:
	kindletool create ota2 ${SUPPORTED_DEVICES} uninstall $@

clean:
	rm -rf *.bin *.zip hackedupreader_${VERSION}

zip:
	mkdir hackedupreader_${VERSION}
	cp ../../README.md hackedupreader_${VERSION}/README.txt
	mv hackedupreader_${VERSION}_install.bin hackedupreader_${VERSION}_uninstall.bin hackedupreader_${VERSION}
	zip -r0 hackedupreader_${VERSION}.zip hackedupreader_${VERSION}/

hackedupreader.tar.gz:
	cp ../../README.md $(DESTDIR)/mnt/us/hackedupreader/README.txt
	rm -f install/hackedupreader-*.tar.gz
	tar -czf "install/hackedupreader-${VERSION}.tar.gz" -C $(DESTDIR)"/mnt/us/" hackedupreader 
