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

Principais Entidades:
Usuários: Armazena informações dos usuários do sistema (administradores e clientes).
Salas/Mesas: Representa os espaços disponíveis para reserva.
Reservas: Registra as reservas feitas pelos usuários.
Pagamentos: Caso necessário, gerencia pagamentos de reservas.
Notificações: Armazena alertas sobre confirmações, cancelamentos e lembretes de reservas.

Relacionamentos Chave:
Um usuário pode fazer múltiplas reservas (1:N).
Uma sala/mesa pode ter múltiplas reservas (1:N).
Um pagamento está vinculado a uma reserva (1:1).

**Estrutura da API**
A API segue os princípios RESTful, organizando os endpoints por recursos.

/api/auth          > Autenticação e autorização  
/api/users         > Gerenciamento de usuários  
/api/spaces        > Gerenciamento de salas/mesas  
/api/reservations  > Gerenciamento de reservas  
/api/payments      > Processamento de pagamentos  
/api/notifications > Notificações do sistema  
/api/reports       > Relatórios sobre ocupação e reservas 


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
| **GET**    | `/api/users` | Lista todos os usuários (apenas admin). |
| **GET**    | `/api/users/{id}` | Obtém detalhes de um usuário específico. |
| **PUT**    | `/api/users/{id}` | Atualiza informações de um usuário. |
| **DELETE** | `/api/users/{id}` | Exclui um usuário do sistema. |

**Salas e Mesas**
| Método  | Endpoint        | Descrição |
|---------|----------------|-----------|
| **GET**    | `/api/spaces` | Lista todas as salas e mesas disponíveis. |
| **GET**    | `/api/spaces/{id}` | Obtém detalhes de uma sala/mesa específica. |
| **POST**   | `/api/spaces` | Cria uma nova sala ou mesa (apenas admin). |
| **PUT**    | `/api/spaces/{id}` | Atualiza informações de uma sala ou mesa (apenas admin). |
| **DELETE** | `/api/spaces/{id}` | Remove uma sala ou mesa (apenas admin). |

**Reservas**
| Método  | Endpoint        | Descrição |
|---------|----------------|-----------|
| **GET**    | `/api/reservations` | Lista todas as reservas (admin) ou reservas do usuário autenticado. |
| **GET**    | `/api/reservations/{id}` | Obtém detalhes de uma reserva específica. |
| **POST**   | `/api/reservations` | Cria uma nova reserva. |
| **PUT**    | `/api/reservations/{id}` | Atualiza informações de uma reserva existente. |
| **DELETE** | `/api/reservations/{id}` | Cancela uma reserva. |


**Exemplo de Requisição e Resposta**
Exemplo: Criar uma reserva (POST /reservations)
Requisição:
```
{
  "userId": 1,
  "spaceId": 3,
  "date": "2025-02-20",
  "timeStart": "10:00",
  "timeEnd": "12:00"
}
```

Resposta:
```
{
  "id": 101,
  "userId": 1,
  "spaceId": 3,
  "date": "2025-02-20",
  "timeStart": "10:00",
  "timeEnd": "12:00",
  "status": "confirmed",
  "message": "Reserva realizada com sucesso!"
}
```


## Considerações de Segurança

Segurança e Autenticação
- Todas as rotas protegidas exigem autenticação via JWT.
- Permissões diferenciadas: Administradores podem gerenciar usuários, enquanto usuários comuns só podem criar e visualizar suas próprias reservas.

## Implantação

[Instruções para implantar a aplicação distribuída em um ambiente de produção.]

1. Defina os requisitos de hardware e software necessários para implantar a aplicação em um ambiente de produção.
2. Escolha uma plataforma de hospedagem adequada, como um provedor de nuvem ou um servidor dedicado.
3. Configure o ambiente de implantação, incluindo a instalação de dependências e configuração de variáveis de ambiente.
4. Faça o deploy da aplicação no ambiente escolhido, seguindo as instruções específicas da plataforma de hospedagem.
5. Realize testes para garantir que a aplicação esteja funcionando corretamente no ambiente de produção.

## Testes

[Descreva a estratégia de teste, incluindo os tipos de teste a serem realizados (unitários, integração, carga, etc.) e as ferramentas a serem utilizadas.]

1. Crie casos de teste para cobrir todos os requisitos funcionais e não funcionais da aplicação.
2. Implemente testes unitários para testar unidades individuais de código, como funções e classes.
3. Realize testes de integração para verificar a interação correta entre os componentes da aplicação.
4. Execute testes de carga para avaliar o desempenho da aplicação sob carga significativa.
5. Utilize ferramentas de teste adequadas, como frameworks de teste e ferramentas de automação de teste, para agilizar o processo de teste.

# Referências

Inclua todas as referências (livros, artigos, sites, etc) utilizados no desenvolvimento do trabalho.
