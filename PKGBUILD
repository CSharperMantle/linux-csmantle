# Maintainer: csmantle <aur at csmantle dot top>
# Contributor: Jan Alexander Steffens (heftig) <heftig@archlinux.org>
# shellcheck shell=bash disable=SC2034,SC2154,SC2164

pkgbase=linux-csmantle
pkgver=6.18.8.arch0
pkgrel=1
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
  # FIXME: -arch0 packages don't have official patch list from Arch.
  # We track patches together as *.patch files.
  #$url/releases/download/$_srctag/linux-$_srctag.patch.zst{,.sig}
  config  # the main kernel config file
)
validpgpkeys=(
  ABAF11C65A2970B130ABE3C479BE3E4300411886  # Linus Torvalds
  647F28654894E3BD457199BE38DBBDC86092693E  # Greg Kroah-Hartman
  83BC8889351B5DEBBB68416EB8AC08600F108CDF  # Jan Alexander Steffens (heftig)
)
# https://www.kernel.org/pub/linux/kernel/v6.x/sha256sums.asc
sha256sums=('37f0c5d5c242c1d604e87d48f08795e861a5a85f725b4ca11d0a538f12ff8cff'
            'SKIP'
            '505d823490e964e66ebe5889a3701347b4e4e2faf1772b3964f0360a176eadf8'
            '60e26da620d96a7c0fad031d25b11b7d02a809d558b819bef2b10575f96e8195'
            '797fd7271367a1ce04485dbeb21eb15ec2594e9c7e0c0111a761490b21d7c6d8'
            '22e20a599cf25bf12974dd3379c71cbb875da592aba93a0f4574e46aa0d15f5a'
            '10a7832124b0fdbc0b6bed10794a93f3ddd9420ac6d63a28fb090d72dd982033'
            '812af8534837720718b125403b57f83b56566af5ee6e886245459f0c24da6f1a'
            '439c7a269574ba2dd715eeddd959b41f6931984faf4c5ccf6f829073c49e3d9d'
            '3165aecab24e06625f7560525cf4cf79937ac026a8f4c42a9893a3166d9bb752'
            'a0016c4e4d837929647b5d19d06783dd14a6b888e60fe56d821ffb9e4a571901'
            'e2f412e09c7dc8a63ca9b5a4cf4ad06e6f007ee6d0ecf0e9ff0495658368a50f'
            '963fcca3491a158a12979513349b467b92aed433ba3c5e913d25abc4831d6493'
            '73f4150e444175c19d25856c4f96ee57d63f0dc6f7733eb4e3efd044eb91cb1e'
            '06e58d2b1a6584046246785758bb9b3c586ad8819997b7ae5f3fed83d071807f'
            'c711a315103f442ba4504fd85d52b12bb1e40d43909e1bea12cf0e7d6c96dc63'
            'a795cf9c621f1557eeb6da7a87e84a25a2e62800c509dba9cd5bd2324a1acafe'
            'eff884aaa2a05d139f6845aa358f5bbe15f2edd757cdd7e91857dd1b2e592383'
            '4e6c7beb0b6cc3f648e8f50595f5e2eca5e8aa1c3f8d876aada1dc3ba3517cbe'
            '7342fe388bd9e36d703e32d4afc3e36cac1e8c8bb0d6fe0faf13b6a871448d8b'
            '00de8a466477da6749d40a8452703157d1eacccf1a8417c507c47da9902782b2'
            'ab6bbd7a8d52b260d44ffea11a7c0107482a8818a32d678a52b2a432f3d1f1f6'
            'd04a5b05343ef0b53cd5e94cd02b961f390cc009725e7d07f13a45c080324c48'
            '30f7c9e4b463a3a859b34d8c3ce76541b321328049e83fa2192063f101cc2e8e'
            '75d4f3167a8a23310ecc0f9ec38c37a010d6027ba2ada6a8665b0e6fbc1dde5d'
            '308320eb378578d1eb92c98ac84f107950e84a404cde157a399d6a1f7eca828e'
            '1383c5db33404c80ec8f9fbdb48fff3bf3cee0cc7f1e67b64367bf35d7623da7'
            '8cfa78a3ee1427b66117b76effcb74c4b3b59681bf0470692312e90be8586f48'
            'c0e33c742fa02e1a31404d78c82c2269a2b36adfc8b4875c0c10179614f785ea'
            'f79442fe7c8b508e8601bb3ed3a0420adf15985727dd724cca1185615f267185'
            '34f1740d722b403b85b2ed2481248ac46c3d948695a6fb337e5e568293184f02'
            'b7e63c0876eb0a1cdc5074cc0d9066b92bbf4016d30eee26807069c07cfc7399'
            '12087ec0a95f7dc7eebf2d3b6a5711c8bab94a8391da28b5c8ca7f21ba8a6535'
            '32841923e8997a3d210fd59b434c413465820ed21f943b8f867ac1a6c29019fe'
            'ce25353113febb79700926e56bde10d1d918bb49ecffa465dbc713bbdc1e378e'
            '7fe6de45e701feab4f95f6851cd1a109aae341bfcecffbf2ced7e75814339d16'
            'c77dc1c7ce7bef289ab1650a10bd3b5b3e8c170713464bfd6bb1bee318b76117'
            'f159a22f57b5e7a632cba1dfe63dbca01e13069bc6ba0e250aeabc7aaeabee60'
            '84f6d1765a17092e099276b343edef43e6754bd2f32121df3cd7d11e8cca274c'
            'b627af414713c703b1823c5a6f63fb5bbe39fd08a9af797e3fc41bb82fbd8d2e'
            '2090817b7f37bc12bb581e435f10c646be11d626de66f8e375f697b0d642faa0')
b2sums=('9434b32e65e42c8663233d6ca4a7fe4fcbcc8fe2f5b0ba1c3a0bf602c0156009ecce4aef8cb6ed9435bc9b4f14cb4f5be8b5b8ea80f64b1dc2c9d4ad0faf5b4e'
        'SKIP'
        'f31d83e1e10bb901d0d25c1db0ad2844584ff1014c8bf36f342fcf1999f41e5e2d5ddfa20a5a23d4626c6b35005c7e01ebe8ae7f3de3d4b61a189a49add3a158'
        'b8c684b5baf73e687d8bb3379a757ec25d788b512b01fc10fc601930f087c7d411d338026ace88df603b201f512ce57bff28a2b646ddbf9e8ed9f65fba10681d'
        '323a7b55f34f60c39395c44b98f739c52ce142403fc1ec66230ba4dd0159c8073ee63754a97ba7959cbe8152624aa3a919f5ed50044585921424627e20ac455c'
        '15ecee5cfc294f86998c4e790416f0a018eee26413afa128f6dd3b3455773290a00a54b78528658c5c7979f96a2792660320661097cff35fdce554bd8ada71ee'
        '76ea414296ed11afd5bff9033ec494d6dd4bcabc99ade933d4b977cd5103628d8b07edd75b78079ac7bef207f42a256cb7ed327d66b50b05febc5166e0686a58'
        '1faaf5754727b8c54cab5c9585556a88d05356fdd9bfc76a97da54427eced5c00cdce4d15489bd5882548104e51e292d64f7ee8337048863c6653d9d9ea19d37'
        '8b8f5518d08608a2c7ce7881e9008779e7df259c5c7284590ad4cb799e5ab1300d2a425f685547c34d064fd2d74f349a02cacbde4469c8f342058f123d69805b'
        '2e33720620dde1df1a3d5cb1e2528378737e0a350bc1a7c51df582cb9c0536cd818b216aa7e83b4f28c0d4a731b00c84f1da158401f660e7854c289dfcb8d04d'
        'd68ddad4e67bbbf2b91b9eefab97b078551ecf72843e0ac419530d1bb5a2ed4314b04e9b734b6c104068a876429f9c558af3988f29f5e67cfaf095293a3e7753'
        'b3127d0e7eab2699c05ea22435375ce06aa41deefc2e466a4faacf8d70c40df4ba775e8efbab5e6cc824f1a26a7e0c56f4803b36a8dbb844160c8bb015d656b0'
        'c52a155e5691baecbe5a0b750e9f88f56a8edb4782872112fdb44008effb6796b26ba36026140276d2365d3900c4b9a3005d050587a4dcc92f7be098beddf520'
        '1bfd0a085d307ee151d724d0c06d4d4faece1031a0f75ae8b2fc13ada4252a2092139dbb1e1e8606387b325b462367f7ad3fccfaea6d08592ecfe1be676b24dd'
        '283eaadd40a22574e1f645124f545d2c53e7bfa8a031bad3ccae53c46604cde0aadd4973c6fe4b5428bf8f7614ee1fc59a666729a4e09b374639022ec3a2d649'
        'fe4660164e92d5cbb69a7ea3405531980a34ec15722a43245d0358627223df946036219536a501ecc39f240173adefe71dc1076473ed333f871b50f151295309'
        '23b365d8ad22f2f33539f1ccb3061fe26e0e092625666fba4265d7af01d282e481b5a2f661cd8eba2e92e45142810b497a587ce35588d19b4d34d455aa14ce32'
        '9ba86402aa829306d8f9e92dd6f1c26f38e661fdcd91bec635cc1a486bf04443ab11a45ccd369505f8c5f165bb181df3d418632bd0a4e8d09b6c778595d5a9a8'
        '7cde62a6db33de29bc44468d282fe2caef5aa98041dc0e9f6fb5f3705df7cddf40bc74e1d524c7755a3f7c124ef9cbfb2a83d5a56e2647038705d4cfb73f348e'
        'abe94d5d7655823a32c4c2fd41c11f3cc73cb20ee175aff13db93f8deeb37b9be14e7ca999f233e80bb767aff3666544d8e1f0683435f06716b5bbf06ccb2288'
        'bb2d1a3fc0d0742e54311f5c0ea3cf3f15fbcd88ed3c103be9af1f454248cc33e1bfbe3376870283d10badeb17d1e196414ad737073791706bfcd6eea20b7111'
        '3e941d995b33d1393c3d371a8fd8b47067a1fc97f5639749dc026f8e54c99655a8533fd7475273d94df56c2193238b9c3faae5d8bdf22c4fcfa5de98ff6beb09'
        'e535ad22ce528f6f2632d328d05770a94a22d5cc5bbfd4219c4e511f3a16be07e2ebe988f5873f1347453f55a2f1445173f336d3458527e128e2ac30e085a4f7'
        '4ec0c83ec9b2361494c367dd476fac1f91298ea51064b0995f7e7dd6330a6623c364b323997061c2a15c29361aa994c29690c14f14468d676d157a5e9d8a7256'
        '3d8a29121fd8b8d3087f09439c30748bb06347de9b3dc5b7471f4cad70f895233eed8f27442f7586faca5549244f56c7d798cedbb04a7e357feffa1a6c489966'
        'ad502e6a4b0942d6418866693d21c82e4670a436aebe1df8c2ade233ea50e03aab80c66bf59ebc4645fa00c2e4aa1fa4cae770574fcb721a1293059ddaffddb7'
        'd6843de0701dd7ff3c512531b8caad3969ddd4d3859ad83801107419203c77a2b80a2ab505e75312aa34aa3deae0f94d1f8822918f9c92ce3abacbc306f1823f'
        '771410be07e3937b1eb766c821e66b4e8f64e282f46a29d1c337c475d3f1bfe81acc027269a0d524db9668b07d382ffeac345db7b707df93dc8cb8d060fc156c'
        '8497d85f3a59653973abdf3567174c0152529ddb74c5e23aeb4c990bda6c45ca1dc6cc3b31b1faa9770cd80f62d769b1a94b95360ae8aaf0401eb24a4983405e'
        '5244711972adc07bd36561013f41be219ea768b6fbedcbec4faa9c12619b06b979259276b2fdc15324fc7666c86d193e3f40723b805f11a904265b2163d9f1be'
        'fa41823e026bc3de73bfcd44d414bbe8ad0e51877c1ab417cb649a91375be2304222ccb157519ffcb0e2db44b041729c2ea7476a5205fd6becfaadea83129c94'
        '90018d52ac94581b3f31487a833dc07df67b6013ba31c0a5b4eed819b233272842bf3a7b305157e75d3d386621bec4820ca7bbdf46588b0a86942e0c250a289e'
        '39f0d980361b537c41fbe02a4cc9e96a221515461cba14112ccc72dee8de937dd113f137151e8c03b6e45c172be6e1e5def659f7f81c3604b0c3af2158b324c6'
        '6d26ce98887c21e0ee809e4c1cb4f72340cc68902fdb012abace5133258de2ec6dc8ef6c67d5b9877564b2b156aee8db5e06f079d3338d4adb3ff6915c11295e'
        '4b936ad0ccb1066350e0ee4e104b836d8e2c5268727ff991b11d872ed05d281d90fe3592c12f44056a1d36bb30576059dfc9526a52dc3957a3ae02f3443be5ed'
        '4bc93fc83210d9da9fb800f5109c5add2aa0e438b031f4f0d3c5db442308141482e62d92362b64d54036ecfde2167c51a591cb26333b6f60ddbf7c25578d3913'
        'f0855fe1ab0308dc1ddd7f1d7c82673d131d868b12ee471ba5d2157e0744cd686e4c4d5537f0001055cee4da8e86a8bbba401064ab8a384ddeff36f087cec607'
        '7fe4a2169393f315ff85e597fe73f35025b27044c91f5849d0e99e707a2aafabbde4f053ab527794322983618a03bb66f9acd1a74303c3700d44316c91ece676'
        '80125a07dbf0772c5012e89598e8df31e30a8ff63e3df427ceb63112d12ab940bc52c815bc568b3d9e6dc9746f590918a28a05d1f3314650552a9aac0013aea6'
        'd857de1c140b527d567dd4476dbf5bde7b9891545d4dcdbf5f33b3be3f37d6d8eaac54bd8c995be310ccbfb4053abe7d3a2ffe31b6bba6da0717ae86986f7cac'
        'a119b0293264b62d6306ade2822cc3b3ff2f3dedb6483edd0555c15897f38ba65b37b9d7e515036c51e88b5ed87b9a5642ab1e234e81859541e5415cc629277a')

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
         "0001-drm-amdgpu-avoid-memory-allocation-in-the-critical-c.patch"
         "0002-drm-amdgpu-use-GFP_ATOMIC-instead-of-NOWAIT-in-the-c.patch"
         "0003-rust_binder-correctly-handle-FDA-objects-of-length-z.patch"
         "0004-drm-amd-display-Add-an-hdmi_hpd_debounce_delay_ms-mo.patch"
         "0005-Arch-Linux-kernel-v6.18.8-arch0.patch"
         "0006-LOONGSON-irqchip-loongson-eiointc-Improve-IRQ-affini.patch"
         "0007-LOONGSON-LoongArch-Add-CPU-HWMon-platform-driver.patch"
         "0008-LOONGSON-drivers-firmware-Move-sysfb_init-from-devic.patch"
         "0009-LOONGSON-drm-radeon-Workaround-radeon-driver-bug-for.patch"
         "0010-LOONGSON-drm-ast-Restore-vaddr-field-to-struct-ast_p.patch"
         "0011-LOONGSON-drm-ast-Support-both-SHMEM-helper-and-VRAM-.patch"
         "0012-BACKPORT-FROMLIST-drm-Makefile-Move-tiny-drivers-bef.patch"
         "0013-FROMLIST-drm-radeon-Call-mmiowb-at-the-end-of-radeon.patch"
         "0014-FROMLIST-LoongArch-Update-the-flush-cache-policy.patch"
         "0015-FROMLIST-LoongArch-dts-Add-uart-new-compatible-strin.patch"
         "0016-FROMLIST-serial-8250-Add-Loongson-uart-driver-suppor.patch"
         "0017-FROMLIST-dt-bindings-serial-8250-Add-Loongson-uart-c.patch"
         "0018-BACKPORT-FROMLIST-drm-xe-bo-fix-alignment-with-non-4.patch"
         "0019-BACKPORT-FROMLIST-drm-xe-guc-use-SZ_4K-for-alignment.patch"
         "0020-BACKPORT-FROMLIST-drm-xe-regs-fix-RING_CTL_SIZE-size.patch"
         "0021-FROMLIST-drm-xe-use-4K-alignment-for-cursor-jumps.patch"
         "0022-FROMLIST-drm-xe-query-use-PAGE_SIZE-as-the-minimum-p.patch"
         "0023-FROMLIST-PCI-Prevent-LS7A-Bus-Master-clearing-on-kex.patch"
         "0024-FROMLIST-PCI-Use-local_pci_probe-when-best-selected-.patch"
         "0025-FROMLIST-LoongArch-KVM-Get-VM-PMU-capability-from-HW.patch"
         "0026-FROMLIST-PCI-Release-BAR0-of-an-integrated-bridge-to.patch"
         "0027-FROMLIST-mailmap-map-all-Icenowy-Zheng-s-mail-addres.patch"
         "0028-BACKPORT-FROMLIST-loongarch-wire-up-memfd_secret-sys.patch"
         "0029-ANOLIS-LoongArch-adjust-the-calc-method-of-number-of.patch"
         "0030-AOSCOS-drm-amdgpu-use-amdgpu-by-default-for-si-cik-d.patch"
         "0031-AOSCOS-drm-amdgpu-radeon-disable-cache-flush-workaro.patch"
         "0032-AOSCOS-drm-loongson-add-ls7a2000_support-module-para.patch"
         "0033-FROMLIST-PCI-loongson-Override-PCIe-bridge-supported.patch"
         "0034-FROMLIST-loongarch-retrieve-CPU-package-ID-from-PPTT.patch"
         "0035-BACKPORT-DEEPIN-pci-quirks-LS7A2000-Fix-pm-transitio.patch"
         "0036-AOSCOS-drm-radeon-limit-mmiowb-hack-for-radeon_ring_.patch"
         "0037-AOSCOS-ast-Drop-drm_gem_vram_-un-pin-calls.patch"
)

# vim:set ts=8 sts=2 sw=2 et:
