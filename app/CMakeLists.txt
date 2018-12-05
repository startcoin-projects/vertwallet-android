# Sets the minimum version of CMake required to build your native library.
# This ensures that a certain set of CMake features is available to
# your build.

cmake_minimum_required(VERSION 3.4.1)

# Specifies a library name, specifies whether the library is STATIC or
# SHARED, and provides relative paths to the source code. You can
# define multiple libraries by adding multiple add_library() commands,
# and CMake builds them for you. When you build your app, Gradle
# automatically packages shared libraries with your APK.

# now build app's shared lib
set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -DANDROID_STL=gnustl_static -DANDROID_TOOLCHAIN=clang")

# -Wimplicit-function-declaration
# -Wno-missing-prototypes -Werror=return-type -Wdocumentation -Wunreachable-code-aggressive -Wno-missing-braces
# -Wparentheses -Wswitch -Wno-unused-function -Wunused-label -Wno-unused-parameter -Wunused-variable -Wunused-value -Wempty-body
# -Wconditional-uninitialized -Wno-unknown-pragmas -pedantic -Wshadow -Wfour-char-constants -Wno-conversion -Wconstant-conversion
# -Wint-conversion -Wbool-conversion -Wenum-conversion -Wassign-enum -Wno-shorten-64-to-32 -Wpointer-sign -Wnewline-eof
# -Wdeprecated-declarations -Wno-sign-conversion

add_library( # Specifies the name of the library.
             core-lib

             # Sets the library as a shared library.
             SHARED

             # Provides a relative path to your source file(s).
             src/main/jni/dashwallet-core/BRAddress.c
             src/main/jni/dashwallet-core/BRAddress.h
             src/main/jni/dashwallet-core/BRArray.h
             src/main/jni/dashwallet-core/BRBase58.c
             src/main/jni/dashwallet-core/BRBase58.h
             src/main/jni/dashwallet-core/BRBIP32Sequence.c
             src/main/jni/dashwallet-core/BRBIP32Sequence.h
             src/main/jni/dashwallet-core/BRBIP38Key.c
             src/main/jni/dashwallet-core/BRBIP38Key.h
             src/main/jni/dashwallet-core/BRBIP39Mnemonic.c
             src/main/jni/dashwallet-core/BRBIP39Mnemonic.h
             src/main/jni/dashwallet-core/BRBIP39WordsEn.h
             src/main/jni/dashwallet-core/BRBloomFilter.c
             src/main/jni/dashwallet-core/BRBloomFilter.h
             src/main/jni/dashwallet-core/BRCrypto.c
             src/main/jni/dashwallet-core/BRCrypto.h
             src/main/jni/dashwallet-core/BRInt.h
             src/main/jni/dashwallet-core/BRKey.c
             src/main/jni/dashwallet-core/BRKey.h
             src/main/jni/dashwallet-core/BRMerkleBlock.c
             src/main/jni/dashwallet-core/BRMerkleBlock.h
             src/main/jni/dashwallet-core/BRPaymentProtocol.c
             src/main/jni/dashwallet-core/BRPaymentProtocol.h
             src/main/jni/dashwallet-core/BRPeer.c
             src/main/jni/dashwallet-core/BRPeer.h
             src/main/jni/dashwallet-core/BRPeerManager.c
             src/main/jni/dashwallet-core/BRPeerManager.h
             src/main/jni/dashwallet-core/BRSet.c
             src/main/jni/dashwallet-core/BRSet.h
             src/main/jni/dashwallet-core/BRTransaction.c
             src/main/jni/dashwallet-core/BRTransaction.h
             src/main/jni/dashwallet-core/BRWallet.c
             src/main/jni/dashwallet-core/BRWallet.h

             src/main/jni/dashwallet-core/x11/aes_helper.c
             src/main/jni/dashwallet-core/x11/blake.c
             src/main/jni/dashwallet-core/x11/bmw.c
             src/main/jni/dashwallet-core/x11/common.h
             src/main/jni/dashwallet-core/x11/cubehash.c
             src/main/jni/dashwallet-core/x11/echo.c
             src/main/jni/dashwallet-core/x11/groestl.c
             src/main/jni/dashwallet-core/x11/hash.c
             src/main/jni/dashwallet-core/x11/hash.h
             src/main/jni/dashwallet-core/x11/jh.c
             src/main/jni/dashwallet-core/x11/keccak.c
             src/main/jni/dashwallet-core/x11/luffa.c
             src/main/jni/dashwallet-core/x11/shavite.c
             src/main/jni/dashwallet-core/x11/simd.c
             src/main/jni/dashwallet-core/x11/skein.c
             src/main/jni/dashwallet-core/x11/sph_blake.h
             src/main/jni/dashwallet-core/x11/sph_bmw.h
             src/main/jni/dashwallet-core/x11/sph_cubehash.h
             src/main/jni/dashwallet-core/x11/sph_echo.h
             src/main/jni/dashwallet-core/x11/sph_groestl.h
             src/main/jni/dashwallet-core/x11/sph_jh.h
             src/main/jni/dashwallet-core/x11/sph_keccak.h
             src/main/jni/dashwallet-core/x11/sph_luffa.h
             src/main/jni/dashwallet-core/x11/sph_shavite.h
             src/main/jni/dashwallet-core/x11/sph_simd.h
             src/main/jni/dashwallet-core/x11/sph_skein.h
             src/main/jni/dashwallet-core/x11/sph_types.h


             src/main/jni/transition/core.c
             src/main/jni/transition/core.h
             src/main/jni/transition/JNIBase58.c
             src/main/jni/transition/JNIBase58.h
             src/main/jni/transition/JNIBIP32Sequence.c
             src/main/jni/transition/JNIBIP32Sequence.h
             src/main/jni/transition/JNIKey.c
             src/main/jni/transition/JNIKey.h
             src/main/jni/transition/PeerManager.c
             src/main/jni/transition/PeerManager.h
             src/main/jni/transition/wallet.c
             src/main/jni/transition/wallet.h)


include_directories(src/main/jni/dashwallet-core/)
include_directories(src/main/jni/dashwallet-core/x11)
include_directories(src/main/secp/secp256k1/include/)
include_directories(src/main/secp/secp256k1/src/)
include_directories(src/main/secp/secp256k1/)
include_directories(src/main/secp/)

# add lib dependencies
target_link_libraries(
    core-lib
    android
    log)
