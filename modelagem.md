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

