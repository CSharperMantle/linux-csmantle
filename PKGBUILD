# Maintainer: csmantle <aur at csmantle dot top>
# Contributor: Jan Alexander Steffens (heftig) <heftig@archlinux.org>
# shellcheck shell=bash disable=SC2034,SC2154,SC2164

pkgbase=linux-csmantle
pkgver=6.19.12.arch1
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
  $url/releases/download/$_srctag/linux-$_srctag.patch.zst{,.sig}
  config  # the main kernel config file
)
validpgpkeys=(
  ABAF11C65A2970B130ABE3C479BE3E4300411886  # Linus Torvalds
  647F28654894E3BD457199BE38DBBDC86092693E  # Greg Kroah-Hartman
  83BC8889351B5DEBBB68416EB8AC08600F108CDF  # Jan Alexander Steffens (heftig)
)
b2sums=('d016cebe33cfd8f43798d52f90c94b81cc61a0914ac3ac663c399cdde2ebf024331c84da53813a0d09c1c21419b8a36e97eec092adc1888624625897dc976228'
        'SKIP'
        '8a84b338e199c9f89fc15bfa34775d717dbd46166341e4c217b4d08bb2f477f5cf76675353cb73a9b758b6493806b5579ceecb300078806abe024a7f63bcb452'
        'SKIP'
        'bef3377ad86440af76e9dde4c29c9f4aaad42f5fe343f7d31f5eb537d6d358602f996f5d63986af275f2e92f94e71dc28c320edc8c03d05bd64dbd8ed23d75dc'
        'dfd366b283243f95c318471fe35e3a36646a38388dd6c4d9746bc981985a02ea303d75127244e9feac14564a8f49385483dfb56a8842814bdf97ca747bc2a4d5'
        '46f0fd181d20e8ba9e535264b443517c9a41700491f96a80d20f357d721c32652299c71949929c364b6471a7bb4bb6a09dde60fe1e3ad2fe4faa8a52708b49c0'
        '92e270373532196e623f408ece2a368421e6f79200ee9b9cc9b4a0d474333f5bf0ea86a0572de291616ec88521e0610af6a128503634c5c56fec3c78b1728120'
        'c795c05707c139dd5dac65524702320f625c74e3009e6698084769560f6883e9c788190d9f7d93b5db9644dee74345ea64b96077e44ee7bc95e78b72bf2d8955'
        '1b1c8ae0eb8ff3f24f393a8bf4eb61cf624fe646985b3e2a2968fd17ab508cfbf1b6a28d9cd8349e70b781c424b6e4f0c9a44d20e68282e723a8f41a93c220d3'
        '9d5718f810f58e12e41cbf0d3c0da83b8371b68f715f0634647c26c1e489f2dcf38ab3fcf7c4f561fb0e500801d29fdad5527d26d0e2463e6a70eedb118fcf47'
        '1d8bea838aa90a6d6668924d9470708d6858a0561a0a10ca03d2263b91dbe9d31e2496a3f10e43757f8a23f93b5d51679b74efbcfc5d15909344fcd2ca6bd27b'
        '225ea1b52a8f12ee1f2b668ba50ce23837e9c2b2bcea904657ec5a4e8df14e27e9b6f871908f615df772647a680f155a42eefc6a3a0d018d7dc702308d15416a'
        'be6f1b5d03f0170f8a22fe29ef6f80da0ca227a1c417d1ffc758fc663f92331af9a606e541cd3aef2561b058834d30f8f3da8f1a5eb71a397977a4092e2ca0a1'
        '92d448c6a933f54e95689de59508249744238fbe9fc2c6938124e34e2fc570afe865a8dc7a300f600c7bb035c9e8dada82dfe674957f1aa64458177039380245'
        'c7f198283e6137e16a73f2588e3c168943617814b3d933f6170cb1f81ed113adc8543ac4b4f3797e64ca66a1fb664a56d766fcee04a02e10b8d678cb7b88d347'
        '421012f414dc3126fe1c885750765ac2ee97fa89077550b968fda3fff0f86aeb1f8b288ccf9910cb56e3d54cad532f19e76ccfc2c84859ac8c541f8acb058fb6'
        '9187e8e56916f0c5e1a54a66db76520926d5abcb99655d37ac6f391e16e20ee35edabac799d6222c3fe41da757647c14dc9a9bccb06d957efd74f22b36000bbd'
        'ec3a249c57dcc65ffe022c143178c304b37c2804a079b7d7afe7380b2f1dd5ab8c70b9809d73bd27d4159e857bda8f94b140e83cfbada177b9f706a8296fbb22'
        'a90e05c1c053b492cddc08123f06c8ecb28ade7697214a1283f416309edee53ccc7f4766f7bad5439af57a794228bdfe5374d9be4aea2a95f1fbe0d1e4c2bcb1'
        '0b211c6cd68519b56dba4a3667fd05a314322bf9e60828788f6e8d82adf25536369ac1cd705d94c490641d9b2dfd1a11be5afea210c928a5a73599b0cdd9fdff'
        '0b5fa5f6e3d399ecdb89f325f6a79a94480eb22981c9a09828c874d13606a94e305345ba47f91b4b49cd6ec2e2f634c42e2769832ea024205a66f76e8d3f0dd3'
        '086ecf4b71d85868f15160ac7751387fb58482ff5a11eaff7c43a7a576ec9fe4e4b1562a8471b3fe64979d655f7be3665b761a92ab6ffb327909a3e6c93cad5c'
        '3815baa11093e1fa9013a01d1656039664e8707b73d9f0fd288c6c7619e7f7dbda6a6214609e89980691d357bb4c7ffbce759fd81aed98c7cd76583b7a5e94ac'
        'aae73e77c8ea8b5ba546ff1575d21cadf85522b8bd971ff6119f2b67ffa0824557837d2e03e46393af88a16345a7801caaaedd3568fa6bbb5a4232e3dc737ea5'
        '121a9a9419fcb0332d7b66ca6dd86586b2b5d9ab8df45ec60dd587c1c004c987809d025ae40f05b1145a3254aeb530c7ab86b113e7bb639457cccd6784fc9257'
        'bacb54468586caa6d20353a6c19b739e6f3e8df8269d091a95cb942d890cd7a37150711f591772665421243266986ef8777d9cf7ba511cca5dd12f40af3e5545'
        'd3598e9b37997d1187d0585e6235886d9fe7e121b358007a1d7d40e02abe0ab459ee74a9b1fa0e0c760f20a40f03f54f822c64b607182c26ab4cef7e590861a7'
        'fde43d47f42e2304f104eef2f55801488d12b2f30bffd26f9c1bc67de70f88de7adbd99d163cce52891dd1cb5cb4e53e1833cbf9f15ec7f764110b71c7f36264'
        'e78886c3827fcd8a1263df60d058c2bc03111054641ea60dbe24bda3bdd80ae4b946bf564b8cabaa33d1e216b51eed36930f82f098df6c212383f0b5164feddd'
        '1a94220eb38253d9e443d772e8adefae1a1267bee1387c629d7db67310e792e3cb861cf4ed521b540b727c443a68fdcd825ad27052bb31bb47f10f62611d72d4'
        '40a0a2674fe24d575d931db68d4e6daf55e6a592989af005782bbe2a26a94c18a82de7713be8b961705cd30dfcbfbb56fe344eb295c3b05b7b3f224a5238571d'
        '0859ce8bfc8d05428a75d319ca77c865fb0f58f02bbb1c4bf3d718efa987301ffb26150009795093127505138b608644229a5988605457264533b6cbf70c6dc9'
        '098d00046b2b07d01e4e730c2422bf53130634473b18834c19d96875313eb2440a20868663b5b43246125e2db68d600b22891c51ba6e345b40866bd080e20755'
        '718407c0782f1a37c3519529acf36a14bcf0d5bdbb1169a768a327ca547d4009eb0c76fe2d09a06520faa01043d511b2d1da06c422b06db23538f8f9f051ea4c'
        '372b9dab4caad381b39da5a8ec3f0d3ab2431d867298610c2d07a24553727213f97eed309b2bf557daffbb742c19170b14ac58ef2ffd81d19568708d3c339862'
        '2725d0c98b860261c44769e59d2a429945c81a63c9868810ef2ae312425e9d8f4366611df23f1d5f48e8fe485527f5b0f273ba2668a1253b78ecb6217e7e1b7e'
        '12870d4edf8ad939bf87c1f8f8ce699ad5b808a96ca61672aef321d6be5af720430892fe0a13a2429efe4688143d0e98a235d92a7fc9f7e9b1ea04a34ab2781b'
        'd8a1b4bd6ebf535dca0f9acd088b6e1173b2a33fa7e3ac66b31b0106c6e5f3f98d126d7fd775165b025cce057776483314d2bfd8be724188c9f60613995abce3'
        '1ceb71bd3d5f517d9a608b7bd54c701d6ae6ae0e71ed090b032ef05474fb5dfb8bd792c6ee073acf037468c5eb1718c505078e17e3485ebeb514a467b18c47ce'
        'a58cf39e0fe75212b6602d7fdb596efad70c2ae2b883373bd6e16a4b33a1efd1b045d2196c7e0ac004bf092831d47529b9d65de082f1bc71edb5ccaf828eec27'
        '0110e234a45c52887ac57f4b69d4c5a07402876d7359d9228fff77ce163579dcad15ddc982ccd44fb755f5e44af061133466e6e9e303f60dab6b5b5d8576ce81'
        '6e8deac5515e651aa7b073e2d00b4cc8790be959340274b211c7031cd1e7e8e3123bd4ded4f6a9ecbacb1b268f451ab6887ff2046b41ecf5adfb811868e2dd26'
        'c977da537a7ba683227917664b83616a52c319b21f679e20dcd1d6e3969e5ba44e4ccd5bef60dd836779b359ef59328c8ab81a9f3d71bd772e5b6d4c47f925ec'
        'b81e1468272ede9069a4aed2ada62306559ce5b5ceca0ea38ab1a7a8f94d04f718b54fbd073ba78b69c7da1d862019950786ba0bebd8d6b7b875a91b23b5bfb9'
        '6d3c2105c0ec75a6d5c1a0bf6e253abd322dd85c063c22a1eccf085ec81c10bb868d46d295121d9638277406adf693f2f43540d99f8a8276af6be4b2fda0b519'
        'af135b9cacbdf8dca43f6285811bc60c0da383bd8e9ca767180f2c6294a3e6847547bc79ee9b363305c5287ecb587a45122243152870002b554cc39548ce164a'
        'ce22abf4fed09bdbf18ee9b4463be5ba3d0564d3f1836606d689b6deb40be48f3d67e30e74e225be3711138aa6eca589769eb774fe75589133ce16e3894888e3'
        '7ebfec3a210ea30e684d7d3262b79f589e826a879b0562619ee0562515a450ea284fcf24c75dd54e13f2e20f356d13bdab20468f0849669052af916846fd5e89'
        '57c5536e4eb9a9664c096ac994d1d9ee723ef1fd12c77b0e8e304da423e5661d80480540cf5ab61c40754c93cd8f8dba30c6c6ecf6cf24147f75b2130a8fc147'
        '09f7ebc100851c4bc9bd3e937d42e12259a7784c8a784184c8870087b07d280bbe7806d69f31e8b33c0ddb32d79b04081abcd91fba1fe776182c4996f782274e'
        'b10c360e1d4b21830865d2a549cac13774ba3d218c8d439f1026562397d7c579e6f69375a8d134ca2176b94d3a346007ca038036659f8e60a6c7a021ae2f5cb9'
        '41028f4cfc56aaa05a5fc3ffbef6d11f401c6c35e9acfec66721ff0f048ec618c25a37ac7ebd2f99d72506770557a8041344aae32a399740096fb8387b4b85f4'
        'e94b198148760777d173a920d5f5fd70c99a474a4e735fc2c975ea60eed3ea27e15735f52f1fcf365ea99b57b4321808e50532bcf0339653bf4a7a6167d19a0f'
        '30a215793199b1250638f7774d02161ac0e7504e7a01be2bb4558d5a9867c1126218dbe70b08b77e0598079c14b7e3fa059bcf826d486511562bc5d76661297c'
        'e47c2d7722124e7fcdbf7020c50336bab1296ff0252d3ccb38205dbe51ab5e2a88521275dec63469abb364a1c3f2050429636137911cbd9cf2d356cc7bf64115'
        'bd06da09fb937b85e6c50be5ece8a49351eecc54fb61774c86560b5bd6bcd67de0e3f5aea0d43ef2fafe9024a2812cc556ed258cb9b1a6af6b5f716bb120ccbe'
        '4fe7f934ea9df15daa1d488a059c4294057829f841ee171a59519239a18eb130a97614643812d7e9be9c467ef6dba0660ea90e301917a4f3abd75a6b71e26ce7'
        'ab278983a8e5052f8f3cc80f4183846953774a58718511322287940328abf78a39882a1feb59ced67cfb26bee6eba3d0c91cfbfc9c365214007ad4b0b32e65d6'
        'f030cbc746a6da5736db8c3ba4ba7b9305cd95242cf6d00378dace3e8ce23d58b08e9cf530572d9438ab27afb4e117535d1e921e9d6974a5ba9f71e82f3c0c98'
        'eb855e85b90337f9b0d465279dea8a9313f7de555e90f205b8b8be5d8ff2ec9d644c254862fd4eb3a0169473dd2aaf2e4c5f42b9fd26d22f7d8df2f739110db9'
        '7ded2280f8114f443ec44234116e06f86603df59ce077ee496592f760b196ed0e54e67f45c8e0fe36243d84e5b2d3738a12648d331db138eb1724903b376414b'
        '4ba2329815d80912c75391d32e5eb99856e14dc6efae2f06ad11f669212ec204e9b4e701dd9f5c8788f74ac99e4c5eadf67e2d7262cf5fd95b7c4dffc20e503a'
        'ac5623252d33e025d81d3061baa0f8c17dc639d9b45674545df9e9515577994fbdf78fb863ff0d2e1f1a580c8a25d1f65314c79d59acaa46b9be9d76fe82bfe8'
        '46f3a510e00659deb1fd0c53606e28c56e19b3b78a174cfbc0869cdc1a9cda594ddc201c7a6958426febac726b8913e807552c839421e92c72c54d11679ab3c3'
        'ab2ea122732d4b94bde757b1dc6af1d08b397a5675541ffe9bf4beba251918bf9da2ba9ce194562b8598b2e74940f44f0c183f00c73fe888463c0bfbb893e31f'
        'adda0ab45bb978d0e6474b7183cb2448bd503722acd230a4fde64a4831a289127ebcb00fa5813e839a48bd7f0324fbf0d7e8ba0cb3005a1038714c43307028b2'
        'f7f0a35a1e0275097b4a8098de3ae38dd019433e2c728c5bff590667859cdced68072e2e878dc992b51a084d13babb1886f5babc82abde25f70ccd4b4568b4b8'
        '9c4ecf1086c275358fdfb385623ac9692143d64ed9d6dc2fc9350e5d6b3222efd406095b1b5a6b5415c84e9799d6cb7f429392a63faee9498c625b6a6272246b'
        '12dddd4781914562a1aa89e73ceac75f98e27bf040c881b57b425ac5ae50d9b1126bdf296b1b7a85c4a2285e6963cdf1d7e6fed84ea4b823f0f483bae334dce6'
        'a5784c4c39ab02c8db8932367ee074f4cb61aaaf60dfe51fe96e0d728e9dbbc3912abdeead4de48c63924d9f5118a2a166fd01967cd679b86b593bb821ae5c68'
        '3a1e0573636268f7681a9bff77be58849b40277ac5545dd248298cd8bd4c5cddf0c83b722ac73d9325263111f73688853cf02c10219e80406f5b845444af8cf5'
        '2376dd985bfa723280ae31a1583a685a127489ecb7fd558ffdf2e352a26b7f5cfaeb39b1326300bf9dbb1bbde14613505a0e36f789365eed832157657b793c03')

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
         '0001-BACKPORT-FROMLIST-drm-Makefile-Move-tiny-drivers-bef.patch'
         '0002-FROMLIST-drm-radeon-Call-mmiowb-at-the-end-of-radeon.patch'
         '0003-FROMLIST-LoongArch-Update-the-flush-cache-policy.patch'
         '0004-FROMLIST-USB-core-Enable-root_hub-s-remote-wakeup-fo.patch'
         '0005-FROMLIST-scsi-Bypass-certain-SCSI-commands-on-disks-.patch'
         '0006-FROMLIST-PCI-Use-local_pci_probe-when-best-selected-.patch'
         '0007-FROMLIST-PCI-Prevent-LS7A-Bus-Master-clearing-on-kex.patch'
         '0008-FROMLIST-RFC-drm-amdkfd-disable-HSA_AMD_SVM-on-Loong.patch'
         '0009-BACKPORT-FROMLIST-drm-ttm-save-the-device-s-DMA-cohe.patch'
         '0010-BACKPORT-FROMLIST-drm-ttm-downgrade-cached-to-write_.patch'
         '0011-FROMLIST-PCI-Release-BAR0-of-an-integrated-bridge-to.patch'
         '0012-FROMLIST-mailmap-map-all-Icenowy-Zheng-s-mail-addres.patch'
         '0013-FROMLIST-net-phy-motorcomm-Support-YT8531S-PHY-in-YT.patch'
         '0014-FROMLIST-net-stmmac-Add-glue-driver-for-Motorcomm-YT.patch'
         '0015-FROMLIST-MAINTAINERS-Assign-myself-as-maintainer-of-.patch'
         '0016-FROMLIST-rust-export-BINDGEN_TARGET-from-a-separate-.patch'
         '0017-FROMLIST-rust-generate-a-fatal-error-if-BINDGEN_TARG.patch'
         '0018-FROMLIST-rust-add-a-Kconfig-function-to-test-for-sup.patch'
         '0019-FROMLIST-PCI-loongson-Override-PCIe-bridge-supported.patch'
         '0020-BACKPORT-FROMLIST-loongarch-wire-up-memfd_secret-sys.patch'
         '0021-FROMLIST-loongarch-retrieve-CPU-package-ID-from-PPTT.patch'
         '0022-BACKPORT-FROMLIST-ACPI-PCI-check-if-the-root-io-spac.patch'
         '0023-FROMLIST-PCI-MSI-Conservatively-generalize-no_64bit_.patch'
         '0024-FROMLIST-PCI-MSI-Check-msi_addr_mask-in-msi_verify_e.patch'
         '0025-FROMLIST-drm-radeon-Raise-msi_addr_mask-to-dma_bits.patch'
         '0026-FROMLIST-genirq-reserve-NR_IRQS_LEGACY-IRQs-in-dynir.patch'
         '0027-FROMLIST-dt-bindings-interrupt-controller-add-LS7A-P.patch'
         '0028-BACKPORT-FROMLIST-irqchip-loongson-pch-lpc-extract-n.patch'
         '0029-FROMLIST-irqchip-loongson-pch-lpc-guard-ACPI-init-co.patch'
         '0030-FROMLIST-irqchip-loongson-pch-lpc-add-OF-init-code.patch'
         '0031-FROMLIST-irqchip-loongson-pch-lpc-enable-building-on.patch'
         '0032-FROMLIST-kbuild-install-extmod-build-do-not-exclude-.patch'
         '0033-FROMLIST-LoongArch-Select-HAVE_CMPXCHG_LOCAL-in-Kcon.patch'
         '0034-FROMLIST-LoongArch-Add-HOTPLUG_SMT-implementation.patch'
         '0035-LOONGSON-irqchip-loongson-eiointc-Improve-IRQ-affini.patch'
         '0036-LOONGSON-LoongArch-Add-CPU-HWMon-platform-driver.patch'
         '0037-LOONGSON-drivers-firmware-Move-sysfb_init-from-devic.patch'
         '0038-LOONGSON-drm-radeon-Workaround-radeon-driver-bug-for.patch'
         '0039-LOONGSON-dt-bindings-dmaengine-Add-Loongson-Multi-Ch.patch'
         '0040-LOONGSON-dmaengine-loongson2-mcdma-New-driver-for-th.patch'
         '0041-LOONGSON-LoongArch-Add-canfd-support-for-ls2k3000.patch'
         '0042-DEEPIN-net-stmmac-fix-potential-double-free-of-dma-d.patch'
         '0043-BACKPORT-DEEPIN-pci-quirks-LS7A2000-Fix-pm-transitio.patch'
         '0044-AOSCOS-drm-amdgpu-radeon-disable-cache-flush-workaro.patch'
         '0045-AOSCOS-loongarch-re-introduce-add_numamem_region-ini.patch'
         '0046-AOSCOS-loongarch-basic-boot-support-for-legacy-firmw.patch'
         '0047-AOSCOS-loongarch-parse-BPI-data-and-add-memory-mappi.patch'
         '0048-AOSCOS-loongarch-add-MADT-ACPI-table-conversion.patch'
         '0049-AOSCOS-loongarch-correct-missing-offset-of-PCI-root-.patch'
         '0050-AOSCOS-loongarch-fix-missing-dependency-info-in-DSDT.patch'
         '0051-AOSCOS-loongarch-fix-DMA-address-offset.patch'
         '0052-AOSCOS-loongarch-fix-HT_RX_INT_TRANS-register.patch'
         '0053-AOSCOS-arch-loongarch-add-la_ow_syscall-as-in-tree-m.patch'
         '0054-AOSCOS-la_ow_syscall-add-kconfig-for-module.patch'
         '0055-AOSCOS-drm-loongson-add-ls7a1000_support-module-para.patch'
         '0056-AOSCOS-drm-amdgpu-disable-ABM-Adaptive-Backlight-Man.patch'
         '0057-AOSCOS-MIPS-Check-address-space-in-ADE.patch'
         '0058-AOSCOS-kvm-disable-enable_virt_at_load-by-default.patch'
         '0059-AOSCOS-drm-loongson-add-ls7a2000_support-module-para.patch'
         '0060-AOSCOS-drm-radeon-limit-mmiowb-hack-for-radeon_ring_.patch'
         '0061-AOSCOS-USB-core-only-enable-root_hub-wakeup-on-MACH_.patch'
         '0062-AOSCOS-ACPI-scan-Add-pwm_lookup_entry-for-PWM3-on-LS.patch'
         '0063-AOSCOS-Revert-FROMLIST-rust-generate-a-fatal-error-i.patch'
         '0064-BORE-linux6.19.7-bore-6.6.2.patch'
         '0065-CSMANTLE-loongarch-Add-CONFIG_LOONGARCH_NATIVE_CPU.patch'
         '0066-BACKPORT-FROMLIST-perf-annotate-Use-jump__delete-whe.patch'
)
         
# vim:set ts=8 sts=2 sw=2 et:
