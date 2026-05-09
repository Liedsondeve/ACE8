# 🧩 Exercícios e Desafios — Linux e Terminal

**Minicurso ACE 8 | CPTA156 | Ciência da Computação**

---

> **Como usar este documento**  
> Os exercícios estão organizados em 4 blocos progressivos.  
> Cada bloco termina com uma **dica** caso você trave.  
> O Bloco 4 é o **Desafio Final** — tente resolver sem consultar o guia!

---

## 🟦 Bloco 1 — Navegação e Exploração (30 min)

**Objetivo:** Se familiarizar com o sistema de arquivos e os comandos básicos de navegação.

### Exercício 1.1 — Onde estou?

1. Abra o terminal
2. Descubra em qual diretório você está
3. Liste o conteúdo do diretório, mostrando arquivos ocultos e detalhes
4. Navegue até `/etc` e liste apenas os arquivos que comecem com a letra `h`

```bash
# Escreva aqui seus comandos:



```

**Resultado esperado:** Você deve ver uma listagem de arquivos como `hosts`, `hostname`, `hosts.allow`, etc.

---

### Exercício 1.2 — Explorando a árvore

1. A partir de qualquer diretório, navegue até `/var/log`
2. Descubra qual é o maior arquivo do diretório (`ls -lhS` ordena por tamanho)
3. Exiba as 10 primeiras linhas desse arquivo
4. Volte para sua pasta pessoal com **um único comando**

```bash
# Escreva aqui seus comandos:



```

> 💡 **Dica:** `cd ~` leva você direto para home a partir de qualquer lugar.

---

### Exercício 1.3 — Histórico e autocomplete

1. Pressione `↑` no teclado várias vezes e observe o histórico de comandos
2. Digite `ls /et` e pressione `Tab` — o shell deve completar automaticamente
3. Use `Ctrl+R` e comece a digitar `cd` para buscar um comando antigo no histórico

---

## 🟩 Bloco 2 — Criação e Manipulação (30 min)

**Objetivo:** Criar uma estrutura de projeto completa usando apenas o terminal.

### Exercício 2.1 — Estrutura de projeto

Crie a seguinte estrutura de diretórios e arquivos **usando apenas comandos do terminal** (sem interface gráfica):

```
projeto_ace8/
├── README.md
├── src/
│   ├── main.py
│   └── utils/
│       └── helpers.py
├── docs/
│   └── instrucoes.txt
└── tests/
    └── test_main.py
```

```bash
# Escreva aqui seus comandos:



```

**Verificação:**

```bash
# Use este comando para confirmar a estrutura
find projeto_ace8/ -type f
```

---

### Exercício 2.2 — Conteúdo nos arquivos

1. Adicione o texto `# Projeto ACE 8` ao `README.md`
2. Adicione a linha `print("Olá, mundo!")` ao `src/main.py`
3. Adicione a linha `# Funções auxiliares` ao `src/utils/helpers.py`
4. Verifique o conteúdo dos arquivos com `cat`

```bash
# Escreva aqui seus comandos:



```

---

### Exercício 2.3 — Copiar e organizar

1. Faça um backup do `README.md` chamado `README_backup.md`
2. Crie um diretório `backup/` dentro de `projeto_ace8/`
3. Mova o arquivo de backup para dentro de `backup/`
4. Liste o conteúdo de `backup/` para confirmar

```bash
# Escreva aqui seus comandos:



```

> 💡 **Dica:** Lembre-se de `cp` para copiar e `mv` para mover.

---

## 🟨 Bloco 3 — Permissões, Processos e Pipes (30 min)

**Objetivo:** Dominar permissões de arquivo, gerenciamento de processos e o poder dos pipes.

### Exercício 3.1 — Criando e executando um script

1. Crie um arquivo chamado `ola.sh` com o seguinte conteúdo:

```bash
#!/bin/bash
echo "Olá! Hoje é $(date)"
echo "Você está em: $(pwd)"
echo "Usuário: $(whoami)"
```

1. Tente executar com `./ola.sh` — o que acontece?
2. Corrija o problema com `chmod` e execute novamente
3. Verifique as permissões com `ls -l ola.sh`

```bash
# Escreva aqui seus comandos:



```

**Resultado esperado após chmod:**

```
-rwxr-xr-x 1 usuario grupo 85 Jan  1 10:00 ola.sh
```

---

### Exercício 3.2 — Pipes e filtros

1. Liste todos os processos em execução e filtre apenas os que contêm "bash" no nome
2. Conte quantas linhas tem o arquivo `/etc/passwd`
3. Liste os arquivos do seu projeto e salve a listagem em `listagem.txt`
4. Mostre apenas as 3 últimas linhas de `listagem.txt`

```bash
# Escreva aqui seus comandos:



```

---

### Exercício 3.3 — Buscas avançadas

1. Dentro do diretório `projeto_ace8/`, encontre todos os arquivos com extensão `.py`
2. Busque a palavra `Olá` dentro de todos os arquivos do projeto (recursivo)
3. Encontre arquivos criados nas últimas 2 horas
4. Mostre onde o Python3 está instalado no sistema

```bash
# Escreva aqui seus comandos:



```

> 💡 **Dica para 3.3-item 2:** `grep -r "Olá" ./projeto_ace8/`

---

## 🏆 Bloco 4 — Desafio Final (20–30 min)

**Objetivo:** Simular a resposta a um incidente de infraestrutura. Você receberá as "regras de negócio" e precisará traduzi-las para os comandos corretos do Linux.

### Desafio Único: Resposta a Incidente (Incident Response)

Sua equipe detectou instabilidade em um servidor web. Sua missão é criar um ambiente isolado, simular os logs, extrair os dados críticos e trancar o relatório gerado por questões de segurança.

**Requisitos da Missão:**

1. **Isolamento:** Crie um diretório chamado `incidente_01` e entre nele.
2. **Geração de Dados:** Crie um arquivo chamado `server.log`. Insira dentro dele, no mínimo, 4 linhas de texto simulando logs. Duas dessas linhas devem obrigatoriamente conter a palavra `ERRO` e as outras duas a palavra `INFO`.
3. **Extração:** Analise o arquivo `server.log` e extraia **apenas** as linhas que relatam erros. Salve esse resultado em um novo arquivo chamado `relatorio_falhas.txt`.
4. **Assinatura:** Adicione ao final do arquivo `relatorio_falhas.txt` a frase "Analise concluida" **sem apagar** as linhas de erro que você acabou de inserir lá.
5. **Segurança (Trancar arquivo):** O arquivo `relatorio_falhas.txt` contém dados sensíveis do cliente. Altere as permissões dele para que **absolutamente ninguém** além do dono tenha acesso. Além disso, o próprio dono deve ter **apenas permissão de leitura** (ele não pode editar nem executar o arquivo).
6. **Validação:** Liste os arquivos do diretório de forma detalhada para provar que a permissão foi aplicada corretamente e exiba o conteúdo final do relatório na tela.

---

## ✅ Gabarito — Comandos Principais

*(Dica para o instrutor: Deixe os alunos quebrarem a cabeça consultando o guia antes de mostrar as respostas)*

<details>
<summary>Clique para ver as respostas do Bloco 1</summary>

```bash
# 1.1
pwd
ls -la
cd /etc && ls -l h*

# 1.2
cd /var/log
ls -lhS
head $(ls -S | head -1)
cd ~
```

</details>

<details>
<summary>Clique para ver as respostas do Bloco 2</summary>

```bash
# 2.1
mkdir -p projeto_ace8/src/utils projeto_ace8/docs projeto_ace8/tests
touch projeto_ace8/README.md
touch projeto_ace8/src/main.py projeto_ace8/src/utils/helpers.py
touch projeto_ace8/docs/instrucoes.txt projeto_ace8/tests/test_main.py

# 2.2
echo "# Projeto ACE 8" > projeto_ace8/README.md
echo 'print("Olá, mundo!")' > projeto_ace8/src/main.py
echo "# Funções auxiliares" > projeto_ace8/src/utils/helpers.py
```

</details>

<details>
<summary>Clique para ver as respostas do Bloco 3</summary>

```bash
# 3.1 — problema: arquivo sem permissão de execução
nano ola.sh  # (colar o conteúdo)
./ola.sh     # Permission denied
chmod +x ola.sh
./ola.sh     # funciona!

# 3.2
ps aux | grep bash
wc -l /etc/passwd
ls -la projeto_ace8/ > listagem.txt
tail -3 listagem.txt

# 3.3
find projeto_ace8/ -name "*.py"
grep -r "Olá" ./projeto_ace8/
find . -mmin -120
which python3
```

</details>

<details>
<summary>Clique para ver as respostas do Bloco 4 (Desafio Final)</summary>

```bash
# 1. Isolamento
mkdir incidente_01
cd incidente_01

# 2. Geração de Dados (alunos podem usar nano, touch ou echo)
echo "INFO: Servidor web iniciado" > server.log
echo "ERRO: Banco de dados caiu" >> server.log
echo "INFO: Usuario logado" >> server.log
echo "ERRO: Falha de memoria" >> server.log

# 3. Extração (exige entender grep e redirecionamento >)
grep "ERRO" server.log > relatorio_falhas.txt

# 4. Assinatura (exige entender o append >>)
echo "Analise concluida" >> relatorio_falhas.txt

# 5. Segurança (exige calcular octal: r-------- = 400)
chmod 400 relatorio_falhas.txt

# 6. Validação
ls -la
cat relatorio_falhas.txt
```

</details>

---

*Bom trabalho! O terminal é uma ferramenta poderosa — quanto mais você usa, mais rápido fica. 🐧*
