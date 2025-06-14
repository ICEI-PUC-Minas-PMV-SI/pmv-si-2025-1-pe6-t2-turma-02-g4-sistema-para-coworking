# Front-end Móvel

Este projeto visa desenvolver uma interface móvel para um sistema de gestão de coworking, que permita aos usuários visualizar e reservar salas e mesas de maneira simples, rápida e eficiente. O foco está em proporcionar uma experiência de usuário fluida, segura e responsiva, tanto para clientes quanto para administradores do espaço.

## Projeto da Interface

A interface móvel foi projetada com foco na usabilidade, priorizando clareza, simplicidade e acesso direto às funcionalidades principais. O layout segue o conceito mobile-first, garantindo compatibilidade com dispositivos de diferentes tamanhos de tela, especialmente smartphones.

### Funcionalidades principais:

- Login e Cadastro de Usuário  
- Visualização de Salas com Imagens  
- Reserva de Salas  
- Painel Administrativo para gerenciamento  
- Formulário para criação, edição e exclusão de usuários  
- Busca por ID  
- Visualização de todos os usuários cadastrados  

As interações foram projetadas para serem intuitivas, com botões bem visíveis, campos de formulário organizados e feedback claro ao usuário. Ícones de navegação ajudam a reforçar a experiência mobile, e o sistema mantém consistência de navegação com cabeçalhos e menus fixos.

### Wireframes

<p align="center">
  <img src="https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-1-pe6-t2-turma-02-g4-sistema-para-coworking/blob/main/docs/img/painel2.png?raw=true" width="550px" />
  <img src="https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-1-pe6-t2-turma-02-g4-sistema-para-coworking/blob/main/docs/img/root2.png?raw=true" width="550px" />
  <img src="https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-1-pe6-t2-turma-02-g4-sistema-para-coworking/blob/main/docs/img/sistema2.png?raw=true" width="550px" />
  <img src="https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-1-pe6-t2-turma-02-g4-sistema-para-coworking/blob/main/docs/img/gerenciar.png?raw=true" width="550px" />
</p>

### Design Visual

O design visual da aplicação segue uma estética moderna e minimalista, com foco na clareza das informações e facilidade de uso:

- **Paleta de Cores:** tons de verde (destaque para botões e cabeçalhos), branco e cinza-claro para fundo e áreas neutras, reforçando um ambiente limpo e profissional.  
- **Tipografia:** fontes sem serifa (como Inter ou Roboto) foram utilizadas para garantir legibilidade em telas pequenas.  
- **Ícones:** ícones simples e funcionais foram usados para facilitar a navegação, seguindo o padrão de aplicações mobile modernas.  
- **Componentes:** botões com cantos arredondados, campos de input bem espaçados, e cards para exibir conteúdos visuais (como salas disponíveis).  

## Fluxo de Dados

O fluxo de dados na aplicação segue uma estrutura clara entre o cliente (mobile) e o backend:

### Login e Autenticação

- Usuário envia email e senha  
- Backend valida e retorna token/autorização  

### Visualização de Salas

- App requisita lista de salas disponíveis  
- Backend retorna dados com imagens, horários e identificadores  

### Reserva

- Usuário escolhe sala e envia solicitação de reserva  
- Backend valida disponibilidade e confirma/agrega ao banco  

### Administração (caso autorizado)

- Acesso ao painel administrativo  
- CRUD de usuários, salas, mesas e reservas via formulários  
- Dados são enviados e recebidos via API RESTful  

### Notificações

- Backend dispara confirmações e lembretes por e-mail/push notification (em etapas futuras)  

Esse fluxo é mediado por uma API central, que garante a sincronização dos dados entre o app mobile, a aplicação web e o painel administrativo.

## Tecnologias Utilizadas

O projeto do sistema de coworking utiliza as seguintes tecnologias principais:

- **Flutter:** Usado para o desenvolvimento do front-end do aplicativo móvel.  
- **C# com ASP.NET:** Responsável pelo desenvolvimento do backend e da API, incluindo toda a lógica de negócios.  
- **SQL Server Express:** Banco de dados utilizado para armazenar informações sobre usuários, reservas, salas e mesas.  
- **RESTful API:** Estrutura de endpoints organizada por recursos como autenticação, usuários, salas, mesas e reservas.  
- **JWT (JSON Web Token):** Utilizado para autenticação e autorização dos usuários.  

## Considerações de Segurança

A segurança da aplicação foi planejada com base nos seguintes pontos:

- **Autenticação via JWT:** O login gera um token JWT que deve ser enviado no cabeçalho `Authorization` em rotas protegidas.  
- **Autorização por perfil:** A aplicação diferencia permissões entre usuários comuns e administradores.  
- **Validações:** A API aplica regras de negócio e validações antes de persistir dados no banco.  
- **Rotas protegidas:** Apenas usuários autenticados podem acessar recursos específicos.  
- **Uso interno:** A API não é aberta para terceiros, sendo usada apenas pelas interfaces web (React.js) e mobile (Flutter).  


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
