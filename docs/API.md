# API Documentation

## Base URL
```
http://localhost:3000/api
```

## Autenticação
Todas as requisições (exceto login/register) devem incluir:
```
Authorization: Bearer {token}
```

---

## Auth Endpoints

### POST /auth/register
Registrar novo usuário

**Request:**
```json
{
  "name": "João Silva",
  "email": "joao@example.com",
  "password": "123456",
  "role": "operador|gestor|lideranca",
  "department": "TI"
}
```

**Response:**
```json
{
  "success": true,
  "token": "eyJhbGc...",
  "user": {
    "id": "507f1f77bcf86cd799439011",
    "name": "João Silva",
    "email": "joao@example.com",
    "role": "operador"
  }
}
```

### POST /auth/login
Fazer login

**Request:**
```json
{
  "email": "joao@example.com",
  "password": "123456"
}
```

**Response:**
```json
{
  "success": true,
  "token": "eyJhbGc...",
  "user": {
    "id": "507f1f77bcf86cd799439011",
    "name": "João Silva",
    "email": "joao@example.com",
    "role": "operador"
  }
}
```

### GET /auth/me
Obter usuário atual

**Response:**
```json
{
  "success": true,
  "data": {
    "_id": "507f1f77bcf86cd799439011",
    "name": "João Silva",
    "email": "joao@example.com",
    "role": "operador"
  }
}
```

---

## Ideas Endpoints

### POST /ideas
Criar ideia (Operadores)

**Request:**
```json
{
  "title": "Automatizar processo X",
  "description": "Implementar sistema para automatizar...",
  "category": "inovacao|problema"
}
```

### GET /ideas
Listar ideias

### GET /ideas/:id
Obter detalhes da ideia

### PUT /ideas/:id
Atualizar ideia (Gestores, Liderança)

**Request:**
```json
{
  "status": "pendente|em_analise|aprovada|rejeitada",
  "priority": "baixa|media|alta",
  "feedback": "Comentário do gestor"
}
```

### DELETE /ideas/:id
Deletar ideia

---

## Projects Endpoints

### POST /projects
Criar projeto (Gestores, Liderança)

**Request:**
```json
{
  "name": "Projeto Automação",
  "description": "Implementar automação...",
  "idea": "507f1f77bcf86cd799439011",
  "budget": 50000,
  "expectedEndDate": "2026-12-31"
}
```

### GET /projects
Listar projetos

### GET /projects/:id
Obter detalhes do projeto

### PUT /projects/:id
Atualizar projeto (Gestores, Liderança)

**Request:**
```json
{
  "status": "planejamento|em_andamento|concluido|pausado",
  "stage": "etapa_1|etapa_2|etapa_3|concluida",
  "investment": 45000,
  "results": {
    "roi": 15.5,
    "costReduction": 5000,
    "productivityGain": 20,
    "revenue": 75000
  }
}
```

### DELETE /projects/:id
Deletar projeto (Gestores, Liderança)

---

## Strategies Endpoints

### POST /strategies
Criar estratégia (Liderança)

**Request:**
```json
{
  "title": "Estratégia de Inovação 2026",
  "description": "Descrição breve",
  "content": "Conteúdo completo da estratégia..."
}
```

### GET /strategies
Listar estratégias ativas

### GET /strategies/:id
Obter detalhes da estratégia

### PUT /strategies/:id
Atualizar estratégia (Liderança)

**Request:**
```json
{
  "title": "Novo título",
  "description": "Nova descrição",
  "content": "Novo conteúdo",
  "isActive": true
}
```

### DELETE /strategies/:id
Deletar estratégia (Liderança)

---

## Dashboard Endpoints

### GET /dashboard
Obter resumo do dashboard (Liderança)

**Response:**
```json
{
  "success": true,
  "data": {
    "summary": {
      "totalProjects": 10,
      "completedProjects": 5,
      "ongoingProjects": 3,
      "totalROI": 125.5,
      "totalCostReduction": 25000,
      "totalProductivityGain": 45,
      "totalRevenue": 500000,
      "totalInvestment": 200000,
      "averageROI": 12.55
    },
    "projectsByStatus": {
      "planejamento": 2,
      "em_andamento": 3,
      "concluido": 5
    },
    "ideaStats": {
      "total": 50,
      "approved": 10,
      "pending": 30
    },
    "projects": [...]
  }
}
```

### GET /dashboard/project/:projectId
Obter detalhes do projeto

---

## Error Responses

### 400 Bad Request
```json
{
  "error": "Please provide all required fields"
}
```

### 401 Unauthorized
```json
{
  "error": "Not authorized to access this route"
}
```

### 403 Forbidden
```json
{
  "error": "User role 'operador' is not authorized to access this route"
}
```

### 404 Not Found
```json
{
  "error": "Idea not found"
}
```

### 500 Internal Server Error
```json
{
  "error": "Internal Server Error",
  "message": "Error details..."
}
```
