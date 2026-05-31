# OXY-LINUX-RETRO

Sistema de arquivos **OXY-OS** otimizado para execução no **Termux**, oferecendo um ambiente Linux isolado através do PRoot sem necessidade de acesso root.

---

## 📋 Requisitos

Atualize o Termux e instale as dependências necessárias:

```bash
pkg update && pkg upgrade -y
pkg install tar proot xz-utils curl -y
```

---

## 📥 Download

Baixe a versão mais recente do sistema de arquivos:

```bash
curl -LO https://github.com/gabgame2012-collab/OXY-LINUX-RETRO/releases/download/1.0/rootfs-oxy.tar.xz
```

---

## 📦 Instalação e Extração

Crie o diretório de instalação e extraia o sistema:

```bash
mkdir -p ~/oxy-os
tar -xvf rootfs-oxy.tar.xz -C ~/oxy-os
```

---

## 🚀 Execução

Inicie o OXY-OS utilizando o PRoot:

```bash
proot -0 -r ~/oxy-os \
-b /dev \
-b /proc \
-b /sys \
-w /root \
/bin/sh
```

---

## ⚡ Alias de Acesso Rápido

Adicione um comando personalizado para iniciar o sistema facilmente:

```bash
echo "alias oxyos='proot -0 -r ~/oxy-os -b /dev -b /proc -b /sys -w /root /bin/sh'" >> ~/.bashrc
source ~/.bashrc
```

Após configurar o alias, basta executar:

```bash
oxyos
```

---

## 🛠 Recursos

* Ambiente Linux isolado com PRoot
* Não requer root
* Inicialização rápida
* Compatível com Termux
* Estrutura leve e portátil
* Fácil instalação e remoção
* Ideal para estudos, testes e desenvolvimento

---

## 🗑 Remoção

Para remover completamente o OXY-OS:

```bash
rm -rf ~/oxy-os
```

Opcionalmente remova o alias:

```bash
sed -i '/alias oxyos=/d' ~/.bashrc
source ~/.bashrc
```

---

## 📄 Licença

Este projeto é distribuído sob a licença GPL3.

---

## ℹ️ Nota

O OXY-LINUX-RETRO utiliza PRoot para criar um ambiente Linux isolado dentro do Android, permitindo executar ferramentas e aplicações sem modificar o sistema operacional do dispositivo.

Desenvolvido para usuários que desejam uma experiência Linux prática diretamente no Termux.
