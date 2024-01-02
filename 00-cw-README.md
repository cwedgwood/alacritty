
## Background

As of 2023/March Alacritty was quite buggy.  This branch tracks
updatesd to this


This is a version I built locally (cross compiled).  For this reason
the icon isn't strictly correct.

## Steps

    rustup update
    rustup target add x86_64-pc-windows-gnu

## Building

    git clone git@github.com:alacritty/alacritty.git
    cd alacritty

    ( cd alacritty && cargo build --target x86_64-pc-windows-gnu --release )
    /usr/x86_64-w64-mingw32/bin/strip target/x86_64-pc-windows-gnu/release/alacritty.exe

	cp --backup -v target/x86_64-pc-windows-gnu/release/alacritty.exe /net/tmp/
