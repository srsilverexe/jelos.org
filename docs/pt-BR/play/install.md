# :material-progress-check: Instalando o JELOS

JELOS é instalado baixando a imagem para o seu dispositivo, gravando-o em um cartão SD (Ou no armazenamento interno do seu dispositivo) e ligando o dispositivo para que ele inicie o processo de instalação.

## Primeiro passo: Download

[![Latest](https://img.shields.io/github/release/JustEnoughLinuxOS/distribution.svg?labelColor=111111&color=5998FF&label=Latest&style=flat#only-light)](https://github.com/JustEnoughLinuxOS/distribution/releases/latest)[![Latest](https://img.shields.io/github/release/JustEnoughLinuxOS/distribution.svg?labelColor=dddddd&color=5998FF&label=Latest&style=flat#only-dark)](https://github.com/JustEnoughLinuxOS/distribution/releases/latest)

* Baixe a ultima versão do JELOS para o seu dispositivo, esse download pode ser encontrado na [pagina de lançamentos](https://github.com/JustEnoughLinuxOS/distribution/releases/latest).
    * Você vai encontrar o link de download para cada dispositivo/plataforma que suportamos na divisão: "Installation Package Downloads".
    * Tenha certeza que de baixar a imagem correta para o seu dispositivo. Por exemplo, se você estiver instalando o JELOS em um [Loki Zero](../devices/ayn/loki-zero.md) você deve baixar a imagem `JELOS-AMD64`. 
    * Se você qualquer dúvida, você pode verificar os [Dispositivos suportados](../devices/index.md), para confirmar qual imagem você deve baixar para seu dispositivo. 

## Segundo passo: Gravação

* Primeiro descomprima a imagem.
* Grave a imagem em um cartão SD utilizando uma ferramenta de gravação.
    * As ferramentas de gravação mais comuns incluem o [Balena Etcher](https://www.balena.io/etcher/), [Raspberry Pi Imager](https://www.raspberrypi.com/software/) e o [Win32 Disk Imager](https://sourceforge.net/projects/win32diskimager/). Se você já tiver experiencia com linha de comando, `dd` também pode ser uma boa opção.

## Terceiro passo: Ligar seu dispositivo

* Insira seu cartão SD em seu dispositivo ainda desligado, apenas quando o cartão for inserido ligue o dispositivo. 
> Obs: Alguns dispositivos precisam que você modifique a ordem que seu cartão SD é carregado, para que ele seja o primeiro na lista. Por favor verifique a documentação especifica do seu dispositivo para ver se isso é necessario no seu caso.
* JELOS vai iniciar automaticamente o processo de instalação, e em seguida reiniciara o dispositivo quando estiver completo.
* Quando o dispositivo reiniciar ele ira iniciar diretamente no EmulationStation. Nesse ponto você já pode prosseguir como achar melhor.

---

## Observações adicionais

* O sistema operacional JELOS é armazenado em uma partição Ext4, esse tipo de partição pode ser lido pelo LINUX, mas não é legível de forma nativa no Windows; atualmente não é possível acessar a partição primaria do JELOS (Ext4) no Windows para adicionar jogos.
* Em dispositivos que suportam um segundo cartão SD, esse cartão pode ser formatado como Ext4, FAT32 ou exFAT. JELOS ira detectar automaticamente o segundo cartão durante o boot e criara as pastas essenciais para armazenar as roms.
* Em dispositivos x86 JELOS inclui uma ferramente de instalação. Essa ferramenta pode ser encontrada do menu `tools`, listado em meio aos sistemas no EmulationStation.

## Próximos passos

* [Adicionar Jogos](/play/add-games)
* [Configurar rede/internet](/configure/networking)
* [Temas](/configure/themes)
