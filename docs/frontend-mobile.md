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

# Documentação de Implantação - Sistema de Coworking

Este documento descreve os requisitos e procedimentos para implantar a aplicação de Coworking em um ambiente de produção.

## Requisitos de Hardware e Software

### Hardware Recomendado

| Componente         | Mínimo Recomendado | Ideal para Escalabilidade |
|--------------------|--------------------|----------------------------|
| CPU                | 2 vCPUs            | 4+ vCPUs                   |
| Memória RAM        | 4 GB               | 8+ GB                      |
| Armazenamento SSD  | 50 GB              | 100+ GB                    |
| Largura de banda   | 10 Mbps            | 50+ Mbps                   |

### Software Necessário

#### Backend (ASP.NET Core)

- .NET SDK (ex: .NET 7 ou 8)
- IIS (Windows Server) ou Kestrel (Linux)
- Runtime do .NET instalado

#### Frontend (React)

- Node.js (LTS)
- npm ou yarn
- Webpack (opcional)

#### Mobile (Flutter)

- Apenas para build e publicação (APK/IPA)
- Não exige hospedagem no servidor

#### Banco de Dados

- SQL Server Express (desenvolvimento) ou Azure SQL Database / SQL Server Web (produção)
- SQL Server Management Studio (SSMS)

---

## Escolha da Plataforma de Hospedagem

### Comparativo

| Provedor  | AWS EC2 + RDS         | Azure App Service + SQL DB |
|-----------|------------------------|-----------------------------|
| Backend   | EC2 (Linux ou Windows) | App Service (Windows/Linux)|
| Banco     | RDS (SQL Server)       | Azure SQL Database          |
| Frontend  | S3 + CloudFront        | Azure Blob Storage + CDN    |
| Escalável | Alta                   | Alta                        |
| Custo     | Flexível               | Gerenciado, mais simples    |

### Recomendação

**Azure App Service + Azure SQL Database**

- Integração com Visual Studio, GitHub Actions e Azure DevOps
- Escalabilidade automática
- Deploy simplificado com integração contínua
- Segurança e backups automáticos

---

## Configuração do Ambiente de Implantação

### Estrutura Geral do Projeto

``bash
/project-root
|-- backend/ (ASP.NET)
|-- frontend/ (React)
|-- mobile/ (Flutter)
|-- database/ (Scripts SQL)
|-- .env (variáveis sensíveis)

## Variáveis de Ambiente

### Backend (.NET)
```env
ASPNETCORE_ENVIRONMENT=Production
ConnectionStrings__DefaultConnection=Server=sqlserver-url;Database=coworkingdb;User Id=admin;Password=senha123;
```
### Frontend (React)
```env
REACT_APP_API_URL=https://api.seudominio.com
```

### Mobile (Flutter)
```env
API_URL=https://api.seudominio.com
```

## Testes

## Estratégia de Testes do Aplicativo Mobile (Flutter Web - VSCode/Chrome)

Durante a fase inicial de validação funcional do aplicativo mobile, foi adotada uma estratégia de testes utilizando a execução local por meio do comando `flutter run`, com destino ao navegador **Chrome**, via **Visual Studio Code**.

Essa abordagem permitiu simular a experiência do usuário de forma ágil, especialmente útil para validar a interface, navegação e comunicação com a API.

---

### Ambiente de Testes

- **Editor**: Visual Studio Code
- **Comando de execução**: `flutter run -d chrome`
- **Plataforma de destino**: Navegador Web (Chrome)
- **Ambiente de backend**: API ASP.NET rodando localmente ou hospedada na nuvem (Azure/AWS)
- **Banco de dados**: SQL Server Express, acessado pela API

---

### Tipos de Testes Realizados

| Tipo de Teste            | Descrição                                                                 |
|--------------------------|---------------------------------------------------------------------------|
| Teste Funcional          | Verificação do comportamento esperado das funcionalidades principais     |
| Teste de Navegação       | Checagem de fluxos entre telas (login, reserva, perfil, etc.)            |
| Teste de Interface       | Validação visual dos componentes (botões, formulários, listas, etc.)     |
| Teste de Integração API  | Simulação de requisições reais para a API (login, cadastro, reservas)    |
| Teste de Formulário      | Verificação de validações de campos obrigatórios, formatos e mensagens   |

---

### Casos de Teste Exemplares

1. **Login com credenciais válidas**
   - Entrar com e-mail e senha válidos
   - Esperado: Redirecionamento para a tela inicial do usuário

2. **Reserva de uma mesa**
   - Selecionar data, horário e mesa
   - Confirmar reserva
   - Esperado: Exibição de mensagem de sucesso e inclusão na lista de reservas

3. **Validação de campos obrigatórios**
   - Tentar salvar reserva sem data
   - Esperado: Exibição de erro informando campo obrigatório

4. **Atualização de perfil**
   - Alterar nome ou e-mail
   - Esperado: Dados atualizados após confirmação

---

### Limitações da Estratégia

- O teste via Chrome não representa com total fidelidade o comportamento em dispositivos móveis (iOS/Android)
- Algumas funcionalidades específicas de mobile (notificações push, câmera, sensores) não são testáveis via web
- Diferenças de layout/responsividade entre web e dispositivos móveis podem existir

---

### Conclusão

Essa estratégia de testes via `flutter run` no Chrome se mostrou eficaz para validar funcionalidades principais e a integração com o backend. Para garantir qualidade total, é recomendada uma fase posterior de testes em dispositivos físicos ou emuladores Android/iOS.

A execução dos testes segue no documento em PDF na pasta docs conforme link abaixo.
[📄 Testes Coworking Mobile (PDF)](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-1-pe6-t2-turma-02-g4-sistema-para-coworking/blob/main/docs/Testes%20Coworking%20Mobile.pdf)
[📥 Baixar Testes Coworking Mobile (PDF)](https://raw.githubusercontent.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-1-pe6-t2-turma-02-g4-sistema-para-coworking/main/docs/Testes%20Coworking%20Mobile.pdf)


# Referências

## 📚 Referências Bibliográficas

- ALUR, R. et al. *Principles of Web Design and Application Development*. Springer, 2020.

- FREEMAN, Eric; FREEMAN, Elisabeth. *Use a Cabeça!: Padrões de Projetos*. Alta Books, 2ª edição, 2021.

- TROELSEN, Andrew; JAPIKSE, Philip. *Pro C# 10 with .NET 6: Foundational Principles and Practices in Programming*. Apress, 2022.

- LIBERTI, Alberto. *Desenvolvimento de APIs REST com ASP.NET Core*. Casa do Código, 2022.  
  [https://www.casadocodigo.com.br/products/livro-aspnet-core](https://www.casadocodigo.com.br/products/livro-aspnet-core)

- ECKSTEIN, Robert. *Flutter for Beginners: An Introductory Guide to Building Cross-Platform Mobile Applications with Flutter and Dart 2*. Packt Publishing, 2020.

- WILLIAMS, Ben. *Full-Stack React Projects*. Packt Publishing, 2ª edição, 2022.

- Microsoft Docs. *ASP.NET Core Documentation*.  
  [https://learn.microsoft.com/en-us/aspnet/core/](https://learn.microsoft.com/en-us/aspnet/core/)

- Flutter Docs. *Flutter – Beautiful native apps in record time*.  
  [https://flutter.dev/docs](https://flutter.dev/docs)

- ReactJS Docs. *React – A JavaScript library for building user interfaces*.  
  [https://reactjs.org/docs/getting-started.html](https://reactjs.org/docs/getting-started.html)

- Microsoft Learn. *SQL Server Documentation*.  
  [https://learn.microsoft.com/en-us/sql/sql-server/](https://learn.microsoft.com/en-us/sql/sql-server/)

- AWS Docs. *Amazon EC2 e Amazon RDS Documentation*.  
  [https://docs.aws.amazon.com/](https://docs.aws.amazon.com/)

- Microsoft Azure. *Guia de início rápido para App Services e Azure SQL Database*.  
  [https://learn.microsoft.com/pt-br/azure/app-service/](https://learn.microsoft.com/pt-br/azure/app-service/)

- FIELDING, Roy T. *Architectural Styles and the Design of Network-based Software Architectures*. University of California, 2000.  
  [https://www.ics.uci.edu/~fielding/pubs/dissertation/top.htm](https://www.ics.uci.edu/~fielding/pubs/dissertation/top.htm)

- ISO/IEC. *ISO/IEC 25010:2011 – Systems and software engineering — Systems and software Quality Requirements and Evaluation (SQuaRE)*.  
  [https://iso.org/standard/35733.html](https://iso.org/standard/35733.html)


