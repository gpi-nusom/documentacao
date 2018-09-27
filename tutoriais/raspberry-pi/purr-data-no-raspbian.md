---
description: Tutorial de instalação do Purr Data no Raspbian.
---

# Purr Data no Raspbian

**Válido para o** [**Rasbian Stretch with Desktop**](https://www.raspberrypi.org/downloads/raspbian/)**.**

**PASSO 1** - Baixe o pacote binário do mais recente do [Purr-data](https://github.com/jonwwilkes/purr-data/releases).

    No momento em que este tutorial foi escrito:  
    [purr-double-trouble-test1-raspbian\_stretch-armv7l.zip](https://github.com/jonwwilkes/purr-data/releases/download/2.6.0/purr-double-trouble-test1-raspbian_stretch-armv7l.zip)

**PASSO 2** - Descompacte o arquivo baixado.

**PASSO 3** - Abra o Terminal pressionando  as teclas:

```text
Ctrl + Alt + T
```

**PASSO 4** - Navegue até a pasta em que foi decompactado o arquivo de instalação do pd-l2ork. Se você descompactou no diretório de download padrão será assim:

```bash
cd Downloads
```

**PASSO 5** - Instale as dependências do pacote:

```bash
sudo apt install fluid-soundfont-gm libgsl2 liblua5.3-0 libquicktime2
```

**PASSO 6** - Instale o pacote do Purr Data:

```bash
sudo dpkg -i pd-l2ork-2.5.1-20180414-rev.8916c70d-armv7l.deb
```

> _**Dica:** no terminal ao invés de digitar o nome completo, digite as primeiras letras e pressione a tecla **Tab.**_

**PASSO 7** - Confirme a instalação e aguarde a finalização.

**PASSO 8** - Agora é só utilizar o Purr-data no Raspbian

