PKGTITLE=puppet-sqlite3
PKGVERSION=1.3.11
PKGID=com.github.clburlison.puppet-sqlite3
# SIGN=--sign "Developer ID Installer: Clayton Burlison"

all: clean build

clean:
	rm -rf pkgroot
	rm -rf out
	rm -rf repo

build: install
	mkdir -p pkgroot/Library/Ruby/Gems/2.0.0
	mkdir -p out
	cp -R repo/* pkgroot/Library/Ruby/Gems/2.0.0/
	pkgbuild --root pkgroot --identifier ${PKGID} --version ${PKGVERSION} ${SIGN} --ownership recommended out/${PKGTITLE}-${PKGVERSION}.pkg

install:
	gem install sqlite3 -v ${PKGVERSION} --platform 'Darwin' -i repo -N