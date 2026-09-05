# Maintainer: csmantle <aur at csmantle dot top>
# Contributor: Jan Alexander Steffens (heftig) <heftig@archlinux.org>
# shellcheck shell=bash disable=SC2034,SC2154,SC2164

pkgbase=linux-csmantle
pkgver=7.1.13.arch0
pkgrel=2
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
  # FIXME: -arch0 does not have upstream patches.
  #$url/releases/download/$_srctag/linux-$_srctag.patch.zst{,.sig}
  config.x86_64  # the main kernel config file
)
validpgpkeys=(
  ABAF11C65A2970B130ABE3C479BE3E4300411886  # Linus Torvalds
  647F28654894E3BD457199BE38DBBDC86092693E  # Greg Kroah-Hartman
  83BC8889351B5DEBBB68416EB8AC08600F108CDF  # Jan Alexander Steffens (heftig)
)
b2sums=('39db33eae1dcb52ecbbc5a0818ad388fe0cb263f7c8a06b04827b9354e6653f500873354c6c5fe220b332c020087716eef6f4d7915489e4748a6b5c076080e47'
        'SKIP'
        '512543621b3244ee00fbc3a6071a784ed63a269c8c8dd25da0da0a90269ba8539b558b555aa63bad9bf52d96148e3184ad6bba0b62edf9a5ba3111643241a96f'
        '652069e50060a3d84530f004f7064d98d6ac9bb02e690a3510d092d0df17598c9b3d564ae07fdb0dbbecc68d2d12d58c4c78c02cc08fbcbb8c01ba6e6256d922'
        '9682585b979585cd1e2b2fd76879954d0c101c2e27d989da02225881d1b5739c01bc8e8643d9e7fbef257834b6a08d8db247b15727f98ef9eac4c533a027eb26'
        '4f255450641ead6dfada6f5e32823ba02fb383d309122825cca941f33ccaed174eec65e86af75fad22082fd7bb2df5a3241e12589e87646f61202ef62b0dc690'
        '2f73174ab84f0267871838a156eeaa251775e0ba4b7f97bbeffed3cc3be303bc4f256e787d1718bf775c143649e4250c3a6d1e405a81a13c494bdd04082b2184'
        'fe0cc2e4c3402dbf2e0d87576a479bb2639019e2089710bd77b08d838fb4cddf9ef2f997b92290473539aaf48c747bc369e29ecd5e922b2d828333e0fb7a6129'
        '8768630f3fcadbf563294e3a208004f0593842bf5465cd222fa4663ce0fe8d9806eefc761e20d0d2de2185a9ea521265ef156b88fffb24e8b29050faca1a1cc7'
        'e033c1b5b843f9a806a843a96dedaa2d8bba9190ff68da7fb44d45d4eae4c848f5ed2f04dad2d158f4541918105aafe0d81013e9961fe1f25a9855dc596ec0f0'
        '76d02b6a01745f244d3a201d817bdda9feec62663554c8b3124fd568944d1df25e682cc44e012d9613e4026a18f3c42da76a4c70f6743e8d876f71addc464fb0'
        'c2ba43fb7f2efebb9570b5ce5a1bd2639b2c21632ad66c18bee48467fef51f4fba22b91c110866266a218307a5f9331363eef0ef416b9454ab0e98f731c7e0b6'
        '63707af8c170880b56eed55850c85ddbb1f74f25caba7b7caa06d96ad5ca23c3a7b7a86ab3a4b1b218ebdc70cc51f2f8e92ae97601db6bb1b337e9005dda4960'
        '105f2d05c7850802fcdf5e0bef47c5af67df0dc178dabc8fe48841e9d71c8ec8f8ac5b91260d6b6def4dd08f2b9fbab79365ebcf7dd336b9034cdebc4c0a2b2f'
        '6cf82d0447e7f176b361a55104d4dce280260d1c2796e3aa76d9833585c2aa3555a41058a500931917822d74e4ca93c6a891dfc0cc47dbedddc7a7b7fc7acd70'
        'a348a9a074a9816629b98c66a8718c7ffc62ce36de6ac805dad26a96dddfadcf80945abe8e36cce3bdf5470478dcbc3ffc32384be3fc8b04cf6a49997fa9d4fc'
        '1d23dc527e7f2e177402b20b705dfe3000146696407f928c150dd3041a83f9b1bbbacfbc61024954fa63fd2c0658c64c58b28dfcd8ba9a693ea1b081591dc03a'
        'f8ecffe40f3a070b2072eaf0514d83db30c11d92b27aa521be9b7edb58c6661f57835331ab3abb27d689edc1d218c735b231139782c90ea5dba53e7a2e6dd122'
        '49c2ef8453fd0399c57b5e403cad701ffde11bbb790e8ed5fffa35f5b419150d3d093952af1742b25d229f4494dc002703b6d3bf2a18ef0bcc9528daf3e1b18d'
        '0ff2bf630d65532040767c8d6d8e73a175b8d282c623c1cb08cd99098e78f0a5fd6bd8ff9513d97c2b3360e2b19d6e8c058d0a784f9e80998e99a1eff7063379'
        '8c7d20baeba5ca740b8816756545d47b54c54097f5d44bbdbbc24ad60cee2abb767a3a86e33b32c89baf9ea60b4226f4b570751ac187a19324c1a659d0ff6246'
        '1d07a1171d13b9e411e2b6728afb6e712fbbd6dc1775b468a67c7335ef5df998791dfe5ec73afa46abc021c1b78b0efea554a80d8803a06756e45a20f9f84ef1'
        '77474abdbab02fd9ba7884f421d9d028a596706d3b4c56a42c8a0517c67f9df8727b9bd3b3075058c502c614603faa4d4cc37be0eb4d315e8d056ff1e36681bc'
        '097be4625ff528c32c2ed8fa2c7a802330d57e4df644986ff3dd62cf83451806886c508841d619141a3f27d56829d93c1ddbf1f245a38141e4cc45f8ada98d66'
        '5a06565f9caa7c66a0ef6b6b182c17a1e3ea09c0f88f28177b5422ddcfdaeeca36cd5d6748d7cc3d6ca212b1473fe94f24fb36af625c09e3a148b47f5bd09da8'
        '680c1992ae30ae624aa70d0af7740cb03fcff87c0cfd454b0eb97553c4b5de4f4f14d9869cbd9a8d0b4ab7750c3bc15e674bffe0e94b50630db6601f03b1a907'
        '4f96a0deb9793f837c11d4933f9f87bd03db8630527d08a36c8911caf797d50fd639a1897789e3f44f6ebb737e3a26626cef6e8b0248b711b50078499a9fc4a7'
        'a8ce73a3995cf70307bbae81fe6b83ff9075d0936304292579c9e8dd1dbf2a624832d9484608e5f7646bedeff4057edfc389cb1aef3b28b371a42cfb99139f39'
        '2937cc5968cbd3143d188d2749b3ed99919ae3865b763ae60c591a6162233585e3d0bc2b2cdba1e11d6b3b89cfbc63a28cd7c8fb2634ff9093dd16c2dd7e50a2'
        '2cf28ee30eb42c49222488db861d10c719cc3e6bfe0af683a220fabc2c288db62b0e9282159d0c5ceeb14c1f69aac2893bbc7ed8651ef089bd63e04bdf56678d'
        'b9ddf99f03727e014f3d649577796545b6fd419e0a67f04ad078463bb7860d1f777eefc7662885dbd872b7860e4e9aca235f55c1f767af760bc6799178239c7e'
        '228439b996b1914fcfceb8a5e8c19012a2d43d70beb4344bfe84ece17e552bcbfb1459f5c24cb4c3783ee5022354173156fd1e22b1c93bab45fe1d15da714e48'
        '96b98a8038f1bd207583ea4e738015cfa007aeb91366c52bbd1acb33ab70cbe294ad609909ec9518ddcbb847016cc0fc2b99025d325d346f605a0c828201d2a3'
        'a508bb9b36d3869b73003cfee5f3f9c6fa9b28b9f9b012bfbacdefc29047525c22fcfbb9caae641c47bd621b659dcf3ce08e81812535ed828b60b3143e3b2f49'
        'c5f4a114ea38502a2ccba9f7f1adb8798209e4567d2dfd27add10cc03c07c1e418c67f6059187baa4d73abfdca04480de48ad4535658a46801bca0c33df3c442'
        'c79fd3c59790e8bb73d541bff918877c2e53f6d60a39fef45c956607c4ec008798fe324b907843901de7d150061cf8e1306b392766224802d9cccb3124a8725c'
        '83686d310cea916478c8c0ebfe0370c0a26eb508f090a0a6c9d5a079057b0c20891c81d5c457f4a0deb4415be44e64c2ee9268acab5c0e7b70200255f7460e90'
        'a2dddb6a983b929087564f9511446c9a83b03033dca60814813745f1c166e93071824ca515ce106ac8ccd672e9914363614b3c8997eeb0f189a9e8a7d3295a2c'
        '282c12b3ca7854d99655053f146a7d59c0c8d983d59560b0e9afa99e4a42fd298979b737229fa75da29bbbb68bc8a6dd469f24842c79564b6d6a7700c19ff745'
        '1967d069dc830fbcad0ec414d07e39c640d0908bef437945b2dd38c1c088e19fa1228b0dbbbcfd33749458e7e6fd2c356f732ea47e9a210a6ca7f04a24eb612f'
        'afd02533617b2855f768b6cde8848f48f7c40fe7db1724b0724f73c64e443b9b49aeb96ca24f94146eb9e38eefc89408536352092189d09589996b3add142481'
        '7d1ad8670665bc1487ff0a9239f98c31fad46272efab7d435f7fb1eda4bb29ff4425db9dcd25a62a48d03ae1b38abe4b56b06084fce19ac83d3d72c2438edeb3'
        '17569c11e5b365b35cd2607946d78ca61184e4d02639a3add6d452078a63e1da182130014acdfeef093efdb7bc3b2a92fe5b3e755fd2b9d5d7f6fbbd9391c297'
        'd5fad922e2f696ab89825cae28597bd421f8edcbc05b5c4809160bbdf89c88f2c54bc9d6ed0ea47c578244c006b683c784a4922fedc511e4897dc8393be0f4d4'
        '30e894639705b3b59a3b9fa2c9ef9de70c42a9f20be9696b7312eeb752ba66fba84d1f6f0296944851165b232b73f7385390da72e549c63b27eb2a96048ca72a'
        '4393d350e93c713de5ca4a5e575b74e2e67d6f064e3352199422c3a4b89955730ed8783639bc2e37d675d1abef66f22ae20b00339cb0a6b4a97ad90da0fcca00'
        'bf092bb263a25f144746988bb511bea1b27c06074638e9c39f9222a5d8ab2d2b7fde765be439ae1e2200239309970b5691c89f75766b580501bcd32c631c04d4'
        '20b3bd0517099afd5d0a76c474698321299db17b440d60a9b51b93e8299c26faf022210f0efb0c2b7c8a667ede42b59388a6f243bdb6dfe11f0c3b5513b1798d'
        'ca22263664160855aa7c540cbe839b440c0719bfe6b0d32b5007f3dcc70228184edcee81ff0b4f548351ca58a115a3a85bc505623f5c40661a54bf05669e5620'
        '033bd1919ba7990b4987b5c955380a04c6c842bed910524b85a1564381150a5b7c0c20d360fbe8fb985ab1e607f3c6e50e88c0373fa1490e84fd977af614ee8a'
        '1fdfaf7a5a4753268c5431ca09222ca932e4bf11b8c4cbece4cb943b147c2e469397e8d38441020d02e0f364af9c7fb72916b6d3c8c44f7b9848931c9f0b4650'
        '8a964038a3bdf1b6611cc3ef34cecde0f1c1f683d9fd1d40c464c8c186a8fb6e6f722d72dfd172fbc7b423133c0e8b3af46faf8d463981d8e75f6f3aba856b28'
        'ce8e5a01247edf31f48cc23225dbfb837a14f2aede033273eb78f733b4a6150358b42beaa8a6142f4e4d8be59bded66e5d6d8a5decac76a540da73011821cb7c'
        'ca8f1f045274f8a11e551eb6fdc95171ffd7207225d7a5c0cb73cb2d9d04cf55cad8865c954dffc53e5c8693f5326ad732809b64f3196b504db92b143b971a0a'
        '9df15af24a7bcc811f73527fee68122153a964328166e807b86965b1183935083175d474b39761a8f84c4bbd264e8b8e06516a8d644228e37916f6404e5adc02'
        '66693aed8ebfc2634fbc8890c06abe3f06150893b5b045a6071972eb8ce6d58bc51c16d18dc0cbd334223c383d2e4ac665c782c2c8540379f0cd83b29f05ba90'
        'f1547b18cf09f4b89f0ba7eae1528447b4e32f1668cf9e422dd3350b5e1b06349fe5247116118e867763153f2e52472c11be0175727771657e5aa89defe0d46c'
        '69c67428d26c5e60ada142486210ade73ff211df9aaf6f031b8ea316cfba816fa0981d18c8da930ecbd13ad5ab3b5d20f7661b1f6236f2cfd5564151f3d5da91'
        '87a43d96734860c43bf09178a9fac4866d42e67ec950609d23006e6f202c24560a58c699e54acf2dcb924e10105b72c961d43b7569eba3acdcfd6d320c88e9fd'
        '1e0efc7d9337eb8cbe399559f19acacff2f0b814b8c48addb6b460c24c44aba8dc43b7923527be3fc03a6f53319aa549578e8edfc653cfce074543262d90764f'
        'db1c7cb7c86eaffc7d3e042782fe02474a5d7a06dbe6dfbca693b1b45263e6a05375a8f07a60051785d1c2e212e5f128aafacfcff5a90011fe9125680c9d75ae'
        '3d31e6fe8f441e62158f50f63880924486f7143fe0ae02f864d7ca525a3bf83c8a35614b466edf7cf020e400d4720d2a367fd96d72cf241c6234d37593301f5d')

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
      "$srcdir"/config.x86_64 \
      "$srcdir"/001-arch4loong64-addition.frag.config \
      "$srcdir"/002-aosc-loongarch64-16k.frag.config \
      "$srcdir"/003-local.frag.config
  else
    cp ../config.x86_64 .config
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

source+=('001-arch4loong64-addition.frag.config'
         '002-aosc-loongarch64-16k.frag.config'
         '003-local.frag.config'
         '0001-add-sysctl-to-allow-disabling-unprivileged-CLONE_NEW.patch'
         '0002-udmabuf-Do-not-create-malformed-scatterlists.patch'
         '0003-block-try-slab-allocation-in-bio_alloc_bioset-before.patch'
         '0004-Revert-tracing-perf-Fix-stale-head-for-perf-syscall-.patch'
         '0005-Arch-Linux-kernel-v7.1.13-arch0.patch'
         '0006-BACKPORT-FROMLIST-drm-Makefile-Move-tiny-drivers-bef.patch'
         '0007-FROMLIST-drm-radeon-Call-mmiowb-at-the-end-of-radeon.patch'
         '0008-FROMLIST-LoongArch-Update-the-flush-cache-policy.patch'
         '0009-FROMLIST-USB-core-Enable-root_hub-s-remote-wakeup-fo.patch'
         '0010-FROMLIST-scsi-Bypass-certain-SCSI-commands-on-disks-.patch'
         '0011-FROMLIST-PCI-Prevent-LS7A-Bus-Master-clearing-on-kex.patch'
         '0012-FROMLIST-RFC-drm-amdkfd-disable-HSA_AMD_SVM-on-Loong.patch'
         '0013-BACKPORT-FROMLIST-drm-ttm-save-the-device-s-DMA-cohe.patch'
         '0014-BACKPORT-FROMLIST-drm-ttm-downgrade-cached-to-write_.patch'
         '0015-BACKPORT-FROMLIST-rust-export-BINDGEN_TARGET-from-a-.patch'
         '0016-FROMLIST-rust-generate-a-fatal-error-if-BINDGEN_TARG.patch'
         '0017-FROMLIST-rust-add-a-Kconfig-function-to-test-for-sup.patch'
         '0018-BACKPORT-FROMLIST-ACPI-PCI-check-if-the-root-io-spac.patch'
         '0019-FROMLIST-kbuild-install-extmod-build-do-not-exclude-.patch'
         '0020-BACKPORT-FROMLIST-LoongArch-detect-and-disable-sc.q-.patch'
         '0021-FROMLIST-i2c-ls2x-Add-clocks-property-parsing-and-ad.patch'
         '0022-FROMLIST-iwlwifi-add-new-pci-id-for-6235.patch'
         '0023-FROMLIST-cpufreq-loongson3-Make-this-drvier-depend-o.patch'
         '0024-FROMLIST-cpufreq-loongson3-Adjust-the-width-of-id-an.patch'
         '0025-FROMLIST-cpufreq-loongson3-Replace-per-package-mutex.patch'
         '0026-FROMLIST-cpufreq-loongson3-Use-global-physical-CPU-I.patch'
         '0027-FROMLIST-cpufreq-loongson3-Replace-IOCSR-read-write-.patch'
         '0028-LOONGSON-LoongArch-Add-CPU-HWMon-platform-driver.patch'
         '0029-LOONGSON-drivers-firmware-Move-sysfb_init-from-devic.patch'
         '0030-LOONGSON-drm-radeon-Workaround-radeon-driver-bug-for.patch'
         '0031-BACKPORT-DEEPIN-pci-quirks-LS7A2000-Fix-pm-transitio.patch'
         '0032-AOSCOS-drm-amdgpu-radeon-disable-cache-flush-workaro.patch'
         '0033-AOSCOS-loongarch-re-introduce-add_numamem_region-ini.patch'
         '0034-AOSCOS-loongarch-basic-boot-support-for-legacy-firmw.patch'
         '0035-AOSCOS-loongarch-parse-BPI-data-and-add-memory-mappi.patch'
         '0036-AOSCOS-loongarch-add-MADT-ACPI-table-conversion.patch'
         '0037-AOSCOS-loongarch-correct-missing-offset-of-PCI-root-.patch'
         '0038-AOSCOS-loongarch-fix-missing-dependency-info-in-DSDT.patch'
         '0039-AOSCOS-loongarch-fix-DMA-address-offset.patch'
         '0040-AOSCOS-loongarch-fix-HT_RX_INT_TRANS-register.patch'
         '0041-AOSCOS-arch-loongarch-add-la_ow_syscall-as-in-tree-m.patch'
         '0042-AOSCOS-la_ow_syscall-add-kconfig-for-module.patch'
         '0043-AOSCOS-Revert-rcu-Fix-rcu_barrier-VS-post-CPUHP_TEAR.patch'
         '0044-AOSCOS-drm-loongson-add-ls7a1000_support-module-para.patch'
         '0045-AOSCOS-drm-amdgpu-disable-ABM-Adaptive-Backlight-Man.patch'
         '0046-AOSCOS-kvm-disable-enable_virt_at_load-by-default.patch'
         '0047-AOSCOS-drm-loongson-add-ls7a2000_support-module-para.patch'
         '0048-AOSCOS-drm-radeon-limit-mmiowb-hack-for-radeon_ring_.patch'
         '0049-AOSCOS-USB-core-only-enable-root_hub-wakeup-on-MACH_.patch'
         '0050-FROMLIST-gpio-loongson-64bit-Add-back-the-support-fo.patch'
         '0051-AOSCOS-ACPI-scan-Add-pwm_lookup_entry-for-PWM3-on-LS.patch'
         '0052-CSMANTLE-Revert-FROMLIST-rust-generate-a-fatal-error.patch'
         '0053-AOSCOS-drm-ttm-fix-incorrect-caching-type-caused-by-.patch'
         '0054-BORE-linux7.1-rc1-bore-6.6.3.patch'
         '0055-CSMANTLE-loongarch-Add-CONFIG_LOONGARCH_NATIVE_CPU.patch'
         '0056-CSMANTLE-loongarch-expose-LAMCAS-existence-via-cpuin.patch'
)
# vim:set ts=8 sts=2 sw=2 et:
