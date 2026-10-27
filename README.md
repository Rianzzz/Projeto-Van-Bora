# Van Bora

Aplicativo que conecta estudantes a motoristas de vans, com contratação, pagamento e acompanhamento da van em tempo real.

Projeto de Inovação Tecnológica I (PIT I) — Faculdade Cotemig, curso de Sistemas de Informação.

## Descrição do projeto

O Van Bora é um aplicativo móvel (Android e iOS) que reúne em um só lugar a busca, a contratação, o pagamento e o acompanhamento do transporte por van.

- **Estudante:** pesquisa vans por origem, destino e horário, compara opções, solicita uma vaga por período (de no máximo 6 meses) e dias da semana, paga pelo aplicativo depois que o motorista aceitar e acompanha a van no mapa, com alertas de proximidade.
- **Motorista:** cadastra sua van e CNH, vincula sua conta de recebimento, publica rotas com o valor por viagem, responde às solicitações, conduz a viagem com a sequência de paradas, registra embarques e ausências e consulta seus recebimentos.

O pagamento é feito dentro do aplicativo, por Pix ou cartão de crédito, e a plataforma retém 10% do valor do contrato como comissão. O Van Bora não armazena dados de cartão.

## Problema abordado

Como um software pode facilitar a conexão entre estudantes que procuram transporte por van e motoristas que possuem rotas compatíveis com a localização, o horário e o destino desses estudantes e, após a contratação e o pagamento do serviço, permitir o acompanhamento da viagem em tempo real com segurança e privacidade?

Hoje, a busca por vans depende de indicações, grupos de mensagens e redes sociais. As informações sobre rotas, horários e vagas ficam dispersas, o pagamento é combinado fora de um registro central e o estudante não sabe onde a van está nem quando ela chega ao ponto de embarque.

## Objetivos

**Objetivo geral:** desenvolver o projeto de um software denominado Van Bora, que permitirá conectar estudantes a motoristas de vans com rotas compatíveis com sua localização, horário e destino, formalizar a contratação do serviço, viabilizar o pagamento pelo próprio aplicativo e possibilitar o acompanhamento da viagem em tempo real pelos estudantes contratantes.

**Objetivos específicos:**

- Identificar as dificuldades de estudantes e motoristas na procura, na divulgação e na organização do transporte por van.
- Definir as funcionalidades de pesquisa, comparação e solicitação de vagas pelos estudantes e de cadastro e divulgação de rotas pelos motoristas.
- Definir o contrato entre estudante e motorista, com período de no máximo seis meses, dias da semana, pontos de embarque e desembarque, valor e situação.
- Definir o fluxo de precificação e de pagamento: valor por viagem definido pelo motorista, cobrança somente depois do aceite, comissão de 10% e reembolso proporcional em caso de cancelamento.
- Projetar o acompanhamento da van em tempo real, com mapa, previsão de chegada e alertas de proximidade.
- Projetar a área do motorista para iniciar, conduzir e finalizar viagens, com sequência otimizada de paradas e registro de embarques e ausências.
- Estabelecer requisitos de segurança e privacidade para o tratamento de dados de localização e de pagamento, em conformidade com a LGPD.

## Contribuidores

| Nome | GitHub |
|------|--------|
| Rian Nascimento Alves | [@Rianzzz](https://github.com/Rianzzz) |
| Gabriel Silvério da Silva | [@gabrielsilverioo](https://github.com/gabrielsilverioo) |
Orientador: Humberto Fernandes Villela — Faculdade Cotemig, Belo Horizonte.

## Tecnologias previstas

| Camada | Tecnologia | Justificativa |
|---|---|---|
| Aplicativo | React Native com Expo e TypeScript | Um só código para Android e iOS e acesso à localização em segundo plano para o motorista |
| API | Node.js com TypeScript e NestJS | Mesma linguagem do aplicativo; módulos, WebSocket e tarefas agendadas |
| Contrato da API | REST com JSON, documentada em OpenAPI | Interface clara entre aplicativo e servidor |
| Tempo real | WebSocket com Socket.IO | Entrega a posição da van ao estudante em poucos segundos |
| Banco de dados | MySQL 8 com Prisma (ORM) | Modelo já feito para MySQL; integridade e transações |
| Segurança | JWT, bcrypt, HTTPS/TLS | Autenticação, senhas protegidas e transmissão criptografada |
| Mapas e rotas | Google Maps Platform | Sequência de paradas, previsão de chegada e mapa |
| Pagamentos | Mercado Pago (Checkout Transparente, OAuth e webhooks) | Pix, cartão, vínculo da conta do motorista e divisão do pagamento |
| Notificações | Firebase Cloud Messaging | Alertas de proximidade e avisos de contrato, pagamento e viagem |
| Infraestrutura e qualidade | Docker, Nginx, Git e GitHub, GitHub Actions, Jest | Mesmo ambiente em desenvolvimento e implantação, versionamento e testes automáticos |

Mapas, notificações e pagamentos são acessados por interfaces substituíveis, de modo que o fornecedor possa ser trocado sem mudar as regras do sistema.

## Estrutura do repositório

```
van-bora/
├── README.md
├── docs/
│   ├── 01-problema-de-pesquisa/        Entrega 2
│   ├── 02-personas-e-historias/        Entrega 3
│   ├── 03-requisitos/                  Entrega 4
│   ├── 04-casos-de-uso/                Entrega 5
│   ├── 05-modelo-de-dados/             Entrega 6
│   ├── 06-diagrama-de-classes/
│   ├── 07-wireframes/
│   ├── 08-prototipo-e-arquitetura/     8ª entrega
│   └── 09-gestao/                      Product Backlog e Project Model Canvas
├── backend/                            API (NestJS)
├── mobile/                             Aplicativo (React Native com Expo)
└── database/                           Scripts do banco MySQL
```

## Fluxo de trabalho

- A branch `main` guarda a versão estável.
- Cada funcionalidade é desenvolvida em uma branch própria (por exemplo, `feature/us34-pagar-contrato`), com base no Product Backlog, e entra na `main` por pull request revisado pelo outro integrante.
- Os commits seguem o padrão de mensagens curtas no imperativo (por exemplo, `Adiciona cadastro de rota`).

## Status

Projeto em fase de planejamento e projeto: o levantamento de requisitos, a modelagem, o protótipo, a arquitetura, o Product Backlog e o Project Model Canvas estão em `docs/`. A implementação seguirá as releases do Product Backlog: Release 1 (contratação e pagamento), Release 2 (viagem e acompanhamento) e Release 3 (complementos).
