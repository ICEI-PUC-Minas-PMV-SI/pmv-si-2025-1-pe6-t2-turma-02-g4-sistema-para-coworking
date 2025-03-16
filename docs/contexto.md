# Introdução

Com o crescimento do trabalho híbrido e remoto, os espaços de coworking se tornaram uma alternativa essencial para profissionais autônomos, startups e empresas que buscam flexibilidade e infraestrutura adequada. No entanto, a gestão eficiente desses espaços ainda representa um desafio, principalmente quando realizada de forma manual ou com sistemas pouco integrados.

Este projeto propõe o desenvolvimento de um Sistema para Coworking, uma plataforma web e mobile que permite aos usuários visualizar e reservar salas e mesas em tempo real. Além disso, oferece um painel administrativo para que gestores possam monitorar e gerenciar reservas de forma eficiente.

O objetivo é otimizar a operação dos espaços de coworking, evitando agendamentos conflitantes e melhorando a experiência dos usuários por meio de um sistema intuitivo, seguro e de fácil acesso. A plataforma também contará com recursos como notificações sobre reservas, relatórios de ocupação e, opcionalmente, pagamento online.

Diante do crescimento contínuo desse mercado no Brasil, uma solução tecnológica como essa se torna fundamental para garantir um ambiente organizado, acessível e funcional tanto para os usuários quanto para os administradores dos espaços de coworking.

## Problema
Muitos espaços de coworking enfrentam desafios na organização e gestão de reservas, frequentemente utilizando processos manuais ou sistemas fragmentados. Isso pode resultar em agendamentos conflitantes, falta de transparência na disponibilidade de recursos e dificuldades na comunicação com os usuários, impactando negativamente a eficiência operacional e a satisfação dos clientes.

## Objetivos

Desenvolver um backend robusto para gerenciar a lógica de negócios e garantir a comunicação eficiente com o banco de dados.

Implementar um banco de dados relacional, armazenando informações sobre usuários, reservas e disponibilidade de salas e mesas com integridade e segurança.

Criar uma aplicação web responsiva com React.js, permitindo que os usuários realizem reservas de forma intuitiva e visualizem a disponibilidade em tempo real.

Desenvolver um aplicativo mobile em Flutter para possibilitar o acesso rápido e prático às reservas diretamente pelo smartphone.

Oferecer um painel administrativo que permita aos gestores visualizar, monitorar e gerenciar reservas, garantindo um controle eficiente do espaço de coworking.

Garantir a segurança dos dados através da criptografia de senhas, comunicação segura (SSL/TLS) e conformidade com a LGPD.

Assegurar a escalabilidade e desempenho do sistema, garantindo suporte para pelo menos 1.000 usuários simultâneos com tempo de resposta inferior a 2 segundos.

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

## Requisitos do Sistema para Coworking

## 1. Requisitos Funcionais (RF)
Os requisitos funcionais descrevem as funcionalidades que o sistema deve oferecer.

| Código  | Descrição | Prioridade | Responsável |
|---------|-----------|------------|-------------|
| **RF01** | O sistema deve permitir o  Gestão de usuários. | **Alta** | Fillipe |
| **RF02** | O sistema deve permitir o  Gestão de salas e mesas, incluindo capacidade e recursos disponíveis. | **Alta** | Túlio |
| **RF03** | O sistema deve permitir o  Gestão de reservas de salas e mesas. | **Alta** | Nicollas |
| **RF04** | O sistema deve permitir a vizualização de salas e mesas disponíveis para reserva com data e hora. | **Alta** | Vinicius |
| **RF05** | O sistema deve exibir notificações no site/aplicativo sobre confirmação, cancelamento e lembretes de reservas. | **Média** | Josenilson |
| **RF06** | O administrador deve poder gerenciar usuários e suas permissões. | **Alta** | Fillipe |
| **RF07** | O administrador deve poder visualizar e gerenciar reservas. | **Alta** | Nicollas |
| **RF08** | O sistema deve oferecer relatórios sobre ocupação e uso dos espaços. | **Baixa** | Tulio |
| **RF09** | O sistema deve permitir o pagamento online das reservas, caso necessário. | **Baixa** | Vinicius |

## 2. Requisitos Não Funcionais (RNF)
Os requisitos não funcionais definem características e restrições técnicas do sistema.

| Código  | Descrição | Prioridade |
|---------|-----------|------------|
| **RNF01** | O sistema deve ser entregue até o final do semestre. | **Alta** |
| **RNF02** | O sistema não deve ter custo financeiro. | **Alta** |
| **RNF03** | O sistema deve ser hospedado em um ambiente que suporte um mínimo de 1.000 usuários simultâneos. |
| **RNF04** | Deve ser implementado um banco de dados relacional que suporte transações simultâneas e integridade referencial. |
| **RNF05** | O sistema deve estar disponível 24/7, garantindo alta disponibilidade para os usuários. |
| **RNF06** | O sistema deve seguir normas de proteção de dados e privacidade, como a **LGPD (Lei Geral de Proteção de Dados)**. |
| **RNF07** | Os relatórios sobre ocupação e uso dos espaços devem ser gerados em formato **visual e acessível** para facilitar a análise de dados. |
| **RNF08** | O projeto deverá ser entregue até o final do semestre |


## Restrições

O projeto está restrito pelos itens apresentados na tabela a seguir.

| ID  | Restrição |
|-----|---------------------------------------------------------------|
| **R01** | O projeto deverá ser entregue até o final do semestre |



# Catálogo de Serviços

| **Serviço** | **Descrição** | **Funcionalidades** | **Restrições** |
|-------------|-------------|--------------------|---------------|
| **Gestão de Usuários** | Permite que usuários se cadastrem, gerenciem suas informações e acessem o sistema com diferentes níveis de permissão. | Cadastro de novos usuários com autenticação segura. <br> Login e recuperação de senha. <br> Atualização de informações pessoais. <br> Definição de permissões para administradores e usuários comuns. | Apenas administradores podem alterar permissões de usuários. <br> As senhas devem ser armazenadas com criptografia. <br> O acesso ao sistema deve ser feito via autenticação segura. |
| **Gestão de Salas e Mesas** | Permite que administradores cadastrem, editem e removam salas e mesas disponíveis para reserva. | Cadastro de salas e mesas, incluindo capacidade e recursos disponíveis (Wi-Fi, projetores, lousas digitais etc.). <br> Atualização de informações sobre as salas e mesas. <br> Remoção de espaços que não estarão mais disponíveis. | Apenas administradores podem cadastrar ou remover salas e mesas. <br> As informações devem estar sempre sincronizadas para evitar conflitos de reserva. |
| **Reservas de Salas e Mesas** | Permite que usuários realizem reservas de salas e mesas com data e hora específicas. | Consulta de disponibilidade de salas e mesas. <br> Realização de reservas com data e hora. <br> Cancelamento e modificação de reservas. | As reservas devem ser validadas em tempo real para evitar conflitos. <br> Apenas o usuário que realizou a reserva pode cancelá-la ou modificá-la. |
| **Notificações no Site/Aplicativo** | O sistema exibirá notificações internas para manter os usuários informados sobre suas reservas. | Notificação de confirmação de reserva. <br> Lembretes de reserva próximos ao horário agendado. <br> Notificação sobre cancelamento ou modificação da reserva. | As notificações serão apenas no site/aplicativo, sem uso de SMS ou e-mail. |
| **Gestão de Reservas pelo Administrador** | Os administradores terão acesso a um painel para visualizar e gerenciar todas as reservas do sistema. | Consulta de todas as reservas realizadas no coworking. <br> Cancelamento de reservas em casos necessários. | Apenas administradores podem visualizar e modificar reservas de outros usuários. |
| **Relatórios de Ocupação e Uso** | Geração de relatórios detalhados sobre a ocupação dos espaços e padrões de uso. | Geração de relatórios em formato visual e acessível. <br> Exibição de estatísticas sobre salas mais reservadas, horários de pico, taxa de ocupação, etc. | Apenas administradores terão acesso aos relatórios completos. |
| **Pagamento Online (Opcional)** | Possibilidade de realizar pagamentos online para reservas, caso o coworking tenha planos pagos. | Integração com meios de pagamento online (cartão de crédito, Pix, boleto). <br> Histórico de pagamentos e recibos. | O serviço de pagamento será opcional e ativado apenas se necessário. |



# Arquitetura da Solução

A arquitetura do sistema será baseada em uma abordagem cliente-servidor, utilizando uma estrutura multi-camada para garantir modularidade, escalabilidade e manutenibilidade. O sistema será composto pelas camadas Apresentação (Frontend e Mobile), de Aplicação (Backend e API) e de Dados (Banco de Dados).

![arq](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-1-pe6-t2-turma-02-g4-sistema-para-coworking/blob/main/docs/img/arquitetura.drawio%20(1).png)


## Tecnologias Utilizadas

1 - C# e ASP.NET → Responsável pela lógica de negócios e comunicação com o banco de dados.
2 - Banco de Dados: SQL Server Express → Armazena informações sobre usuários, reservas e disponibilidade de salas/mesas.
3 - React.js → Proporciona uma interface intuitiva para os usuários realizarem reservas.
4 - Flutter → Permite que os usuários façam reservas diretamente pelo smartphone.




## Hospedagem

Explique como a hospedagem e o lançamento da plataforma foi feita.

> **Links Úteis**:
>
> - [Website com GitHub Pages](https://pages.github.com/)
> - [Programação colaborativa com Repl.it](https://repl.it/)
> - [Getting Started with Heroku](https://devcenter.heroku.com/start)
> - [Publicando Seu Site No Heroku](http://pythonclub.com.br/publicando-seu-hello-world-no-heroku.html)
