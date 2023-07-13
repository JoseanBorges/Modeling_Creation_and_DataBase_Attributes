<<<<<<< Updated upstream
# Projeto Módulo 3

## Squad 4

Bem-vindo! Neste projeto, fomos designados para modernizar o processo de armazenamento de dados e construção para gerenciamento da estrutura de ensino de uma empresa. Seguimos as seguintes etapas:

- Geramos uma representação das entidades, seus atributos e relacionamentos;
- Criamos uma modelagem do Banco de Dados;
- Utilizamos scripts SQL para criar o Banco de Dados e suas Tabelas;
- Criamos scripts para inserção de dados nas Tabelas;
- Realizamos testes de consulta.

Acreditamos que o resultado foi satisfatório, pois agora podemos realizar consultas eficientes que fornecem informações estratégicas para a empresa.

Em caso de dúvidas, você pode entrar em contato conosco através do LinkedIn:

- [Aline Bozollan](https://www.linkedin.com/in/alinebozollan/)
- [Arthur Vilarverde](https://www.linkedin.com/in/arthur-vilarverde-dataanalytics-webdev/)
- [Joel Nunes Jr](https://www.linkedin.com/in/joel-nunes-jr-0883b2265/)
- [Josean Borges](https://www.linkedin.com/in/joseanplborges/)
- [Rafael Antonio](https://www.linkedin.com/in/rafael-antonio-759a04241/)

## Apontamentos

Aqui estão algumas observações importantes para entender o funcionamento do código:

#significado de cada uma dessas entidades e seus atributos:
 Estudante
=======
# DATABASE RESILIA: Projeto Módulo 3 - Squad 4

Bem-vindo ao Projeto Módulo 3! Neste projeto, fomos designados para modernizar o processo de armazenamento de dados e construção para gerenciamento da estrutura de ensino de uma empresa. Seguimos as seguintes etapas:

Geramos uma representação das entidades, seus atributos e relacionamentos;
Criamos uma modelagem do Banco de Dados;
Utilizamos scripts SQL para criar o Banco de Dados e suas Tabelas;
Criamos scripts para inserção de dados nas Tabelas;
Realizamos testes de consulta.
Acreditamos que o resultado foi satisfatório, pois agora podemos realizar consultas eficientes que fornecem informações estratégicas para a empresa.

## Sumário:
- Integrantes da Squad.
- Entidades e atributos.
- Relacionaments.
- Trigger
- VIEWs para as consultas.

### Em caso de dúvidas, você pode entrar em contato conosco através do LinkedIn:

- Aline Bozollan(Colaboradora)
- Arthur Vilarverde(Gestor de Gente e Engajamento)
- Joel Nunes Jr.(Gestor de Conhecimento)
- Josean Borges(Colaborador)
- Rafael Antonio(Co-Facilitador)

#### Para compor nosso banco de dados foram criadas e povoadas 7 tabelas. São elas:

**Estudante**
>>>>>>> Stashed changes
- id_estudante (INT, PK)
- nome (VARCHAR)
- data_nascimento (DATE)
- email (VARCHAR)
- telefone (VARCHAR)
- id_turma (INT, FK)

**Estudante_auditoria**
- id_estudante (INT, FK)
- data_insert timestamp

**Pessoa_Facilitadora**
- id_facilitador (INT, PK)
- nome (VARCHAR)
- email (VARCHAR)

**Turma**
- id_turma (INT, PK)
- nome (VARCHAR)
- id_curso (INT, FK)
- id_facilitador (INT, FK)

**Turma_aluno**
- id_turma (INT, FK)
- id_estudante (INT, FK)
- id_modulo (INT, FK)

**Módulo**
- id_modulo (INT, PK)
- nome (VARCHAR)

**Curso**
- id_curso (INT, PK)
- nome (VARCHAR)
- descricao (TEXT)

## Relacionamento.

**Referência da tabela ESTUDANTE com a tabela TURMA**
ALTER TABLE IF EXISTS public.estudante
    ADD CONSTRAINT id_turma FOREIGN KEY(id_turma)
    REFERENCES public.turma (id_turma) MATCH SIMPLE
    ON UPDATE NO ACTION
    ON DELETE NO ACTION
    NOT VALID;

**Referência da tabela TURMA com a tabela CURSO**
ALTER TABLE IF EXISTS public.turma
    ADD CONSTRAINT id_curso FOREIGN KEY (id_curso)
    REFERENCES public.curso (id_curso) MATCH SIMPLE
    ON UPDATE NO ACTION
    ON DELETE NO ACTION
    NOT VALID;

**Referência da tabela TURMA com a tabela FACILITADOR**
ALTER TABLE IF EXISTS public.turma
    ADD CONSTRAINT id_facilitador FOREIGN KEY (id_facilitador)
    REFERENCES public.pessoa_facilitadora (id_facilitador) MATCH SIMPLE
    ON UPDATE NO ACTION
    ON DELETE NO ACTION
    NOT VALID;

**Referência da tabela TURMA_ALUNO com a tabela TURMA**
ALTER TABLE IF EXISTS public.turma_aluno
    ADD CONSTRAINT id_turma FOREIGN KEY (id_turma)
    REFERENCES public.turma (id_turma) MATCH SIMPLE
    ON UPDATE NO ACTION
    ON DELETE NO ACTION
    NOT VALID;

**Referência da tabela TURMA_ALUNO com a tabela ESTUDANTE**
ALTER TABLE IF EXISTS public.turma_aluno
    ADD CONSTRAINT id_estudante FOREIGN KEY (id_estudante)
    REFERENCES public.estudante (id_estudante) MATCH SIMPLE
    ON UPDATE NO ACTION
    ON DELETE NO ACTION
    NOT VALID;

**Referência da tabela TURMA_ALUNO com a tabela MÓDULO**
ALTER TABLE IF EXISTS public.turma_aluno
    ADD CONSTRAINT id_modulo FOREIGN KEY (id_modulo)
    REFERENCES public.modulo (id_modulo) MATCH SIMPLE
    ON UPDATE NO ACTION
    ON DELETE NO ACTION
    NOT VALID;

## Fez-se necessária a criação de um TRIGGER(Gatilho), para o registro a cada inserção na tabela ESTUDANTE.

VISUALIZAÇÃO DOS DADOS COM VIEWS

- 1. Selecionar a quantidade total de estudantes cadastrados no banco;
**SELECT * FROM TOTAL_ALUNO**

- 2. Selecionar quais pessoas facilitadoras atuam em mais de uma turma;
**SELECT * FROM FACILITADOR_COM_VARIAS_TURMA**

- 3. Crie uma view que selecione a porcentagem de estudantes com status de evasão agrupados por turma;
**SELECT * FROM PORC_EVASAO**

- 4. Além disso, vocês deverão pensar em mais uma questão que deverá ser respondida por scripts SQL que combine pelo menos 3 tabelas. 
    **SELECT * FROM TURMA_FACILITADOR_ALUNO**