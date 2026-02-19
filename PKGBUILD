# Maintainer: csmantle <aur at csmantle dot top>
# Contributor: Jan Alexander Steffens (heftig) <heftig@archlinux.org>
# shellcheck shell=bash disable=SC2034,SC2154,SC2164

pkgbase=linux-csmantle
pkgver=6.19.2.arch0
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
  # FIXME: -arch0 packages don't have upstream patches.
  #$url/releases/download/$_srctag/linux-$_srctag.patch.zst{,.sig}
  config  # the main kernel config file
)
validpgpkeys=(
  ABAF11C65A2970B130ABE3C479BE3E4300411886  # Linus Torvalds
  647F28654894E3BD457199BE38DBBDC86092693E  # Greg Kroah-Hartman
  83BC8889351B5DEBBB68416EB8AC08600F108CDF  # Jan Alexander Steffens (heftig)
)
# https://www.kernel.org/pub/linux/kernel/v6.x/sha256sums.asc
sha256sums=('88611981582cceb7cdd4d688d9d881073cf4977176252193a23ca6d4b982ee5a'
            'SKIP'
            '9fed188f89847418aaf6416b64457a30bee34dcd0fa42a84dbd0f4dfca063402'
            '157126a09f9a0db855ccada3d560c5a2e469c91186596b7f6b15afd2b983b67f'
            '8750c285dc48f1511e565062069b2a027cc3fdae6bf478fa4e5efdde9b8cf9e4'
            '1ad5fc6784e2235fd7805909f96ec2c52e6b57add884662ea2741bb1cfc575f7'
            '5e5120cdcd94dedfac92b22a8a4ba99502630d903ecf3e38bd89d0b8c0f5fc6f'
            'b909bacf31112e344f6e12ab20b781390a01a0a9b3873ed1ba369b8343d2c960'
            '9459c4838d99e220eaebb209e6c5f4ce0b090bc27e3a6549c9c4792d8bd3d43e'
            '037c9067c1607c75d73bc1724d3d097b14d1f354e74a67dbcebd884236521330'
            '722ca0a15cbce497af8c245ae34c88c671e686430744d8b786ebeaff7656e249'
            'eb1f8485c720ef292edddb690521e1d5b1b45e354577f12b8728bc7162856b0d'
            '097d1ed1535489ae5d5011e020ac7f9f4ae3914af58db96c7ef7d8fced1c36ed'
            '6b3ab070797c00340a7178d3d2f03c48960f9c727b512744a3a1068943071885'
            '6e35db931cdaa288e1771ac343966db070a8441db3bc5b630fbbffc85de66c22'
            '106a1922ebeeffc58f66b1e78cd8a86f9476933f2835383145eb6841e48a0c47'
            'b6e54820636f5ed8e42e6a33b96a31be0a7cc6e7a3e33bcaef3de5f85c883fe3'
            '2cf484e7e3096ea58d5122bf629bd687dfcb5a456f7ba033ab205a93c145de0a'
            'faedef0c0c71836f49a109cf279e8400b3be27c7faf868b0db445f9aad5c79e2'
            'b6592e09084cd9a2139c09a6e84c4ccc2e06fe861f37281057d6e32ea7802fb3'
            'c3be19a272615036a20df64b3e4f1faa90c41a8ca6d4d318d6d94ed8370a8557'
            'c80d800dfe42c3932d4f74e0ae97d6756cfc02b153eb691ac26c09d15c66bfbe'
            '2eac58e215cf519e1c4c5649150372c43969276105cf4819c7a7ac64d0eb3191'
            '02d06331c41875e6c617cf9507059b9d9cbd94ce6a61ccb94a0b8e96f11922c9'
            'b457e1cfad84ddbfb1d366afa68eae306e1bb5aba87256baa9235c9acd4d690c'
            'd1422c3e91078b9935865fdd1bddaafc6341d88dcc10ef37c62849960205b214'
            '49c3a5cf306ee657de8aff72f194e0275302360ef0eb9ed8661fb04a91768a65'
            '8dcce6c49f1393184e6a6804392731b5f512032ea57129f06548419923b907cf'
            'beb008f6f41aa67244602264c5435b1e1b87329b0a8dbd144642e8b3b329c500'
            '438762196e387f5f8c40b7e511e6e6d28b8f611d501679e828e9399578040e02'
            '0cc313ff2f8e1ae39de645cf060b8ef733372753c3149604a55b67c06fa50dde'
            '1563ded93965816eaa85a340508d672ab5fa69af8f4eddccf985889b79386eba'
            'dcdbdd47231d146227204cafe7ec93fed74d43e729aa716b24d3d943b0f964de'
            '677aa1d19f7d46051d6cc64256f3d34e6c6bed19a1a53f0d9f0e93fbd52f532d'
            '86d014188297f2892aef90e8a28b45ae5f7422021acf20fd1a1b427d9fca1316'
            '7e0fb5577edfd0649121202ded4e04850ccfcb2af9d64f8a553c41b69ea27485'
            '44c8ab53dc857ff493f4f972c8fd2d2c7d331cef06f9bd393bd2532489dbba98'
            '9e9051963fcb256e7a2e2e9cf52f50ca25d270dc552c1860e1e0775c00b4d2fa'
            '874ce921dd9cbaf28753c54574a8d6bc697c99e717135bdd55a7238e376839a6'
            '8d304ac25c2792e9f0cea4107df953979714e4498fbb8945cb9a3db7ccd4824a'
            '5d0364f2f88d5f09f28764dfef30a897fc0d0e59bd2ce122a1b5a3b5d72daeae'
            'ae12ec58aed127aa80ba3f96446a761b35d81831700a096ea8c2c59d96a30f4a'
            '9c12d0c70786274bf603027d6a259305d7975be85e50d32fa3cc0d09cd6549cd'
            '1a5f42d6e3ddcbcf2f8815f841122312124eb8d56fc5c2217f85e0121f59329d'
            'ae92fa3acbc6f5c309cc5a93e789bb55b84e9642a692408528d270ba79aaa1ac'
            '13e4e7e4ea689a4f0b121cefb261f12e0b9a46c9e9521e726718aef4fdc668be'
            'ab5c16612a8ebebca9a9c7996e61d55ca6d832fd84e65aff30f86156973116d4'
            '0f1d4058cbe8825613dcaa4f218d483991861c93355176314363a93ca53270ee'
            'f5729a6748123a73ce9be1280937610b6d7312a61185fb5bbd5c59aaa276d46a'
            'f306eac627b57800c854e4133a147ef722fef88b9d71ce90b20c301c80e4ab5c'
            '61aaa28e6fb38d8300fae210e0d29ba9b1647059603f0f295e16a5710003eafa'
            '3715f4b59a03b053f85e8b37be005397bdf44453406a9487f18695736053b9b1'
            '7776ad24beb68283117c9d17c94f1dcdda92c32dbf21b51dae9ade29db5d10fa'
            '6db08d2491f639474478093b423910f9930f9c289f382e1332eef9a529f9dae3'
            'ac9cf54ae7d89115240ff4c9109e4ea2cee18989e1550260b8df763077cb2f7c'
            '5cbe02a0f89cdd35f2e66a21179a5a60fdf509a4949153babe82c01e86f99648'
            '953d82043f5732037607b8eaa16a7ff4d6ffb5c5abf0124c0e1b4ceab29f5e6c'
            'f367f1f360f67e61bc282d412ab12c924f04cef058fa824909681deec61063c3'
            '057a11d67a62bc838ebeb9cdbb544bf6f3a635c264178a8ce620cf3a206f6e26'
            '396d0e93ee40a88f567c4f34bd70f52f5d53ead79e1646b3fbd367dadb07ebc1'
            '76e42c84a4aeb8c15fe438fe4ebd81a93b82e944ade96c95c384b5cab22babe0'
            '5e6f69e6c754a1ab128556b2d4f7f54f5c2c339a81cf50b68cf530149b89c1af'
            '8aa0c198ca866639bbc6e5b5acbf98f431ff5e3eb4ac53c6cb9f88f6d9374415'
            '0d35b7d2a8a44ca7cd40e1c8da9d6ac0f4f5b797a5321919bee4139ded1b4c71'
            'ffd1073e629a5cc096a29afc1c2173ac021ea88fb311321e31cab96db5cc35d9'
            'de5c095ae4b940fa7c51d1345d11008599fa3ed6b0e9392557564c03255a69ae'
            '164b02319ec514628a5f434285c984c7351b00d3259c6c68e2bec22e3e03002a'
            '135189c4750f73f19030b7bd538bbff273bf6f8526e83528410f02ba699dd542'
            '10715da357c534bd34443c915817ba8092314d7b27aa98e65df7f1ba38c3e8cb'
            'a5277a41789909269d4f5ac7f460e77b844208d4d503ff882e80971928155a8a'
            '241cb81d99f3bf540f9066c36889200ea7a16212638fc57d24b76a6fb00d6b23'
            '414dd672bee561def9bb3ebb00922d16b8355c95d26148950f1dafa43f6ee523'
            '9a3ae471bccd5112c5dc9e183759ae172c973d06b37e340b83b745df800d63dc'
            '147a35134b57916d5142d4a44b1412f99708b261f60be135a1c7ff26f1c55909'
            '1587089bde16adaca835593621c68192fa753dec73cb1f74390862967a540c70'
            '28146ffd26eaa31bf54c854e3d64b68b2a5ecf7b5536a5e738b91843f90d148e')
b2sums=('cbd50ebd08bd10ac95397b61757a330bf670ab32949350e8ed69d82f1b663b37315e31e289b8eb2fea23be9f19c79c2e3b90beadd9349a1c1f8cb0644a699367'
        'SKIP'
        'bef3377ad86440af76e9dde4c29c9f4aaad42f5fe343f7d31f5eb537d6d358602f996f5d63986af275f2e92f94e71dc28c320edc8c03d05bd64dbd8ed23d75dc'
        'dfd366b283243f95c318471fe35e3a36646a38388dd6c4d9746bc981985a02ea303d75127244e9feac14564a8f49385483dfb56a8842814bdf97ca747bc2a4d5'
        '8f9568afff28bdfed46375a11adac228e23d36bf6eabac99a4b6596aa093d1eda8f8c06d712d0643912290187d695b6ec2d52aaaa5c3b0736ccae7006fb533dd'
        'ee6e43148cafcdad018f5f7d81c03d73a9ceddf1afd0b396dd1371850bca1b7a2d4add4b27a278aaeb76e822b54c0e3c0f8f8e1ad759347701d181662230c2d0'
        'fba6f04715c267a011ac5302f861e931660938d70257833a26e8c7b4f704a608843cc7894b1f14ebc52181f0fa70e28a986bcd89ed123700658813a22cdabcab'
        '65db4f578ee2cee0a0decab0b95f2bc1a6f6a38406d6c3a1015f9158aa14ce2f26bec036f84a6b1be94faae66b0534640017f47d4f72d8fa411357c745e22885'
        '90d338ee0fd73ccee568b486d9b080d8e2a81d9c7246fd1a63bf35f6e97bbbd127dc90e32f1cc7f593e2dfa81aab8e0bc75956b0c60080ca58051c2f07130524'
        '4f7bf5686ae6c507b439bf511cfa062d6027b715e5ef4f024b7a346457a7a3ebb91ba3598953bdfde3f089e641839531fa950ec397608919c8086b6e875112fa'
        '0eb8ab3622998b57ca063715b7bf4da8f6422a71b32c2e055f4f99c3e44b53530ed8bfb4e59adf54396fa1533f7372504f3b41b0f081f9b82577150e3cc513d6'
        'a9b13286a864fe85a49c0fd27c540421dcb1d1e6d4d2a36601d51a78db82d3ca2ab9e8f7ee79a92dcf197511e2b3872b870d912379463e6656b29be939f10688'
        '63c8187f5d7117833e34acf976f7d2134dc61c1dd49a03c6ed0aafb663f7c4956e31511e8f3f942c95b43f048655317de2e913e81293acd4bb150105b3e2c777'
        'bdd7d59a881f3a3c447ad700602d38369d4b82febb506ed14051dff7566ce66e47cc2a5dca98e6bed94455605adba59e4269121dac6f6d557c9a422423624a88'
        'e0b5146bb77b0e4e11a3564a29ee55e5c163ce7132e7b4a0035f45892c63f46af9e06fed968d1a190c1e919e021db983321d190de1c751b69a3c091cd1456377'
        '65a84f106f556432ebe663cc889bb8dc5a0c722ec5f638663bb922334d5f1f8c2ccd3d4fff4cc1fbd8af7b2813f3fc081a4e94f2a9bef3d50079a83e266937b7'
        '1286ab8b5ff41ca81983fcc24a2d8b08e0887e58f03086f596cfe70a57b40d4261f5a5b269000a8ae6e7a91c2304843d935eb5a1c223d4b819b91e6470b6ff89'
        'a42fafc612fad859732cac289554530c2be0295b4c46f95fdc1a1a60d51384aeb58f5e088486b088a6f5e38f7f263d8e08cf93fc1d502db0612ec77e955a250a'
        '41541e91dc614817115e499cf7ffc8679129e1b07a7d68885f1211a06fe9f705df998e60bc0a908a73c1440633f49d41d1b96ebc7aae5ad24f91bd6264bbc85b'
        'd9a5ba01764389eab622501cee2f69939efaefdb23148f79fc173be7a4b4a25ad106f742c4620164d68fa365b898174c00ff8e487dbc7f5f10a3de0a3dbfd9d5'
        '9efdbdd1ce879cf490de5ffc8d0071bc4c843da8f328de277446e357aa8faa09a4342b73be93e0909ac832ac16874f17cf71d345aea03ad3a2688ed8cd6cf1d7'
        'd57c8ca4504ce359772a199a11abd959ec32b4e30fc2fb4ea5b7d97524f4cbe8a19586c9faf6f9d8d597961ef0c1c5426ad1d3cc97a7b16ddbba9b5dad777b2f'
        'f013f4ed5f1b39a3d2a029660c056f3db6a6f2642297d303f98f0a7dd99633db665d2bc7f83c936a9b095fbcba2ae7994044aee7bc03519258982b5c4ec56706'
        'dc576c86ec7949e4cdce21e8df11daa4976ab4882fec17b497b6d2c6fcc0df70294d2be85de6f2956ee0c464952d74c535028fa07d8fec8d67cbefc7661f427b'
        '7e2628dbebd4f2046c425fdc873cbc622f116b0987b7b5aefe387882c26d5941e821bf1e78fe5f5872c33c7dfcbc0a4b59b18a4413784db943c2bcb8f98e0c4e'
        '4d4dfbc9485b165c301dd5c3eb4dc731164500c2d9d4f21081d0e1424bde83ec409c7087c8caffa25356c9a0d33f12faa142936dfaef4fb259d3de014c1aca23'
        'e1984f71c2a331ae2ab48f6c5201f18fb7aca9228ef75d58849301f5ffa30099137f349691d4a36750c83c0c9f4b5a55b9617d391eec1300e554d83604048d14'
        '04168222dd71b43643f84d7040e7a7bdf31e5bfb187d1b17355bf440f7daa3c794079c3e3e894be8e92fb3fe8078edebb35c2945109963bd7e03c1f3020975b0'
        'f7d6600afe139cc9a15f6c1ec6c2e599b5cd32baff1960c0966386eb7264292fbe50a94c01590c8738dd81e49c4f8e8e9558ee4ba8b840867c5c124a404a689d'
        '0cf33e24285597ca9a52d1b4b254555e7e3fdc95422266f2fc66117716f796b3a8a4bebfd1d03335b112fa0f162c6d26a4945a61316431102f2fcdb0209f52e0'
        '8fe715e896c15efe17458bc84f6b32f4322be594cd2abe065f4d63d23d82140e27d97e37f03afdf79a633534bb661bbbc623a45fedd0d5c9465a0d17420dd06e'
        '5fc562621f19fdf6235a6fcc2d23d5320d0dffd0879e9aa342936cdb147816c407802a09c4f6e1630e1ebff9e121b1ce35823255991561051247381d5f922c82'
        '4c23fae8ef4abcbe94eab6701ea802dd12160b886d6b4fa2460567b8de020de07ed22d41413c334ce9562219d97a9b702f3e750590557536658a0d040b6d98f5'
        'f90ea89fc6ff8ddda4379f92001316cbbfa9e867e06076fe11896ced15dafa3488bdfaa78f88a6c8d0490ec4119fc32bd908e7c38a0110c50ddae6357eb703f3'
        'f1ab2827899194273c9b52c7c24c5807aa2839881d334ec53ab8039cb0e5aa446ff9ce8987e44be40e9b51175bf8f49f95796756a589021cd9463e6bc6989213'
        '0ff4ff14b10ede257d2c3ae8e8a9ef3b064ea1ec4bb25406995d94dd2fca8e0554c2e75e430790a841a0b718dc23427bceb136b9419025758bcb62a83c790fe4'
        'cb7dfd6e3ac90c144804fc81a8a8a8ff00cdd4ab3c80e06a987cd321e0646f06226a52095444d61988b3c55eed8a97f841f976ffb5d3ad83862067fd7095bb65'
        'eeeeec00cd15760d8abff2a7222eb7483471772e308ba8cc33bfffc0df854a8d178b41249d8806ee96f53eb3d19013a1fc0d258df1501a14277c813bf24cf5d1'
        'ea82aa742380e325c42ea3cdcdb7e526f6c0ebb0d8b832b83872540cce0f1c6025dc258db6084c7a1d389b18266465b38cfb60c9f8064e8df610550f35cc9f0f'
        'c4763c8b6e451da6e49b2b6e170799d3c81b3d410bd133800844bebd3b29a3306b10b7402d23c9f8fce8335f3306702b74c8b5cff9b1960189d5ce85933e35d5'
        'c15a4ef913f233ccf62219c663a4c9bda30d6f6e405fac82e693d3a77eec0eb318a72f6c64df9ec642a22705e9451bd62c89b59a4104003e0fd292f3d14ef3ce'
        '45ee32b14f668ec0686800870fe326930933b24680687f9c591310d8135e5dc7ce5b27b0bd3a46013b4a15615148b7a7b8bc76d5546c312396d5610b91213b8b'
        '66cfb0a479b9d9e660336cec1458ff47dbc59198c1c706c93a06d0d192ca51dcf34689119d89562ef29bc3be72a6d2d9774b6901130f89b6cc9105c58b9c7480'
        '88a051e64877e382c39e5f4766cf99cc0944dd1d45607caffa9f43bfbf9264f86fbbebf82c4e22656e8674fd6c799e5a4014149d226b3278284a50c3bcdb865b'
        'ffeac74a80c70b4ac5e22ed8ed17478437548062bed57e856169f4b06346db98319840b5307ef0c161c518bf6b3a6d7f5fba54f54099e72f70e6992967605299'
        'a6d4c5931f776a5184f8bdfc265775ee73a0af61823ba382a464dfba995e8083ac8caf6da5a7b883a07024268daedf57252e65190765fa5b17081d91dc239dc1'
        '5f4e9678535c77ce1fa8bead1781597b3597aacb4cdbce29362efdff60dbce42248df5906b94f1368a059bac86869f626f95aa370da54fe5e412ed1c59c50244'
        '70a87b921a513e24998816b2641bdb08847fb15d568bf79a4210b61f2bc21796102f14af0fd9f333b6f2d07283d5e487ac440c6504c7c4cd4b3316b6cc57fdea'
        '8498c09d8579e0cda425bda4a8adaa0972fe62d6f79ccdd07bcb4430b77a01dceb5e33c0ebc306ba3f00198ebca1ab2a5f3ba861d99bb1c229a59d1da4c64e17'
        'c27eddbb4cea40b37d934bfe7d3c5ee5e234bec51df8fc2c600b6885d2fb0c50937e4e46951dff0e7163fc3c21059371ec85aa75804eda606fec9d452a13d71f'
        '6d74e04bafcc1265e4b8d033955e7c4fdcdb9b513021f7ebb984bcac2d5438c38030e5b6a7e9c5981208104f28348f265b1ecb83c383258d201045fc362093e3'
        'a52e8f7b20238d603a300959be6548961865492decec9c22fb73362558c5feb3b329244cdcd2a0f6fd9a6e7bfe531331fe082cc9b3029d4cc076d912255591cd'
        '661ba69bf87763177ce478dc0f0530fdfa970bd391fc837ca4eea6cb1fc8bfbbb2d8cc3ce1296b4a053dc4007dfc1b36c61f3f2543ac7ea686a9e50723d5ff2f'
        '8304da2f7e4ed44c9f0777dd2f4f17d1b8bfffd98cdf2e940759e71386ec6f1be68f2cdbb486a4e329473f3579dbcc4636ef4476f9664f11bca6589bf3ddeccd'
        '83a34ab33d9dad6b77136c89d98d2321aa4090c2e14cacf4a0f1f9eafd7a3a0fdec7f489b0a23e9585632c144fb84d2679946586e8836690e8e970d08cdd5827'
        '61f985aa11980cb33f2cada9a431912c15ee5f87155768f0f9673af37c4011b6dfe9da5dad445f1b49cf6e5139fd0f5d504c388c27a50e8d5b0f68732c3e7e5b'
        'c925023a9f01b696b9f67b44d3a511f38e4e2ee51011f04a218676dea53295a948b19ca4a8b2ef904bc7996a7de6fa76f463cbedb102eb1a280d710bf36da353'
        '6461e1c0786fcbd0680de68c2b34b47e0ae21816eb653040e13080b35e6c102fd3274e603dc5e44ee798bcb6e7751f6194008ac16067f6d93ea4dad5ea1b5299'
        'bec80a207d3982c7a044f98b67508924d47a4e53fccd0c914f5b139391420ac4be3f4b46723f2fa42881cc42be71a819eb31bc55d0476b7d988f59534ffa7e66'
        'e88b3cfbbad120a15651d088a8427a2898676b4bb8f4ee7b6c564e164a3a6e0313476a86d471c0afcac8319ed81f9290c18bb715eb547af7084b25cd9ecc48d2'
        'd3ea6bbbbe8a6607c72aea15419a7de1e2af7ac3cb4350913dcc2f70347de9458cc07cd3536afe1acd2ad06cfceffb261866208786afa8275f7deef530c454c9'
        '4bf1ce286dc85aa9a43ed1cf7924b57256310ae9189770dfde7ea6734ed04dc0d53fbc4968fbd405d2ef7758254428bc10a975667507c20810ce5e08c90a9eb2'
        'fbb61b34d26a66c33fec191b14c619c483ce39eef23cda3389132f1431df98e28ece75336270d0f1bae50c106f327e931289ea327f851cd878913f9039214715'
        'f40a13da7aecd7324df2833faeeb053bddb15ae4d57413c3328605eb8918e1f01958eefa3f4529e47f9d48b8206aa1b378e209aec02585832cb3e1e5f0894c85'
        'b8c112121aff688d5de4d683d5c7e167ae7478e916867ad0abf4080f102237b8f8ec01c93a5a8295a87c5b9f334768d57bcf44c0929ff7fefbae2bb5f37cb296'
        '6e9c2093b8a6041ea8eeac346f68ff9d0999e655046c4d8c45e9fc33a304da8be54865b5e6b979dcc995a3b298f6e47e96c3f898b6fa80835d7949418a016f25'
        'c21386287c06a249f041e6d188b314d5013987a5e281036619b0f8aee44b076ed8cc0349000f7c77b22889b82c8e1f4ad3a1bfe73b2f0a5898260e4f68bd5fe5'
        '63b8faf7bf9b65a2e2a35f7d59f32b4dbcff390cbf5cabe6379de310ad5522a71347688ecf470160644b99acf2d8f0e279807025e22e9281bc16c58246ad5f6d'
        '977f6601f6a35c87632f4fee6312a528eab489a28d774b19a747d772a25e15183d54d0a3a428af83a26f0750a4da10f80d24d377fd4ff474dbfcac1977626cfc'
        'eada90bd946a8f897f35eaa8e8c2bd7f99b065e038692afed4317e3ac9d3628f31a626554649d1e4ef0e5aae1eda81abaa6316d03c46928ea1eb16b33c3ed6dd'
        'f2ca95d53fb55656b58b8366871a4171097eb152b53124b5bf3483a3fbb01580912c222784d774a820730cecc3dba9939204ed3e9024bcd31e424ca2f9870b22'
        '598b41884b5b1f7aa8c6efc07e1a8a008c39bd1f915cc9ab118c1730d958f8bc79afa1c77aa04e7d6aad9b6de68a26a065cbbc32acf11aeba48c5fd6e5ada77c'
        'c791036d7da8761283b97eaa656c8f067ef8ec2152c139dbd5f89d1d4c56faf9c25ede1d4ecde2f5d3f87916922985f5239a1d0dfd99b81c50d057a7137f8c41'
        '6128ccc6437ee4e14ba67a08de7be01d87c2333bf0f3f99c43877ab79808d58ae034410e25e8fa620b26a60b481cf464ec4d5fe08a06a698d1c86a8f50baaf44'
        '8212f1d3d7a4266fd7e56799ef5aa4bf3b6f6ea4506dc52620b2355246f701e938b67e3527e2b79ad94d0635e06e016de7ea5562db90b91edb02eeb38ce24a82'
        '76e0b511088cd48df641a687472aedcb4e1b6fe97b206a093f5470bb09f0832791891e5c95ce010b06a2a3069f3e3cfa0f4a4f91b6aa1eb340612bab955ca415')

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
  make listnewconfig
  # make menuconfig
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
         '0001-add-sysctl-to-allow-disabling-unprivileged-CLONE_NEW.patch'
         '0002-Arch-Linux-kernel-v6.19.2-arch0.patch'
         '0003-BACKPORT-FROMLIST-drm-Makefile-Move-tiny-drivers-bef.patch'
         '0004-FROMLIST-drm-radeon-Call-mmiowb-at-the-end-of-radeon.patch'
         '0005-FROMLIST-LoongArch-Update-the-flush-cache-policy.patch'
         '0006-FROMLIST-USB-core-Enable-root_hub-s-remote-wakeup-fo.patch'
         '0007-FROMLIST-scsi-Bypass-certain-SCSI-commands-on-disks-.patch'
         '0008-FROMLIST-PCI-Use-local_pci_probe-when-best-selected-.patch'
         '0009-FROMLIST-PCI-Prevent-LS7A-Bus-Master-clearing-on-kex.patch'
         '0010-FROMLIST-RFC-drm-amdkfd-disable-HSA_AMD_SVM-on-Loong.patch'
         '0011-BACKPORT-FROMLIST-drm-ttm-save-the-device-s-DMA-cohe.patch'
         '0012-BACKPORT-FROMLIST-drm-ttm-downgrade-cached-to-write_.patch'
         '0013-FROMLIST-PCI-Release-BAR0-of-an-integrated-bridge-to.patch'
         '0014-FROMLIST-mailmap-map-all-Icenowy-Zheng-s-mail-addres.patch'
         '0015-FROMLIST-net-phy-motorcomm-Support-YT8531S-PHY-in-YT.patch'
         '0016-FROMLIST-net-stmmac-Add-glue-driver-for-Motorcomm-YT.patch'
         '0017-FROMLIST-MAINTAINERS-Assign-myself-as-maintainer-of-.patch'
         '0018-FROMLIST-rust-export-BINDGEN_TARGET-from-a-separate-.patch'
         '0019-FROMLIST-rust-generate-a-fatal-error-if-BINDGEN_TARG.patch'
         '0020-FROMLIST-rust-add-a-Kconfig-function-to-test-for-sup.patch'
         '0021-FROMLIST-PCI-loongson-Override-PCIe-bridge-supported.patch'
         '0022-BACKPORT-FROMLIST-loongarch-wire-up-memfd_secret-sys.patch'
         '0023-FROMLIST-loongarch-retrieve-CPU-package-ID-from-PPTT.patch'
         '0024-BACKPORT-FROMLIST-ACPI-PCI-check-if-the-root-io-spac.patch'
         '0025-FROMLIST-PCI-MSI-Conservatively-generalize-no_64bit_.patch'
         '0026-FROMLIST-PCI-MSI-Check-msi_addr_mask-in-msi_verify_e.patch'
         '0027-FROMLIST-drm-radeon-Raise-msi_addr_mask-to-dma_bits.patch'
         '0028-FROMLIST-genirq-reserve-NR_IRQS_LEGACY-IRQs-in-dynir.patch'
         '0029-FROMLIST-dt-bindings-interrupt-controller-add-LS7A-P.patch'
         '0030-BACKPORT-FROMLIST-irqchip-loongson-pch-lpc-extract-n.patch'
         '0031-FROMLIST-irqchip-loongson-pch-lpc-guard-ACPI-init-co.patch'
         '0032-FROMLIST-irqchip-loongson-pch-lpc-add-OF-init-code.patch'
         '0033-FROMLIST-irqchip-loongson-pch-lpc-enable-building-on.patch'
         '0034-FROMLIST-kbuild-install-extmod-build-do-not-exclude-.patch'
         '0035-FROMLIST-LoongArch-Select-HAVE_CMPXCHG_LOCAL-in-Kcon.patch'
         '0036-FROMLIST-net-stmmac-dwmac-loongson-Set-clk_csr_i-to-.patch'
         '0037-FROMLIST-LoongArch-Prefer-top-down-allocation-after-.patch'
         '0038-FROMLIST-LoongArch-Disable-instrumentation-for-setup.patch'
         '0039-FROMLIST-LoongArch-Rework-KASAN-initialization-for-P.patch'
         '0040-FROMLIST-LoongArch-Add-HOTPLUG_SMT-implementation.patch'
         '0041-LOONGSON-irqchip-loongson-eiointc-Improve-IRQ-affini.patch'
         '0042-LOONGSON-LoongArch-Add-CPU-HWMon-platform-driver.patch'
         '0043-LOONGSON-drivers-firmware-Move-sysfb_init-from-devic.patch'
         '0044-LOONGSON-drm-radeon-Workaround-radeon-driver-bug-for.patch'
         '0045-LOONGSON-drm-ast-Restore-vaddr-field-to-struct-ast_p.patch'
         '0046-LOONGSON-dt-bindings-dmaengine-Add-Loongson-Multi-Ch.patch'
         '0047-LOONGSON-dmaengine-loongson2-mcdma-New-driver-for-th.patch'
         '0048-LOONGSON-LoongArch-Add-canfd-support-for-ls2k3000.patch'
         '0049-DEEPIN-net-stmmac-fix-potential-double-free-of-dma-d.patch'
         '0050-BACKPORT-DEEPIN-pci-quirks-LS7A2000-Fix-pm-transitio.patch'
         '0051-AOSCOS-drm-amdgpu-radeon-disable-cache-flush-workaro.patch'
         '0052-AOSCOS-loongarch-re-introduce-add_numamem_region-ini.patch'
         '0053-AOSCOS-loongarch-basic-boot-support-for-legacy-firmw.patch'
         '0054-AOSCOS-loongarch-parse-BPI-data-and-add-memory-mappi.patch'
         '0055-AOSCOS-loongarch-add-MADT-ACPI-table-conversion.patch'
         '0056-AOSCOS-loongarch-correct-missing-offset-of-PCI-root-.patch'
         '0057-AOSCOS-loongarch-fix-missing-dependency-info-in-DSDT.patch'
         '0058-AOSCOS-loongarch-fix-DMA-address-offset.patch'
         '0059-AOSCOS-loongarch-fix-HT_RX_INT_TRANS-register.patch'
         '0060-AOSCOS-arch-loongarch-add-la_ow_syscall-as-in-tree-m.patch'
         '0061-AOSCOS-la_ow_syscall-add-kconfig-for-module.patch'
         '0062-AOSCOS-drm-loongson-add-ls7a1000_support-module-para.patch'
         '0063-AOSCOS-drm-amdgpu-disable-ABM-Adaptive-Backlight-Man.patch'
         '0064-AOSCOS-MIPS-Check-address-space-in-ADE.patch'
         '0065-AOSCOS-kvm-disable-enable_virt_at_load-by-default.patch'
         '0066-AOSCOS-drm-loongson-add-ls7a2000_support-module-para.patch'
         '0067-AOSCOS-drm-radeon-limit-mmiowb-hack-for-radeon_ring_.patch'
         '0068-AOSCOS-USB-core-only-enable-root_hub-wakeup-on-MACH_.patch'
         '0069-AOSCOS-ACPI-scan-Add-pwm_lookup_entry-for-PWM3-on-LS.patch'
         '0070-AOSCOS-Revert-FROMLIST-rust-generate-a-fatal-error-i.patch'
         '0071-CSMANTLE-loongarch-Add-CONFIG_LOONGARCH_NATIVE_CPU.patch'
)
         
# vim:set ts=8 sts=2 sw=2 et:
