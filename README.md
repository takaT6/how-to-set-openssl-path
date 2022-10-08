# howto-set-openssl-path
M1 mac で cmakeを実行したらopensslでこけたのでその対処法

## 該当エラー
```
CMake Error at /opt/homebrew/Cellar/cmake/3.24.1/share/cmake/Modules/FindPackageHandleStandardArgs.cmake:230 (message):
  Could NOT find OpenSSL, try to set the path to OpenSSL root folder in the
  system variable OPENSSL_ROOT_DIR (missing: OPENSSL_CRYPTO_LIBRARY
  OPENSSL_INCLUDE_DIR)
Call Stack (most recent call first):
  /opt/homebrew/Cellar/cmake/3.24.1/share/cmake/Modules/FindPackageHandleStandardArgs.cmake:594 (_FPHSA_FAILURE_MESSAGE)
  /opt/homebrew/Cellar/cmake/3.24.1/share/cmake/Modules/FindOpenSSL.cmake:599 (find_package_handle_standard_args)
  deps/libsrtp/CMakeLists.txt:75 (find_package)
```

## 対処法
まずはopensslをインストールしているか
```
brew install openssl-devel
```
シンボリックリンクを強制的にはる
```
brew link openssl --force
```

以上

