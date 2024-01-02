
default: install

chk:
	cargo check --target x86_64-pc-windows-gnu --release

build: chk
	cargo build --target x86_64-pc-windows-gnu --release

install: build
	/usr/x86_64-w64-mingw32/bin/strip target/x86_64-pc-windows-gnu/release/alacritty.exe
	cp --backup -v target/x86_64-pc-windows-gnu/release/alacritty.exe /net/tmp/

	# https://stackoverflow.com/questions/18287960/signing-windows-application-on-linux-based-distros

	# this doesn't work without having to enter a password, also
	# the MOK cert probably is NOT the one i want

	# osslsigncode sign \
	# 	-certs ~/wk/linux/certs/mok/MOK.der \
	# 	-key ~/wk/linux/certs/mok/MOK.priv \
	# 	-n "Alacritty unofficial cross by cw" \
	# 	-i https://f00f.org/ \
	# 	-in target/x86_64-pc-windows-gnu/release/alacritty.exe \
	# 	-out /net/tmp/alacritty-signed.exe

clean:
	rm -vf *~

realclean: clean
	cargo clean
