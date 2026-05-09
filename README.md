link repositorio: https://github.com/Liedsondeve/ACE8
# Plano de Aula: Projeto de Extensão

**Título do Minicurso:** Introdução ao Linux e Terminal: Da interface gráfica a linha de comando  
**Carga Horária Total:** 4 horas (aproximadamente)

---

## 1. Objetivos de Aprendizagem
Ao final deste minicurso, o aluno deverá ser capaz de:
* Compreender o que é o sistema operacional Linux e sua importância no mercado de tecnologia (servidores e desenvolvimento).
* Navegar com confiança pela interface gráfica de distribuições amigáveis (Ubuntu ou Linux Mint).
* Operar o terminal do Linux para executar tarefas fundamentais de navegação, manipulação de diretórios e arquivos.
* Compreender e aplicar permissões básicas de execução de arquivos.
* Instalar pacotes e programas utilizando o gerenciador de pacotes via linha de comando.

---

## 2. Pré-requisitos
* Conhecimentos básicos de informática (uso de mouse, teclado e navegação na internet).
* Computador com sistema operacional Ubuntu ou Linux Mint (pode ser instalado nativamente, via Máquina Virtual ou WSL - Windows Subsystem for Linux).

---

## 3. Tópicos Abordados
* **Conceitos Básicos:** O que é Linux, diferença entre Kernel e SO, distribuições e uso no mercado.
* **Interface Gráfica:** Navegador de arquivos e instalação visual de programas.
* **Informações do Sistema e Usuário:** `uname`, `whoami`.
* **Comandos de Navegação:** `pwd`, `ls`, `cd`.
* **Manipulação de Texto e Saída:** `grep`, `echo`.
* **Manipulação de Arquivos e Diretórios:** `mkdir`, `touch`, `cp`, `mv`, `rm`.
* **Visualização e Edição de Texto:** `cat`, `nano`.
* **Permissões Básicas:** `chmod`.
* **Gerenciamento de Pacotes:** `apt install`.
* **Outros comandos:** `clear`, `find`.

---

## 4. Metodologia de Ensino
O minicurso adotará uma abordagem ativa e pragmática, dividida em quatro momentos:
1. **Exposição breve dialogada:** Apresentação de conceitos fundamentais com apoio visual, focando na motivação e no "porquê" de aprender a ferramenta.
2. **Demonstração prática:** O aluno-extensionista demonstrará o uso do terminal explicando a sintaxe e o retorno de cada comando.
3. **Exercícios guiados:** Os alunos executarão os comandos em suas próprias máquinas, acompanhando o professor passo a passo.
4. **Aprendizagem Baseada em Projetos (Desafio):** Resolução de um cenário prático e autônomo, no qual o aluno precisa integrar os conhecimentos adquiridos para entregar um resultado funcional.

---

## 5. Recursos Necessários
* Computadores pessoais dos alunos.
* Acesso à internet para a instalação de pacotes (`apt`).

---

## 6. Cronograma da Aula

| Etapa | Duração | Atividade e Conteúdo |
| :--- | :--- | :--- |
| **Introdução ao tema** | 30 min | **Conceitos e Motivação:** Apresentação teórica rápida. O que é o Linux, ecossistema de distribuições (foco em Ubuntu/Mint), por que é o padrão em servidores. Demonstração rápida da Interface Gráfica (arquivos e loja de apps). |
| **Demonstração prática** | 70 min | **Uso da ferramenta (Terminal):** O professor abre o terminal e demonstra, bloco por bloco, os comandos fundamentais. Explica a sintaxe de navegação (`pwd`, `ls`, `cd`), criação e manipulação (`mkdir`, `touch`, `cp`, `mv`, `rm`), leitura/edição (`cat`, `nano`), permissões (`chmod`) e instalação (`apt`). |
| **Exercícios guiados** | 80 min | **Prática supervisionada:** Os alunos abrem seus terminais. O professor dita pequenas missões (ex: "Criem uma pasta chamada 'teste'", "Entrem nela", "Criem um arquivo de texto", "Apaguem o arquivo"). |
| **Desafio ou projeto curto** | 60 min | **Consolidação do aprendizado:** Os alunos recebem um desafio prático sem o passo a passo na tela. Missão: Criar via terminal a estrutura de um projeto web. Devem criar uma pasta `meu_site`, dentro dela criar as pastas `css` e `js`, criar o arquivo `index.html`, abri-lo com o nano, escrever um título, salvar, instalar o pacote `tree` via `apt install` e rodar o comando para visualizar a árvore de diretórios criada. |
