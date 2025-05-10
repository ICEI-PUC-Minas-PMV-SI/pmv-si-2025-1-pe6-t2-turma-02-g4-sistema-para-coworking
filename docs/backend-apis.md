# APIs e Web Services

O planejamento de uma aplicação de APIS Web é uma etapa fundamental para o sucesso do projeto. Ao planejar adequadamente, você pode evitar muitos problemas e garantir que a sua API seja segura, escalável e eficiente.

Aqui estão algumas etapas importantes que devem ser consideradas no planejamento de uma aplicação de APIS Web.

[Inclua uma breve descrição do projeto.]

## Objetivos da API

A API do sistema de coworking será responsável por fornecer uma interface centralizada para comunicação entre o backend e os clientes web e mobile como principais objetivos:
- Gerenciar reservas de salas e mesas, permitindo que os usuários consultem disponibilidade e realizem reservas.
- Fornecer um ambiente seguro de autenticação e autorização, garantindo acesso controlado aos dados.
- Facilitar a administração do sistema, permitindo que administradores gerenciem usuários, reservas e espaços.
- Garantir a integridade dos dados ao aplicar regras de negócio e validações antes de persistir informações no banco de dados.

A API será usada pela aplicação Web (React.js): Interface web para usuários e administradores, pelo aplicativo Mobile (Flutter): Aplicação móvel para reservas rápidas.
A API não será aberta para terceiros, sendo utilizada apenas pelos sistemas internos (site e app).

A API será estruturada em diferentes recursos (endpoints), organizados de forma RESTful, para fornecer as funcionalidades necessárias.
- Autenticação e Autorização
- CRUD de Usuários
- CRUD de Salas e Mesas
- CRUD de Reservas

## Modelagem da Aplicação

**Estrutura de Dados**
A aplicação segue um modelo relacional para armazenar e gerenciar os dados, utilizando SQL Server Express como banco de dados. O Modelo de Entidade-Relacionamento (MER) descreve as principais tabelas e seus relacionamentos:

![arq](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-1-pe6-t2-turma-02-g4-sistema-para-coworking/blob/main/docs/img/MER.png)

Principais Entidades:
Usuários: Armazena informações dos usuários do sistema (administradores e clientes).
Salas/Mesas: Representa os espaços disponíveis para reserva.
Reservas: Registra as reservas feitas pelos usuários.
Notificações: Armazena alertas sobre confirmações, cancelamentos e lembretes de reservas.

Relacionamentos Chave:
Um usuário pode fazer múltiplas reservas (1:N).
Uma sala/mesa pode ter múltiplas reservas (1:N).
Um pagamento está vinculado a uma reserva (1:1).

**Estrutura da API**
A API segue os princípios RESTful, organizando os endpoints por recursos.

/api/auth/login    > Autenticação e autorização  
/api/usuarios      > Gerenciamento de usuários  
/api/salas         > Gerenciamento de salas  
/api/mesas         > Gerenciamento de mesas
/api/reservations  > Gerenciamento de reservas  



## Tecnologias Utilizadas

O projeto contempla o desenvolvimento de: Backend e API: Implementação em C# e ASP.NET, responsável pela lógica de negócios e comunicação com o banco de dados. Banco de Dados: Uso do SQL Server Express para armazenar informações sobre usuários, reservas e disponibilidade de salas/mesas. Frontend: Aplicação web desenvolvida em React.js, proporcionando uma interface intuitiva para os usuários realizarem reservas. Aplicativo Mobile: Desenvolvido em Flutter, permitindo que os usuários façam reservas diretamente pelo smartphone.

## API Endpoints

**Autenticação**
| Método  | Endpoint        | Descrição |
|---------|----------------|-----------|
| **POST**   | `/api/auth/register` | Registra um novo usuário no sistema. |
| **POST**   | `/api/auth/login` | Autentica um usuário e gera um token JWT. |
| **POST**   | `/api/auth/logout` | Encerra a sessão do usuário. |
| **GET**    | `/api/auth/me` | Retorna os dados do usuário autenticado. |

**Usuários**
| Método  | Endpoint        | Descrição |
|---------|----------------|-----------|
| **GET**    | `/api/usuarios` | Lista todos os usuários (apenas admin). |
| **GET**    | `/api/usuarios/{id}` | Obtém detalhes de um usuário específico. |
| **PUT**    | `/api/usuarios/{id}` | Atualiza informações de um usuário. |
| **DELETE** | `/api/usuarios/{id}` | Exclui um usuário do sistema. |

**Salas**
| Método  | Endpoint        | Descrição |
|---------|----------------|-----------|
| **GET**    | `/api/salas` | Lista todas as salas disponíveis. |
| **GET**    | `/api/salas/{id}` | Obtém detalhes de uma sala específica. |
| **POST**   | `/api/salas` | Cria uma nova sala (apenas admin). |
| **PUT**    | `/api/salas/{id}` | Atualiza informações de uma sala (apenas admin). |
| **DELETE** | `/api/salas/{id}` | Remove uma sala (apenas admin). |

**Mesas**
| Método  | Endpoint        | Descrição |
|---------|----------------|-----------|
| **GET**    | `/api/mesas` | Lista todas as mesas disponíveis. |
| **GET**    | `/api/mesas/{id}` | Obtém detalhes de mesas específica. |
| **POST**   | `/api/mesas` | Cria novas mesas (apenas admin). |
| **PUT**    | `/api/mesas/{id}` | Atualiza informações de mesas (apenas admin). |
| **DELETE** | `/api/mesas/{id}` | Remove mesas (apenas admin). |

**Reservas**
| Método  | Endpoint        | Descrição |
|---------|----------------|-----------|
| **GET**    | `/api/reservas` | Lista todas as reservas (admin) ou reservas do usuário autenticado. |
| **GET**    | `/api/reservas/{id}` | Obtém detalhes de uma reserva específica. |
| **POST**   | `/api/reservas` | Cria uma nova reserva. |
| **PUT**    | `/api/reservas/{id}` | Atualiza informações de uma reserva existente. |
| **DELETE** | `/api/reservas/{id}` | Cancela uma reserva. |


**Exemplo de Requisição e Resposta**
Exemplo: Criar uma reserva (POST /reservas)
Requisição:
```json
{
  "salaId": 0,
  "mesaId": 0,
  "dataHora": "2025-04-08T00:11:02.789Z"
}
```

Resposta:
200	OK

```json
{
  "id": 0,
  "usuarioId": 0,
  "usuario": {
    "id": 0,
    "nome": "string",
    "email": "user@example.com",
    "telefone": "string",
    "cpf": "string",
    "senhaHash": "string",
    "role": "string"
  },
  "salaId": 0,
  "sala": {
    "id": 0,
    "nome": "string",
    "capacidade": 0,
    "recursos": "string"
  },
  "mesaId": 0,
  "mesa": {
    "id": 0,
    "numero": 0,
    "salaId": 0,
    "sala": {
      "id": 0,
      "nome": "string",
      "capacidade": 0,
      "recursos": "string"
    }
  },
  "dataHora": "2025-04-08T00:11:02.790Z",
  "status": "string"
}
```


## Considerações de Segurança

Segurança e Autenticação
- Todas as rotas protegidas exigem autenticação via JWT.
- Permissões diferenciadas: Administradores podem gerenciar usuários, enquanto usuários comuns só podem criar e visualizar suas próprias reservas.
- Tokens são gerados via login e devem ser enviados no header Authorization: Bearer {token}.

## Implantação

A implantação da aplicação de coworking envolve a publicação da API ASP.NET no ambiente de produção, configuração do banco de dados SQL Server e integração com o frontend (React) e aplicativo mobile (Flutter).

## Caso de Teste – Fluxo do Administrador

### Cenário
O administrador realiza login, gerencia usuários, consulta espaços e realiza uma reserva de teste para verificar a funcionalidade da aplicação.

---

### 1. **Login do Administrador**

**Rota:** `POST /api/auth/login`  
**Requisição:**
```json
{
  "email": "admin@email.com",
  "senha": "Senha123"
}
```
**Resposta:**
```json
{
  "token": "<JWT_TOKEN_AQUI>",
  "message": "Login realizado com sucesso."
}
```

### 2. **Criar um novo usuário**

**Rota:** `POST /api/auth/register`  
**Requisição:**
```json
{
  "nome": "João da Silva",
  "cpf": "12345678900",
  "email": "joao@email.com",
  "senha": "Senha123"
}
```
**Resposta:**
```json
{
  "message": "Usuário registrado com sucesso!"
}
```

### 3. **Deletar um usuário**

**Rota:** `DELETE /api/users/5`  
**Resposta:**
```json
{
  "message": "Usuário deletado com sucesso."
}
```

### 2. **Criar um novo usuário**

**Rota:** `POST /api/reservas`  
**Requisição:**
```json
{
  "salaId": 2,
  "salaId": 1,
  "dataHora": "2025-05-08T20:00:00"
}
```
**Resposta:**
```json
{
    "message": "Sua reserva foi confirmada! ID: 9"
}
```
![arq](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-1-pe6-t2-turma-02-g4-sistema-para-coworking/blob/main/docs/img/Teste%20Postman.png)


## Configurações da API e Testes Postman

No pdf anexo se encontra as descrições de todos os endpoins, seus métodos acompanhados de testes de cada um via Postman

https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-1-pe6-t2-turma-02-g4-sistema-para-coworking/blob/main/docs/Endpoints_prints_testes.pdf)
