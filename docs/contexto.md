# Introdução

Este documento apresenta o contexto para o desenvolvimento do Sistema para Coworking, abordando sua justificativa, objetivos e público-alvo. O projeto visa criar uma plataforma tecnológica que facilite a gestão e a reserva de espaços compartilhados, oferecendo uma experiência otimizada tanto para usuários quanto para administradores.

## Problema
Muitos espaços de coworking enfrentam desafios na organização e gestão de reservas, frequentemente utilizando processos manuais ou sistemas fragmentados. Isso pode resultar em agendamentos conflitantes, falta de transparência na disponibilidade de recursos e dificuldades na comunicação com os usuários, impactando negativamente a eficiência operacional e a satisfação dos clientes.

## Objetivos

O Sistema para Coworking tem como objetivo principal fornecer uma plataforma integrada (web e mobile) que permita aos usuários visualizar e reservar salas e mesas de acordo com a disponibilidade em tempo real. Além disso, oferecerá um painel administrativo para que os gestores dos espaços possam monitorar e gerenciar as reservas de forma eficaz.

## Justificativa

O mercado de coworking no Brasil tem experimentado um crescimento significativo nos últimos anos. De acordo com o Censo Coworking 2024, realizado pela Woba, o número de espaços de coworking no país aumentou aproximadamente 20% em um ano, totalizando 2.986 espaços ativos. Esse crescimento é impulsionado pela demanda por ambientes de trabalho flexíveis, especialmente devido à popularização do trabalho híbrido e remoto.

Além disso, a pesquisa indica que 91% dos coworkings brasileiros se posicionam como multidisciplinares, atendendo profissionais de diversos segmentos. Isso ressalta a necessidade de sistemas eficientes que possam gerenciar a diversidade de usuários e suas respectivas demandas.

A implementação de uma plataforma integrada para gestão de reservas não apenas otimiza a operação dos espaços, mas também melhora a experiência do usuário, promovendo maior transparência e facilidade no processo de agendamento.

REFERÊNCIA: <https://www.terra.com.br/economia/meu-negocio/censo-do-coworking-2024-revela-crescimento-do-setor-no-brasil%2C6e44c008ed53d31c86b4a3dc4e18b8dfx2t4r92o.html?utm_source=chatgpt.com>

## Público-Alvo

O sistema será direcionado para os seguintes perfis:

Profissionais Autônomos e Freelancers: Indivíduos que buscam um ambiente profissional fora de casa para aumentar sua produtividade e expandir sua rede de contatos. Geralmente, possuem familiaridade com ferramentas tecnológicas e valorizam a flexibilidade e o networking proporcionados pelos coworkings.

Pequenas Empresas e Startups: Empresas em fase inicial ou em crescimento que necessitam de espaços de trabalho flexíveis e escaláveis. Esses usuários frequentemente procuram soluções que ofereçam infraestrutura completa sem os altos custos de um escritório próprio.

Empresas Adotando Modelos Híbridos/Remotos: Organizações estabelecidas que implementaram políticas de trabalho remoto ou híbrido e buscam espaços para reuniões presenciais, treinamentos ou para colaboradores que preferem não trabalhar exclusivamente de casa.

Administradores de Espaços de Coworking: Profissionais responsáveis pela gestão e operação dos coworkings, que necessitam de ferramentas eficientes para gerenciar reservas, pagamentos e a comunicação com os membros.

De acordo com estudos, a idade média dos usuários de coworking no Brasil é de 33 anos, com uma distribuição equilibrada entre homens e mulheres. As áreas de atuação mais comuns incluem tecnologia, comunicação, design, administração e serviços. Esses profissionais geralmente possuem nível superior completo ou pós-graduação e buscam nos coworkings não apenas um espaço físico, mas também oportunidades de networking e colaboração.

REFERÊNCIA: <https://clubcoworking.com.br/perfil-do-coworker-qual-e/?utm_source=chatgpt.com>

# Especificações do Projeto

--- Escopo do Projeto ---
O projeto contempla o desenvolvimento de:
Backend e API: Implementação em C# e ASP.NET, responsável pela lógica de negócios e comunicação com o banco de dados.
Banco de Dados: Uso do SQL Server Express para armazenar informações sobre usuários, reservas e disponibilidade de salas/mesas.
Frontend: Aplicação web desenvolvida em React.js, proporcionando uma interface intuitiva para os usuários realizarem reservas.
Aplicativo Mobile: Desenvolvido em Flutter, permitindo que os usuários façam reservas diretamente pelo smartphone.
--- Funcionalidades Principais ---
Cadastro e autenticação de usuários
Visualização de salas/mesas disponíveis
Reserva e cancelamento de espaços
Painel administrativo para gerenciamento das reservas
Notificações e confirmação de agendamentos

## Requisitos do Sistema para Coworking

## 1. Requisitos Funcionais (RF)
Os requisitos funcionais descrevem as funcionalidades que o sistema deve oferecer.

| Código  | Descrição | Prioridade |
|---------|-----------|------------|
| **RF01** | O sistema deve permitir o cadastro, login e autenticação de usuários. | **Alta** |
| **RF02** | O usuário deve poder visualizar salas e mesas disponíveis para reserva. | **Alta** |
| **RF03** | O usuário deve poder realizar reservas de salas e mesas, selecionando data e horário. | **Alta** |
| **RF04** | O usuário deve poder cancelar ou modificar suas reservas. | **Média** |
| **RF05** | O sistema deve exibir notificações no site/aplicativo sobre confirmação, cancelamento e lembretes de reservas. | **Média** |
| **RF06** | O administrador deve poder gerenciar usuários e suas permissões. | **Alta** |
| **RF07** | O administrador deve poder visualizar e gerenciar reservas. | **Alta** |
| **RF08** | O sistema deve permitir o cadastro e edição de salas/mesas, incluindo capacidade e recursos disponíveis. | **Alta** |
| **RF09** | O sistema deve oferecer relatórios sobre ocupação e uso dos espaços. | **Baixa** |
| **RF10** | O sistema deve permitir o pagamento online das reservas, caso necessário. | **Baixa** |

---

## 2. Requisitos Não Funcionais (RNF)
Os requisitos não funcionais definem características e restrições técnicas do sistema.

| Código  | Descrição | Prioridade |
|---------|-----------|------------|
| **RNF01** | O sistema deve ser desenvolvido com **C# e ASP.NET** no backend. | **Alta** |
| **RNF02** | O frontend da aplicação web deve ser desenvolvido em **React.js**. | **Alta** |
| **RNF03** | O aplicativo mobile deve ser desenvolvido em **Flutter**. | **Alta** |
| **RNF04** | O banco de dados deve ser o **SQL Server Express**. | **Alta** |
| **RNF05** | A interface do sistema deve ser responsiva e acessível em dispositivos móveis e desktop. | **Alta** |
| **RNF06** | O sistema deve garantir **segurança de dados**, com criptografia de senhas e comunicação segura (SSL/TLS). | **Alta** |
| **RNF07** | O sistema deve ser compatível com os navegadores **Chrome, Firefox, Edge e Safari**. | **Média** |
| **RNF08** | O sistema deve ter um **design intuitivo e acessível**, seguindo diretrizes de UX/UI. | **Média** |




## Restrições

O projeto está restrito pelos itens apresentados na tabela a seguir.

|ID| Restrição                                             |
|--|-------------------------------------------------------|
|01| O projeto deverá ser entregue até o final do semestre |
|02| Não pode ser desenvolvido um módulo de backend        |

Enumere as restrições à sua solução. Lembre-se de que as restrições geralmente limitam a solução candidata.

> **Links Úteis**:
> - [O que são Requisitos Funcionais e Requisitos Não Funcionais?](https://codificar.com.br/requisitos-funcionais-nao-funcionais/)
> - [O que são requisitos funcionais e requisitos não funcionais?](https://analisederequisitos.com.br/requisitos-funcionais-e-requisitos-nao-funcionais-o-que-sao/)

# Catálogo de Serviços

Descreva aqui todos os serviços que serão disponibilizados pelo seu projeto, detalhando suas características e funcionalidades.

# Arquitetura da Solução

Definição de como o software é estruturado em termos dos componentes que fazem parte da solução e do ambiente de hospedagem da aplicação.

![arq](https://github.com/user-attachments/assets/b9402e05-8445-47c3-9d47-f11696e38a3d)


## Tecnologias Utilizadas

Descreva aqui qual(is) tecnologias você vai usar para resolver o seu problema, ou seja, implementar a sua solução. Liste todas as tecnologias envolvidas, linguagens a serem utilizadas, serviços web, frameworks, bibliotecas, IDEs de desenvolvimento, e ferramentas.

Apresente também uma figura explicando como as tecnologias estão relacionadas ou como uma interação do usuário com o sistema vai ser conduzida, por onde ela passa até retornar uma resposta ao usuário.

## Hospedagem

Explique como a hospedagem e o lançamento da plataforma foi feita.

> **Links Úteis**:
>
> - [Website com GitHub Pages](https://pages.github.com/)
> - [Programação colaborativa com Repl.it](https://repl.it/)
> - [Getting Started with Heroku](https://devcenter.heroku.com/start)
> - [Publicando Seu Site No Heroku](http://pythonclub.com.br/publicando-seu-hello-world-no-heroku.html)
