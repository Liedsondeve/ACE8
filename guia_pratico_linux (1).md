# 🐧 Guia Prático — Linux e Terminal
**Minicurso ACE 8 | CPTA156 | Ciência da Computação**

---

## Pré-requisitos

- Ter acesso a um terminal Linux ou macOS  
- Alternativa: usar o [Play with Docker](https://labs.play-with-docker.com/) ou instalar o WSL (Windows Subsystem for Linux) no Windows  
- Nenhum conhecimento prévio de terminal é exigido

---

## Módulo 1 — Introdução ao Terminal

O **terminal** (ou shell) é uma interface de texto que permite interagir diretamente com o sistema operacional. O shell mais comum é o **Bash** (Bourne Again Shell).

Ao abrir o terminal, você verá algo assim:

```
usuario@maquina:~$
```

Isso é chamado de **prompt**. Ele indica:
- `usuario` → seu nome de usuário
- `maquina` → nome do computador
- `~` → diretório atual (`~` representa sua pasta pessoal `/home/usuario`)
- `$` → você está como usuário comum (`#` significa root/administrador)

### Seu primeiro comando

```bash
echo "Olá, Linux!"
```

O comando `echo` imprime texto na tela. Simples assim.

---

## Módulo 2 — Navegação no Sistema de Arquivos

O sistema de arquivos Linux é organizado em uma **árvore de diretórios** com raiz em `/`.

```
/
├── home/       ← pastas dos usuários
│   └── aluno/
├── etc/        ← arquivos de configuração do sistema
├── var/        ← logs, dados variáveis
├── tmp/        ← arquivos temporários
├── usr/        ← programas instalados
└── bin/        ← comandos básicos do sistema
```

### Comandos essenciais de navegação

| Comando | O que faz |
|--------|-----------|
| `pwd` | Mostra o diretório atual |
| `ls` | Lista arquivos e pastas |
| `ls -la` | Lista com detalhes e arquivos ocultos |
| `ls -lh` | Lista com tamanhos legíveis (KB, MB) |
| `cd /caminho` | Entra em um diretório |
| `cd ..` | Volta ao diretório pai |
| `cd ~` | Vai direto para a pasta pessoal |
| `cd -` | Volta ao diretório anterior |

### Pratique agora

```bash
# Onde estou?
pwd

# O que tem aqui?
ls -la

# Explorando o sistema
cd /etc
ls
cd ~

# Listando com detalhes
ls -lh
```

---

## Módulo 3 — Criação e Manipulação de Arquivos

### Criar diretórios e arquivos

```bash
# Criar um diretório
mkdir meu_projeto

# Criar diretórios aninhados de uma vez
mkdir -p meu_projeto/src/utils

# Criar um arquivo vazio
touch README.md

# Criar arquivo e escrever conteúdo
echo "# Meu Projeto" > README.md

# Acrescentar conteúdo sem apagar o que já existe
echo "Descrição do projeto." >> README.md
```

### Visualizar conteúdo de arquivos

```bash
# Exibe todo o conteúdo na tela. Use cat -n para numerar linhas
cat arquivo.txt

# Navega pelo arquivo página a página — ideal para arquivos grandes (q = sair)
less arquivo.txt

# Mostra as primeiras N linhas (padrão: 10)
head -n 20 arq.txt

# Mostra as últimas N linhas (padrão: 10)
tail -n 20 arq.txt

# Acompanha o arquivo em tempo real — essencial para monitorar logs
tail -f /var/log/syslog

# wc - Conta linhas, palavras ou bytes
wc -l arquivo.txt   # conta linhas
wc -w arquivo.txt   # conta palavras
wc -c arquivo.txt   # conta bytes
```

### Copiar, mover e remover

```bash
# ----- cp (Copiar) -----
# Copia um arquivo com novo nome no mesmo diretório
cp relatorio.txt relatorio_bak.txt

# Copia para outro diretório mantendo o nome original
cp relatorio.txt /home/user/docs/

# Copia diretório inteiro recursivamente (-r é obrigatório)
cp -r projeto/ projeto_backup/

# Pergunta antes de sobrescrever — evita perda acidental
cp -i orig.txt dest.txt

# ----- mv (Mover / Renomear) -----
# Renomeia o arquivo
mv old.txt new.txt

# Move para outro diretório
mv arq.txt docs/

# Confirma antes de sobrescrever
mv -i src dest

# ----- rm (Remover) -----
# Remove arquivo (sem recuperação)
rm arquivo.txt

# Pede confirmação antes de remover
rm -i arquivo.txt

# Remove diretório e todo conteúdo
rm -rf pasta/
```

> ⚠️ **Atenção:** No Linux não existe "lixeira" no terminal. `rm` é permanente.

---

## Módulo 4 — Permissões de Arquivos

Todo arquivo no Linux possui três tipos de permissão para três grupos de usuários:

```
-rwxr-xr--
│└┬┘└┬┘└┬┘
│  │   │   └─ outros (others): r-- = leitura
│  │   └───── grupo  (group):  r-x = leitura e execução
│  └───────── dono   (user):   rwx = leitura, escrita e execução
└──────────── tipo: - = arquivo, d = diretório, l = link
```

### Notação octal

| Permissão | Valor |
|-----------|-------|
| `r` (leitura) | 4 |
| `w` (escrita) | 2 |
| `x` (execução) | 1 |

Exemplos:
- `chmod 755` → dono tem tudo (7=4+2+1), grupo e outros têm leitura+execução
- `chmod 644` → dono lê e escreve (6=4+2), outros só leem

### Comandos de permissão

```bash
# Ver permissões
ls -l

# ----- chmod — Modo Octal -----
chmod 755 script.sh       # Scripts e executáveis
chmod 644 arquivo.txt     # Arquivos comuns (docs)
chmod 600 key.pem         # Chaves SSH, dados sensíveis
chmod 777 publico/        # Todos podem tudo — evite!
chmod 400 dados.txt       # Somente leitura pelo dono

# ----- chmod — Modo Simbólico -----
chmod u+x script.sh       # Dono: adiciona execução
chmod g-w arquivo.txt     # Grupo: remove escrita
chmod o+r dados.txt       # Outros: adiciona leitura
chmod a+r config.txt      # Todos: adiciona leitura
chmod ug=rw arq.txt       # Define exato para dono e grupo

# ----- chown — Mudar proprietário -----
chown alice arq.txt       # Muda dono para alice
chown alice:devs arq.txt  # Muda dono e grupo
chown -R alice pasta/     # Aplica recursivamente

# ----- sudo — Executar como root -----
sudo chmod 600 /etc/ssh/key  # Altera arquivos do sistema
sudo chown root config.txt   # Transfere para root
sudo !!                      # Repete último comando como root
```

---

## Módulo 5 — Processos

```bash
# Lista todos os processos em execução
ps aux

# Monitor interativo de processos
top
# (ou htop, se instalado: sudo apt install htop)

# Encontrar o PID de um processo
pgrep firefox

# Encerrar processo pelo PID
kill 1234

# Forçar encerramento (use com cautela)
kill -9 1234

# Executar em background (libera o terminal)
sleep 30 &

# Ver processos em background
jobs

# Trazer processo para foreground
fg %1

# Suspender processo atual (Ctrl+Z) e colocar em background
bg
```

---

## Módulo 6 — Pipes e Redirecionamento

O **pipe** (`|`) encadeia a saída de um comando na entrada do próximo. É uma das ferramentas mais poderosas do terminal.

```bash
# Listar e filtrar apenas arquivos .py
ls -la | grep '.py'

# Contar quantos arquivos existem no diretório
ls | wc -l

# Ver processos e filtrar pelo nome
ps aux | grep python

# Ver as 5 primeiras linhas de um arquivo longo
cat /etc/passwd | head -5

# Ordenar um arquivo e remover duplicatas
sort nomes.txt | uniq

# Redirecionar saída para arquivo
ls -la > listagem.txt

# Acrescentar ao arquivo
echo "nova linha" >> listagem.txt

# Combinar tudo: buscar erros nos logs e salvar
grep "ERROR" /var/log/syslog | tail -20 > erros_recentes.txt
```

---

## Módulo 7 — Busca e Filtro de Texto

```bash
# Buscar texto dentro de arquivos
grep "palavra" arquivo.txt

# Busca recursiva em diretórios (muito útil para projetos!)
grep -r "def main" ./src/

# Busca ignorando maiúsculas/minúsculas
grep -i "erro" log.txt

# Mostra número da linha onde aparece o padrão
grep -n "TODO" *.py

# Encontrar arquivos por nome
find . -name "*.txt"

# Encontrar arquivos modificados nas últimas 24h
find . -mtime -1

# Encontrar arquivos maiores que 10MB
find / -size +10M

# Localizar um programa instalado
which python3
whereis python3
```

---

---

## Referência Rápida — Atalhos do Terminal

| Atalho | Ação |
|--------|------|
| `Tab` | Autocomplete de comandos e arquivos |
| `↑` / `↓` | Navega pelo histórico |
| `Ctrl+C` | Cancela o comando atual |
| `Ctrl+Z` | Suspende o processo (pausa) |
| `Ctrl+L` | Limpa a tela |
| `Ctrl+A` | Move cursor para o início da linha |
| `Ctrl+E` | Move cursor para o fim da linha |
| `Ctrl+R` | Busca no histórico de comandos |
| `!!` | Repete o último comando |
| `!grep` | Repete o último comando que começa com `grep` |

---

## Recursos para continuar aprendendo

- **man** `<comando>` — manual do próprio sistema
- [tldr.sh](https://tldr.sh) — versão simplificada dos manuais
- [explainshell.com](https://explainshell.com) — explica qualquer comando visualmente
- [The Linux Command Line (livro gratuito)](https://linuxcommand.org/tlcl.php)
- `vimtutor` — tutorial interativo do editor Vim no próprio terminal
