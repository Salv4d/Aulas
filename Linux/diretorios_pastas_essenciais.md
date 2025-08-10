# Guia Prático do FHS Linux - Diretórios Essenciais

Este guia apresenta os principais diretórios do Filesystem Hierarchy Standard (FHS) do Linux de forma prática e objetiva. O FHS organiza a estrutura de pastas do sistema Linux, definindo onde cada tipo de arquivo deve ficar para manter consistência e compatibilidade entre distribuições.

**Objetivo:** Oferecer o conhecimento essencial para navegar com segurança no sistema Linux e resolver os problemas mais comuns.

---

## 📁 Diretórios do FHS - Estrutura e Arquivos Importantes

### `/home` - **SUA CASA** 
Arquivos pessoais e configurações do usuário (sempre seguro mexer)

**Estrutura típica:**
```
/home/
├── usuario1/
│   ├── .bashrc              # Configurações do bash
│   ├── .profile             # Configurações de login
│   ├── .ssh/                # Chaves SSH
│   ├── Documents/
│   ├── Downloads/
│   ├── Pictures/
│   └── Desktop/
└── usuario2/
```

**Arquivos importantes:**
- `.bashrc` - Configurações do terminal
- `.ssh/id_rsa` - Chave privada SSH
- `.gitconfig` - Configurações do Git

---

### `/root` - **CASA DO ADMINISTRADOR**
Diretório pessoal do usuário root (superusuário)

**Estrutura típica:**
```
/root/
├── .bashrc                  # Configs do bash para root
├── .ssh/                    # Chaves SSH do root
├── scripts/                 # Scripts administrativos
└── .history                 # Histórico de comandos
```

**Arquivos importantes:**
- `.bashrc` - Configurações do terminal do root
- `.ssh/authorized_keys` - Chaves públicas autorizadas

---

### `/etc` - **CENTRO DE CONTROLE**
Configurações do sistema (cuidado ao editar)

**Estrutura típica:**
```
/etc/
├── passwd                   # Usuários do sistema
├── shadow                   # Senhas criptografadas
├── group                    # Grupos de usuários
├── hosts                    # Mapeamento IP/nomes
├── fstab                    # Montagem automática
├── crontab                  # Tarefas agendadas
├── ssh/
│   └── sshd_config         # Configuração SSH
├── apache2/                 # Configurações Apache
├── nginx/                   # Configurações Nginx
└── systemd/                 # Configurações de serviços
```

**Arquivos críticos:**
- `hosts` - Mapear IPs para nomes
- `fstab` - Montagem automática de discos
- `passwd` - Lista de usuários
- `ssh/sshd_config` - Configuração do servidor SSH

---

### `/bin` - **COMANDOS ESSENCIAIS**
Binários básicos como ls, cp, mv (necessários para boot)

**Estrutura típica:**
```
/bin/
├── ls                       # Listar arquivos
├── cp                       # Copiar
├── mv                       # Mover/renomear
├── rm                       # Remover
├── cat                      # Mostrar conteúdo
├── grep                     # Buscar texto
├── bash                     # Shell bash
└── sh                       # Shell básico
```

**Comandos essenciais:**
- `ls`, `cp`, `mv`, `rm` - Manipulação de arquivos
- `cat`, `grep`, `find` - Visualização e busca
- `bash`, `sh` - Shells do sistema

---

### `/sbin` - **COMANDOS ADMINISTRATIVOS**
Binários de administração como mount, systemctl

**Estrutura típica:**
```
/sbin/
├── mount                    # Montar sistemas de arquivos
├── umount                   # Desmontar
├── ip                       # Configuração de rede
├── systemctl               # Gerenciar serviços
├── fdisk                   # Gerenciar partições
└── iptables                # Firewall
```

**Comandos administrativos:**
- `mount/umount` - Montar/desmontar dispositivos
- `systemctl` - Gerenciar serviços
- `ip` - Configuração de rede

---

### `/lib` - **BIBLIOTECAS ESSENCIAIS**
Código compartilhado necessário para programas básicos

**Estrutura típica:**
```
/lib/
├── libc.so.6               # Biblioteca C padrão
├── ld-linux.so.2           # Carregador dinâmico
├── modules/                # Módulos do kernel
│   └── 5.4.0-linux/       # Por versão do kernel
└── firmware/               # Firmware de dispositivos
```

**Bibliotecas importantes:**
- `libc.so.*` - Biblioteca C essencial
- `modules/` - Drivers do kernel
- `firmware/` - Firmware de hardware

---

### `/usr` - **PROGRAMAS INSTALADOS**
Software não-essencial e recursos do sistema

**Estrutura típica:**
```
/usr/
├── bin/                     # Comandos de usuário
├── sbin/                    # Comandos administrativos
├── lib/                     # Bibliotecas
├── share/                   # Dados compartilhados
│   ├── man/                # Páginas de manual
│   ├── doc/                # Documentação
│   └── applications/       # Atalhos de programas
├── local/                   # Software local
│   ├── bin/
│   ├── lib/
│   └── share/
└── src/                     # Código fonte
```

**Subdiretórios importantes:**
- `bin/` - Comandos não-essenciais
- `share/man/` - Páginas de manual (help)
- `local/` - Software compilado localmente

---

### `/boot` - **ARQUIVOS DE BOOT**
Kernel e arquivos necessários para inicialização

**Estrutura típica:**
```
/boot/
├── vmlinuz-5.4.0           # Kernel Linux
├── initrd.img-5.4.0        # Disco RAM inicial
├── config-5.4.0            # Configuração do kernel
├── System.map-5.4.0        # Mapa de símbolos
└── grub/                   # Bootloader GRUB
    └── grub.cfg            # Configuração do GRUB
```

**Arquivos críticos:**
- `vmlinuz-*` - Kernel do Linux
- `grub/grub.cfg` - Configuração do bootloader

---

### `/dev` - **DISPOSITIVOS**
Interface para hardware (discos, USB, etc.)

**Estrutura típica:**
```
/dev/
├── sda                     # Primeiro disco SATA
├── sda1                    # Primeira partição
├── sdb                     # Segundo disco
├── nvme0n1                 # Disco NVMe
├── tty1                    # Terminal virtual
├── pts/                    # Pseudo-terminais
├── null                    # "Buraco negro"
├── zero                    # Gerador de zeros
├── random                  # Gerador aleatório
└── input/                  # Dispositivos de entrada
```

**Dispositivos importantes:**
- `sda`, `sdb` - Discos rígidos
- `null` - Descarta dados
- `random` - Números aleatórios

---

### `/mnt` - **MONTAGEM TEMPORÁRIA**
Ponto para montar sistemas de arquivos manualmente

**Estrutura típica:**
```
/mnt/
├── usb/                    # Para pendrives
├── backup/                 # Para discos de backup
├── network/                # Para compartilhamentos
└── temp/                   # Para montagens temporárias
```

---

### `/media` - **MÍDIA REMOVÍVEL**
Montagem automática de pendrives, CDs, cartões SD

**Estrutura típica:**
```
/media/
├── usuario/
│   ├── USB_DISK/          # Pendrive
│   ├── KINGSTON_32GB/     # Cartão SD
│   └── Audio_CD/          # CD de áudio
└── cdrom -> /dev/sr0      # Link simbólico
```

---

### `/opt` - **SOFTWARE OPCIONAL**
Aplicações comerciais e de terceiros auto-contidas

**Estrutura típica:**
```
/opt/
├── google/
│   └── chrome/            # Google Chrome
├── discord/               # Discord
├── steam/                 # Steam
├── vmware/               # VMware
└── local/                # Software local da empresa
```

---

### `/proc` - **INFORMAÇÕES VIRTUAIS**
Interface para dados do kernel e processos (tempo real)

**Estrutura típica:**
```
/proc/
├── cpuinfo                # Informações da CPU
├── meminfo                # Informações de memória
├── version                # Versão do kernel
├── uptime                 # Tempo de funcionamento
├── loadavg                # Carga do sistema
├── 1234/                  # Processo PID 1234
│   ├── cmdline           # Linha de comando
│   ├── environ           # Variáveis de ambiente
│   └── status            # Status do processo
└── sys/                   # Configurações do kernel
```

**Arquivos importantes:**
- `cpuinfo` - Informações do processador
- `meminfo` - Uso de memória
- `uptime` - Há quanto tempo o sistema está rodando

---

### `/var` - **DADOS VARIÁVEIS**
Logs, cache, bancos de dados (muda durante operação)

**Estrutura típica:**
```
/var/
├── log/                    # Logs do sistema
│   ├── syslog             # Log geral
│   ├── auth.log           # Logs de autenticação
│   ├── apache2/           # Logs do Apache
│   └── mysql/             # Logs do MySQL
├── cache/                  # Cache de aplicações
├── lib/                    # Dados persistentes
│   ├── mysql/             # Bancos MySQL
│   └── postgresql/        # Bancos PostgreSQL
├── spool/                  # Filas (email, impressão)
├── tmp/                    # Temporários que persistem
└── www/                    # Conteúdo web (algumas distros)
```

**Subdiretórios críticos:**
- `log/` - Logs para troubleshooting
- `lib/mysql/` - Bancos de dados
- `cache/` - Cache de aplicações

---

### `/srv` - **DADOS SERVIDOS**
Conteúdo para serviços web, FTP, repositórios Git

**Estrutura típica:**
```
/srv/
├── www/                    # Sites web
│   ├── site1.com/
│   └── blog.empresa.com/
├── ftp/                    # Servidor FTP
│   ├── pub/               # Área pública
│   └── upload/            # Área de upload
├── git/                    # Repositórios Git
│   ├── projeto1.git/
│   └── projeto2.git/
└── samba/                  # Compartilhamentos
```

---

### `/tmp` - **ARQUIVOS TEMPORÁRIOS**
Espaço para arquivos que não precisam persistir

**Estrutura típica:**
```
/tmp/
├── .X11-unix/             # Sockets do X11
├── systemd-private-*/     # Namespaces do systemd
├── firefox_temp/          # Cache do Firefox
├── ssh-*/                 # Sockets SSH
└── programa.lock          # Arquivos de trava
```

**Características:**
- Limpo automaticamente no boot
- Todos os usuários podem escrever
- Arquivos temporários de programas

---

## 🎯 Prioridades para Iniciantes

### 🥇 **NÍVEL 1 - Dominar Primeiro (80% dos Problemas)**

#### `/home` - Sua Zona Segura
- **O que é:** Seus arquivos pessoais e configurações
- **Por que dominar:** Impossível quebrar o sistema aqui
- **Comandos essenciais:**
  ```bash
  cd ~                    # Voltar para casa
  ls -la                  # Ver arquivos ocultos também
  du -h ~ | sort -hr      # Ver o que ocupa mais espaço
  ```

#### `/etc` - Centro de Controle
- **O que é:** Configurações do sistema inteiro
- **Por que dominar:** Você vai editar configs constantemente
- **⚠️ SEMPRE fazer backup:** `sudo cp arquivo arquivo.backup`
- **Arquivos críticos:**
  ```bash
  /etc/hosts              # Mapear IPs para nomes
  /etc/fstab              # Montagem automática de discos
  /etc/ssh/sshd_config    # Configuração SSH
  ```

#### `/var/log` - Detective do Sistema
- **O que é:** Logs para diagnosticar problemas
- **Por que dominar:** Primeira parada quando algo quebra
- **Comandos de investigação:**
  ```bash
  sudo tail -f /var/log/syslog           # Log geral em tempo real
  sudo grep -i "error" /var/log/syslog   # Buscar erros
  sudo journalctl --since today          # Logs de hoje
  ```

---

## 🚨 Resolução de Problemas - 80% dos Casos

### **🔥 Sistema Lento/Travando**
```bash
# 1. Ver erros recentes
sudo tail -100 /var/log/syslog | grep -i error

# 2. Verificar uso de espaço
df -h

# 3. Ver processos pesados
top
```

### **🔒 Não Consegue Fazer Login**
```bash
# 1. Ver tentativas de login
sudo tail -50 /var/log/auth.log

# 2. Buscar senhas falhadas
sudo grep "Failed password" /var/log/auth.log

# 3. Verificar SSH (se remoto)
sudo systemctl status ssh
```

### **🌐 Internet/Rede Não Funciona**
```bash
# 1. Verificar configuração de rede
cat /etc/hosts
cat /etc/resolv.conf

# 2. Testar conectividade
ping google.com

# 3. Ver logs de rede
sudo journalctl -u NetworkManager
```

### **💾 Problemas de Disco/Partição**
```bash
# 1. Ver espaço disponível
df -h

# 2. Verificar montagens
mount | grep -v tmpfs

# 3. Ver erros de hardware
sudo dmesg | grep -i error
```

### **🖥️ Serviço Não Funciona**
```bash
# 1. Status do serviço
sudo systemctl status nome_servico

# 2. Ver logs específicos
sudo journalctl -u nome_servico -f

# 3. Reiniciar serviço
sudo systemctl restart nome_servico
```

---

## 💡 Dicas de Segurança

### ✅ **Sempre Seguro:**
- Qualquer coisa em `/home` - é seu território
- Ler arquivos em `/var/log` - somente leitura
- Explorar `/proc` - tudo é virtual

### ⚠️ **Cuidado (Fazer Backup):**
- Editar arquivos em `/etc`
- Mexer em `/boot`
- Alterar permissões em `/dev`

### 🚫 **Evitar Completamente:**
- Deletar coisas em `/bin`, `/sbin`, `/lib`
- Mexer em `/proc` como root
- Modificar estrutura de `/usr` manualmente

---

## 🔧 Comandos de Navegação Essenciais

```bash
# Navegação básica
pwd                     # Onde estou?
ls -la                  # O que tem aqui? (incluindo ocultos)
cd /caminho            # Ir para local específico
cd ~                   # Voltar para casa

# Busca e localização
find /local -name "*nome*"     # Encontrar arquivos
which comando                  # Onde está o programa?
locate arquivo                 # Busca rápida (se disponível)

# Informações do sistema
df -h                   # Espaço em disco
du -h pasta            # Tamanho de pasta
ps aux                 # Processos rodando
free -h                # Uso de memória
```

Para mais comandos informações de navegação iniciais, acesse [Comandos indispensáveis](./Comandos%20indispensáveis.md)

## 📚 Próximos Passos

Depois de dominar `/home`, `/etc` e `/var/log`, explore gradualmente:

1. **`/tmp`** - Para experimentos e scripts
2. **`/dev`** - Para entender dispositivos
3. **`/usr/bin`** - Para localizar programas
4. **`/proc`** - Para monitoramento avançado

**Lembre-se:** O Linux é seu amigo, não tenha medo de explorar, apenas faça backups antes de mexer em configurações importantes!
