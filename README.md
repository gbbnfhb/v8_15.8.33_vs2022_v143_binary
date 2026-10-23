元ネタはこちら。https://github.com/pmed/v8-nuget  
最新のversionでビルドしてみた。大きいファイルは上げられないみたいなので残りは下に  
  
v8-v143-x64.15.8.33.nupkg ヘッダとlibファイル。ここに上がってるやつ  
  
v8.redist-v143-x64.15.8.33.nupkg  dllファイル  
https://mega.nz/file/06xjhAQR#4T_9M2ykB8zzhlhCCoEtUE3UVaSvAoQ3lHn_1AjMGlc  
  
v8.symbols-v143-x64.15.8.33.nupkg シンボルファイル まあ普段は使わない  
https://mega.nz/file/BihiWJBa#6FTXRpxty5PYw-F2d0SNKN5-saQpGwXt4sovN9jNcl4  
   
v8_test.zip サンプル  
https://mega.nz/file/wmxhQSjD#GxZfI3gq1fZUl50CenXbGgUx4kkn9GQIHvX69CifuH4  
  
  
  
  
visual studio2022 x64 msvc(v143) sdk 10.0.26100.0 用   
c++/clang両方対応。あまり複雑なのは試していませんが、今の所どちらでも使えてるみたいです。  
  
※visualstudio 2026 x64 10.0.28000.0用だったのをvs2022 sdk 10.0.26100.0 用に書き換えました。  
10.0.26100.0 は必須なのでこれは変えないでください   
    
最新版は結構あちこち変わってたので苦労しました  
他にもあるけど主な変更は以下のところ  
~~~
✅ SDK_VERSION = '10.0.26100.0' patched in both setup_toolchain.py and vs_toolchain.py
✅ NTDDI_VERSION=NTDDI_WIN11_GE patched in build/config/win/BUILD.gn
✅ --skip-sync flag added so it won't reset your manual changes
✅ windows_sdk_version = "10.0.26100.0" and visual_studio_version = "2022" in GN_OPTIONS
✅ DEPOT_TOOLS_UPDATE = '0' set to prevent depot_tools from updating itself
✅ INCLUDE/LIB env var filtering to remove non-existent paths
~~~  
<br><br><br><br><br>
■d8とv8windbgが入ってない理由  
static linkにするとファイルが2G以上になると言われているし、リンクに時間がかかるようになるため今回は同梱してません  
<img width="689" height="783" alt="無題" src="https://github.com/user-attachments/assets/9eb543e8-7ce7-4bf2-b4f2-14e696adb43a" />

