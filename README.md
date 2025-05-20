Claro! Aqui está a estrutura completa e organizada da API para o sistema de serviços da oficina, considerando os documentos enviados e que os funcionários são usados para escalonamento:

⸻

📦 Estrutura da API - Sistema de Serviços da Oficina

⸻

1. 🔍 Serviços

GET /servicos

Descrição: Retorna todos os serviços com seus dados completos.

Resposta:

[
  {
    "codigo": "S1",
    "descricao": "REGULAR BOMBA INJETORA",
    "natureza": "DIE",
    "tpr": 2.5,
    "valor_unitario": 390.00,
    "valor_total": 975.00
  },
  ...
]


⸻

2. 🧩 Etapas dos Serviços

GET /servicos/:codigo/etapas

Descrição: Retorna as etapas que compõem um serviço específico (ex: revisão, regulagem etc).

Resposta:

{
  "codigo": "S1",
  "etapas": [
    { "nome": "LAVADOR", "tpr": 0.13, "percentual": "5%" },
    { "nome": "ORCAMENTO", "tpr": 0.37, "percentual": "15%" },
    { "nome": "REVISAO", "tpr": 0.75, "percentual": "30%" },
    { "nome": "REGULAGEM", "tpr": 1.00, "percentual": "40%" },
    { "nome": "ACABAMENTO", "tpr": 0.25, "percentual": "10%" }
  ]
}


⸻

3. 📄 Ordens de Serviço

GET /ordens-servico

Descrição: Lista todas as ordens de serviço com cliente, serviços incluídos e status.

Resposta:

[
  {
    "id": 101,
    "cliente": "Joao da Silva",
    "data": "2025-05-20",
    "servicos": ["S1", "S104"],
    "status": "em andamento"
  },
  {
    "id": 102,
    "cliente": "Maria Souza",
    "data": "2025-05-19",
    "servicos": ["S148"],
    "status": "concluida"
  }
]


⸻

4. 👷 Funcionários (para escalonamento)

GET /funcionarios

Descrição: Lista os funcionários da oficina com especialidades e disponibilidade para alocação nas etapas dos serviços.

Resposta:

[
  {
    "id": 1,
    "nome": "Carlos Almeida",
    "cargo": "Mecânico",
    "especialidades": ["REGULAR BOMBA INJETORA", "REVISAO"],
    "disponivel": true
  },
  {
    "id": 2,
    "nome": "Fernanda Lopes",
    "cargo": "Orçamentista",
    "especialidades": ["ORCAMENTO"],
    "disponivel": false
  }
]


⸻

🚀 Possíveis futuros endpoints (opcional)
	•	POST /ordens-servico: Criar nova ordem de serviço
	•	POST /escalonar-servico: Atribuir funcionários automaticamente às etapas de um serviço com base na disponibilidade
	•	GET /funcionarios/:id/escalonamentos: Ver em quais etapas/ordens o funcionário está alocado

⸻

Se quiser, posso gerar os modelos MER, os controllers em Node.js ou documentação Swagger com base nisso. Deseja seguir com essa próxima etapa?
