---
title: "BlueBomb"
---

{% include toc title="Table of Contents" %}

## BlueBomb Micro

{% capture technical_info %}
<summary><em>Technical Details (optional)</em></summary>
BlueBomb Micro is a port of Fullmetal5's BlueBomb exploit for the Rasperry Pi Pico W or ESP32, thus bypassing the need for a Linux system. It takes advantage of a flaw in the Wii and Wii mini's Bluetooth libraries. This port was made possible by [GaryOderNichts](https://github.com/GaryOderNichts)

This exploit also enables recovery from certain bricks, such as banner bricks and (some) theme bricks.

{% endcapture %}
<details>{{ technical_info | markdownify }}</details>
{: .notice--info}

Wii Miniをブリックさせる可能性が高いため、YouTubeなどにある動画を使用して改造しないことを推奨します。
{: .notice--warning}

チュートリアル中に質問があったら、[ディスコード](https://discord.gg/6ryxnkS)でお問い合わせください。
{: .notice--info}

For the original Wii, we do not recommend using BlueBomb if you intend to install the Homebrew Channel and BootMii, as there are more convenient exploits available. ブリックを修復する場合などの例外はあります。
{: .notice--info}

Bluetoothを接続するため、Wii本体とパソコンを近づけるようにしてください。1m未満の距離が望ましいです。
{: .notice--info}

### 必要なもの
* A Rasperry Pi Pico W or an ESP32 with BR/EDR (Classic) support.
* FAT32でフォーマットされたUSBドライブ
* [The HackMii Installer](https://bootmii.org/download/)

A normal Rasperry Pi Pico will not work. It MUST to be the wireless model. Additionally, an ESP32 with a BLE only controller will not work.
{: .notice--info}

### 実行方法

1. Extract it and place the `boot.elf` file in your flash drive.
    + (ブリックを修正する場合、使用するHomeberwアプリをappsフォルダにコピーする必要があります)
    + - (Even for a Wii mini, bootmini.elf will **not** work, its purpose is entirely different and unrelated. boot.elfを使用してください。 )
1. USBドライブをWii本体に接続します。
    + Wiiの場合、縦向きの場合は右のUSBポート、横向きの場合は下のUSBポートに接続してください。
    + For a normal Wii, use the bottom port. (or the right port if it's upright).
1. Wiiの電源を入れます。
1. `Wii設定`に進みます。
1. バージョンを確認してください。1ページ目の右上に表示されています。
    + これはシステムメニュー領域に対応しており、後ほど実行する手順に必要となります。

    ![](/images/wii/SystemMenuVersion.png)

1. Wiiの電源を切ります。

#### Rasperry Pi Pico W

1. Download [The latest Pre-Compiled Binaries](https://github.com/GaryOderNichts/bluebomb_micro/releases) from the releases page, and extract it to your PC.
1. Plug in your Pico W to your PC while holding down the `BOOTSEL` button. Your Pico should now show up as a drive on your PC.
1. Unzip the downloaded file and copy the file which matches your Wii or Wii mini to the drive. For example, if you have a European Wii running version 4.3, you would copy bluebomb_WII_SM4_3E.uf2, or if you have a European Wii Mini, you would copy bluebomb_MINI_SM_PAL.uf2, etc...
1. The drive should disconnect and your Pico is ready. You may unplug the device from your PC.

#### ESP32

1. Set up the latest [ESP IDF](https://docs.espressif.com/projects/esp-idf/en/stable/esp32/get-started/index.html).
1. Build the binary [from source](https://github.com/GaryOderNichts/bluebomb_micro/tree/main/ports/esp32#building-from-source).
1. [Flash the binary](https://github.com/GaryOderNichts/bluebomb_micro/tree/main/ports/esp32#flashing) to your ESP32.
1. Your device is now ready. You may unplug the device from your PC.

### Performing the Exploit

1. Plug your flashed device back into your PC.
1. Wiiの電源を入れます。
    + Turn on your console and **do not** connect any Wii Remotes.
1. Press the Sync button repeatedly until the bluebomb screen shows up.
    + 何度も押す必要がある場合があります。
1. 成功すると、WiiはHackMiiインストーラーをロードします。

If using a Wii, proceed to installing the Homebrew Channel and BootMii<br>
{: .notice--info}

If using a Wii mini, proceed to installing the Homebrew Channel
{: .notice--info}

## BlueBomb Classic

Wii Miniで唯一使用可能な改造方法ですが、Wiiでも問題無く使えます。 {% capture technical_info %}
<summary><em>Technical Details (optional)</em></summary>
BlueBomb is an exploit that takes advantage of a flaw in the Wii and Wii mini's Bluetooth libraries.

This exploit also enables recovery from certain bricks, such as banner bricks and (some) theme bricks.

{% endcapture %}
<details>{{ technical_info | markdownify }}</details>
{: .notice--info}

Wii Miniをブリックさせる可能性が高いため、YouTubeなどにある動画を使用して改造しないことを推奨します。
{: .notice--warning}

チュートリアル中に質問があったら、[ディスコード](https://discord.gg/6ryxnkS)でお問い合わせください。
{: .notice--info}

For the original Wii, we do not recommend using BlueBomb if you intend to install the Homebrew Channel and BootMii, as there are more convenient exploits available. ブリックを修復する場合などの例外はあります。
{: .notice--info}

Bluetoothを接続するため、Wii本体とパソコンを近づけるようにしてください。1m未満の距離が望ましいです。
{: .notice--info}

### 必要なもの

* Linuxがインストールされているパソコン
    * 仮想環境でも可能ですが、仮想環境でBluetoothを使うことは複雑であるため、推奨されません。 後述のLiveUSBを利用することを推奨します。
    * Raspberry Piがある場合、Linuxがインストールされているパソコンの代わりに利用できます。
    * Windows Subsystem for LinuxやChromebookのLinuxモードではBluetoothが使用できないため、BlueBombを実行することはできません。
    * Linuxがインストールされているパソコンが無い場合、WindowsやMacで利用可能な[Ubuntu](https://ubuntu.com/download/desktop)を推奨します。
        * 32ビットのPCでは[Ubuntu 16.04](http://releases.ubuntu.com/16.04/)が必要です。
        * 64ビットのPCでは不具合が起きづらいLTS(長期サポート)版のUbuntuを推奨しますが、最新版のUbuntuでも使えます。
    * Linux LiveをPCにインストールする代わりに、[USBドライブにLinuxをインストール](https://ubuntu.com/tutorials/tutorial-create-a-usb-stick-on-windows#1-overview)することができます。
* Bluetoothアダプター
    * 内臓Bluetoothアダプターも使用できます。
    * 外付けBuletoothアタブターを使用する場合、Linuxと互換性のあるもの使用してください。
* FAT32でフォーマットされたUSBドライブ
    * LinuxをダウンロードしたUSDドライブとは別の物を使用してください。
* [HackMii Installer v1.2](https://bootmii.org/download/)

### 実行方法

1. Extract it and place the `boot.elf` file in your flash drive.
    + (ブリックを修正する場合、使用するHomeberwアプリをappsフォルダにコピーする必要があります)
    + - (Even for a Wii mini, bootmini.elf will **not** work, its purpose is entirely different and unrelated. boot.elfを使用してください。 )
1. USBドライブをWii本体に接続します。
    + Wiiの場合、縦向きの場合は右のUSBポート、横向きの場合は下のUSBポートに接続してください。
    + For a normal Wii, use the bottom port. (or the right port if it's upright).
1. Wiiの電源を入れます。
1. `Wii設定`に進みます。
1. バージョンを確認してください。1ページ目の右上に表示されています。
    + これはシステムメニュー領域に対応しており、後ほど実行する手順に必要となります。

    ![](/images/wii/SystemMenuVersion.png)

1. Wiiの電源を切ります。
1. Linuxを起動し、インターネットに接続されていることを確認します。
1. ターミナルを開きます。
1. 以下のコードを実行します。

    ```bash
    wget https://wii.hacks.guide/assets/files/bluebomb-helper.sh
    chmod +x bluebomb-helper.sh
    ./bluebomb-helper.sh
    ```

1. コードを実行すると、必要なファイルをダウンロードし、Wiiの情報を求めます。
    + Wii miniを選択した場合、リージョンを入力するように求められます。 これは、STEP4で確認したWiiメニューの最後の文字(U,E,Kのいずれか)です。
    + Wiiを選択した場合、Wiiメニューのバージョンの入力を求められます。
1. Wiiの電源を入れます。
    + Turn on your console and **do not** connect any Wii Remotes.
1. PCに`got connection handle`が表示されるまで、Wii本体のSyncボタンを押してください。
    + 何度も押す必要がある場合があります。
1. 成功すると、WiiはHackMiiインストーラーをロードします。
    + You can now shut down your Linux computer if you are not planning to use it later.

If using a Wii, proceed to installing the Homebrew Channel and BootMii<br>
{: .notice--info}

If using a Wii mini, proceed to installing the Homebrew Channel
{: .notice--info}
