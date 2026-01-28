# Maintainer: csmantle <aur at csmantle dot top>
# Contributor: Jan Alexander Steffens (heftig) <heftig@archlinux.org>
# shellcheck shell=bash disable=SC2034,SC2154,SC2164

pkgbase=linux-csmantle
pkgver=6.18.7.arch1
pkgrel=4
pkgdesc='Linux'
url='https://github.com/archlinux/linux'
arch=(loong64)
license=(GPL-2.0-only)
makedepends=(
  bc
  cpio
  gettext
  libelf
  pahole
  perl
  python
  rust
  rust-bindgen
  rust-src
  tar
  xz

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
# https://www.kernel.org/pub/linux/kernel/v6.x/sha256sums.asc
sha256sums=('b726a4d15cf9ae06219b56d87820776e34d89fbc137e55fb54a9b9c3015b8f1e'
            'SKIP'
            '57c22879f2228398564091db2ec9b186acbd56dfb0e1072f83418bfdd3829aae'
            'SKIP'
            '505d823490e964e66ebe5889a3701347b4e4e2faf1772b3964f0360a176eadf8'
            '60e26da620d96a7c0fad031d25b11b7d02a809d558b819bef2b10575f96e8195'
            'b0fd3e8099b0950e7a8c3d7059aff28591ba6bedee6c84406449163ab2bbc52f'
            '979302da4c16ae79da6f90be0aa638463b8521898a6102933d0c300490301d69'
            'a39ac4934eef20f1051da06bd8cfaa1b4ad2414985a8d3208b02eb88bc176fe5'
            '5b52bbf899c1107deb5e9df5f974965c1c715a23bc692dbb78cea5336c38d698'
            '78c65ac344a38cfeabeb40816ba6bdbdfb23986350a11ecb731d0f1282cc4478'
            '2de5cd51a986cfdc104f5cc6066714bf798aee8fbb2c5d46372acc85ab5b0517'
            'c140990f77ef26c1bcd1295ee7cc8c96706815250614024187c6855aba0781e0'
            '91eb22aee9baa6f7b542bdde8fd9515e7fd436326d1984a3540353d9fb803b76'
            '31da4313b1f3b3e994364054c6b42c0c113348f0f6cc192a668f7725dec3ef5d'
            '65cbe858330dbf551f3d6d7d988b2ce8378f2bb29f03e09bfc33f1046a2b952f'
            '600532e4ad26c32fb75807e1ec875c557e368f8150b35f8cdc3d8f246b869b46'
            '91c98780e1b32d80fde4c6a5992ea45df72d2fa9c39775a58c64c731429b381c'
            '1f2e255c26f6a8bcc83152b48a989c1678a5d2729e0b61da386a20b37d510936'
            '16f20d8eed6d0bdd1301f659b31fd54c6fd79de9c9e3740944012b26674d4ba1'
            'f61b021a0124a9ce0610e8f27493c034140ba76586f79d23f26558376a3d0bed'
            'e133ee1a4c4fdbce811f89e45790ce0fc183ce3782ec490373361ecac51f4d7a'
            'a15027c8fe5c152ec389a470a491689612837c28ae52bdf8e2eb215c987fb481'
            '01fe3816cd4115f0e462b83cf8c21d7963de48e938519343816f58204e05243f'
            'ed01e256ae5d58b2b3de975712b9bfcd959953df241a3383fc1fdc05204f8715'
            'ea2aa7e8ac2593993ac10753ed073731a1b70d9e59138a9e891a85e310b87ae0'
            '627647a59ee7cfd6e2708734dade5de43736ff3174de39bcd01d4384e413a183'
            'f6d0d3599b096e61a11def5f50991c629e386ac95397ccbad51d72201d8a1216'
            'ee3d4b0302c8d5617cf87cb24f255c5ea214a306176d7dec6bd32b58cbc3d360'
            '93f0ed5db82ad513123764f999d944c8225f8f49f753c074bc42180c7633361d'
            'b764599bd8cfc5099e3ebe6e40b52bcfdf7445a388f4de60a0c9bdcdccac2ebb'
            'e94e941b687a0275f7741eea1aadb850e025d61847762033a98609432e524b14'
            'efa0c55fe44df6b8a8703e8d4ceccaab610735b01830e10cf4f06048ad012a85'
            'e1fd36d8bcc318350ff67409da7eeaf1e7a96c1258379417046ed0867d3d2a31'
            '12f43abf70a9ab3a2214abc521e2d8dcfaa0961516ad9c38147021ab7f04547d'
            '9dd1af66e63e3fbd7a8dc0f6c40343a5f628eac13f04075cc3b41085cc613daa'
            '361b38dd89b3f5d3d019e2b8e399c33327b79cff8844580d9731dd7158432065'
            '2a2578d9e0c251031bdeeaa2299e0d92a7005e0b21ae2aadd9af273a67d7ac4c')
b2sums=('3ad31b9b36ea2c8f865c87e63c97a4e7b6684abee35ae71d5838026de9f476edb4c847adab315235293c5f37f8f3b90799ae2b3d41915716710eae63acbf6863'
        'SKIP'
        '8ece2f1b2fc6530cdd65e597141550c184089a206b9aa49cb9e46d61d2e7cf9c3f07f35ed523670d892aa7e62626644a5b1e98dd9c6acd824cb7ad3254c17665'
        'SKIP'
        'f31d83e1e10bb901d0d25c1db0ad2844584ff1014c8bf36f342fcf1999f41e5e2d5ddfa20a5a23d4626c6b35005c7e01ebe8ae7f3de3d4b61a189a49add3a158'
        'b8c684b5baf73e687d8bb3379a757ec25d788b512b01fc10fc601930f087c7d411d338026ace88df603b201f512ce57bff28a2b646ddbf9e8ed9f65fba10681d'
        'f03e92a15c482a99640aa2b96aa4c4cea350bef9ad28f4c17ae5ab0b5be4fba686006b75d99dd0be62e87e2cfe18b38c6342a63af7aff16f3b7dc4369d270c2c'
        'd81213126fdb09fda20685b26ca49c35a8e406fd4d5243558edc435e0a29fb0c2ad9d96d6a9d6bc566ce0fa611af7f704ae8b3c8bde622c8e1ada3d758329ef9'
        '4559d44e21fcf93c9fbaaa96459c0b83793df68cf85114ff32857d7c49def3ea671a05b27b6e6afa93173aa35e2c1f5b7569a0ff48cc006350801194329532b1'
        'add7334cdfba8907ef3f470ccff6950f6cef605263a7c5c138705fef1f97fc7d125ef6b2d21644d8a1b7f2f2fb35e48ad4c6a18bec9af2f0095e15777bf00c55'
        'fb752715bd7de3ca52aab3315eabc5dfd3a24c3ccf2496647b93edf026610b937185ba93cb8e7aae0919555e71cc7ab3051f68c4446293732fecad4eec033e36'
        '06728e2d5b11641200768d23eef232c516ebef7ea6ef878cecfb496ecbfafae707e5ce879466d209526c06e513cb9f2514fb82e7382a1bd2c8eb1e97ad38892e'
        'ed8d20ea183387d98ed47456eb220f7fa68fbf848e75f8fa2cdf49ac3d90cae520f1486bf3aed138a4af9cc0990b833c4fba6bbaf65e30956e239f0e1571baf3'
        '4864d565d44446c2bc824367dabdd71421adc1640b9d3a25b820195f84f03a6e8cddfcc0d12a7274131550bf2642977fe59001d3e983bbe4fcbc682dc5dcadbe'
        '06aa3a51d569077acd0cde86ce601248d883b58f3e2c642ffc251961021a5707dd94d9335cc656d9116e9aba9b5fa1f2a9c9e2c2badfe7a8bf7ec904dfda0e2d'
        'c41ac23cab76dd5d74c9b964aad13894b12e7139576900d562d6734b1b112fda3db1e58adeec28a14429817be785dc1889ab2f4303b644694d8e2dc3da113a3a'
        '8e933616ad045c3edf2f3468b23d9ae9d23385c1f643d67c88de954e891cb09995389006536d5c1cedf5fa6dd67ee22a1f157a43b6215b5358a1f1e6a96b245d'
        'aa4403893223fda812e78288999cbf818635a73d54d4d7f607d352fe146dc7c6cf3fa083fa2ea56da788a86fe34d9822a0548906549fced0b8f848bbb3a1aca9'
        '8b204c836063812570c285bff1ac1c21923c17827e24c42a5e1be49752aad4d60dbe12608f757c05cd065ca04ff26f86f3584e2850f175ccd929af7a9bc353a1'
        'c4338eff5fcea50b1bb3614c4a18703069800badfd6652f053b96ca6bf28b6d00e9024d5c024705ebe54570fbc53616632762bde5a718eb73d0bce00d47751cb'
        '70a9ea9af7d67b2dcffd0cdf067fc1ed7ce5c71e856480ef3c580a4b834a0d43b615bc3d6dd3d3af53577facc9bad453a31af74d8232fbed2fec007974a24391'
        'a002f8ae610f240a64538984715f8732db4a43bc2425c6532dff82fbdb0652efd3b905831192264684a73ed6bdc416c8ecf4e545cc5d4bc86045307dd4953fd4'
        '0422e8bd91911a6501af60602e00226112185698757a8989f7225d70bd3058f4db5e1134b84950a6aa21f4c98b673e1fffd0c4db161a91d388d97dc8bab70608'
        '81b26866a517f4baa14ad6986ba962c9850aa9a6bbc7661d2335fa554081c2a3ab2f8029d81457acb46c9f55a00cc8ceb2386cbf8b63a2ccf7625e49988a7d30'
        '71a99141bf07a973c9894e27df12e5620e375ec0f33b2675c28ba4694927e34663a3f4160aa046f1f446afbf871bf82463ac6cf0757bc073a7fcab27e681bd54'
        'ef9481e544cb26dbc0cafd7c888f3fc0ec3fa394ff56573f33f7a53361486056244d6cb759a9273a9e9283ace1ab2d2942127902375a20769617b4c376fa6105'
        'fe045fe08f798cdf99e991ccd15569bf565cda2da4924c5d6d0134c0addb8fcd75aa1eeed77e94106b17cf9b53034df3d40613a54ade870277060b063f74559b'
        'e23dc26e6d695db35275c6644c1fa9f07cba6c29cd184ce0c9db5cf385658faf1c5815980a60fad0a788e8cdd10f17d137de6cea654c4616322824810d4d44e7'
        'f614c43d73b917df7787d7720882346b8f548255150f87ec88437e07e580d222b0a41c4a6f6dd821b4c153b90685f2847572f881321d32553bce80adeff753af'
        'e0599202e8cde39dbe7321151e3aec2a83f425ad112ef1ed21852e1aa42ba6cf5808b5b3ff3a988c4af9a35efd39138ccb414e86962c83d1ac4613947e262281'
        'd96107c34e9343d5b193114cdb616280d5def0308a891a0bc91d4bdd5fecfa52255c6b839775a995412880bac440f26e3d746d0ef4b761b249f321bceebb742b'
        'b5cbef5014e3a66f496909b497f534944d61ca0e32585e1c0b9f7aac4a5eff5a3da50c7a0f88a8e5d8b60c6f3a6d3bf5e0b820542ebf3a11705e92694ebe1d24'
        '76e0ee5054dea5c56c2e9d348d9d8e5990e08f85434ed81cbf5620a1ce98e386368e866a4500156aa249f15fea9ff73598f88bcda36e4b25bb140693a41d7daa'
        '11d7dc28658d48502754f761b4aed0bbbd84eff7ca44bab523353d7276fc4f13133fb4a11acfa7267a58d86fe105c919c673ac545a8cbd1106bb48835165698a'
        '4b76aec376918f75f0fc71187387ef38e6430e3cff60972b72b8c8cb6031e84e56413449ca08200f5312c11c0b29dee74656309b84f35bf681cd0880bbe07c29'
        '1d3edc072d56442fc173f902ffe7f6a376e9a3a48b5668a0dde6a3572871e805346d01d94bfdb33a299577cdfa6e4405de6aee9a6e7e904198ff1c833f80617b'
        '3af648b1b006c4b3b34e3c74907c017853dde30636b29f7165f7bb9232216e3efe88a71b863592e628f9bc64d7cbb7cdac620f4ab80f5fdc27383e19ce973502'
        '185013376ed5f9815576ad7b356d8570529e2fabe5975e6a8e1ec86503c3a44d2289e0c19012cab912f5c569996ca83fc845086f183643137d8d69f51bc207a1')

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
  cp ../config .config
  if [ $CARCH == loong64 ]; then
    make savedefconfig
    cat defconfig ../loong-config.16k > .config
  fi
  # make olddefconfig
  make menuconfig
  make prepare

  diff -u ../config .config || :

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
  depends=(pahole)

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

source+=("loong-config.16k"
         "0001-LOONGSON-irqchip-loongson-eiointc-Improve-IRQ-affini.patch"
         "0002-LOONGSON-LoongArch-Add-CPU-HWMon-platform-driver.patch"
         "0003-LOONGSON-drivers-firmware-Move-sysfb_init-from-devic.patch"
         "0004-LOONGSON-drm-radeon-Workaround-radeon-driver-bug-for.patch"
         "0005-LOONGSON-drm-ast-Restore-vaddr-field-to-struct-ast_p.patch"
         "0006-LOONGSON-drm-ast-Support-both-SHMEM-helper-and-VRAM-.patch"
         "0007-BACKPORT-FROMLIST-drm-Makefile-Move-tiny-drivers-bef.patch"
         "0008-FROMLIST-drm-radeon-Call-mmiowb-at-the-end-of-radeon.patch"
         "0009-FROMLIST-LoongArch-Update-the-flush-cache-policy.patch"
         "0010-FROMLIST-LoongArch-dts-Add-uart-new-compatible-strin.patch"
         "0011-FROMLIST-serial-8250-Add-Loongson-uart-driver-suppor.patch"
         "0012-FROMLIST-dt-bindings-serial-8250-Add-Loongson-uart-c.patch"
         "0013-BACKPORT-FROMLIST-drm-xe-bo-fix-alignment-with-non-4.patch"
         "0014-BACKPORT-FROMLIST-drm-xe-guc-use-SZ_4K-for-alignment.patch"
         "0015-BACKPORT-FROMLIST-drm-xe-regs-fix-RING_CTL_SIZE-size.patch"
         "0016-FROMLIST-drm-xe-use-4K-alignment-for-cursor-jumps.patch"
         "0017-FROMLIST-drm-xe-query-use-PAGE_SIZE-as-the-minimum-p.patch"
         "0018-FROMLIST-PCI-Prevent-LS7A-Bus-Master-clearing-on-kex.patch"
         "0019-FROMLIST-PCI-Use-local_pci_probe-when-best-selected-.patch"
         "0020-FROMLIST-LoongArch-KVM-Get-VM-PMU-capability-from-HW.patch"
         "0021-FROMLIST-PCI-Release-BAR0-of-an-integrated-bridge-to.patch"
         "0022-FROMLIST-mailmap-map-all-Icenowy-Zheng-s-mail-addres.patch"
         "0023-BACKPORT-FROMLIST-loongarch-wire-up-memfd_secret-sys.patch"
         "0024-ANOLIS-LoongArch-adjust-the-calc-method-of-number-of.patch"
         "0025-AOSCOS-drm-amdgpu-use-amdgpu-by-default-for-si-cik-d.patch"
         "0026-AOSCOS-drm-amdgpu-radeon-disable-cache-flush-workaro.patch"
         "0027-AOSCOS-drm-loongson-add-ls7a2000_support-module-para.patch"
         "0028-FROMLIST-PCI-loongson-Override-PCIe-bridge-supported.patch"
         "0029-FROMLIST-loongarch-retrieve-CPU-package-ID-from-PPTT.patch"
         "0030-BACKPORT-DEEPIN-pci-quirks-LS7A2000-Fix-pm-transitio.patch"
         "0031-AOSCOS-drm-radeon-limit-mmiowb-hack-for-radeon_ring_.patch"
         "0032-AOSCOS-ast-Drop-drm_gem_vram_-un-pin-calls.patch"
)

# vim:set ts=8 sts=2 sw=2 et:
