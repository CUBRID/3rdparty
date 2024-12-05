# 3rdparty
mirror of the 3rd party external libraries required for CUBRID Engine build
#
The original URL for downloads of each library is as follow:

For Engine build (3rdparty/CMakeLists.txt)
==========================================
1. FLEX: https://github.com/westes/flex/files/981163/flex-2.6.4.tar.gz
2. BISON: https://ftp.gnu.org/gnu/bison/bison-3.4.1.tar.gz
3. LIBEXPAT: https://github.com/libexpat/libexpat/releases/download/R_2_2_5/expat-2.2.5.tar.bz2
4. LIBJANSSON: https://github.com/akheron/jansson/releases/download/v2.10/jansson-2.10.tar.gz
5. RAPIDJSON: https://github.com/Tencent/rapidjson/archive/v1.1.0.tar.gz
6. LIBOPENSSL: https://www.openssl.org/source/old/1.1.1/openssl-1.1.1f.tar.gz
7. LIBUNIXODBC: https://ftp.osuosl.org/pub/blfs/conglomeration/unixODBC/unixODBC-2.3.9.tar.gz
8. LIBTBB: https://github.com/oneapi-src/oneTBB/archive/refs/tags/v2021.11.0.tar.gz

For CI (.github/workflows/check.yml)
====================================
1. indent: https://ftp.gnu.org/gnu/indent/indent-2.2.11.tar.gz
2. code style: https://github.com/google/google-java-format/releases/download/google-java-format-1.7/google-java-format-1.7-all-deps.jar
3. cpp check: https://github.com/danmar/cppcheck/archive/2.4.1.tar.gz

Guidlines to upgrade a package
==============================
1. Download new version package using wget or appropriate commands
2. Move it to the appropriate directory (for example, $ mv v2021.11.0.tar.gz tbb/)

3rdparty/CMakeLists.txt:
   * Bison: bison/		# $ mv bison-3.4.1.tar.gz bison/
   * Flex: flex/		# $ mv flex-2.6.4.tar.gz flex/
   * expat: expat/		# $ mv expat-2.2.5.tar.bz2 expat/
   * Jansson: jansson/		# $ mv jansson-2.10.tar.gz jansson/
   * Openssl: openssl/		# $ mv openssl-1.1.1f.tar.gz openssl/
   * Rapidjson: rapidjson/	# $ mv v1.1.0.tar.gz rapidjson/
   * tbb: tbb/			# $ mv v2021.11.0.tar.gz tbb/
   * unixODBC: unixODBC/	# $ mv unixODBC-2.3.9.tar.gz unixODBC/
.github/workflows/check.yml:
   * google-java-format: google-java-format/	# $ mv google-java-format-1.7-all-deps.jar google-java-format/
   * cppcheck: cppcheck/			# $ mv 2.4.1.tar.gz cppcheck/
   * indent-2.2.11.tar.gz: indent/		# $ mv indent-2.2.11.tar.gz indent/

3. make a new branch for git repo '3rdparty' (for example, v2, v3, ...)
4. Change URL for 3rdparty/CMakeLists.txt or .github/workflows/check.yml respectively
