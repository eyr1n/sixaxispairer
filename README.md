# sixaxispairer

## 準備: ESP32のMACアドレス確認

以下のスケッチをESP32に書き込む。

するとシリアルモニタにMACアドレスが表示されるので、メモしておく。

```cpp
#include <Ps3Controller.h>

void setup() {
  Serial.begin(115200);
  Ps3.begin();
  Serial.println(Ps3.getAddress());
}

void loop() {}
```

## ビルド・実行

事前にUSBでDualShockとPCを接続する。

`10:89:10:89:10:89` の部分はメモしておいたMACアドレスを入力する。

```bash
sudo apt install libhidapi-dev
cmake -B build .
cmake --build build
sudo build/sixaxispairer 10:89:10:89:10:89
```

