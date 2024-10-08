---
title: "Criando Atalhos de Jogos no Wii"
---

{% include toc title="Sumário" %}

Do you use a Wii backup loader and want to create game shortcuts to launch them on your Wii Menu? Então tente WiiGSC (Wii Game Shortcut Creator), previamente conhecido como Crap.

No caso de um brick, [instalar Priiloader é obrigatório](/priiloader). Também, instale BootMii (como Boot2 se você tem um Wii antigo). Instalar proteção de bricks e seguir o guia corretamente deve mantê-lo seguro contra bricks. NÃO CONTINUE COM O GUIA ATÉ VOCÊ TER INSTALADO PRIILOADER E BOOTMII!
{: .notice--warning}

NÃO faça atalhos para os jogos "Mario Party 9" ou "A Boy and His Blob". Irá causar um brick em seu Wii.
{: .notice--warning}

The Wii Menu is limited to 48 channels, not including existing system channels.
{: .notice--info}

### Requisitos

* Um Wii
* An SD or USB drive
* [YAWM ModMii Edition](yawmme)
* Um computador Windows.
* [WiiGSC](https://wiidatabase.de/downloads/pc-tools/wiigsc-ehemals-crap/)

### Instruções

1. Install WiiGSC, then right click on it and choose **Run as administrator**. If you do not do this, WiiGSC will throw an error when you open it.

    ![](/images/desktop-apps/wiigsc/wiigsc-home.png)

2. Select the path to the ISO or WBFS file on your SD or USB drive, and select the loader you use. The other options should be fine the way they are.

    ![](/images/desktop-apps/wiigsc/wiigsc-selection.png)

If you are on vWii, use the [Wiiforwarder2vWii](https://gbatemp.net/download/wiiforwarder2vwii-wii-forwarder-to-vwii-wii-u-forwarder-converter-beta-version.37254/) tool to convert the WAD for use on the vWii.
{: .notice--info}

3. Install the generated WAD with your [WAD manager](yawmme).

<div class="notice--info" markdown="1">
If you get an error saying "The system files are corrupted", don't panic as long as you installed Priiloader. Turn off your Wii, then [boot into Priiloader](priiloader#section-iii---entering-priiloader) using one of the available methods for your console. Enter the Homebrew Channel and launch your WAD manager to uninstall the WAD. If priiloader was not installed, proceed to [BlueBomb](bluebomb).
</div>

[Clique aqui para voltar ao índice do site.](site-navigation)
{: .notice--info}
