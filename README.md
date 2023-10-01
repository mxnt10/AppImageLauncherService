# rc.AppImageLauncher

Serviço de integração de AppImage para o Slackware feito em bash e sem precisar de nenhuma  ferramenta ou recurso adicional.

# Instalação

Não execute o comando como superusuário. Ele depende da variável $HOME para as configurações padrão. A instalação irá pedir a senha de root quando necessário.

`$ ./rc.AppImageLauncher install`

Após a instalação será criado automaticamente o diretório AppImageLauncher no diretório home. Não será necessário pós configuração, ele já estará rodando no sistema.

# Configurações

Ele já estará funcional após a instalação. Mas é possível configurar as opções caso precise. 

`$ /etc/rc.d/rc.AppImageLauncher configure`

Não se preocupe com o root, o serviço irá solicitar sempre que precisar.

Caso queira usar um editor de sua preferência, por exemplo, o kate:

`$ sudo kate /etc/rc.d/rc.AppImageLauncher.conf`

As opções configuráveis são:

- APPIMAGE_DIR: Local do diretório para os AppImages.
- CREATE_MENU: Habilita ou desabilita um menu personalizado só para os AppImages. Por padrão, essa opção se encontra desabilitada, com `false`. Habilite-a com `true`.  
- LOOP_TIME: Tempo de espera a cada verificação em segundos. Foi usado `2` por padrão.

É preferível não mexer no resto.

Após as configurações o serviço deve ser reiniciado. Não inventei moda, para maior performance, é bom as configurações serem lidas uma vez.

`$ /etc/rc.d/rc.AppImageLauncher restart`

Se precisar redefinir:

`$ /etc/rc.d/rc.AppImageLauncher reconfigure`

# Demais opções

Reinstalação do serviço, novamente é bom usar o arquivo usado para instalação:

`$ ./rc.AppImageLauncher reinstall`

Iniciar e parar o serviço:

`$ /etc/rc.d/rc.AppImageLauncher start`

`$ /etc/rc.d/rc.AppImageLauncher stop`

Verificação de status:

`$ /etc/rc.d/rc.AppImageLauncher status`

# Desinstalação

A desisntalação não detona as operações feitas pelo serviço. Então se preferir, pode desinstalar sem medo. Eu recomendo usar o arquivo usado na instalação.

`$ ./rc.AppImageLauncher uninstall`
