Estudante
- id_estudante (INT, PK)
- nome (VARCHAR)
- data_nascimento (DATE)
- email (VARCHAR)
- telefone (VARCHAR)
- id_turma (INT, FK)

Pessoa_Facilitadora
- id_facilitador (INT, PK)
- nome (VARCHAR)
- email (VARCHAR)

Turma
- id_turma (INT, PK)
- nome (VARCHAR)
- id_curso (INT, FK)
- id_facilitador (INT, FK)

Turma_aluno
- id_turma (INT, FK)
- id_estudante (INT, FK)
- id_modulo (INT, FK)

Módulo
- id_modulo (INT, PK)
- nome (VARCHAR)

Curso
- id_curso (INT, PK)
- nome (VARCHAR)
- descricao (TEXT)

Estudante_auditoria
- id_estudante (INT, FK)
- data_insert timestamp
