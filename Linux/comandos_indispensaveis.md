# Guia Prático - Comandos Essenciais do Terminal Linux

Este guia apresenta os comandos fundamentais do terminal Linux de forma prática e objetiva. Se você está começando no mundo Linux, estes são os comandos que resolvem 90% das tarefas básicas do dia a dia.

**Objetivo:** Te dar confiança para navegar, criar, editar e gerenciar arquivos no terminal Linux sem medo.

---

## 🧭 Comandos de Orientação - "Onde Estou?"

| Comando    | O que faz                                                 | Exemplo                        |
| ---------- | --------------------------------------------------------- | ------------------------------ |
| `whoami`   | **QUEM SOU EU** - Mostra seu nome de usuário              | `whoami` → `joao`              |
| `hostname` | **NOME DO COMPUTADOR** - Mostra o nome da máquina         | `hostname` → `meu-laptop`      |
| `pwd`      | **ONDE ESTOU** - Mostra o caminho completo da pasta atual | `pwd` → `/home/joao/Documents` |

### 🎯 **Para que serve:**

Quando você abrir o terminal e não souber onde está ou se o prompt não mostrar informações claras.

---

## 👀 Comandos de Visualização - "O que tem aqui?"

| Comando   | O que faz                                                      | Quando usar                 |
| --------- | -------------------------------------------------------------- | --------------------------- |
| `ls`      | **LISTAR ARQUIVOS** - Mostra o que tem na pasta                | Ver conteúdo básico         |
| `ls -l`   | **LISTAGEM DETALHADA** - Mostra permissões, tamanho, data      | Preciso de mais informações |
| `ls -a`   | **MOSTRAR OCULTOS** - Inclui arquivos que começam com `.`      | Ver configurações ocultas   |
| `ls -la`  | **TUDO DETALHADO** - Combina listagem longa + arquivos ocultos | Investigação completa       |
| `ls -lah` | **TAMANHOS LEGÍVEIS** - Adiciona tamanhos em K, M, G           | Verificar espaço usado      |

### 📖 **Como ler o `ls -l`:**

```
drwxr-xr-x 2 joao joao 4096 Jan 15 10:30 pasta/
-rw-r--r-- 1 joao joao  142 Jan 15 09:15 arquivo.txt
```

- **Primeiro caractere:** `d` = pasta, `-` = arquivo, `l` = link
- **Resto:** permissões, links, dono, grupo, tamanho, data, nome

### 💡 **Símbolos especiais:**

- `.` = pasta atual
- `..` = pasta pai (uma acima)
- Arquivos com `.` no início = ocultos

---

## 📄 Comandos de Leitura - "O que tem dentro?"

| Comando            | O que faz                                                | Exemplo              |
| ------------------ | -------------------------------------------------------- | -------------------- |
| `cat arquivo.txt`  | **LER ARQUIVO COMPLETO** - Mostra todo o conteúdo        | `cat lista.txt`      |
| `head arquivo.txt` | **PRIMEIRAS LINHAS** - Mostra início do arquivo          | `head -10 log.txt`   |
| `tail arquivo.txt` | **ÚLTIMAS LINHAS** - Mostra final do arquivo             | `tail -20 log.txt`   |
| `less arquivo.txt` | **NAVEGAÇÃO INTERATIVA** - Ver arquivo grande com scroll | `less documento.txt` |

### 🔍 **Dica importante:**

No Linux, **extensão não define tipo de arquivo**. O sistema reconhece pelo conteúdo, não pelo nome.

---

## ✏️ Comandos de Criação e Edição

### **Criar Arquivos:**

| Comando                   | O que faz                                       | Exemplo                      |
| ------------------------- | ----------------------------------------------- | ---------------------------- |
| `touch arquivo`           | **CRIAR ARQUIVO VAZIO** - Cria novo arquivo     | `touch lista_compras.txt`    |
| `echo "texto" > arquivo`  | **CRIAR COM CONTEÚDO** - Cria arquivo com texto | `echo "maçã" > lista.txt`    |
| `echo "texto" >> arquivo` | **ADICIONAR TEXTO** - Anexa ao final do arquivo | `echo "banana" >> lista.txt` |

### **Editar Arquivos:**

| Comando        | O que faz                                             | Como usar        |
| -------------- | ----------------------------------------------------- | ---------------- |
| `nano arquivo` | **EDITOR SIMPLES** - Abre editor de texto no terminal | `nano lista.txt` |

#### 🖊️ **Usando o nano:**

- Navegue com as setas
- Digite normalmente
- `Ctrl + X` = sair
- `Y` = confirmar salvamento
- `Enter` = confirmar nome do arquivo

---

## 📁 Comandos de Gerenciamento de Arquivos

### **Copiar e Mover:**

| Comando                 | O que faz                              | Exemplo                    |
| ----------------------- | -------------------------------------- | -------------------------- |
| `cp origem destino`     | **COPIAR ARQUIVO** - Faz uma cópia     | `cp lista.txt backup.txt`  |
| `cp -r pasta/ destino/` | **COPIAR PASTA** - Copia pasta inteira | `cp -r projeto/ backup/`   |
| `mv origem destino`     | **MOVER/RENOMEAR** - Move ou renomeia  | `mv lista.txt compras.txt` |

### **Deletar:**

| Comando        | O que faz                                    | ⚠️ Cuidado                |
| -------------- | -------------------------------------------- | ------------------------- |
| `rm arquivo`   | **DELETAR ARQUIVO** - Remove permanentemente | **Não vai para lixeira!** |
| `rm -r pasta/` | **DELETAR PASTA** - Remove pasta e conteúdo  | **Não tem volta!**        |

### 🚨 **ATENÇÃO:**

- `rm` **deleta permanentemente** - não vai para lixeira
- **Sempre confirme** o que está deletando
- **Faça backup** de coisas importantes antes

---

## 📚 Comandos de Ajuda - "Como funciona?"

| Comando          | O que faz                                       | Exemplo     |
| ---------------- | ----------------------------------------------- | ----------- |
| `comando --help` | **AJUDA RÁPIDA** - Opções principais do comando | `ls --help` |
| `man comando`    | **MANUAL COMPLETO** - Documentação detalhada    | `man cp`    |

### 📖 **Navegando no `man`:**

- `Espaço` = próxima página
- `q` = sair
- `/palavra` = buscar palavra
- `n` = próxima ocorrência da busca

---

## 🎯 Comandos para 90% das Situações

### **🔰 Iniciante Absoluto (primeiro dia):**

```bash
pwd                    # Onde estou?
ls                     # O que tem aqui?
cd pasta              # Ir para pasta
cd ..                 # Voltar uma pasta
cd ~                  # Ir para home
```

### **📝 Trabalhando com Arquivos:**

```bash
touch arquivo.txt      # Criar arquivo
nano arquivo.txt       # Editar arquivo
cat arquivo.txt        # Ler arquivo
cp arquivo.txt backup.txt    # Fazer backup
```

### **🔧 Organização:**

```bash
ls -la                       # Ver tudo com detalhes
mv arquivo.txt nova_pasta/   # Mover arquivo
rm arquivo_velho.txt         # Deletar arquivo
cp -r pasta/ backup/         # Backup de pasta inteira
```

---

## 🛡️ Dicas de Segurança e Boas Práticas

### ✅ **Sempre Seguro:**

- `ls`, `pwd`, `whoami`, `cat` - apenas lêem informações
- `cd` - apenas navega, não modifica nada
- Trabalhar na sua pasta `/home/usuario`

### ⚠️ **Cuidado (fazer backup primeiro):**

- `rm` - deleta permanentemente
- `mv` - pode sobrescrever arquivos
- `echo "texto" >` - sobrescreve arquivo existente

### 🚫 **Evitar como iniciante:**

- `rm -rf /` - **NUNCA DIGITE ISSO** (você vai destruir todo seu sistema, é comum distriuições terem travas contra isso, mas melhor evitar)
- `sudo rm` - deletar como administrador
- Editar arquivos fora da sua pasta pessoal

---

## 🔄 Fluxo de Trabalho Típico

### **📊 Exploração (quando chegar em lugar novo):**

```bash
pwd     # Onde estou?
ls -la  # O que tem aqui?
cat arquivo_interessante.txt    # Vamos ver o conteúdo
```

### **✏️ Criação de Conteúdo:**

```bash
touch meu_projeto.txt  # Criar arquivo
nano meu_projeto.txt   # Editar
cat meu_projeto.txt    # Conferir resultado
```

### **🗂️ Organização:**

```bash
cp projeto.txt projeto_backup.txt    # Backup
mkdir projetos                       # Criar pasta
mv projeto.txt projetos/            # Organizar
```

---

## 🚀 Próximos Passos

Depois de dominar estes comandos básicos, explore:

1. **Navegação avançada:** `find`, `locate`, `which`
2. **Manipulação de texto:** `grep`, `sort`, `cut`
3. **Monitoramento:** `ps`, `top`, `df`
4. **Compressão:** `tar`, `zip`, `unzip`
5. **Rede:** `ping`, `curl`, `wget`

**Lembre-se:** Pratique um comando por vez. O terminal Linux é poderoso, mas não é complicado, apenas diferente do que você pode estar acostumado!

## 📄 Conheça mais

- [Diretórios e pastas essenciais no linux](./Diretórios%20e%20pastas%20essenciais.md)
