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

## Requisitos

As tabelas que se seguem apresentam os requisitos funcionais e não funcionais que detalham o escopo do projeto. Para determinar a prioridade de requisitos, aplicar uma técnica de priorização de requisitos e detalhar como a técnica foi aplicada.

### Requisitos Funcionais

|ID    | Descrição do Requisito  | Prioridade |
|------|-----------------------------------------|----|
|RF-001| Permitir que o usuário cadastre tarefas | ALTA | 
|RF-002| Emitir um relatório de tarefas no mês   | MÉDIA |

### Requisitos não Funcionais

|ID     | Descrição do Requisito  |Prioridade |
|-------|-------------------------|----|
|RNF-001| O sistema deve ser responsivo para rodar em um dispositivos móvel | MÉDIA | 
|RNF-002| Deve processar requisições do usuário em no máximo 3s |  BAIXA | 

Com base nas Histórias de Usuário, enumere os requisitos da sua solução. Classifique esses requisitos em dois grupos:

- [Requisitos Funcionais
 (RF)](https://pt.wikipedia.org/wiki/Requisito_funcional):
 correspondem a uma funcionalidade que deve estar presente na
  plataforma (ex: cadastro de usuário).
- [Requisitos Não Funcionais
  (RNF)](https://pt.wikipedia.org/wiki/Requisito_n%C3%A3o_funcional):
  correspondem a uma característica técnica, seja de usabilidade,
  desempenho, confiabilidade, segurança ou outro (ex: suporte a
  dispositivos iOS e Android).
Lembre-se que cada requisito deve corresponder à uma e somente uma
característica alvo da sua solução. Além disso, certifique-se de que
todos os aspectos capturados nas Histórias de Usuário foram cobertos.

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
