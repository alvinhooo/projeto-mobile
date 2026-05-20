# Challenge Grupo Águia Branca - SPRINT 1

Aplicativo de Gestão de Ideias e Projetos para diferentes perfis de usuários (Operadores, Gestores e Liderança).

## 🏗️ Arquitetura

- **Backend**: Node.js + Express + MongoDB
- **Mobile**: Android Nativo + Kotlin
- **Autenticação**: JWT
- **Banco de Dados em Tempo Real**: Firebase Realtime Database

## 📱 Funcionalidades

### Operadores
- Login seguro
- Consultar orientações estratégicas
- Cadastrar ideias/problemas
- Acompanhar status das ideias

### Gestores
- Login seguro
- Consultar orientações estratégicas
- Consultar, priorizar e aprovar ideias
- Cadastrar projetos e iniciativas
- Acompanhar progresso dos projetos

### Liderança
- Login seguro
- Gerenciar orientações estratégicas (CRUD)
- Consultar andamento dos projetos
- Visualizar dashboard com resultados (ROI, redução de custos, produtividade)

## 📁 Estrutura do Projeto

```
projeto-mobile/
├── backend/
│   ├── src/
│   │   ├── controllers/
│   │   ├── models/
│   │   ├── routes/
│   │   ├── middleware/
│   │   ├── services/
│   │   └── server.js
│   ├── .env.example
│   ├── package.json
│   └── README.md
│
├── mobile/
│   ├── app/
│   └── README.md
│
└── docs/
    ├── ARQUITETURA.md
    ├── FLUXO_USUARIOS.md
    └── API.md
```

## 🚀 Como Começar

### Backend
```bash
cd backend
npm install
cp .env.example .env
npm start
```

### Mobile
```bash
cd mobile
./gradlew build
./gradlew run
```

## 📋 Entrega Sprint 1
- APK Android
- Código-fonte completo
- Documentação técnica
- Vídeo demonstrativo (máx 5 min)

## 👥 Equipe
- Aluno: alvinhooo

---
**Data de Entrega**: 26/05/2026
