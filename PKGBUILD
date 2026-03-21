# Maintainer: csmantle <aur at csmantle dot top>
# Contributor: Jan Alexander Steffens (heftig) <heftig@archlinux.org>
# shellcheck shell=bash disable=SC2034,SC2154,SC2164

pkgbase=linux-csmantle
pkgver=6.19.9.arch1
pkgrel=2
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
            '5207b4952003c6dfb5bc0222b54f0aec19d869d85e38b50a21a8881174223ebf'
            '6591a98b0ed738d1fd92710b00198410901dfcf1d46e7c6cf76771ca7a61695f'
            '096b2244bd3bec01ddd65a3fe53771ace688665f0d18fc6ed716668f4e9b3183'
            '8cd8f220fb1109491663024f5b3e9eeb29fa369f2c964a7eafdcbc0f23d11fcd'
            'd42070ac8ad8f61421243ec148954162caf54296291c656c024654928fcb2f1e'
            'eb9af5dc0d73b001b450abd8f25de2db68351b77bd80949759423c19f4073bcd'
            'f93e5b63128c465a5f643c7be3f3ce968905dc0629053a959aafcc5dd01658bc'
            'eaa61b73baa6471013215522339c8901297f66e15218e4ba8c8c46862540ffe9'
            'dd5ae10830ff88d64a842a59c4f77c264bdde6b27dc4084ce62348760e9298a3'
            'b83b52ecaad4107f176bf7fca845df70f3d309085345a56d3b30fa6428cbcf9d'
            'a31e0d3ddeb1bf5c8b21f75d0eeb5c88f8787c4cf2c3657f0e936f2ca2aff466'
            'edacb13033b21abec571f3cff2defc60decbfa1500a415f326037dd5fa5862b6'
            'd3ecd40d659336f5caff7614b1c7c9e05cd4f16842080514490284f61bd42753'
            '9c2ec31efa29d48d36bb794a8664e813cc55ecd48acfb7ab819e0578b9d7bf05'
            '574a35303cfa23766c5a030bc94ed59560b7e984923d1a2989b31bab9a0919e3'
            'bd2a62422189870f05ed23268059f88ffc4db914eb17192be41ca7555bbddfad'
            'd128a467dff459c08b0a9b80dc0376dc245d3c14ec741f0e48b84c357979923a'
            'cff47dc7fb4c567dd0cfcbcd5787af6d8e8e260e080daaa54a69581920b31c27'
            '77661970f962fc6c3de67b6aab5393d10d455789ac9904146deea945bceada57'
            '9dc21914b815d38f9aebe0cd253683559ca88096c00075ba738d2fd4fdd3c075'
            '350aec6a961b8444c084c796a980dfdd9332c5505a66f98f0102c6f97c7fe1bd'
            '848c56f7fc34034366b4c8a2f87b4dbddcf9b0dacb6920ec88c8caabb58317d9'
            '59fd5bbc8672cba4db389117879796621c206dbf30a024e808961bdcb3fa8885'
            '83bc8aede073eb883af8d90a1c9d431ade5d947a85897448c2afda8c08f0228e'
            '739c632b789aa8ba9b122849f07dff4df66ad877d602f5e9ff687813fb8bafc0'
            '076448b76882c55e3b09f133617189be01c83f8adbbedd3a5cd7775bf196cdc1'
            '1b8fbbf6d0eb1d5a2572bf039039c9881a0e6f8229104c76c0033c57d0d68c0a'
            'd0351f5a84e28752adfecd5d507a32dc7f2a1821f6875ce4fe632dbc6adf544f'
            'c7e7d3ffdccf956ea58e9f51ba4bcc1441a7ebd83dcae1c12679b07523554e66'
            '96b6853cff9e93049604245ef34eb2e795b5e178f9a1c8861c2e183c5dd0e66c'
            '5cf1bfffb5cec358bba1957ef1df5f91e76fae3dd134e1003364ca67ae4b8df0'
            '121936cfea35cd96c82bea8fa651823b12353241340b6fe9d826a983a53b9ec8'
            '6ad5918a08d4437d15b26945a1f9274a323d9b466bec83609a4bfb498cfb55ac'
            'c976ad71a3357aeb4d9e110c68d76dad22fa69a29c569cb959d6cd9ca386a70d'
            '38098df0e245da8c7835b9e5f07ecce3e535ab183c5fe0741dbf8f781199fa61'
            '6ca1b29f590a8f91c2d6d713a986d8a61f942dc948b47b41f4bf7150a16756f8'
            'b013c29853fa66e39734eeb896ef45044257c8911ae198e2fce5b9446d2f739f'
            '001be54b8bbce8a4ade9d0dcc1c182100c7a0ad5e58175d63536bc3aa277d6ad'
            'eccacf4574bd665c43d773dd7b45761300f72f5fededcbdcef04bb2422d792a2'
            '05fa69dc6542bab2e0314fa9d5499d463e912585024110c7b9e838fe4ff32d7b'
            '33e9edb8308e09b097421ef83c6d0109cadca15704b746df48df4615952335c6'
            'd3e01c236212c75ffe893dd7b8f6fd27c767ee0773726f317678e3724ab6a663'
            'b4faa7c05ba584b18f7a1d89d21cfc804cf8c60ddd72dca95e1b86fb65f60e7e'
            '7a70525bac5c4db605408c48897e7f8312162651722b092fca7ad954e273554f'
            'e8b2d81e3710252779be1a70023282109db41b23fc0b8c9a9285f4e577009c2b'
            '8273d9c83916b9b51080564cda1e1e6933ace390cd602f0771046f9b0d11e27a'
            '2f9c343a760b0633853438adbb5f4f7ddbe95255af206b208454d12a5931dc17'
            '99389825b1ebe294bb946d11c414c2050edab13683263632eb4104d754f0e5bf'
            '44b30fadc9e8f86a03a2801893d68ff09c646d21af45c8fe105bf91c1c6ea7f6'
            '141352ab0794013e51ca12ad57b32bf1f8c11959786ddcff5d54c1ece30c3503'
            'b2eb937a6c53f1aa3c61b6e21dd9486e1bb3cb12805f25330c4c41ced0676a38'
            'd83276e1923b0e9a5c8f3c840602faa7283b010d83efbc61a8a9f9858578108d'
            '67324dc28da916284a9782179400fd52c1547a384af069a6b9dc9e4f892b8a94'
            '34fd82d35f28171d7338572624e212b27afe9ddac09d8100e5c03a45d3c98b1f'
            '6ac267364b614861d25964831e1338ffdb944359815ef1be09e340de8fb681aa'
            'c0f3a50c11baab79fbf56d080a632da23aca006b68b83bcdcbb50eb8d503e720'
            '8d981913681506838ae5abcba1fa048d4b9d8302ed8d5455023a375dc8e5c944'
            '28c6e3c1661113f551e73613dbea94b241f63618f048ae9b642eea3099cd6449'
            '50c422f1e2a10ff63baf50f9e7566f71e09a3b37f34718038c51ec98048e3fe6'
            'ff93eb3b36075e08c5ba308856276ddd55ef81075e1f26ab3a034b328fe9ef52'
            '5655c676aae4a4ea75b777d12f350ce977a148b847e35eb3adce40c895da29e0'
            '1616b6614790c967b3c6c755a89e79f2b3edaac901728d10c914aee4a2f39b2f'
            '1bdc5603e49a30fa703c71e7239e1690d5a9c832dd7be0b178f4aafae786c7eb'
            'c5b945d08f5d3ece14eadbf83a086939f4a199a0f4b6259de9fdf60412cd87d1'
            '72f9a49d03cf0c79236d1785a9922de0f5aafac48330fd3ac76680c73dff8e29')
b2sums=('6be41037c5b18e9a8d1c58fdd613e37bb5c841b7f43baf95516f3dda461adc6eb20da03e6a8892bd5b8410125ad42dae8ef4634a0eb95b84aaf3882a6ed00074'
        'SKIP'
        'edc6d11f32f16a53e520b53b52be690d192c0a64153419cbba65e4a2c0f426ce76ab2c10dbddd7f82f2c407c071039b05018796cf2b8ba501d46e3a259146ced'
        'SKIP'
        'bef3377ad86440af76e9dde4c29c9f4aaad42f5fe343f7d31f5eb537d6d358602f996f5d63986af275f2e92f94e71dc28c320edc8c03d05bd64dbd8ed23d75dc'
        'dfd366b283243f95c318471fe35e3a36646a38388dd6c4d9746bc981985a02ea303d75127244e9feac14564a8f49385483dfb56a8842814bdf97ca747bc2a4d5'
        'ee5fb2bd15a6199e42d8496181af49d9f4cbbbfb35b2bb155e50ea74157fcf2f92262d413aba53231c3134db4c2f494dd27e55fa00bcd20f08c885ad20b82182'
        'c312ffba92d3e2196361fcb8e45cb5fe194e2279b52761b2004208a6057e0b385d1ef47ec3a43d89e09d7db4c77c53530598dd7132beeb7f46823405c428ac98'
        'eba18c421f6df5f562869fb8859d9a3827eff81db47041309cab5f57c99be71f5caddc79be3ecb3bebde530765c1a1a4807e222780c7ca5a0e272d10f5be5598'
        '9bbc25ed09a3c31fe50204303c31ca114088df591041eb517f9f2c3272bbf9a06f0603d716469f90951d2c6863d2198c7f89908ef19b68dfbc620ed1512f1e32'
        '4cd2deaf0e2d2a4f0c9da3d21a7a7c2083e3096f5efa876fe005ee8813fbe891d4c9957383b753fedd417d1dfca8746b19980fb7878f2d6dbdda78bf9f7cb14e'
        'd168d19ada919e86038961288dc578f2a65313b2adde9489fbc1e9fa89bdbefb171852332f3ee38865f15559cfa65d6b94f2b5db08c893efc1b0787b338cbae4'
        '50c702b5c4ade6334906ae1f833d3a6e3692c4c8cb847dfd8596d5ee2ac24b8ec8c9cc9b18ebc109fc40b4d3ca0d74b7e0e21b7e52bf8bd9e9ea23649787755b'
        'c9afb8666774d30ca1f73e93426723c66c892ab88c83fa340cf6e82f515c9eb5edafd63225404fe4522f50acc90e51c09ff14053ee35abac8dc242768b9fa6f1'
        'f3f6e8bfa84acc9c92835af97e9db28281a9204b608bd202d4e394e7d92c8b28c906c53ad17db0c003d0459f68d5013d6692ec7a9cdb792685aac7487a582d59'
        'd2faf42d2aca65499db956906b5f537e5dbcacdaf735b61dc720f99ca1390d13716c37e8455d2201c30d4f282f9209aad19aff9599064a53759a9eb23528eeb9'
        '9dee4cbf5f4057d17fe5b14bef5ef133da31965039c049124812689c9b5c8d66e23202894c5db2c83f1e7f4abdc18a05db891fc3af3c666d046b86049683fae4'
        '564526e54c70d1f9acaed51eed5835d5df3dddf1f7007d60b486c1896f975fa1b24186e7b9fb2f8b7be20b0766237d08b56632e4ce1d20d439eaa1fb8abde5fd'
        '1d5ef3f52c7bbd2a89ee0d8d0546f0c0025a31fc618c3e2307ae6cd1ee29a3479ba8e13199016e2792a55d1aaaedcff5e79df29280e88a881b3c303f1e50ac5b'
        '2ba4f253feb94db4cfd51c55c92c29313f84270856ec33df6e837be03fc5abc8a1ce9ebc098d0c9f77817de1ae6d3a3a5023228ce120c293dbe215a65adb765d'
        '02b2cd0bb07ef94c72de6fd3117837c2f27e88afb5faddc96df74814c4d39a3bb99d1b4a30039eebe65062400bd3c3bbe136d3fc2026eefe2abe3bfbe1b4a02f'
        'ba94a31753db6d4aa4e812b05eb7ad28080e100446ef8ac5ae977f6432b5426e997fe76372944cd61f0d14f57081c72fde577bb18f8e828d2b9742454e971396'
        '77343e2e337fb1436e333abbd76ff4fd68d5c5c0ac232034689195eb86a4be48fc03860b10c2d46c8423feaad5a4bb563abd30d3c42dd9c77fa5d5f74dc1fb39'
        '8fac0759993ca57ac79d6ea4ffc0ec0f786903208bb61da7046fffeadbbef45c8b01016109e9f62acba57d1c590b64fa43ef59f74294953816d88aa00bfbec70'
        '151eb50ac9e2df9f46bd9daec7bad31794a62b23d3a3820179979ffc3d8bab377209199a7831777e7f9f173bc419673b9bc25ee09f10c1b2d0478287dd44bc80'
        'b12defbacbe043a22aa29f70561085869ee115802472f07b76145e08d411619cfb3572ee3c576086a06ef01d776de1e981cb43defcb3b666b412c163afd24084'
        '5dd916db68cd82ed0599f3c63566eeb6c1e16fc9222fb4037a471b35b9c79ef6426eca75a9898f0ccf755480691093a9499322072e76c78363685af269b75c15'
        'a06893b5db6cb29fd5d58c5e08619d7389bad3f3efc503d639ab695f4b4b6cdba7b3411a4969a1790e52f8bf4739993829d853f4a2f819c382fe5ec939c69c71'
        '37e50f184de386ccd405b8e8f2a57a02cb894e8eecfcdfaaafacba97bc2ead9065851b22625a24899d328cfbf60db5f801fdf54e7680a8d20f3ae85f17cfc937'
        '94eaf5eea2b06cad5e4c5dcb25c6e4c969686bfabff9e9a0108493f13ae2e8e0914e5455647d8ff70d83804762cce2f2547543ac4417de74c9149265a69caeca'
        '21257605b4e5d0cf3ebee8b486ca9967e2bf97d8be79528833131b48d0c19b72a7b71cabf4ecf1f83e36c124fe18c9e6fd74ef6c6dc9ab8df23ae3d4cb27979b'
        'bac18f1ac3b02fb48434e4b31ba38117b7d788aa5ed3fd517813be25b2cc38fe2c2359067da8ab1832894c3022a568f9e508683d37a93b4c143dd328f4a0e4bc'
        'e5df15c6e83444f09851113b929854cb179e334af776b91f76e8fbfe4d7ce47e96c76b95d622d2e468a361b5cdc6ade7480333bea8f548484e8ed9951c6b5f5f'
        '8a9236f5e85e3363b232f8bf8c2c5b8912c715d09d8e42c7bb3082f1f06f9f837dd2bbafab9909c1dccb574ec4a2bd80a4b5e3149819726057687a2e919596b5'
        'd3abe2b142507fc925587e234a896fa8146a7428f9f5ca85b889a508255840b173833c51a83a89971b50368e5977db86e01a752bd33d8368077ef48246032e26'
        'bb571bf71cb535a9a1dfa575664d12c114b9c8b0f4c317a5747a108aacf47a0d852aee523fee61c0b1e9fda6f06451c9f69c81e21ad762266a14fb0c70302f6b'
        '2033f8ac822b90ab6fa7591c0d78444ff4a961635b2b5e54a0f4f3f8c0e807a31fc8b3f1dd25d84183f7f86da0c874485b970f2373aad408078d82ce29228096'
        '68cd5ecb5a626f124f946bbd5524f32813c20af14c9b4f471290b6a9f1e54f60980e9c0af0b8e5c076da7810d4a235fd89cf0fc3fd749b3fab5060266c0a5349'
        '21e6db49c8252eb6d65beb6acf95dacdb4cfda1b280e65c4d8bb8711f2ea41353c64ae7a71400a41302ee10e49e8732c77d5242fc8fd24f1f78ee0f581697935'
        '9718ade2c7500992a81d916342429d8d9081fee3d23f538edee5e8137f728e89d466acbae0ae0b3595121340a783d336d50f09ce598675e832e725dcc7df92e8'
        'ef9382afebca0ac1de001f5392dd3779cd64439c5a5cb674e74d3eed9d35d5fb676038be2b3f5d59581ad2608a1b56036a8f32a2ff49204a145e2cf80dd18a04'
        '070dab211157b28efd3f77e7ef065f5a48aa9e677f3bf268088e305bbd46e18505d82a8f37d8c9cc48a65c92ae4fcc141ef58c46350d89aefe34b51816b71b6a'
        'f3abc8d2e3232df680ac3960907f503e4460d4f126388e92db28ebb92796aa8bbf0317a57294c571a040a6d6bd442937febb6d6996e724a200c676ae15a53196'
        '9af228017bbd6224c29bcae4db9d2f349f77d8b661236600f3fdab4c965b45738cab6b114aa6dae523c4498e8fc42d8d6a8dc1c9dd698eea50419e4579fba8a9'
        '375f29cda833090fcd7ca06d25207f345b0f9834c3926400992dd5eafd2452c9283e035c72bf72f674ef2b40ed3ed552a762d911de43757cc19b1b3b9e8b8eae'
        '3441b5518d99f62bbcf861fcabb727246af5ffd6ae8a47fe184024c10eaabf5a9894f4de59362a245dd113201485e4073e26dad656c1023bf3bb566f77c13108'
        'b61361c38ba56e8be4f762fbded58ffee2c2c0808e4f0b19c8b51790231d93435ce16eba6c044f2a2b367427242fb1adca77394c29f1e73e3fcd1b58c1a769d7'
        'cc11d2973ea7fbf966337f8222702c32ea3ebf99a0d9a6e77b44fd364c73bbf03e61ad5aafbe07e38f100db526a4b0bcd283ef7c50a69d860a477c433b4c6b1c'
        'a9ef87124abfe773eee00e343c418d66fa010834538d5f367d256f672ef1c807490d5b15f353aacf5ec58411b0dc0855155093de232aa91b78ac9a7b1a4a85ba'
        'c3d4cd5d85f91a192944725ffacf192dd78bc5767d386e811fe2f27f89363dedee9aab08787f00bac889a37736d56bf85458fc572968ef91bfd29fd7b137bc5b'
        '0584c41e0836f909eddb4d50cb6bf30b5e940161676d34db846625768658d1a777847a75ad5174a5b5262778c19390d2d3ae0024ebdbec02962b4bb28af9b12c'
        'c59ae21dd3039865965de773d4303723259da6575dac8f8c68275675e5a57949b990308a7a598c905d95c375b779c3d17fd2faaaae6615f0167a990f5b8c0ba0'
        '2a89d5cfea965f9524ef45090de99002cc1f386c299b854e98561eff84e976ccf59d0a9edd1b43f82b29882bf8606926cf8087a502e7c1e65233037f8d7a3723'
        '2d7540706b14bb2becee959a716ff66ed465b6f699a780a9f183c16c388959d5c5576c34378ddf05219989eee453fc1bdc3fdfe5e9802741b810d6363ac2733f'
        'b71ed10f36ec71d05f7f79feaf7b1b126a58e6edfcfe3b70cdc55c5d4d2f164c0a2b3d09b6a15f4e0350cc0b238e1c9598a5ecfa1111922798aac6e7359f887c'
        '44caee9f07200801132c9372b83aaffdeba0d81e0b09eb340abb668bd45dbebec59461d8cfc3e59207b5a1885d270f409e99997fc25a2c7a6e75231503b92de1'
        '8ca24ae009b64560e086dee887a7f2c203c8a24f36bea2205a5a9c246b35ca1f22c2263572968dce14810afa1b656d668354f43b3b7b1a4d0c62bc076c7042de'
        'aa39dca17e3e3ca50a3008fa1f4f594613585dd9cc4e369eafa23abf50287f8afb78de7634ce0edaca02020c7c6ba297782b9e0ae16465209cd358620eef6036'
        '65d7a4ade92d465f9982d59e9a19faaba1c100e713dce816d0443dd9833ee137331b39e4f351d91a319e3cbd6867d9b4679350ba9fe45abe39ec6a8765d6674a'
        'b5040474995bbad5821e88dee91891c79aec6ba1e200f1134e9f9264d3c503d3ea70839ffe8e733b8f9e079f7d130e196d5ecb0c4d274f829ff50b7bf0fbced8'
        '1cb63cc62863570309e1691f11cb3177dcef3cf4723f2d8b26b388a2c9a47cf8a927ab99d876a96f0e678f99e937709e6eeaff10c8f06d3afecded89682ada95'
        '24e8e17da3a7bb6e6b7f92e4fe6a6c411664e4f611827bb1be363e6d9f1b99caf1f9bf14b2f9b69114e517f3c6d652b83d6bed65e37bb66fab4093cad23d41f5'
        '0359f48fbbc6b7a94506e0855d700f4b454938dd4ff2e0a341f3144a27ac209af464177bc69cb1de23469ef5d09fa0cb72d06d97553ceb37092edaeb414c6028'
        '9718e7c43da0717c5cb8e1ae8519d3ba213a9abd8740bda602da112ad9922c034e802b8cd00a2d6cb7c4548cb54a490188d66e1897659cfa02389fb3d0d247d9'
        '7e10ceb33ac20e2b469ab7922344afe5c82406d11c7e3ba7ac2fa1713dfea99fcb8d150f2ed4299a6c813a441e8d788372941063999f8a71eda038b98c9c3739'
        '04fb2284625d9482402044477fd3d3c063f34db76a9ee59c4594d7fabbfb553df6b3cb55311d53b4cee4054af187265434fd8fb7a01a81ff70a9d4ece3bdbeda'
        'af78c00ab9417c1368f6608f63142d3526cf64636a1d952f36fe60a7ed4ce055516ddc4314774b293ec3b234c7ccd22769cd5164e9b281aaed000da11fd75d24'
        'e3df026eb020acd651d010b0be35fd7fc601a6691640e440acd14228d14b106e0b3ce8b246292a94633502101c89a18cc8b12035744fd95497f89bb5c87cd878'
        '59f0e03e845e5efc97fc35a3c8ba19a026fcfd37ec3568e960bfe26d44e65835e8513fec7b58d7b4c5351a997bf56e112eb7b164a4ca691ad4b3e77fd7ccd56c'
        '832989d9971ac2b7268d9774f9a0b3a1b5388a1b9af9caa5036072a9f68bff97df374ca6b71e2d921cbb61d50646b9ca5b96e4645a40a917bdc301fc6a942c6a'
        '8f446e33d96aa57be6dcffde0703c1ddb8473d7f13a2b3631eeb2886c3ff0bac98651bdd9dd209c2131ec3a25bd78da2056dedae6eb49f7ecfa568274efd33ed'
        'bb5a9a80d0bf01217c9c28314a3a7740786cd124a8373d55e0fbfaa9e49bff439251d3a819f1a319b00ef9224578d601e8fff005b7bdb806a27f310ffbca2f6d')

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
         '0064-BORE-linux6.19.7-bore-6.6.2.patch'
         '0065-CSMANTLE-loongarch-Add-CONFIG_LOONGARCH_NATIVE_CPU.patch'
)
         
# vim:set ts=8 sts=2 sw=2 et:
