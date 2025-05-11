# Front-end Web

A plataforma Front‑end Web é uma aplicação responsiva para gerenciamento de espaços de coworking, desenvolvida para simplificar a reserva de mesas, salas de reunião e ambientes de trabalho híbridos ou remotos. Seus principais objetivos são:

Oferecer uma experiência de reserva intuitiva e ágil para usuários finais e administradores.

Permitir o agendamento de mesas e salas com antecedência, garantindo maior controle de agenda.

Proporcionar visibilidade e gestão centralizada de usuários, reservas e configurações de espaços.

## Projeto da Interface Web

A interface foi projetada com foco em usabilidade e clareza visual, adotando um layout em grade de 12 colunas que se adapta a diferentes larguras de tela. Os principais aspectos incluem:

Navegação principal: menu superior fixo com seções Home, Reservar Mesa, Participar de Mesa, Perfil e Painel Administrativo.

Layouts de página:

Home: seção de boas‑vindas com carrossel de temas (Home Office, Café Ambience, Clean Simple), estatísticas de uso e chamada para ação (CTA) para nova reserva.

Reserva de Mesa: formulário passo a passo para escolha de tema, data, horário e confirmação de reserva.

Participar de Mesa: lista de mesas disponíveis com filtros de tema e horário.

Perfil de Usuário: visualização e edição de dados pessoais, configurações de conta e histórico de reservas.

Administração: painel de controle para gerenciamento de usuários, temas e espaços.

### Wireframes

![arq](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-1-pe6-t2-turma-02-g4-sistema-para-coworking/blob/main/docs/img/Home.jpg)
![arq](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-1-pe6-t2-turma-02-g4-sistema-para-coworking/blob/main/docs/img/Login.jpg)
![arq](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-1-pe6-t2-turma-02-g4-sistema-para-coworking/blob/main/docs/img/Meet.jpg)
![arq](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-1-pe6-t2-turma-02-g4-sistema-para-coworking/blob/main/docs/img/Mesa.jpg)
![arq](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-1-pe6-t2-turma-02-g4-sistema-para-coworking/blob/main/docs/img/meeting.jpg)
![arq](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-1-pe6-t2-turma-02-g4-sistema-para-coworking/blob/main/docs/img/profile.jpg)


### Design Visual

O design adota um estilo moderno e minimalista, com foco em clareza e consistência:

Paleta de Cores:

Primária: verde‑azulado (#2B8A3E)

Secundária: laranja‑quente (#F78C15)

Neutras: branco (#FFFFFF), cinza‑claro (#F5F5F5), cinza‑escuro (#4A4A4A)

Tipografia: combinação das fontes "Inter" para títulos (peso 600‑700) e "Roboto" para textos (peso 400‑500), garantindo legibilidade em diferentes tamanhos.

Ícones e Elementos Gráficos: XXXXXXXX

## Fluxo de Dados

![arq](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-1-pe6-t2-turma-02-g4-sistema-para-coworking/blob/main/docs/img/fluxo_de_dados.png)

## Tecnologias Utilizadas

A aplicação foi desenvolvida utilizando um conjunto de tecnologias, organizadas em camadas para garantir escalabilidade, manutenibilidade e segurança. Abaixo estão as principais tecnologias aplicadas no projeto:

C# com ASP.NET Core – Utilizado para construir a API RESTful que expõe os serviços da aplicação. Estrutura baseada em Controllers, com autenticação via JWT e validações server-side.

Entity Framework Core – ORM utilizado para comunicação com o banco de dados SQL Server, permitindo mapeamento objeto-relacional, migrações e controle de transações.

SQL Server Express – Banco de dados relacional responsável pelo armazenamento de entidades como Usuários, Salas, Mesas e Reservas.

React.js – Framework JavaScript utilizado para o desenvolvimento do front-end web da aplicação, garantindo uma interface responsiva e dinâmica.

Flutter – Framework multiplataforma para a construção do aplicativo mobile, permitindo acesso rápido e nativo à funcionalidade de reservas.

JWT (JSON Web Tokens) – Implementado como mecanismo de autenticação e autorização entre cliente e servidor, protegendo rotas sensíveis.

Postman – Ferramenta utilizada para testes e validações dos endpoints da API durante o desenvolvimento.

Swagger (Swashbuckle) – Utilizado para geração automática da documentação interativa da API, facilitando a inspeção e o consumo por outros desenvolvedores.

## Considerações de Segurança

### Autenticação
Utiliza JWT (JSON Web Token) para autenticação stateless.

Os tokens são gerados no login e enviados em todas as requisições protegidas via header Authorization (Bearer {token}).

Tokens possuem tempo de expiração e são validados a cada requisição.

### Autorização
As rotas da API estão protegidas com políticas de autorização baseadas em perfis (usuario, admin).

Apenas usuários com permissão adequada podem executar ações sensíveis, como cadastro, edição e exclusão de dados.

### Validação de Dados
Todas as requisições são validadas server-side via data annotations e filtros personalizados no ASP.NET Core.

O uso de ModelState e mensagens padronizadas reduz o risco de entrada de dados maliciosos.

### Proteção contra ataques comuns
SQL Injection: mitigado com uso de Entity Framework Core (ORM seguro por padrão).

Cross-Site Scripting (XSS): controlado via escaping automático no React e validação dos inputs.

Cross-Site Request Forgery (CSRF): não aplicável diretamente a APIs REST com JWT (tokens não são enviados automaticamente pelo navegador).

Rate Limiting e throttling podem ser ativados para proteger endpoints públicos contra abusos.

### Armazenamento Seguro de Senhas
Senhas dos usuários são armazenadas como hashes criptografadas, utilizando algoritmo robusto como bcrypt, nunca em texto puro.

## Implantação

### Requisitos de Hardware e Software
Hardware mínimo recomendado:
CPU: 2 vCPUs
RAM: 4 GB
Armazenamento: 20 GB SSD
Conectividade: Porta 80 (HTTP) e 443 (HTTPS) liberadas

### Software necessário no servidor:
.NET SDK 8.0+
SQL Server Express ou outra instância compatível
IIS (opcional) ou uso via Kestrel/serviço Windows
Node.js e npm para build do front-end React
Git (para clonar o projeto)

### Plataforma de Hospedagem
Neste projeto, a aplicação será hospedada em: Servidor dedicado ou VPS (Windows Server) acessível via RDP um EC2 da AWS, com acesso apenas ao sistema operacional

### Preparação do ambiente
Acesse o servidor via RDP.

Instale o .NET SDK e o runtime:

bash
Copiar
Editar
dotnet --version
Configure o banco de dados:

Restaure o backup do SQL Server se necessário

Atualize a ConnectionString no appsettings.Production.json

Clone o projeto:

bash
Copiar
Editar
git clone https://github.com/seu-usuario/seu-repositorio.git
Compile a aplicação:

cd CoworkingAPI
dotnet publish -c Release -o ./publish

### Configuração de variáveis de ambiente
Crie variáveis no sistema ou use appsettings.Production.json para configurar:

JWT Key e Expiração

String de conexão do banco

CORS (separar domínios permitidos)

Logs e modo Production

Exemplo de appsettings.Production.json:


{
  "Jwt": {
    "Key": "chavesecretaprod",
    "Issuer": "CoworkingAPI",
    "Audience": "CoworkingFrontend",
    "ExpireMinutes": 60
  },
  "ConnectionStrings": {
    "DefaultConnection": "Server=localhost;Database=CoworkingDB;Trusted_Connection=True;"
  }
}

### Deploy da aplicação

Execute a API usando dotnet diretamente:
dotnet ./publish/CoworkingAPI.dll
Ou registre como um serviço do Windows para execução contínua.
Para servir como serviço:

Use sc.exe ou o utilitário NSSM (Non-Sucking Service Manager).

Configure para iniciar junto ao sistema.

### Front-end

Faça o build com:

npm install
npm run build
Copie a pasta build/ para o IIS ou use um servidor estático (

## Testes

Os testes de usuário realizados e suas evidências se encontram no pdf abaixo:

https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-1-pe6-t2-turma-02-g4-sistema-para-coworking/blob/main/docs/Teste_de_usuario.pdf)

# Referências

Inclua todas as referências (livros, artigos, sites, etc) utilizados no desenvolvimento do trabalho.
