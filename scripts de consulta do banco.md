**-- 1. Listar todos os alunos**

SELECT \* FROM aluno;



**--2. Listar alunos em ordem alfabética**

SELECT nome, email

FROM aluno

ORDER BY nome;



**-- 3. Mostrar as turmas com seus respectivos professores (JOIN)**



SELECT

&#x20;   t.nome AS turma,

&#x20;   p.nome AS professor

FROM turma t

INNER JOIN professor p

ON t.id\_professor = p.id\_professor;



**--4. Mostrar aluno, turma e modalidade (JOIN com 3 tabelas)**



SELECT

&#x20;   a.nome AS aluno,

&#x20;   t.nome AS turma,

&#x20;   m.nome AS modalidade

FROM matricula mt

INNER JOIN aluno a

&#x20;   ON mt.id\_aluno = a.id\_aluno

INNER JOIN turma t

&#x20;   ON mt.id\_turma = t.id\_turma

INNER JOIN modalidade m

&#x20;   ON t.id\_modalidade = m.id\_modalidade;



**--  5. Quantidade de alunos por turma (GROUP BY)**



SELECT

&#x20;   t.nome,

&#x20;   COUNT(mt.id\_aluno) AS quantidade\_alunos

FROM turma t

LEFT JOIN matricula mt

ON t.id\_turma = mt.id\_turma

GROUP BY t.nome;



**-- 6. Professores que não possuem turma (LEFT JOIN)**



SELECT

&#x20;   p.nome

FROM professor p

LEFT JOIN turma t

ON p.id\_professor = t.id\_professor

WHERE t.id\_turma IS NULL;



**-- 7. Alunos sem matrícula (LEFT JOIN)**



SELECT

&#x20;   a.nome

FROM aluno a

LEFT JOIN matricula mt

ON a.id\_aluno = mt.id\_aluno

WHERE mt.id\_matricula IS NULL;



**--8. Quantidade de turmas por modalidade**



SELECT

&#x20;   m.nome,

&#x20;   COUNT(t.id\_turma) AS quantidade\_turmas

FROM modalidade m

LEFT JOIN turma t

ON m.id\_modalidade = t.id\_modalidade

GROUP BY m.nome;



**-- 9. Consulta usando CTE**



WITH total\_alunos AS (

&#x20;   SELECT

&#x20;       id\_turma,

&#x20;       COUNT(id\_aluno) AS total

&#x20;   FROM matricula

&#x20;   GROUP BY id\_turma

)



SELECT

&#x20;   t.nome,

&#x20;   ta.total

FROM turma t

INNER JOIN total\_alunos ta

ON t.id\_turma = ta.id\_turma;



**-- 10. Window Function**



SELECT

&#x20;   nome,

&#x20;   ROW\_NUMBER() OVER(ORDER BY nome) AS ordem

FROM aluno;







