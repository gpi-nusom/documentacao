# Cirrus Logic Audio Card

**Instalação da placa de som Cirrus Logic Audio Card no Raspberry Pi 2 e 3.**

1. Abrir o terminal teclando: `Ctrl+Alt+T`
2. No terminal:

   ```bash
   sudo rpi-update
   sudo reboot
   ```

   O seu RPi será reiniciado. Aguarde o processo terminar.

3. Abrir o Terminal novamente: `Ctrl+Alt+T`
4. Para habilitar o driver da placa, abra o arquivo de configuração digitando no terminal:

   ```bash
   sudo leafpad /boot/config.txt
   ```

5. No Editor de texto, adicione ao final do documento as seguintes linhas:

   ```text
   #Suporte para placa Cirrus Logic Audio Card
   dtoverlay=rpi-cirrus-wm5102
   ```

6. Salve o documento
7. Agora vamos criar o arquivo de configuração da placa, no Terminal:

   ```bash
   sudo leafpad /etc/modprobe.d/cirrus.conf
   ```

8. Novamente no editor de Texto adicionar as linhas abaixo, salvar e sair:

   ```text
   softdep arizona-spi pre: arizona-ldo1
   options snd slots=snd-soc-rpi-cirrus,snd-bcm2835
   ```

9. Agora baixe e instale "usecase" mixer scripts:

   ```bash
   wget http://www.horus.com/~hias/tmp/cirrus/cirrus-ng-scripts.tgz
   mkdir bin
   cd bin
   tar zxf ../cirrus-ng-scripts.tgz
   ```

10. Reinicie o Raspberry para utilizar a placa:

    ```text
    sudo reboot
    ```



_**Fonte:**_ [_RPi Linux driver for Wolfson / Cirrus Logic Audio Card_](http://www.horus.com/~hias/cirrus-driver.html)\_\_

