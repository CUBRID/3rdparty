# 3rdparty
mirror of the 3rd party external libraries required for CUBRID Engine build
#
The original URL for downloads of each library is as follow:

For Engine build (3rdparty/CMakeLists.txt)
==========================================
1. FLEX: https://github.com/westes/flex/files/981163/flex-2.6.4.tar.gz
2. BISON: https://ftp.gnu.org/gnu/bison/bison-3.4.1.tar.gz
3. LIBEXPAT: https://github.com/libexpat/libexpat/releases/download/R_2_8_2/expat-2.8.2.tar.gz
4. LIBJANSSON: https://github.com/akheron/jansson/releases/download/v2.14.1/jansson-2.14.1.tar.gz
5. RAPIDJSON: https://github.com/Tencent/rapidjson/archive/24b5e7a8b27f42fa16b96fc70aade9106cf7102f.tar.gz  (no upstream release tag since v1.1.0; master snapshot 2025-02-05, includes CVE-2024-38517 fix; mirror file: v1.1.0-250205.tar.gz)
6. LIBOPENSSL: https://github.com/openssl/openssl/releases/download/openssl-3.5.7/openssl-3.5.7.tar.gz
7. LIBUNIXODBC: https://github.com/lurcher/unixODBC/releases/download/2.3.14/unixODBC-2.3.14.tar.gz
8. LIBTBB: https://github.com/oneapi-src/oneTBB/archive/refs/tags/v2021.11.0.tar.gz
9. RE2: https://github.com/google/re2/archive/refs/tags/2023-03-01.tar.gz  (last release before the Abseil dependency was introduced)
10. LZ4: https://github.com/lz4/lz4/releases/download/v1.10.0/lz4-1.10.0.tar.gz

For CI (.github/workflows/check.yml)
====================================
1. indent: https://ftp.gnu.org/gnu/indent/indent-2.2.11.tar.gz
2. code style: https://github.com/google/google-java-format/releases/download/google-java-format-1.7/google-java-format-1.7-all-deps.jar
3. cpp check: https://github.com/danmar/cppcheck/archive/2.13.0.tar.gz

Guidlines to upgrade a package
==============================
1. Download new version package using wget or appropriate commands
2. Move it to the appropriate directory (for example, $ mv v2021.11.0.tar.gz tbb/)

3rdparty/CMakeLists.txt:
   * Bison: bison/		# $ mv bison-3.4.1.tar.gz bison/
   * Flex: flex/		# $ mv flex-2.6.4.tar.gz flex/
   * expat: expat/		# $ mv expat-2.8.2.tar.gz expat/
   * Jansson: jansson/		# $ mv jansson-2.14.1.tar.gz jansson/
   * Openssl: openssl/		# $ mv openssl-3.5.7.tar.gz openssl/
   * Rapidjson: rapidjson/	# $ mv v1.1.0-250205.tar.gz rapidjson/
   * tbb: tbb/			# $ mv v2021.11.0.tar.gz tbb/
   * unixODBC: unixODBC/	# $ mv unixODBC-2.3.14.tar.gz unixODBC/
   * re2: re2/			# $ mv 2023-03-01.tar.gz re2/
   * lz4: lz4/			# $ mv lz4-1.10.0.tar.gz lz4/
.github/workflows/check.yml:
   * google-java-format: google-java-format/	# $ mv google-java-format-1.7-all-deps.jar google-java-format/
   * cppcheck: cppcheck/			# $ mv 2.13.0.tar.gz cppcheck/
   * indent-2.2.11.tar.gz: indent/		# $ mv indent-2.2.11.tar.gz indent/

3. Change URL for 3rdparty/CMakeLists.txt or .github/workflows/check.yml respectively
