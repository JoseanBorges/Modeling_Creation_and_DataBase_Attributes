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
- id_estudante (INT, PK)
- nome (VARCHAR)
- data_nascimento (DATE)
- email (VARCHAR)
- telefone (VARCHAR)
- curso_id (INT, FK -> Curso)

PessoaFacilitadora
- id_facilitador (INT, PK)
- nome (VARCHAR)
- email (VARCHAR)
- telefone (VARCHAR)

Turma
- id_turma (INT, PK)
- nome (VARCHAR)
- facilitador_id (INT, FK -> PessoaFacilitadora)

Modulo
- id_modulo (INT, PK)
- nome (VARCHAR)
- turma_id (INT, FK -> Turma)

Curso
- id_curso (INT, PK)
- nome (VARCHAR)
- descricao (TEXT)

Entidade: Estudante

id_estudante (INT, PK): É a chave primária que identifica exclusivamente cada estudante na tabela.
nome (VARCHAR): Armazena o nome do estudante.
data_nascimento (DATE): Representa a data de nascimento do estudante.
email (VARCHAR): Armazena o endereço de e-mail do estudante.
telefone (VARCHAR): Armazena o número de telefone do estudante.
curso_id (INT, FK -> Curso): É uma chave estrangeira que se relaciona com a tabela Curso, indicando o curso em que o estudante está matriculado.
Entidade: PessoaFacilitadora

id_facilitador (INT, PK): É a chave primária que identifica exclusivamente cada pessoa facilitadora na tabela.
nome (VARCHAR): Armazena o nome da pessoa facilitadora.
email (VARCHAR): Armazena o endereço de e-mail da pessoa facilitadora.
telefone (VARCHAR): Armazena o número de telefone da pessoa facilitadora.
Entidade: Turma

id_turma (INT, PK): É a chave primária que identifica exclusivamente cada turma na tabela.
nome (VARCHAR): Armazena o nome da turma.
facilitador_id (INT, FK -> PessoaFacilitadora): É uma chave estrangeira que se relaciona com a tabela PessoaFacilitadora, indicando a pessoa facilitadora responsável pela turma.
Entidade: Módulo

id_modulo (INT, PK): É a chave primária que identifica exclusivamente cada módulo na tabela.
nome (VARCHAR): Armazena o nome do módulo.
turma_id (INT, FK -> Turma): É uma chave estrangeira que se relaciona com a tabela Turma, indicando a turma à qual o módulo pertence.
Entidade: Curso

id_curso (INT, PK): É a chave primária que identifica exclusivamente cada curso na tabela.
nome (VARCHAR): Armazena o nome do curso.
descricao (TEXT): Armazena uma descrição ou informações adicionais sobre o curso.
Essas entidades e atributos são usados para modelar e organizar os dados relacionados à estrutura de ensino da empresa Resilia. As chaves primárias (PK) identificam de forma única cada registro em uma tabela, enquanto as chaves estrangeiras (FK) estabelecem relacionamentos entre diferentes tabelas.
