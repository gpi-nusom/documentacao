---
description: Neste tutorial iremos compilar o pure-data versão vanilla no Raspberry Pi.
---

# Compilando Pure Data vanilla no RPi



**Válido para o** [**Rasbian Stretch with Desktop**](https://www.raspberrypi.org/downloads/raspbian/)**.**

No momento em que este tutorial foi escrito, a versão mais recente do Pure data é a 0.49, é a versão que instalaremos com este tutorial.

**PASSO 1** - Abra o Terminal: `Ctrl+Alt+T`  


**PASSO 2** - Crie um diretório com código fonte e entre nele \(opcional\):

```bash
mkdir src && cd src
```

**PASSO 3** - Instale as dependências para compilação e baixe o pure data 0.49:

```bash
sudo apt install build-essential autoconf automake libtool gettext git libasound2-dev libjack-jackd2-dev libfftw3-3 libfftw3-dev tcl tk
wget http://msp.ucsd.edu/Software/pd-0.49-0.src.tar.gz
```

**PASSO 4** - Descompacte o código fonte baixado e entre no diretório com o código fonte:

```bash
tar -xzf pd-0.49-0.src.tar.gz
cd pd-0.49-0
```

**PASSO 5** - Configure e compile:

```text
./autogen.sh
./configure --enable-jack --enable-fftw
make
```

**PASSO 6** - Após terminar a compilação, vamos abrir o pd compilado pra conferir se está funcionando:

```text
cd bin
./pd
```

**PASSO 7** - Se o Pure-data funcionou direitinho, é hora de instalá-lo no sistema:

```text
cd..
sudo make install
```

Toda vez que quiser abrir o pure-data  que você compilou, basta abrir o terminal e digitar: `pd`

