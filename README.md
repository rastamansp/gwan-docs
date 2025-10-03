# **Gwan Docs**

Software de wiki e documentação colaborativo de código aberto. É uma alternativa de código aberto ao Confluence e Notion.

**Website** | **Documentação** | **Twitter / X**

## Começando

Para começar com Gwan Docs, siga as instruções abaixo ou consulte nossa documentação.

### Pré-requisitos

- Docker
- Docker Compose

### Instalação Rápida com Docker Compose

1. Clone este repositório:
```bash
git clone https://github.com/rastamansp/gwan-docs.git
cd gwan-docs
```

2. Copie o arquivo de configuração:
```bash
cp .env.example .env
```

3. Configure as variáveis de ambiente no arquivo `.env` (opcional)

4. Execute o projeto:
```bash
docker-compose up -d
```

5. Acesse o aplicativo em:
```
http://localhost:3000
```

## Recursos

* ✅ Colaboração em tempo real
* ✅ Diagramas (Draw.io, Excalidraw e Mermaid)
* ✅ Espaços organizacionais
* ✅ Gerenciamento de permissões
* ✅ Grupos de usuários
* ✅ Sistema de comentários
* ✅ Histórico de páginas
* ✅ Busca avançada
* ✅ Anexos de arquivos
* ✅ Embeds (Airtable, Loom, Miro e mais)
* ✅ Traduções (10+ idiomas)
* ✅ Suporte a Markdown
* ✅ API REST completa

### Screenshots

| Página Inicial | Editor |
|:---:|:---:|
| ![Home](docs/images/home.png) | ![Editor](docs/images/editor.png) |

## Estrutura do Projeto

```
gwan-docs/
├── apps/
│   ├── client/          # Frontend React/Next.js
│   └── server/          # Backend Node.js/Express
├── packages/
│   ├── ui/              # Componentes UI compartilhados
│   ├── core/            # Lógica de negócio compartilhada
│   └── utils/           # Utilitários compartilhados
├── docker-compose.yml
├── .env.example
└── README.md
```

## Configuração de Desenvolvimento

### Requisitos de Desenvolvimento

- Node.js 18+
- pnpm
- Docker
- PostgreSQL 15+

### Instalação Local

1. Instale as dependências:
```bash
pnpm install
```

2. Configure o banco de dados PostgreSQL

3. Configure as variáveis de ambiente em `.env`

4. Execute o projeto em modo de desenvolvimento:
```bash
# Backend
pnpm dev:server

# Frontend (em outro terminal)
pnpm dev:client
```

## Docker Compose

O projeto inclui um arquivo `docker-compose.yml` completo com:

- **Aplicação**: Next.js + Express
- **Banco de dados**: PostgreSQL
- **Buscas**: Elasticsearch
- **Cache**: Redis
- **Proxy reverso**: Nginx
- **Monitoramento**: Prometheus + Grafana (opcional)

### Serviços incluídos:

```yaml
services:
  - app: Aplicação principal
  - postgres: Banco de dados PostgreSQL
  - redis: Cache Redis
  - elasticsearch: Motor de busca
  - nginx: Proxy reverso
  - prometheus: Métricas (opcional)
  - grafana: Dashboards (opcional)
```

## Variáveis de Ambiente

Principais variáveis de ambiente configuráveis:

```bash
# Database
POSTGRES_HOST=postgres
POSTGRES_PORT=5432
POSTGRES_DB=gwandoos
POSTGRES_USER=gwandoos
POSTGRES_PASSWORD=password

# Redis
REDIS_HOST=redis
REDIS_PORT=6379

# Elasticsearch
ELASTICSEARCH_HOST=elasticsearch
ELASTICSEARCH_PORT=9200

# App
NODE_ENV=development
PORT=3000
API_URL=http://localhost:3001

# JWT
JWT_SECRET=your-secret-key

# File Uploads
MAX_FILE_SIZE=10485760
UPLOAD_PATH=/uploads
```

## API

### Endpoints Principais

- `GET /api/spaces` - Listar espaços
- `POST /api/spaces` - Criar espaço
- `GET /api/pages` - Listar páginas
- `POST /api/pages` - Criar página
- `GET /api/users` - Listar usuários
- `POST /api/auth/login` - Login
- `POST /api/auth/register` - Registro

### Exemplo de Uso da API

```bash
# Criar um novo espaço
curl -X POST http://localhost:3000/api/spaces \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer your-token" \
  -d '{
    "name": "Desenvolvimento",
    "description": "Documentação do projeto"
  }'
```

## Contribuição

1. Faça um fork do projeto
2. Crie uma branch para sua feature (`git checkout -b feature/minha-feature`)
3. Commit suas mudanças (`git commit -am 'Adiciona nova feature'`)
4. Push para a branch (`git push origin feature/minha-feature`)
5. Abra um Pull Request

### Diretrizes de Contribuição

- Siga as convenções de código existentes
- Escreva testes para novas funcionalidades
- Documente mudanças na API
- Mantenha o código limpo e legível

## Licença

O código está licenciado sob a [Licença MIT](LICENSE).

## Tecnologias

### Frontend
- **React 18** - Biblioteca UI
- **Next.js 14** - Framework React
- **TypeScript** - Tipagem estática
- **Tailwind CSS** - Estilização
- **Framer Motion** - Animações

### Backend
- **Node.js 18** - Runtime JavaScript
- **Express** - Framework web
- **PostgreSQL** - Banco de dados
- **Redis** - Cache
- **Elasticsearch** - Busca
- **JWT** - Autenticação
- **Socket.io** - Colaboração em tempo real

### DevOps
- **Docker** - Containerização
- **Docker Compose** - Orquestração local
- **Nginx** - Proxy reverso
- **Prometheus** - Métricas
- **Grafana** - Monitoramento

## Suporte

- **Documentação**: [docs.gwandoos.com](https://docs.gwandoos.com)
- **Issues**: [GitHub Issues](https://github.com/seu-usuario/gwan-docs/issues)
- **Discussões**: [GitHub Discussions](https://github.com/seu-usuario/gwan-docs/discussions)
- **Email**: suporte@gwandoos.com

## Roadmap

### v1.0 (Q1 2024)
- [ ] Sistema de autenticação completo
- [ ] Editor de páginas com colaboração em tempo real
- [ ] Sistema de permissões granular
- [ ] Integração com diagramas Mermaid

### v1.1 (Q2 2024)
- [ ] Sistema de buscas avançadas
- [ ] API REST completa
- [ ] Suporte a múltiplos idiomas
- [ ] Mobile responsive

### v1.2 (Q3 2024)
- [ ] Integração com ferramentas externas
- [ ] Sistema de templates de página
- [ ] Backup automatizado
- [ ] Métricas e analytics

## Agradecimentos

Agradecimentos especiais para:

- [Confluence](https://www.atlassian.com/software/confluence) pela inspiração
- [Notion](https://www.notion.so) pelo design moderno
- Comunidade de código aberto pelo suporte contínuo

---

**Feito com ❤️ pela equipe Gwan Docs**
