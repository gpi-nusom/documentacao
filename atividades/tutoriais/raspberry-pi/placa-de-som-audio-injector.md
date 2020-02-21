---
description: 'Procedimento para configurar a Interface de Áudio: Audio Injector ZERO'
---

# Placa de Som Audio Injector Zero

[Audio Injector Zero](http://www.audioinjector.net/rpi-zero) é uma interface de áudio projetada para ser utilizada em conjunto com [Raspberry Pi Zero](https://www.raspberrypi.org/products/raspberry-pi-zero/), mas também pode ser utilizada com outros modelos de Raspberry contanto que tenham GPIO de 40 pinos. Aqui no GPI NuSom testamos com sucesso nos [Raspberry Pi 3 B+](https://www.raspberrypi.org/products/raspberry-pi-3-model-b-plus/).

**Válido para o** [**Raspbian Buster with Desktop**](https://www.raspberrypi.org/downloads/raspbian/)**.**



**PASSO 1** - Abra o Terminal: `Ctrl+Alt+T`

**PASSO 2** - Baixe o pacote de instalação audio.injector.scripts\_0.1-1\_all.deb:

```text
wget https://github.com/Audio-Injector/stereo-and-zero/raw/master/audio.injector.scripts_0.1-1_all.deb
```

**PASSO 3** - Instale o pacote baixado:

```text
sudo dpkg -i audio.injector.scripts_0.1-1_all.deb
```

**PASSO 4** - Rode o script de instalação abaixo e quando perguntado tecle y:

```text
audioInjector-setup.sh
```

{% hint style="warning" %}
O script irá atualizar o sistema para uso da Interface Audio Injector primeiramente rodando rpi-update, apenas responda y \(yes\) para prosseguir com a instalação. O arquivo /boot/config.txt também será alterado para que a placa seja reconhecida \(dtoverlay=audioinjector-wm8731-audio\).
{% endhint %}

**PASSO 5** - Após finalizada a instalação, desligue o seu Raspberry Pi e com a Interface Audio Injector Zero devidamente conectada ligue novamente o RPi.



Agora você já deverá ser capaz de utilizar sua Interface de Áudio. Segundo o suporte com o mesmo procedimento também é possível utilizar a Interface [Audio Injector Stereo](http://www.audioinjector.net/rpi-hat).





Fonte: [https://github.com/Audio-Injector/stereo-and-zero](https://github.com/Audio-Injector/stereo-and-zero)





