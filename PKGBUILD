# Maintainer: csmantle <aur at csmantle dot top>
# Contributor: Jan Alexander Steffens (heftig) <heftig@archlinux.org>
# shellcheck shell=bash disable=SC2034,SC2154,SC2164

pkgbase=linux-csmantle
pkgver=6.19.13.arch0
pkgrel=1
pkgdesc='Linux'
url='https://github.com/archlinux/linux'
arch=(loong64)
license=(GPL-2.0-only)
makedepends=(
  bc
  binutils
  cpio
  gettext
  glibc
  libelf
  libgcc
  openssl
  pahole
  perl
  python
  rust
  rust-bindgen
  rust-src
  tar
  xxhash
  xz
  zlib
  zstd

  # htmldocs
  graphviz
  imagemagick
  python-sphinx
  python-yaml
  texlive-latexextra
)
options=(
  !debug
  !strip
)
_srcname=linux-${pkgver%.*}
_srctag=v${pkgver%.*}-${pkgver##*.}
source=(
  https://cdn.kernel.org/pub/linux/kernel/v${pkgver%%.*}.x/${_srcname}.tar.{xz,sign}
  # FIXME: -arch0 packages have no prepacked patches
  #$url/releases/download/$_srctag/linux-$_srctag.patch.zst{,.sig}
  config  # the main kernel config file
)
validpgpkeys=(
  ABAF11C65A2970B130ABE3C479BE3E4300411886  # Linus Torvalds
  647F28654894E3BD457199BE38DBBDC86092693E  # Greg Kroah-Hartman
  83BC8889351B5DEBBB68416EB8AC08600F108CDF  # Jan Alexander Steffens (heftig)
)
b2sums=('bd6ae85226bcbaba096c64d5cd20ad18d24e9fb5484394ce7db27326d37da500ffdc7bd765493a0a167944836be7275bb84807991a0266f072c0d87ec5df84b3'
        'SKIP'
        'bef3377ad86440af76e9dde4c29c9f4aaad42f5fe343f7d31f5eb537d6d358602f996f5d63986af275f2e92f94e71dc28c320edc8c03d05bd64dbd8ed23d75dc'
        'dfd366b283243f95c318471fe35e3a36646a38388dd6c4d9746bc981985a02ea303d75127244e9feac14564a8f49385483dfb56a8842814bdf97ca747bc2a4d5'
        '46f0fd181d20e8ba9e535264b443517c9a41700491f96a80d20f357d721c32652299c71949929c364b6471a7bb4bb6a09dde60fe1e3ad2fe4faa8a52708b49c0'
        'bbf688fda3b1e0f24faaacaa3dd757a9539daddc0d7a4b83f465a1583571344f9cb0b4c088da9ff0f93e3469956b39ed45d393450858fa8f15e2f68a22d4f333'
        '2f2e68003cbbbbd1ce65085f4134bdc162695b58bfa5095958ac8d97e001eb940c3e34a9f6c064ad3cff2f12cf35ebc6e33f3d9b3fda86b37de02c64c3a20c7c'
        '93aca6f7163c6e651e86f68114dc43116feb61b4fe8e7b4e0f6520dfdc490b1d458ccae4cc1f935082d389a80a2df0b4a9a963068740f6c3a8fa1b40a31487de'
        '07f44a85f0fa61d352ff3ac44712aa32e4d2654962d9eff8983b0ef1a1d423b5801c3cb056667f88c5461946bd4ccaff13599b3e4b7f211d5ca1e4febc3a0aab'
        '72e5d15ba7df2bf057828ae68088ec7f5e9f580598316dae770e78bc3e369a04eaa8c49f8f3ff1239aac3e19e04f1ffafd4ac5eb212adaedbf969311910beb6b'
        '9ade2c26aa3d0ed78da77b91780caebfc1c4407a56436329fcd8235b36cb8e39afe85dc13d1c4a53071af157bffaca30431a7b161afb56c7306107bfa909cdee'
        '0c641d27b51ef4ff6fafaf00e6e214eea8076502ed116230532703ada66b784d29b115789f0d02ddf89392b274be792494082e0454d75b4759fdaffda585bfdd'
        '073eadd1b30ce87e470d8dd5cc8479e74182ca7440ebf2493cd83027e7488cdf594e77d2d08354159594106bfaedb92dae1b442931a2b212a72f8be469eeffb0'
        'be285965137997bf380d2635a84a3c80023c450724d6ed930c716b5d9d3fdf6f902825cbd67c5e1e0a2d4ad8883339708dba87a60fb663137cb2020ce92e51b0'
        'ec3d3ff9b56e554f8c031540330f0de75b88faa6afd3f52344d0affff7732cb8e5cfb2ba32af8c6ef6e3afd4daa721767b35c0b8e39d74613559d2bf4170cca3'
        'e37a26983153e0f4fc9741f654176c07a386de5ba3a305b15ee598d95196c2bf2d55e04e4467e54d9efa747b1f24db56732e21666e7d7b1cbabbe9221f1f21c5'
        'a8b19fbeee6257d9286e43db15a6524fd2c248b9395509c16b8a2f4e47e692e0e0ccaae210caacaae9da63d4e8f6e8c6610317ca9d2979f13142f16adb5fd603'
        '25b402e9d998dbc881495fcbd38663df74fccf874869043e799190ca5210cfdad145609e7ad0724b6114f9b7452a3391d4a777e21a7b022816577da4ddf0bea8'
        '974f0f297d86658e2c50734e31ce30d9983b0df414450d0fe8cf2497c2a866ae1135ad41c9e8bfa1d0ab8edb6f7edb7f442b0aee095b036c9677caccfa56b7ce'
        '708ac5aeae4229487b26a3b0204e2b127cc179d2b819ef936293d55995b4de0519e36a10e6a2cceda6a0d2861a79587a9ea58af2137ce73152607473f6aee1d4'
        'fb2c4232db9b6dfabdab7635ded223d5c3d3723dd59a8fa4c49219ec0a6350bb486449e5ded3997a94a14f1ce32dbe559c787a4b0dec9613a4df7ad0d454edc1'
        '25c0d52e76dd958f9cb0e417f0e5053f46d291621f5783b05aada3e997ba5423bc2062bfb9639f7ccbbfbc8faa3a217ccf8a6a6fa1a934ca64548d4b1f5f6830'
        'f81089969603ce04853a7db813c5a4309eff95043ddb8623e1e6d876500c13651dc940aaf984dc93c7f3e5950922d0eeb1352bce5ec82c060b326e403aec3b67'
        '129fd91557fa4e495c305b632c7afd833fbafbefdb08f6e351e02d41718201c5ebddeac7e48a493d24668d6438aed80964437672fb830b4a1e593c5e12f199dc'
        'c5821c2b235cc75153904ffc65de82e164f266d0bd58e4466d969df1f2f3d080b110342ff7b5822c398e82b7eac03e06360f6cd8392e52538a329ce6a42edcc9'
        '9b912c944f62ad8214f0424b99ddfaa2c722e3341d4c657a03a6ab4ce968c29847eb7ca9c4196985f73f1708f1dbf41139b3e1b39ce03eebd9e4e3200a686d2b'
        '83b75e3b23a59cb1ba9d3e7814db799d0bc40db322276d5345be4027896412aa7634e2c9c0c1206f856fb5cc7cef6de6366c89e535e67419453580b2a7ba65a5'
        '6ff0d1533b8fdf35d816b3af0c52410dfb93ecc700998550da7c7c9cb1cbfce66002e380028453ba46baa5a6e0612ed71a7ef1b4932eda8324a3dd171b2f0ffd'
        '854e169a8b9d0c66365a0e0d51a366c9d92a87123154ce0e903dd37b080ffff5673071f52f0ea045d9f74c4b11b947a0a2f74819c1351a7835b9bcabd8591e0e'
        '57c205af1b15e451d5a1a9d5bd4c5f7ddaf482ed5bda755af8353c368f055803430537d8b7a9e977c36f9e6a3de0daaffe07f6448b997d16127939e724a14637'
        'ffed9ff7d381fc22498bf0e58214e052c16167117f9a486f286bac4cbbb834580025b6ecc16eb2a122ee00b4c0a1fa1969540b2b992f626822f6e055f97731fc'
        '963c39b79b0ffe42851e65d18ef46e970c080f4624eb019b58691fdd0df8c0a9f5986f951e6d291b828cbe94df74c8ce05a575ecf2936b93a2aef0454a8cb111'
        '6f83e408690f6ea1a84c37c453962cb84a2a223a76d0c8966ccecec317968535e5411637a2ce40e21714654475edf0cd690aabd03093b77e66e874b7d1119ad6'
        '829a1947799baa3e3d96449456d83d185628a9f43c920cd0a2068a9575252250cf142712b0c6e4b1ed18634d01d53d9549461d19ef4e7495700849ab7bb02d8d'
        '4e8b635b1f4959eeade08e187d84049477a3abdba4a679969a0395bf80ac9f7f2eb52e647f9b8ccba3ceccc6ebe93b084dcaefea7f2bb3b87c5f5022e03012ed'
        '4e079ab644c5c7732a97aaf08841a36d80b4fda5c060ff06bbf4477a9444210faf36c3f4d568507f1c5a6257743033a37c7d403a998c25c728fb67c87f8593eb'
        '24fd49ef5dca9fb5d2747c90bf1771455126e1439db7f191f2dc5508dfa203df3897de44ebdcd96f42c975c6f7783963ed09600344958ed2a975ac323016720b'
        'f89f685030a783a8429bfe058942cc3e1c53dc3a34e5566f8d0797dda0dd9e21ac4b32fc85621b649c216205d62f54d02110d000d9a3ae6cf69a65610f09bf48'
        '88e059c472dd6f5f3483eb699d705e0726838bca1a1dd66096810954abd919f70e3f16aab1d56ad6307af03a4f020aae99e5050a695553765ee0cdea0614eea0'
        '5f41b8486d1b32e50119da9bb63d5faace760859e499f542f6e902fac463c7d9ed41505b481a265bea1b1443c8675c7ad4bc2ee7971067bea92dc2407a8b7d15'
        '69206432987192ab94c3243405873d7988fc87dcfd64e1591abec2e3b702e255dacd6e03449bfeeca30bee91f03897e545640711d73e491377dde8466e28e921'
        '68cde68e95518b68e7180cf3d6f30db9a92b710bb8170ab994c467b37ab2730507fb97bb774fe473bb2720f93940fe9ea5eec116263a1f53fba6efa0dac33d87'
        'a2127f6a43da3de4a0245f4a79bf8d228730d8e4568ed7f72e03f396a1214f8bdecb61894c1d360acce7cef2d35b3142867ea89f0f5ef1b9162baadce9021c8d'
        'cace780aa9057812b4148547ee2fef087d40350eac3ee7119ef349a521efd362dff2c3db67c1d861df17f02a4ee5ab5690162d347b947fb820d457f256abd255'
        '5f1904b5aabef57aa538721d2542ae78e2463b8e013f7a59ae31e12762c958faac16d0e4f8d7686495610b98a21799597f7dd39ae42c39e65b6ed030242a62f1'
        '71ab5eb1410c748e4921e3434b7218d5d1e9732126a1721e8ac78f5495e01f3045d29af5f5983c437e35d66b1c8d7237318cea19a125db36cb29e8e0720b77d0'
        'b025ab75bc1ebb100592d1934534f94cbe167123a0689631a5a97d246f01fcc2613918d0dd856ad2f7c73f15b4e0153256985e0a21e706e2ae249c6aa6224fb9'
        '9551f0f15b315805051f7a1a17615397e326f8d0fde83753bedbac80057fe76e01fd8e56e342bf1e6904e13f478c4150402f1ffb5abb469709e5b349384d0b48'
        'aad3ef47fd568b02ae50e6511358cf5279628491e2da40934d91af2fe002509855ee04d926d4dc99e7ff73627a8e5f3554a55c9c886f076532d1af0782b330da'
        '5b18977eeef3546ecbccfc0933123ca1ba3bfb334a3438fe72b839340e6c7270c7af70e890019fa80908956b4705fcc67a55b2812e6bb12ea65d863a3dee9e4a'
        '2c0c3af3855f7675f2a8b912ca52d92a0fd5089e42f9cadc30d6e2041adcc1d1dd6e610bb0718fac89274959da9a47fca35f1671617944bc8353d50d6ff96c5a'
        '2d0dfb3d987af48f74727cd2c701c6aa00d09441df731717ff3726dfec81685c7988e940a6419f82e14f60deef721c7e123a3bf37aebcccc82bd4855adb2238c'
        '7cae96b878bb7ea4c253477467f011bd5972b4b911e9db59b3fb42731d7b983cdf74a9092dce1f26807265855df7be10ba79c8a381233f4dd13a43d6a97f6706'
        '004e3e434201384c34bf9b2ec5eef987708ebe659c227c3e6268b65edfafa5cc37ae8757305777efce014ed74435a2c41838a3b15194fe9b4cb0971167fdab5b'
        'e0e0acf742167a16fe17b8e1f2995686d41fefd408873ed0528698218218cc13abdfd761b01b104b1ef6ef8ed6eeac4883737bf6df8087f2ea46ef6648765ee4'
        'b72a268f73f0befc678aec9ca1fc0973c987be03c83bcb95eb923403f0a14a46d305f127b89b97fa00614359b1888554a35c2b28ddca7b819fd28fe02c2c978f'
        '290e18ddfc00ed6ac69a35f43ca8d37b9a5013bd0dceef8f7180db1979b64e1b1f4c0763fba45f743020b2eddd169981aa5ff45f9ebdace780df88bce3f5cdc8'
        '06bf5d8c049726d23298fdc6d7e545d614acff7750a811c01a9523235c43c6008c358c66804812ad8139ed20ca1c00ec56d4da6c6274e5d389e98e8ac0f56901'
        '826c08627756d33d0bb6c7cacddcd3ef2c7f98d09b8a0ceb214e0cd0e2ba66311b098a2e76c29a183e17d964235cb46a75601d121b8e76e22a83a41876efc278'
        '348e089aed132678fe36da9cf75e1ddb0d94849570fa79f92c38e40f44211663e8dfab2870f288139766a19d9eee5a2a13ef5f4a177e1b86fd4368a6912fedaf'
        'da8fba29ec86833e73c03abff5956485121b8acaeb7df60a9be79c2f350cef73172df552c0386e9484ba501da3b987425c9445f2cce7a2ed2b0d0daceb31fd5d'
        'eedfb39cdb976e2faba7a59090b1b73556e2c5ead411b1cf3cfa925c0ae2f32fe866f98f24c1f4e2d9e7445c7271c83a650cb80b54be38e2cdc8b5738c71d3ed'
        'ef8c29ab3fe85d32a5ea85b73ecba7cd75acdc5d9c03b7268fe44281eb81e3f2f8b373ed5d2533d1de6c7ae0ba41a430c0ccd3a0ddb119354a259078366a2cb3'
        '73369d1d32e65204a86f0d1e78700b6fbdf268922e752c9944297c2cb458e138c3a0e062b47cf9615efbbfdfb1e3432fb1c8f323f8620504d6cfa40d80b143f7'
        '6d69a3a96166f58219b11b0aa92e1339d0832f79e285704702aef9fdfeeae7bdb9c4da3368cbca1afa9a5bc880cfe54073614ecbdab8ee2be64cd142974e9c37'
        '9b44a45b86c8914841b52cd99f22812bfde0d715c6452a176457d1ea8cebf2f2d73100a8d160d295d6a3bfdda6f02689101f4d54ed15ba6fd32216b83eb8a990'
        '190f7bac6ef3abe0a347138e8432f29342aae09d659363ebb2d3d3d9a511c6c6349741f3f21b1d966fc970b4aa21878060bcf03691b0870ed1a21623a898b6f1'
        'eea7469f8ed1c3285daf5be7bed7abfae8847bc934e225a87d5c2f17d4e5f0278936841eff40e62fb20dd433478a4b554c6a40d035d3746ab48e5246d9f0a5a4'
        '61516e95bcf435101b6f1f0334a467bf68807dd3dd9967bcc127137079aa66e9507de4a6805580fc687ee8b8a5ad798dc618cc865dea8e4281239946dfec1ae2'
        'fbcc144a3bcf0f638dec81587d256edc4b9219cb49ab4cc5a4c71d7cd6997d4327d972b6fdf9fea5b58dc55ade1019ffab807c12483c18293777b37d18222bf8'
        'ce6e43020e0c69f6459ce02310aafcb602ffdde464401c357787347780a898051c81754804e30ff0a753560c948ab588858245abcb9a5863534b5426c1445fc5'
        'fcdf79dac79739b88d7595d429c74ae52cd9962bd1c084b9e293dbf53e8f5ce146ac0577b92e655ccebdca474099a1eda37b3114fd505b0bc926d61575d6cc34'
        '8d19f610226eaf56874468748ac0595c10807030bc070c4cfc3529308750fb64514550cc11d7049eb0a25b504f5246f8e7b36d57d28f732a4d4848352646b3d7'
        '81954a22c00d32fb2eb145a1da7076a5e014ca26af321db5dd942c7d01dbbb8dee83d4f694c1f590e3496ed6c31587965051afe6f1a49fca969f104bb1870d49')

export KBUILD_BUILD_HOST=archlinux
export KBUILD_BUILD_USER=$pkgbase
export KBUILD_BUILD_TIMESTAMP="$(date -Ru${SOURCE_DATE_EPOCH:+d @$SOURCE_DATE_EPOCH})"

prepare() {
  cd $_srcname

  echo "Setting version..."
  echo "-$pkgrel" > localversion.10-pkgrel
  echo "${pkgbase#linux}" > localversion.20-pkgname

  local src
  for src in "${source[@]}"; do
    src="${src%%::*}"
    src="${src##*/}"
    src="${src%.zst}"
    [[ $src = *.patch ]] || continue
    echo "Applying patch $src..."
    patch -Np1 < "../$src"
  done

  # Ensure amdkfd is avaliable
  sed -i '/^[[:space:]]*depends on DRM_AMDGPU && (/ {
    /LOONGARCH/! {
        s/)[[:space:]]*$/ || LOONGARCH)/
    }
  }' drivers/gpu/drm/amd/amdkfd/Kconfig

  echo "Setting config..."
  if [ $CARCH == loong64 ]; then
    ./scripts/kconfig/merge_config.sh \
      "$srcdir"/config \
      "$srcdir"/001-aosc-loongarch64-16k.frag.config \
      "$srcdir"/002-local.frag.config
  else
    cp ../config .config
  fi
  make olddefconfig
  #make listnewconfig
  #make menuconfig
  make prepare

  make -s kernelrelease > version
  echo "Prepared $pkgbase version $(<version)"
}

build() {
  cd $_srcname
  make all
  make -C tools/bpf/bpftool vmlinux.h feature-clang-bpf-co-re=1
  # make htmldocs SPHINXOPTS=-QT
}

_package() {
  pkgdesc="The $pkgdesc kernel and modules"
  depends=(
    coreutils
    initramfs
    kmod
  )
  optdepends=(
    'linux-firmware: firmware images needed for some devices'
    'scx-scheds: to use sched-ext schedulers'
    'wireless-regdb: to set the correct wireless channels of your country'
  )
  provides=(
    KSMBD-MODULE
    NTSYNC-MODULE
    VIRTUALBOX-GUEST-MODULES
    WIREGUARD-MODULE
  )
  replaces=(
    virtualbox-guest-modules-arch
    wireguard-arch
  )

  cd $_srcname
  local modulesdir="$pkgdir/usr/lib/modules/$(<version)"

  echo "Installing boot image..."
  # systemd expects to find the kernel here to allow hibernation
  # https://github.com/systemd/systemd/commit/edda44605f06a41fb86b7ab8128dcf99161d2344
  install -Dm644 "$(make -s image_name)" "$modulesdir/vmlinuz"

  # Used by mkinitcpio to name the kernel
  echo "$pkgbase" | install -Dm644 /dev/stdin "$modulesdir/pkgbase"

  echo "Installing modules..."
  ZSTD_CLEVEL=19 make INSTALL_MOD_PATH="$pkgdir/usr" INSTALL_MOD_STRIP=1 \
    DEPMOD=/doesnt/exist modules_install  # Suppress depmod

  # remove build link
  rm "$modulesdir"/build
}

_package-headers() {
  pkgdesc="Headers and scripts for building modules for the $pkgdesc kernel"
  depends=(
    binutils
    glibc
    libelf
    libgcc
    openssl
    pahole
    xxhash
    zlib
    zstd
  )
  provides=(LINUX-HEADERS)

  cd $_srcname
  local builddir="$pkgdir/usr/lib/modules/$(<version)/build"

  echo "Installing build files..."
  install -Dt "$builddir" -m644 .config Makefile Module.symvers System.map \
    localversion.* version vmlinux tools/bpf/bpftool/vmlinux.h
  install -Dt "$builddir/kernel" -m644 kernel/Makefile
  if [ $CARCH == x86_64 ]; then
    install -Dt "$builddir/arch/x86" -m644 arch/x86/Makefile
  elif [ $CARCH == loong64 ]; then
    install -Dt "$builddir/arch/loongarch" -m644 arch/loongarch/Makefile
  fi
  cp -t "$builddir" -a scripts
  ln -srt "$builddir" "$builddir/scripts/gdb/vmlinux-gdb.py"

  # required when STACK_VALIDATION is enabled
  install -Dt "$builddir/tools/objtool" tools/objtool/objtool

  # required when DEBUG_INFO_BTF_MODULES is enabled
  install -Dt "$builddir/tools/bpf/resolve_btfids" tools/bpf/resolve_btfids/resolve_btfids

  echo "Installing headers..."
  cp -t "$builddir" -a include
  if [ $CARCH == x86_64 ]; then
    cp -t "$builddir/arch/x86" -a arch/x86/include
    install -Dt "$builddir/arch/x86/kernel" -m644 arch/x86/kernel/asm-offsets.s
  elif [ $CARCH == loong64 ]; then
    cp -t "$builddir/arch/loongarch" -a arch/loongarch/include
    install -Dt "$builddir/arch/loongarch/kernel" -m644 arch/loongarch/kernel/asm-offsets.s
  fi

  install -Dt "$builddir/drivers/md" -m644 drivers/md/*.h
  install -Dt "$builddir/net/mac80211" -m644 net/mac80211/*.h

  # https://bugs.archlinux.org/task/13146
  install -Dt "$builddir/drivers/media/i2c" -m644 drivers/media/i2c/msp3400-driver.h

  # https://bugs.archlinux.org/task/20402
  install -Dt "$builddir/drivers/media/usb/dvb-usb" -m644 drivers/media/usb/dvb-usb/*.h
  install -Dt "$builddir/drivers/media/dvb-frontends" -m644 drivers/media/dvb-frontends/*.h
  install -Dt "$builddir/drivers/media/tuners" -m644 drivers/media/tuners/*.h

  # https://bugs.archlinux.org/task/71392
  install -Dt "$builddir/drivers/iio/common/hid-sensors" -m644 drivers/iio/common/hid-sensors/*.h

  echo "Installing KConfig files..."
  find . -name 'Kconfig*' -exec install -Dm644 {} "$builddir/{}" \;

  echo "Installing Rust files..."
  install -Dt "$builddir/rust" -m644 rust/*.rmeta || true
  install -Dt "$builddir/rust" rust/*.so || true

  echo "Installing unstripped VDSO..."
  make INSTALL_MOD_PATH="$pkgdir/usr" vdso_install \
    link=  # Suppress build-id symlinks

  echo "Removing unneeded architectures..."
  local arch
  for arch in "$builddir"/arch/*/; do
    if [ $CARCH == x86_64 ]; then
      [[ $arch = */x86/ ]] && continue
    elif [ $CARCH == loong64 ]; then
      [[ $arch = */loongarch/ ]] && continue
    fi
    echo "Removing $(basename "$arch")"
    rm -r "$arch"
  done

  echo "Removing documentation..."
  rm -r "$builddir/Documentation"

  echo "Removing broken symlinks..."
  find -L "$builddir" -type l -printf 'Removing %P\n' -delete

  echo "Removing loose objects..."
  find "$builddir" -type f -name '*.o' -printf 'Removing %P\n' -delete

  echo "Stripping build tools..."
  local file
  while read -rd '' file; do
    case "$(file -Sib "$file")" in
      application/x-sharedlib\;*)      # Libraries (.so)
        strip -v $STRIP_SHARED "$file" ;;
      application/x-archive\;*)        # Libraries (.a)
        strip -v $STRIP_STATIC "$file" ;;
      application/x-executable\;*)     # Binaries
        strip -v $STRIP_BINARIES "$file" ;;
      application/x-pie-executable\;*) # Relocatable binaries
        strip -v $STRIP_SHARED "$file" ;;
    esac
  done < <(find "$builddir" -type f -perm -u+x ! -name vmlinux -print0)

  echo "Stripping vmlinux..."
  strip -v $STRIP_STATIC "$builddir/vmlinux"

  echo "Adding symlink..."
  mkdir -p "$pkgdir/usr/src"
  ln -sr "$builddir" "$pkgdir/usr/src/$pkgbase"
}

_package-docs() {
  pkgdesc="Documentation for the $pkgdesc kernel"

  cd $_srcname
  local builddir="$pkgdir/usr/lib/modules/$(<version)/build"

  echo "Installing documentation..."
  local src dst
  while read -rd '' src; do
    dst="${src#Documentation/}"
    dst="$builddir/Documentation/${dst#output/}"
    install -Dm644 "$src" "$dst"
  done < <(find Documentation -name '.*' -prune -o ! -type d -print0)

  echo "Adding symlink..."
  mkdir -p "$pkgdir/usr/share/doc"
  ln -sr "$builddir/Documentation" "$pkgdir/usr/share/doc/$pkgbase"
}

pkgname=(
  "$pkgbase"
  "$pkgbase-headers"
  # "$pkgbase-docs"
)
for _p in "${pkgname[@]}"; do
  eval "package_$_p() {
    $(declare -f "_package${_p#$pkgbase}")
    _package${_p#$pkgbase}
  }"
done

source+=('001-aosc-loongarch64-16k.frag.config'
         '002-local.frag.config'
         '0001-add-sysctl-to-allow-disabling-unprivileged-CLONE_NEW.patch'
         '0002-udmabuf-Do-not-create-malformed-scatterlists.patch'
         '0003-Arch-Linux-kernel-v6.19.13-arch0.patch'
         '0004-BACKPORT-FROMLIST-drm-Makefile-Move-tiny-drivers-bef.patch'
         '0005-FROMLIST-drm-radeon-Call-mmiowb-at-the-end-of-radeon.patch'
         '0006-FROMLIST-LoongArch-Update-the-flush-cache-policy.patch'
         '0007-FROMLIST-USB-core-Enable-root_hub-s-remote-wakeup-fo.patch'
         '0008-FROMLIST-scsi-Bypass-certain-SCSI-commands-on-disks-.patch'
         '0009-FROMLIST-PCI-Use-local_pci_probe-when-best-selected-.patch'
         '0010-FROMLIST-PCI-Prevent-LS7A-Bus-Master-clearing-on-kex.patch'
         '0011-FROMLIST-RFC-drm-amdkfd-disable-HSA_AMD_SVM-on-Loong.patch'
         '0012-BACKPORT-FROMLIST-drm-ttm-save-the-device-s-DMA-cohe.patch'
         '0013-BACKPORT-FROMLIST-drm-ttm-downgrade-cached-to-write_.patch'
         '0014-FROMLIST-PCI-Release-BAR0-of-an-integrated-bridge-to.patch'
         '0015-FROMLIST-mailmap-map-all-Icenowy-Zheng-s-mail-addres.patch'
         '0016-FROMLIST-net-phy-motorcomm-Support-YT8531S-PHY-in-YT.patch'
         '0017-FROMLIST-net-stmmac-Add-glue-driver-for-Motorcomm-YT.patch'
         '0018-FROMLIST-MAINTAINERS-Assign-myself-as-maintainer-of-.patch'
         '0019-FROMLIST-rust-export-BINDGEN_TARGET-from-a-separate-.patch'
         '0020-FROMLIST-rust-generate-a-fatal-error-if-BINDGEN_TARG.patch'
         '0021-FROMLIST-rust-add-a-Kconfig-function-to-test-for-sup.patch'
         '0022-FROMLIST-PCI-loongson-Override-PCIe-bridge-supported.patch'
         '0023-BACKPORT-FROMLIST-loongarch-wire-up-memfd_secret-sys.patch'
         '0024-FROMLIST-loongarch-retrieve-CPU-package-ID-from-PPTT.patch'
         '0025-BACKPORT-FROMLIST-ACPI-PCI-check-if-the-root-io-spac.patch'
         '0026-FROMLIST-PCI-MSI-Conservatively-generalize-no_64bit_.patch'
         '0027-FROMLIST-PCI-MSI-Check-msi_addr_mask-in-msi_verify_e.patch'
         '0028-FROMLIST-drm-radeon-Raise-msi_addr_mask-to-dma_bits.patch'
         '0029-FROMLIST-genirq-reserve-NR_IRQS_LEGACY-IRQs-in-dynir.patch'
         '0030-FROMLIST-dt-bindings-interrupt-controller-add-LS7A-P.patch'
         '0031-BACKPORT-FROMLIST-irqchip-loongson-pch-lpc-extract-n.patch'
         '0032-FROMLIST-irqchip-loongson-pch-lpc-guard-ACPI-init-co.patch'
         '0033-FROMLIST-irqchip-loongson-pch-lpc-add-OF-init-code.patch'
         '0034-FROMLIST-irqchip-loongson-pch-lpc-enable-building-on.patch'
         '0035-FROMLIST-kbuild-install-extmod-build-do-not-exclude-.patch'
         '0036-FROMLIST-LoongArch-Select-HAVE_CMPXCHG_LOCAL-in-Kcon.patch'
         '0037-FROMLIST-LoongArch-Add-HOTPLUG_SMT-implementation.patch'
         '0038-LOONGSON-irqchip-loongson-eiointc-Improve-IRQ-affini.patch'
         '0039-LOONGSON-LoongArch-Add-CPU-HWMon-platform-driver.patch'
         '0040-LOONGSON-drivers-firmware-Move-sysfb_init-from-devic.patch'
         '0041-LOONGSON-drm-radeon-Workaround-radeon-driver-bug-for.patch'
         '0042-LOONGSON-dt-bindings-dmaengine-Add-Loongson-Multi-Ch.patch'
         '0043-LOONGSON-dmaengine-loongson2-mcdma-New-driver-for-th.patch'
         '0044-LOONGSON-LoongArch-Add-canfd-support-for-ls2k3000.patch'
         '0045-DEEPIN-net-stmmac-fix-potential-double-free-of-dma-d.patch'
         '0046-BACKPORT-DEEPIN-pci-quirks-LS7A2000-Fix-pm-transitio.patch'
         '0047-AOSCOS-drm-amdgpu-radeon-disable-cache-flush-workaro.patch'
         '0048-AOSCOS-loongarch-re-introduce-add_numamem_region-ini.patch'
         '0049-AOSCOS-loongarch-basic-boot-support-for-legacy-firmw.patch'
         '0050-AOSCOS-loongarch-parse-BPI-data-and-add-memory-mappi.patch'
         '0051-AOSCOS-loongarch-add-MADT-ACPI-table-conversion.patch'
         '0052-AOSCOS-loongarch-correct-missing-offset-of-PCI-root-.patch'
         '0053-AOSCOS-loongarch-fix-missing-dependency-info-in-DSDT.patch'
         '0054-AOSCOS-loongarch-fix-DMA-address-offset.patch'
         '0055-AOSCOS-loongarch-fix-HT_RX_INT_TRANS-register.patch'
         '0056-AOSCOS-arch-loongarch-add-la_ow_syscall-as-in-tree-m.patch'
         '0057-AOSCOS-la_ow_syscall-add-kconfig-for-module.patch'
         '0058-AOSCOS-drm-loongson-add-ls7a1000_support-module-para.patch'
         '0059-AOSCOS-drm-amdgpu-disable-ABM-Adaptive-Backlight-Man.patch'
         '0060-AOSCOS-MIPS-Check-address-space-in-ADE.patch'
         '0061-AOSCOS-kvm-disable-enable_virt_at_load-by-default.patch'
         '0062-AOSCOS-drm-loongson-add-ls7a2000_support-module-para.patch'
         '0063-AOSCOS-drm-radeon-limit-mmiowb-hack-for-radeon_ring_.patch'
         '0064-AOSCOS-USB-core-only-enable-root_hub-wakeup-on-MACH_.patch'
         '0065-AOSCOS-ACPI-scan-Add-pwm_lookup_entry-for-PWM3-on-LS.patch'
         '0066-AOSCOS-Revert-FROMLIST-rust-generate-a-fatal-error-i.patch'
         '0067-BORE-linux6.19.7-bore-6.6.2.patch'
         '0068-CSMANTLE-loongarch-Add-CONFIG_LOONGARCH_NATIVE_CPU.patch'
         '0069-BACKPORT-FROMLIST-perf-annotate-Use-jump__delete-whe.patch'
)
         
# vim:set ts=8 sts=2 sw=2 et:

