# Third-party software in Toolbox Explorer

## FFmpeg 8.1.2

Toolbox Explorer includes the `ffmpeg` and `ffprobe` programs from
[FFmpeg](https://ffmpeg.org) 8.1.2, in `Contents/Resources/ffmpeg/` inside the app. It runs
them as separate programs.

FFmpeg is the work of the FFmpeg developers, not of Toolbox Explorer's author. It is licensed
under the **GNU Lesser General Public License, version 2.1 or later**. The licence is in
[`ffmpeg/COPYING.LGPLv2.1`](ffmpeg/COPYING.LGPLv2.1), and FFmpeg's own licence summary is in
[`ffmpeg/LICENSE.md`](ffmpeg/LICENSE.md).

This build contains no GPL or non-free parts. It is built from the unmodified FFmpeg 8.1.2
release, configured with:

```
--disable-gpl --disable-nonfree --disable-version3
--enable-static --disable-shared
--disable-doc --disable-htmlpages --disable-manpages --disable-podpages --disable-txtpages
--disable-ffplay --disable-network --disable-autodetect
--enable-zlib --enable-videotoolbox --enable-audiotoolbox --enable-libzimg
--pkg-config-flags=--static --disable-debug
--arch=arm64 --extra-libs=-lc++ --extra-cflags='-arch arm64 -mmacosx-version-min=11.0'
```

### Source

The source for exactly this build is in the `source/` folder of
https://github.com/emmettjez/toolbox-explorer-releases/tree/main/licenses:

| File | What it is |
|---|---|
| `ffmpeg-8.1.2.tar.xz` | the FFmpeg 8.1.2 release, unmodified · SHA-256 `464beb5e7bf0c311e68b45ae2f04e9cc2af88851abb4082231742a74d97b524c` |
| `zimg-3.0.6.tar.gz` | zimg 3.0.6, which this build links statically · git commit `f819b14e8f39d1282400b0d9543e8ef73c1b2bbd` |
| `build-ffmpeg.sh` | the script that builds both, with the configuration above |

The same FFmpeg release is published at https://ffmpeg.org/releases/ffmpeg-8.1.2.tar.xz.

## zimg 3.0.6

`ffmpeg` and `ffprobe` include [zimg](https://github.com/sekrit-twc/zimg) 3.0.6, licensed
under the WTFPL, version 2. The licence is in [`zimg/COPYING`](zimg/COPYING).
