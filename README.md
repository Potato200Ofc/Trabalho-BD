# Trabalho-BD
# 1. Introdução
O desenvolvimento de um sistema de banco de dados eficiente começa muito antes da escrita de
qualquer linha de código SQL. Esta etapa inicial foca na modelagem conceitual e lógica, onde
traduzimos a realidade de uma biblioteca para uma estrutura organizada de dados. O objetivo é garantir
a integridade das informações, evitar redundâncias e permitir consultas rápidas e precisas.

# 2. Identificação das Entidades
As entidades são os pilares do nosso sistema. Elas representam os objetos do mundo real sobre os
quais desejamos armazenar informações. Para este projeto, identificamos as três entidades
fundamentais:
• Alunos: Representa os usuários da biblioteca que realizarão os empréstimos.
• Livros: Representa o acervo disponível para consulta e empréstimo.
• Empréstimos: Representa a ação e o registro histórico da movimentação dos livros pelos alunos.

# 3. Descrição das Tabelas e Campos
Cada entidade identificada acima torna-se uma tabela no banco de dados. Abaixo, detalhamos os
campos (colunas) necessários para cada uma.
Tabela: Alunos
Campo Tipo de Dado Descrição Chave
id_aluno Inteiro Identificador único do aluno. PK (PRIMÁRIA)
nome Texto (Varchar) Nome completo do aluno. -
email Texto (Varchar) Endereço eletrônico para contato. -Parte 1 – Estrutura do Banco (Entendimento)  

Campo Tipo de Dado Descrição Chave
data_cadastro Data Data em que o aluno se registrou na biblioteca. -

# Tabela: Livros

Campo Tipo de Dado Descrição Chave
id_livro Inteiro Identificador único do livro. PK (PRIMÁRIA)
titulo Texto (Varchar) Título da obra. -
autor Texto (Varchar) Nome do autor da obra. -
ano_publicacao Inteiro Ano em que o livro foi publicado. -
isbn Texto Código internacional padrão do livro. -

# Tabela: Empréstimos

Campo Tipo de Dado Descrição Chave
id_emprestimo Inteiro Identificador único do registro de empréstimo. PK (PRIMÁRIA)
id_aluno Inteiro Referência ao aluno que pegou o livro. FK (ESTRANGEIRA)
id_livro Inteiro Referência ao livro que foi emprestado. FK (ESTRANGEIRA)
data_emprestimo Data Data em que o livro saiu da biblioteca. -
data_devolucao Data Data prevista ou real de retorno do livro. -

# 4. Definição das Chaves Primárias (PK)

A Chave Primária (Primary Key) é o elemento que garante a unicidade de cada registro. No nosso
projeto:
Em Alunos, o id_aluno impede que dois alunos diferentes tenham o mesmo registro.
Em Livros, o id_livro identifica cada exemplar individualmente.
Em Empréstimos, o id_emprestimo garante o rastreio individual de cada transação.
•
•
•
# 5. Relacionamentos e Chaves Estrangeiras (FK)

Os relacionamentos permitem que as tabelas "conversem" entre si. Utilizamos Chaves Estrangeiras
(Foreign Keys) para criar essas pontes:
Relacionamento Aluno ↔ Empréstimo: Um aluno pode realizar vários empréstimos ao longo do
tempo (Relacionamento 1 para N). O campo id_aluno na tabela de Empréstimos aponta para o
ID original na tabela de Alunos.
Relacionamento Livro ↔ Empréstimo: Um livro pode ser objeto de diversos empréstimos em
datas diferentes (Relacionamento 1 para N). O campo id_livro na tabela de Empréstimos
conecta o registro ao livro específico do acervo.
Dessa forma, a tabela Empréstimos funciona como uma tabela de ligação, consolidando quem pegou o
quê e quando.

Projeto de Banco de Dados - Etapa de Modelagem Conceitual
