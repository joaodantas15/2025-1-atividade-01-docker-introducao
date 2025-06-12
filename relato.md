**Relatório de Atividade Prática: Introdução ao Docker**

**Disciplina: Sistemas Operacionais (S.O. 2025.1)**
**Professor:** Leonardo A. Minora 
 **Aluno:** João Pedro Dantas Magalhães
Instituição: IFRN - Campus Natal-Central Data: 10 de Junho de 2025
**Observação** Não consegui instalar o Docker na minha máquina então precisei utilizar a máquina do meu irmão Raúl (por isso o nome na imagem, referente ao usuário) Também anexei a imagem de erro da instalação do Docker. 

**1. Objetivo**
O objetivo desta atividade foi aplicar os conceitos fundamentais da plataforma Docker para criar um ambiente de execução isolado (contêiner) para uma aplicação Python simples, compreendendo na prática o ciclo de vida básico de uma imagem e um contêiner.

**2. Metodologia e Procedimentos**
Para alcançar o objetivo proposto, a seguinte sequência de passos foi executada:
Configuração do Ambiente: Realização de um "fork" do repositório da disciplina para a conta pessoal do aluno no GitHub e clonagem para o ambiente de desenvolvimento local.
Criação da Aplicação: Desenvolvimento de um script Python (app.py) com a funcionalidade de imprimir a string "Olá, Docker!" no console.
Definição do Contêiner (Dockerfile): Criação de um arquivo Dockerfile para especificar as instruções de construção da imagem Docker. As diretivas utilizadas foram:
FROM python:3.9-slim: Para utilizar uma imagem base oficial do Python, otimizada em tamanho.
COPY app.py /app.py: Para copiar o script da aplicação para dentro do sistema de arquivos da imagem.
CMD ["python", "/app.py"]: Para definir o comando padrão a ser executado na inicialização do contêiner.
Construção da Imagem Docker: Utilizando o terminal no diretório do projeto, a imagem foi construída e nomeada (taggeada) como python-app através do comando:
 Bash
docker build -t python-app .


Execução do Contêiner: Com a imagem localmente disponível, um contêiner foi iniciado a partir dela com o comando:
 Bash
docker run python-app


**3. Resultados**
A execução do contêiner ocorreu com sucesso, exibindo a saída Olá, Docker! no terminal, conforme esperado. Isso confirma que a aplicação Python foi executada corretamente dentro do ambiente isolado e portátil do contêiner, utilizando as dependências e o runtime definidos na imagem.

**4. Conclusão**
Esta atividade prática permitiu a solidificação dos conceitos de virtualização a nível de sistema operacional com Docker. Ficou evidente a distinção e a relação entre Dockerfile (a receita), a Imagem (o pacote imutável) e o Contêiner (a instância em execução). O processo demonstrou a simplicidade e o poder do Docker para empacotar e distribuir aplicações de forma consistente, independentemente do ambiente do hospedeiro.
