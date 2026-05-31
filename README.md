
OXY-LINUX-RETRO

Sistema de arquivos OXY-OS otimizado para execução no Termux.
Requisitos

Primeiro, atualize o seu Termux e instale as ferramentas necessárias para a extração e execução do ambiente.
#comado
pkg update && pkg upgrade
pkg install tar proot xz-utils
.
Download

Baixe a versão mais recente do sistema de arquivos diretamente do repositório oficial.
#comando

curl -LO https://github.com/gabgame2012-collab/OXY-LINUX-RETRO/releases/download/1.0/rootfs-oxy.tar.xz
.
Instalação e Extração

Crie o diretório de destino e extraia o conteúdo do arquivo comprimido.
#comando
mkdir -p ~/oxy-os
tar -xvf rootfs-oxy.tar.xz -C ~/oxy-os
.
Execução

Inicie o sistema utilizando o proot para isolar o ambiente do Android.
#comando
proot -0 -r ~/oxy-os -b /dev -b /proc -b /sys /bin/sh
.
Alias de Acesso Rápido

Para facilitar o acesso ao OXY-OS, adicione um atalho ao seu arquivo de configuração.
#comando
echo "alias oxyos='proot -0 -r ~/oxy-os -b /dev -b /proc -b /sys /bin/sh'" >> ~/.bashrc
source ~/.bashrc
.
Manutenção

Para remover o sistema de arquivos e liberar o espaço ocupado no armazenamento interno.
#comando
rm -rf ~/oxy-os
.
Nota: Após configurar o alias, basta digitar oxyos em qualquer sessão do seu Termux para iniciar o sistema.
