# プロジェクト3：呼吸するLED

## はじめに
最初の2つのプロジェクトを経て、Arduinoにある程度慣れてきたことと思います。このプロジェクトでは、LEDを使って別のことを行います。呼吸をシミュレートします。面白そうですね？では、始めましょう。プロジェクト2と同じハードウェアを使用します。

## 必要なハードウェア
* V4.0ボードまたはMEGA 2650ボード *1
* USBケーブル *1
* 赤色M5 LED *1
* 220Ω抵抗 *1
* ブレッドボード *1
* ブレッドボードジャンパーワイヤ *2

## 接続図

**V4.0の接続：**
![回路図](../../assets/images/lessons/lesson3/connectionDiagram.webp)
![見取り図1](../../assets/images/lessons/lesson3/connectionDiagram%20physix.webp)
![見取り図1](../../assets/images/lessons/lesson3/0b84c109b56cef032b85631efd27987a.webp)

**MEGA 2560の接続：**

[ここにMEGA 2560の接続図を挿入]

## サンプルコード

```cpp
int ledPin = 11; // デジタルピン11を定義

void setup()
{
  pinMode(ledPin, OUTPUT); // LEDピンを出力として定義
}

void loop()
{
  for (int a=0; a<=255; a++) // LEDを徐々に明るくする
  {
    analogWrite(ledPin, a); // LEDをオンにし、明るさを調整（0-255の範囲、255が最も明るい）
    delay(10); // 0.01秒待機
  }
  for (int a=255; a>=0; a--) // LEDを徐々に暗くする
  {
    analogWrite(ledPin, a); // LEDをオンにし、明るさを調整（0-255の範囲、255が最も明るい）
    delay(10); // 0.01秒待機
  }
  delay(1000); // 1秒待機
}
```

## テスト結果

LEDが徐々に明るくなり、0.01秒待機し、その後徐々に暗くなり、1秒待機します。そしてこのサイクルを繰り返し、まるでLEDが呼吸しているかのように見えます。