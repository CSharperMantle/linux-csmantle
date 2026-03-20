# Maintainer: csmantle <aur at csmantle dot top>
# Contributor: Jan Alexander Steffens (heftig) <heftig@archlinux.org>
# shellcheck shell=bash disable=SC2034,SC2154,SC2164

pkgbase=linux-csmantle
pkgver=6.19.9.arch1
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
  $url/releases/download/$_srctag/linux-$_srctag.patch.zst{,.sig}
  config  # the main kernel config file
)
validpgpkeys=(
  ABAF11C65A2970B130ABE3C479BE3E4300411886  # Linus Torvalds
  647F28654894E3BD457199BE38DBBDC86092693E  # Greg Kroah-Hartman
  83BC8889351B5DEBBB68416EB8AC08600F108CDF  # Jan Alexander Steffens (heftig)
)
# https://www.kernel.org/pub/linux/kernel/v6.x/sha256sums.asc
sha256sums=('c16068a3af12e3943dee3b1eef57ca70229c069128bfa1184fb3f48b219d55bf'
            'SKIP'
            'dacb94dc3be57fc442995a3d3d1519775d3f6877a4e2fec437223d95e318f04b'
            'SKIP'
            '9fed188f89847418aaf6416b64457a30bee34dcd0fa42a84dbd0f4dfca063402'
            '157126a09f9a0db855ccada3d560c5a2e469c91186596b7f6b15afd2b983b67f'
            '87df2f27fd2e2a47f7200d49ed369ec74f58b0e0adb1969223b33817c055cd06'
            '51ca3aef0f75a10a5eaa26c246914da83808e197ea167ddd70eefee386ed8044'
            '3fd274ef0855d963d483ac4423aa1fb19be1777a735f39adb92dc19669467051'
            'f519ec76aa5e3ea7a9033c1a0bd524e0785fe5fe1adba68d5f26c0d7c2e51cd7'
            'b2ed4e050c904256f8ae596a365fcfe9f819d2440adbf783620c42f6193ba8ed'
            'd8966f20a269aa6fd28a5da30a67b94b93690db32d37cec0098c4cf0da0db3a0'
            '54497de641e9e6ebcb407c4cb5452fec8708297b0485971139004aa0c40bd187'
            '7da07be9dcd51d37e697d05dbdb4dcbcbe9d5f76ce276152f1b66ad1883a40d8'
            '264003a19b23f02d6b08c2d077c326e7c9ddd10804f0e5606c54a23ae19df877'
            '5752a5f3a05c727db4f3e0fe19520fcfdd345bd90099aea57dd7d609314c2d1a'
            '020baeef5ae505fb8a71b6b87f3c105529cea60707ca5457cb463a97c171cea3'
            'cccff67919e44f56124addc17ebbfe7a567548a00be8b3c46f41ceed459aa49e'
            'f94d75557929ffb9eb4af8fac68afdb7a3473236c11ee5b6c9636ec61048747b'
            'c5e02d266696444a2970dcd29067af91bdf1361baa2d4c0f33ed65b656d811d5'
            'c333ff49635f130c705c003558e4bfeeeef40a695377c52ed563fe028a210479'
            '73c600b8c39fa19b7c42c50a751369a716cade3c9625e1c69e97a42244727fd9'
            '55d9341e80c8598abd370a8d955c92f595de42dcd1e858b2624b9bbb32520c4d'
            '354117ca80e768ffdd88a187979e06d049df9863cd62d50f7a4e0dd3732dcc64'
            '88d86d169a861dd32f2406a83d5711126c5619edb6acfea7a231a5d7bfd5ffe0'
            'ef7f816712dbe095c857bc135a0ae2e4d7732ae7c2179a1113cf0f0a43f342fc'
            '96f3668f530c319e03023bc957ecdb6370cacaa114bceb0c2f0710a3096bde4f'
            '00d08c381689c5cfda3f76d9fec664324c1c3f9b07051ecef236565426d8b2b9'
            '2cb7a9137db57fa71cbd978889a66d7d45cc923067dc21b90879483d008b61ac'
            '867c7721dd836aa094a7762c97660d24a92d68e02ab8a5ecd4ea6bfcabd5c353'
            '7b124469db48fd19dc76cf481ba0d9fca54c7b194b0a3d07c6b766d849378d07'
            '66efdd7de0dd3eb9f37a0cbd4c56a1f65f3b361e60c17c8687755029d7fa731b'
            'f2ef8460b568fe9d3db4b7d67b5ecdf11b54935cb6d9f1a6b2e40e89a3014aa3'
            '31ebc1826a9e5a8c261ed338347a8fd606fcd700a6c99fce38caa7428783875f'
            '3c544c3d22d2de99e1c74626537c0c51a35b0a72ec94e5f5337bc100983b9dad'
            'ec0f9551a099b15c5bf9e4a3b826718ccf532813f0a91edab0812284596f7aca'
            'be10a8841bf80658cafdab1fd880025bb949924e19cbb5be8789cddfd30cf9ec'
            '5aac907450053761eb9a17eb3dff264de140b00759d351382ec31cb3baa2f3bc'
            '36362fcaf14e3d8bae738bdc9b74418934327dde01f148a6c51349da551c33a4'
            'ea72d3fb66a343a090fd1e9b981c0cb3ef53339e5fc45a37ecc204f568219fb1'
            '0ef2f1039b577a89821ee3483d43f0a52ebf575b812903ab927b23c355cfc71c'
            '7215a02e949b6533d13affbdca9b1874dfb005ddee93953f8848dc8ea78c807c'
            'a4cf45fd3f4b1c707b5b6fb0186aa306c1417b3fe7f0e55a1bb5847401aec677'
            '6f5843b9378fecd3f583107a7cf51f012de96d87274b7206be3e5445a0bbe04f'
            'a2ab76c9a3f9d874e6362db6c3ca497f71de9083b1505e82ed0943b6fed60c70'
            '7bd72a5daf0315ae939efb43c26ed15fd66899d89738915ab01005de42b87ff9'
            '6a2ecad7eadde22f061cfaa307665196eadd283d38efda83ba694bbe8c79b6f4'
            '7c2139d2e641a2e014bcc7c90c756abdb57ffdbfe9698c323d80b56d3fb629f3'
            'ac591ec98754520b409397510c30b5f2002a83e7c8f548feb7c4169b380f2d63'
            'c846aaa3d65a35d9dec0028d04f94c568160947c6567290c8ceee229b411a7f1'
            '57dc7fe251ab846769acb33bcc67fbfec3e798ec958e2a22639d52aad4f8b3c9'
            'b91b5f434d73ae00e970ca7c4917518349f7f05d094fa17701c5fdcbbaec4279'
            'f92208ef9500b81b818f54c59ea3d8cdebb88c3bdfe54d7a5578bf3045c654fd'
            '6c01a18c9eb9b3f09bdea1656477c16a8d2d19f150ed9487c1f317a7f1006101'
            '44909e2b53462e4dd12132c0b3f2656e3c72ad3562db279ef4ed45377a222dfb'
            '5887d79aad3c680b53bddaa642021466bdff24453ddbeef7ea3397f7eb2223b8'
            'd9ce0ac2bc4a1dce4037c0ec6b6ab452b1ce6699dde56dc5a1badefcf3dfcf56'
            '5465a1d5328738f15b5d548e9e5ff4750f6ad0b91ddd01e75601e03e67a7f418'
            'de8be629a13042382f6131243f16b630d3eeaef0bb0cecab1d7558f643bb1a2d'
            'c42ffd06288bdea03872e8ed5d5f24c6f96547976ef1aa92737b30d09dbee615'
            'ef11e1fbd2bd60ad77e92fda39c5cc7e12046b47b1018a6a339b11e16893683f'
            '58bf6b01a1ae161cb5c72a72dd4faefe2c7035d77389865c328a6645599efde8'
            '55928d8fdf848bfcff992c8a8abf80d2f81a34abb206066dd3bdcd568d5e5143'
            '041bb9ecca61b630fd53b0676277db7b90f855db317ac0f7b7594095b645eee2'
            'fc3c8e946f31cd8b2facc4122313b61ffd05a0afdb312c4a925963e73d68841c'
            '8faa8365d706d57cefc6c5011e8e66ffb638240664c843fe0cea47da0acb088e'
            '645587b98f47bf37d3eeb876e753fe1221302fbade9dc863bbbc2aa41a1e495d'
            'ccea9f3eaf13ae0ff85f7f0f4e638230697ac2fa97be471d16b3fec308008896'
            '49610c50bc10063011f895c49fd332950e543c49f362230cec277dcc41ae730b'
            'a790b2f4bfb9756677a80a4cc9ca209916fcea9a6d0f299cd0c7b64039c27c08'
            '334cdc6342f5a4c2c48670b43298740562a4294ad35c598f0453b539fdde5488')
b2sums=('6be41037c5b18e9a8d1c58fdd613e37bb5c841b7f43baf95516f3dda461adc6eb20da03e6a8892bd5b8410125ad42dae8ef4634a0eb95b84aaf3882a6ed00074'
        'SKIP'
        'edc6d11f32f16a53e520b53b52be690d192c0a64153419cbba65e4a2c0f426ce76ab2c10dbddd7f82f2c407c071039b05018796cf2b8ba501d46e3a259146ced'
        'SKIP'
        'bef3377ad86440af76e9dde4c29c9f4aaad42f5fe343f7d31f5eb537d6d358602f996f5d63986af275f2e92f94e71dc28c320edc8c03d05bd64dbd8ed23d75dc'
        'dfd366b283243f95c318471fe35e3a36646a38388dd6c4d9746bc981985a02ea303d75127244e9feac14564a8f49385483dfb56a8842814bdf97ca747bc2a4d5'
        'ee5fb2bd15a6199e42d8496181af49d9f4cbbbfb35b2bb155e50ea74157fcf2f92262d413aba53231c3134db4c2f494dd27e55fa00bcd20f08c885ad20b82182'
        'fbb36d1c8e7d53fa120641574db2272fa7f20eba9f57a480bcb5ff54be2d89704c9eb6a207c991f6be2e0c539a8b20dfbbc644b147a0a1c4d41ab753b4227bd4'
        'f4f82b12e78739950566b40eaf3e01e1731dd61174a28f4b965e9b6f66d902b6b0a27b4815dce1552098c6a6a7a97134bba2a70d31ed60684da986f9e76dfd04'
        'fee7b806f238c585281a65f9ac52cfe9c04a749c9bf99179819e314b2e4916afeb8ffe0341d7ce8ecd23f4df6eefeaa27b5aea33b4a19b910ed88def23adfef9'
        '91d92752bdb48a030235a474efa6e17163f0042873fb401ba5b337af03b2425f9bbd173e4e7b22fae15f7bfaf6b9a6f7ffe27c64e9bc59a8f954828baee92454'
        '1c47a378d6efd5b912cc9bbecc70524889ec15833b9daa4c4905ba15467ddc800678adf48b9bbeef99b32b01b6d12f9ce698c51a799dd07789e965cd62fb9ea0'
        '8a218a88190ec6d04b095be1b503d4d621beb2ceaddd4acbae60aec63810b5aecf75e28ff3aa13ef048ce266b7647285fffff1e8839eb0695593bb8db957dbfe'
        '910a3373479758d61fdc72907db1d5d36418555936506f44e22ab937a6ba9bcb9c36c8de8adbf7e8a0574db9fc49cd6a5865b595e37f758fab072be48bd6b767'
        '066a285965697865ef12a12bc1dd0943a192a33030e29045e1c52c7ec1e39c067534716974482b150650f68d13265d80252d5396d3a955029bee6cb54fca832a'
        'a84bf6bf29334b04d21a1e022ecf87a620a879884b0fe5d51253fbb34a894eac757d9146f76a8ae14fba0c81e94f57d38d9c9d16aa2de0da555b5ea78ec83623'
        '827c30cc351481398c7fff44c359c19a845cb9b9282a44a99b6dcb8d8418eabc015025d33fe4ed0a097f5a7d3c0d5cdea37fe6081af8ca5b9382118808c52742'
        'dc2a2f6eeb2f406e527f9d639ce57bdb1ceaa07def933ee3dfbb9ea5eba45c6e73e2bbfee65e7f504d57dc22992690c1651a99859ebd776deb5785762147fcbd'
        '9710ada9252a4a96bf2013871bbb8ce3d08b5b05c87796d7b9910cc64ffcddc8576450db5754d9b9d4599d6f6c7962595704ae1163d05271dfc1726445e10fbf'
        '6b74df00cf462b6557e0c11a25a4f0e3025bdb1340f813443b0055c714bcf587ec5f851b8396ea0f54cb6453f866ff645634fcf05f28c14089555695532bf248'
        'aa2b5c342449a02a8065dcb870262c1492b22cd9eb9efc267a80fc6f0e1e345af47f2c3082a1a215f619a682b794313dc6d2c7f47b6c38fdc91485c6702ae6e4'
        '1bfdd6067f0c697615dc4909c4b194821ed5200741cb64a776de3c373c9f1d50ec59aebdec88f37d665c74a20af6f9b394e2ad78568bda22f99323e9bbf61a76'
        '813a8fd115e4ac76cc77147c99ce9af5a757109b2214433737cf7ad066ce2b2a404e8ecd5dbcf1828fb6b05d2eb967cefa57d67c6139dbbafcf0f54459568602'
        '118405782f3e3f183dcc377380574ee5804ce770642315d547e66ed10dffd93c8d5412ead451dadff603aa55ca889c17c64a43ed9a9ed5d8dab360dd23a55058'
        '3d19892812bb217ac96969b2c8861b107067a34bbeb3a24b0b8919bbd4c44d46e068412c42bddc3808376cd5687c32ce9bb124135a456f7da6676e4cfa5d6c10'
        'ea7975b66d8e9cf173f513a1126a419c1068a2cdffc51d1e8afab305d7186454fef158dc92665413e25eadf785b471c702a9e62ca54518e218ebfe98672e3216'
        '7072afc4c5e5b8e76c4fd3e1ac8a2987f8f58b43f80b3809de403f15e0d38d5d13c51be50fa1cc1d8815af84e5cb1a7be59e9a45399c6d9a678e906b06ab0d2c'
        'beafb247b0f1096d22b90ee8ef6243afbb40f4375b8a210210cac44a05ba62b256a8f88e0bda6b461b5e3c72dd80fdef89eaa9c59c3db77a5a849c7cb05f802c'
        '56209de5a11ec9673bd6c7a3b763d44c214a360e32d1154ce7c053feeba28167d597b42ce2a6bf3f45e954fa8830d274c5358f7edeae36375a0ad7ca036fe5bf'
        '3ded98d6ff199dcae60484ab13f54227f922fdf17cbf04a39a7a72edf4f0582521e8764ec8cc41b5b3fa96d9ee0627266f1f4c5152f29925144f52f3f6364927'
        'f6570156cd63a1a84c295165e536b7f33a9f79478ee9c7a4afbc6763e70a2c99207c1727ee180b723a3f4f4d8667f36517636fec49b60a27f31921dd2f55262e'
        '98ce77b870cbcdd3a1a31300bed9422f007ec01b4e6c3ecda183f6024bea60b59b9268cf4b23bba4a727595c0f0336ec09c07017bea6b4f1e97100c6199ece6b'
        '4ea02d956b67712236295975b12ef0ee7ecfba4ed4d51f5239bf35cc086f71c5ba54697b473412a428c3cdc15b4129dab37efa2bda97a42b4be35872fd4ad00e'
        'd77c258c1a38d8243b069ebf420483caabeb7724c595ef57a95ab3c446174033eb9f4cb4f299fb47fc00fcb9f7a9812d945b6960afb79b25cdd2d6f0c0aaaea8'
        'ca8560be032e8033f63fb1990e02864b9fc1efa43d7e569ab2ebd0bc1a0cb4fe18dcd07aa6f93d171445739a3287132f7ab15612daffa23273bc2fa70bea3f37'
        'ae3150234e8933af538d0c67d41d0ed09a474c18997a7616d25501678919b7832b14bd92cb6a057f17bdbd97b2c5c23efb30cf6d266910b69770e6d7c17296f8'
        'f64ab754184421eddb0f12d5a1ea76b7b7f33d069da4e3df121c82dd95a85741b9f40e22a3ecfe609c2d9c153643a5391104e01d9ffb7414a1b83100ca823576'
        '6852569e725fee277e628b3ee2783a0f951efd59a26d83258e479b35e3bed012b73caed955be31848c7382f98eb8f5ce8ce42a78360765801a23abd9be36088e'
        '8a799bb5ac915f9ab95fc57f3c75b24380ae66faad68dfde82eb9b772065fd9d9b5f15eeca51bc97383589cf388bc6b3d9cbcf5eb5001a0abafb34c0b70d32a2'
        'e72794a1ec332b875d262cf452914baff1fb65334520c685cf9ecf54bb74efa3ea3f49e53cf0ced1405b84b651a6c1999a91e0900756c840dfefbdcdc019a229'
        '0b1fc98dc0155069882c8571ed8197c1cbe8753718c95ca0c1c7c79b2f4f94b95b8a633e80692da514edeebb28b6cfc9fbafdfe812e90ba9ec909c5624ead950'
        'a27a4cee3eb029bdaec7a20377fe7e7b87ae24967c8bad56134a57ce811f934a772ab9407bbbb7be3b2d79efba7655b1f539dc0cda2a020ed7baeb60e5f55db5'
        'd605a8df3ce80227b1820cd8ab96bde09a1869551034bb22295ea422e2f40f44659aad3e8a4a6d90e32bbbfc57f79e0e2869cee5246e1b69814cd20121c50661'
        'a0b74520ecb5111beb48b99538332f964b2f04acff77d4cc538b109105f1eba6a829aea48d26878d275ba8ea751009eb092658780f4538b81994ff5196122647'
        '221aea27b44b1dbbc2ff8a017d41cf2b55cd0c9b5b9f2968afa2007c0a871985a70ad3653c5bc80d4303d82e70fd7c7e253f28eabc06db8b67ed16d6a7451379'
        '1d2b6ef382e009acb09676837b4d45335314da079c1ce48dec65b3c87080fcf9b610ffbea5184e4e85ba08aae17266a23f98ff760b5036e51768a87f5845c175'
        'dc1b4e93b13f8459b6839c8c577cdde952f436a8f7c8f905f1e15f1a3c9f23745273c6f6de5fa0db22e8a112a09cf6d440b11f2c172c711cdbba3ae4715de49f'
        '44580458674864a41f96737bcf8319d1ab1621bbc01e919def7145e508a48164817201c825022242de86d1a7f11017339ccf120b6915ee4cbc2722fc402c7dca'
        '40711117aa14d052ab1b893947d9089df79a23e2d0d4faeeb54953188372f5c1fdaedafddf525001fad571d880bf0df6791b08d511d72c5431e76067019be7e5'
        '850e19d48ded858a0af589c1643fc4f3162709978a8f12395dbbac44a7389262bc760fefcbfc5af0517ec0d5b05a53a81d9792b945f4234a16c366de4b1f9793'
        '5d521c018dbaea4725826cb7c4e2ae6b2897ecde8dbe383b1cdbe4023bfd286a0857caecfda670f9c7d1115bafbf5876ba5c02e04689fe0b61dd82680e5f2e9f'
        'adfc1e789e7311986c39389ffd3468ec5eb4404bc1f5e1f4b98f10db8429c91dc63ed6aeffc4edb72af461ce46ac47422730c0236159da8e7ee474d1502b86fd'
        '0655c3af03fadef0c32da79c6c4f8bf103ab6481b314ae26764120b49047e45be60423589b6b1330116dc09b6452ccb6eeb3ea9b95d682f11af5a6d87477471f'
        'b7b48840e19e95905961869e2ac60f5b2eeee1b5003297ac99bc77e71703c9bdac4dbd910a80ad16a93567b2bb4d1e8a88a36483f159011257b1b69a09b5ea38'
        'c62c1550099aa05e80a73e2f76fbfa17888032d50f00a345d41482dcacbe8b9e4574888be890346f73d77305e86274ee541f6deeebdd9c97918adf8a3d50e408'
        'a39a055e90eb1415e16e1aa2b28c15fbd7df82e8782b76df0ed8a518634c4edb6905888680489d1a1e3777a4c0488611066404b0ef60bfbe1d66a0610b472a2b'
        'f9fd5010a3ea887ecaf0b14891928dfecf45f86b3fe8bcdd6a778462e4ec483d034c6f382bc408f743251cf3238b2d6939ae7f8b55560bc7eb7c6f647d1d1ee7'
        '9700e5de7cb1156c94d2277f4851b2ee3bf50e3e1cdbb6e0419454f7e57daa2dc9802c937c006ba2d21aa7d8be1b39d4a4823ead721beca56c53ff325e68c072'
        'b1227b6bbc15e01d44332449a4672651ca6f2bc44896305f4ed9d1bb70e0c1fab1a37501705c11816c58e508c5bb68b649fb60ab48b32f3b8516c1b08b6c16c0'
        'a504ddbed6d864df721d96a46bccd89232c3aad3a71efb6fb4cab66d3985656f93761e8c4823f0846b819672d99d7265d71f82b54f41fb45699f94cf786b67c9'
        '5222f59d480c07c4e55a1fa6aa7b3f7acf5951221f488df0f07ef36b0a4c726701e39ea1bb8db5fa530da451738ba5f26d93c4e460f8704e8e5263befa874b45'
        '485bb895b14757069d4e5649c8ea3fc1bfa701e026000d00e594547ac86f6c96c214212f46cdb155b446c5111eab6bebcf9df114c27550c4062a08d0e6baf311'
        '81291f203fdc79263de068a3bdd013f4b38dbcd6f6724fca64d515bed247922e49240826dd629628d4ee8b5250cfb5de869cc0f1aba0e60dca00d50ba8703ff6'
        'bcca4b045397a5019e7a523bfc9ad476ce8767c31db5877e1424d6b136f562e64c7ca5bd8133b5db8355ff5879c3a771577ab009a33ea2b9c3b789eb5786eeda'
        'd2fc00e686e7213c0b5f878eb87b45ef7562cba44c452c390ccca324a54e9b09b91edc258ee30c3bb11892cbdc1734251f11af4c8f6e192e6bf6c76f3f1ce331'
        'fba2888a0d817ccac7badaf368ea6bb116a0e89774d58925f93e7e7dcf3be91146beb39634cc5f01d696b5128ebfd9d57e020232a4af8614c6ee31f1ff7955ad'
        '1e642a1445ca539952058c62cf254fb93d16f7f7892c03be2abeabe46e1cc16f1bdb626cd02cc27b6edf9af695cb56a54bfe7dffd809d5e581770b75f9b145f7'
        '23d390f728066615e57255dd0ddc8306495b16a5f0f6f97f232d7c67ac4d74938e11c67afc0558184ee006e61e6a6d03453884e70278119a1dbb10c72edad56d'
        'f9ab703b769ba190c08d67d0a8f4437980e3bac8a30e6ad28541a268525a1943d7242388f24e56e15d35969777ed7fc1cd5b5c4e7ef393e39b96b705872fc4b9'
        '625077ea928fa96312dae5655247035e7e14072e2b87e1bb2ebe324e8edd869a79d658f9bf403e3d9f538456149c58932b9925a091c85b2f351ee796100a1296'
        'e812a4c88af4e66c7d0f842b72ce131ffb9f0ee445d9aa13d4ac2b16333cc2308ef5c3770860ca31ecdae5760972b3e61adc228db794e24456de2f0f12e24cd2')

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
         '0064-CSMANTLE-loongarch-Add-CONFIG_LOONGARCH_NATIVE_CPU.patch'
)
         
# vim:set ts=8 sts=2 sw=2 et:
