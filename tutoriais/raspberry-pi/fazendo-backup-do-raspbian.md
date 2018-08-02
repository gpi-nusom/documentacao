---
description: >-
  Tutorial de como fazer backup de Raspbian customizado no SD utilizando o
  Ubuntu
---

# Fazendo backup do Raspbian

**Fazendo backup do cartão SD no Ubuntu** \(Para outras opções consultar [artigo original](https://www.htpcguides.com/easy-resize-and-back-up-raspberry-pi-sd-card-with-ubuntu/)\)  


Neste tutorial será fundamental o uso do Terminal. No Ubuntu desktop, para abrir o Terminal pressione as teclas: `Ctrl+Alt+T`



PASSO 1 - Procurar pelo dispositivo que está lendo o cartão SD no sistema:

```bash
sudo blkid
```

deve mostrar algo do tipo:

```bash
/dev/sda1: UUID="8c1f3298-166c-4abe-bd4f-8ee171bae920" TYPE="ext4" 
/dev/sda5: UUID="9c8f07c2-85bb-4581-a6e5-c6d4e4e89952" TYPE="swap" 
/dev/sdb1: SEC_TYPE="msdos" UUID="4F72-0755" TYPE="vfat" 
/dev/sdb2: UUID="18bb9f0f-3eb8-4584-9e2a-c19cd2b58d1e" TYPE="ext4"
```

fique esperto que a sua saída pode ser diferente, o lance é procurar pelo sistema de arquivos que o cartão SD foi criado:

* na linha 3 em verde:

  ```text
  "msdos" e "vfat"
  ```

* na linha 4 em verde:

  ```text
  "ext4"
  ```

o dispositivo \(device\) /dev/sdbX, no nosso caso /dev/sdb1 e /dev/sdb2 indicam que o endereço /dev/sdb é o do dispositivo que procuramos.

{% hint style="info" %}
Se inserirmos um novo pendrive e/ou outro dispositivo de armazenamento qualquer ele irá adquirir o nome de /dev/sdc, /dev/sdd e assim por diante. Supondo que o outro dispositivo de armazenamento tenha 3 partições, cada partição seria nomeada como: /dev/sdd1, /dev/sdd2 e /dev/sdd3.
{% endhint %}



PASSO 2 - Vamos agora fazer a criação de uma imagem do cartão SD \(backup\):

```bash
sudo dd if=/dev/sdb of=/home/meu_usuário/meubackupdoraspberrypi.img bs=1M
```

{% hint style="info" %}
ATENÇÃO

* Repare que após:  _if=_  você deverá substituir o _/dev/sdb_ pelo endereço do dispositivo que você identificou no PASSO 1 deste tutorial.
* Após: _of=_  , a parte escrita "_meu\_usuário"_  deve ser substituido pelo seu nome de usuário e "_meubackupdoraspberrypi_" pelo nome que vc escolher para sua imagem.
{% endhint %}



PASSO 3 - Instalar o [PiShrink](https://github.com/Drewsif/PiShrink) \(Se já tiver instalado o PiShrink, pode pular pro PASSO 4\)

* Baixar o PiShrink. No terminal escreva: 

  ```bash
  wget https://raw.githubusercontent.com/Drewsif/PiShrink/master/pishrink.sh
  ```

* Dê os privilégios necessários ao funcionamento do script baixado:

  ```bash
  chmod +x pishrink.sh
  ```

* Agora copiaremos o script do PiShrink para um diretório onde poderá ser executado sem problemas:

  ```bash
  sudo mv pishrink.sh /usr/local/bin 
  ```



PASSO 4 - Comprimir imagem extraída do SD:

```text
sudo pishrink.sh meubackupdoraspberrypi.img meubackupdoraspberrypicomprimido.img
```



Pronto! Agora você deverá ter uma imagem funcional do seu Raspbian. Mas antes de confiar, desconfie... Teste a sua imagem para conferir se ela realmente funciona.

