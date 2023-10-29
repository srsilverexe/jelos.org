# :material-frequently-asked-questions: Perguntas frequentes

## Sobre o JELOS

### O JELOS oferece qualquer tipo de suporte formal?

Não. JELOS é somente algo que desenvolvemos por diversão, e é distribuído da mesma forma. Existe uma grande variedade de comunidades que buscam ajudar, mas como esse é uma distribuição artesanal, você vai precisar sujar suas mãos para resolver qualquer problema.

### Vocês planejam adicionar algum “port”, software ou emulador?

Nos somos uma comunidade que desenvolve a distribuição, e nós acreditamos que é da responsabilidade da pessoa que quer um novo recurso o desenvolver e contribuir com tal recurso. Se você deseja adicionar algo para o JELOS, "pull requests" são bem-vindos. Por favor, verifique nosso [código de conduta](contribute/code-of-conduct.md), nosso [Guia de contribuição](contribute/index.md) e nosso [guia de builds](contribute/build.md) antes de enviar seu primeiro "pull request".

### Vocês suportam tal dispositivo? Vocês vão adicionar suporte para tal dispositivo?

Você pode encontrar a lista dos dispositivos aqui: [Dispositivos](../devices).

Se o dispositivo que você tem interesse não estiver listado, ninguém contribuiu para adicioná-lo ainda. Por quê? Para adicionar suporte para um dispositivo nós primeiro precisamos estar interessados em adicionar suporte para ele 😊, e segundo precisamos ter acesso direto para o dispositivo.

Isso quer dizer, qualquer um interessado pode enviar atualizações para o JELOS adicionando o dispositivo desejado! Se você tem interesse em adicionar suporte para um novo dispositivo, por favor comece por aqui: [Contribua](../contribute).

### Licenciando JELOS para redistribuição

JELOS utiliza uma licença de copyright não comercial, a "CC BY-NC-SA 4.0", sendo utilizada em todo projeto, com a intenção de prevenir qualquer abuso do nosso trabalho. Fabricantes de dispositivos e qualquer outro que deseja embutir nosso sistema em seus dispositivos não poderão o fazer, sem nossa explícita permissão.

#### Vendendo o JELOS

O JELOS é licenciado para uso não comercial apenas. Isso não é permitido ser vendido ou incluído em arrecadação monetária de qualquer forma, ou em qualquer período. Isso não é e não existe qualquer cogitação de qualquer negociação.

### Oque fazer se vocês pararem de trabalhar no JELOS?

Nós não esperamos que isso aconteça, de qualquer forma JELOS é um projeto Open Source, que é rosteado no GitHub, oque significa que o código-fonte está disponível para que qualquer um no mundo possa pegá-lo e continuar caso nos deixemos o projeto de lado. Nosso modelo de licença([GPLv2](https://choosealicense.com/license/gpl-2.0/)) permite que isso ocorra, providenciando e encorajando a redistribuição([freedom 2](https://www.gnu.org/philosophy/free-sw.en.html#four-freedoms)) e o direito para distribuir uma versão modificada([freedom 3](https://www.gnu.org/philosophy/free-sw.en.html#four-freedoms)). JELOS apenas proíbe o uso comercial de nossa marca, licenciada pela [Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License](https://tldrlegal.com/license/creative-commons-attribution-noncommercial-sharealike-4.0-international-(cc-by-nc-sa-4.0)).

## Usando o JELOS

### Quais emuladores e game engines são suportadas pelo JELOS?
Emuladores e game engines são configurados por uma base individual para cada dispositivo, e são automaticamente documentadas no momento de compilação. A documentação pode ser encontrada na seguinte URL: [Documentação por dispositivo](https://github.com/JustEnoughLinuxOS/distribution/tree/main/documentation/PER_DEVICE_DOCUMENTATION).

### Como eu posso conectar no SSH ou Samba?
Serviços externos (SSH e Samba) são desabilitados por padrão nas compilações de lançamento, porem podem ser habilitadas no menu de configurações de internet. Quando habilitada, o SSH/Samba utilizam o nome de usuário "root". A senha do root é regerada por padrão a cada vez que o sistema é reiniciado, e pode ser encontrada no menu de configurações de sistema. Você opcionalmente pode definir sua própria senha root, caso deseje.

Caso ao conectar no Samba pelo Windows for exibido a seguinte mensagem de erro: "The user name or password is incorrect", você pode verificar esses links para solucionar tal problema: [Windows 10 Pro](https://superuser.com/a/1129426/55073), [Windows 10 Home](https://superuser.com/a/1178850/55073).

Por favor, também verifique as paginas [Internet](/configure/networking) e [Adicionando jogos no JELOS](/play/add-games/#option-1-network-transfer) para detalhes adicionais.

### O som parou repentinamente de funcionar em meu dispositivo!

Faça o login pelo SSH e execute os seguintes comandos:
```
systemctl stop pipewire-pulse pipewire-pulse.socket pipewire pipewire.socket wireplumber
rm -rf /storage/.local/state /storage/.config/pulse
reboot
```

### EmulationStation mostra títulos de jogos duplicados. Como eu posso desabilitar uma extensão de arqui para remover as duplicatas? (Ex: mostrar apenas `.cue` e não mostrar `.bin` file for PlayStation)

* No EmulationStation selecione o sistema desejado. (Ex: PlayStation)
* Pressione `Select` para abrir o menu "View Options".
* No menu de "View Options", escolha "View Customisation".
* Em "File Extensions", desmarque qualquer extensão de arquivos que não são desejadas (Ex: desmarque o `.bin` no PlayStation para utilizar apenas arquivos `.cue`)

### Como eu posso editar o `es_system.cfg` (por exemplo, modificar a lista de sistemas no EmulationStation, e adicionar um core customizado ou script, ou modificar a ordem que os sistemas são mostrados)?

* Delete o link simbólico localizado em `~/.config/emulationstation/es_systems.cfg`.
* Copie a versão customizada do `es_system.cfg` para `~/.config/emulationstation`.
* Pare o serviço de UI, utilizando o seguinte comando: `systemctl stop ${UI_SERVICE}`.
* Em seguida reinicie o serviço de UI para que ele retorne utilizando a versão customizada, para fazê-lo utilize o seguinte comando: `systemctl start ${UI_SERVICE}`.

> Obs: Atualizações de sistema vão sobrescrever as alterações feitas, mas as configurações customizadas serão preservadas no arquivo `last_es_systems.cfg`.

### Onde eu devo colocar os arquivos de bios, arquivos de sistemas e outros arquivos.

* Aquivos de bios devem ser colocados em `/storage/roms/bios`.
* Por favor, veja a documentação correspondente para cada sistema na wiki, para verificar quais arquivos são necessários para cada sistema.

### Onde eu devo colocar os arquivos de música para habilitar músicas de fundo no EmulationStation (enquanto navego pela minha lista de jogos)?

* Arquivos de música devem ser adicionados para `/storage/roms/BGM`.

### Meu jogo sofre de lentidão e problemas com engasgos/quedas de frames. Oque eu posso fazer para melhorar a desempenho?

Primeiro tenha certeza que você não possui o TDP configurado, isso pode estar muito baixo para seu emulador funcionar corretamente. Em seguida tente ajustar as configurações do emular, podendo ser tanto do core no Retroarch ou o menu de configurações independes do emulador.

### Onde os arquivos de log são guardados?

Os arquivos de log podem ser encontrados em `/var/log/`.

Existe uma gama de logs que podem ser gerados, incluindo:

* Os logs do EmulationStation armazenados no arquivo `es_log.txt` (Um log acumulativo que armazena todas as atividades no ES), `es_launch_stdout.log` (Armazena ultimo emulador iniciado pelo ES) e `es_launch_stderr.log` (Ele estará vazio caso não tenha corrido nenhum erro no último emulador inicializado).
* O log de execução armazenado no arquivo `exec.log` (Um log genérico que indica qual foi a última execução do sistema, incluindo o comando utilizado para inicializar o emulador). Ex: para o gzdoom inicializar o `heretic.doom` ele executa o comando: `runemu.sh: Executing /usr/bin/bash start_gzdoom.sh /storage/roms/doom/heretic.doom`.
* O log de boot armazenado no arquivo `boot.log` (Saida para o autostart durante a inicialização do sistema).
* Os logs específicos de cada emulador (para emuladores que não fazem parte do ecossistema Retroarch). Ex: `gzdoom.log` é o arquivo de log especifico do gzdoom, que indica qualquer erro que possa ter ocorrido com o emulador enquanto tentava iniciar o `heretic.doom`.
* Os logs do Retroarch são [desabilitados por padrão](https://github.com/JustEnoughLinuxOS/distribution/blob/main/packages/games/emulators/retroarch/sources/handheld/retroarch.cfg#L420), mas podem ser habilitados por meio do Retroarch (Para a habilitar os logs vá em `Tools > Retroarch`, em seguida vá em `Settings > Logging > Log to a File`); eles são armazenados em `/var/log/retroarch`, e são bastante detalhados, oferecendo informações suficientes para identificar roms faltando em um romset, erros nas configurações, entre outros erros que podem atrapalhar o funcionamento de algum jogo.

> Obs: Retroarch utiliza um arquivo de configurações compartilhado, então o sistema de logs pode ser habilitado pela versão 64bits ou 32bits, e ela seguira habilitada para todos cores do Retroarch.

### Eu tenho um dispositivo com apenas um cartão microsd, mas eu não consigo ver a partição de jogos no Windows ou macOS.

JELOS não cria uma partição ExFAT no boot do dispositivo, e expande a partição inteira utilizando ext4. Você pode sincronizar os arquivos entre os dispositivos utilizando a internet, ou passando seus arquivos para um pendrive USB formatado como EXT4, ExFAT ou FAT32, e os copiando para o dispositivo utilizando o FileMan ou pelo SSH. Por favor, veja também a pagina [Adicionando jogos](/play/add-games) para mais detalhes.
