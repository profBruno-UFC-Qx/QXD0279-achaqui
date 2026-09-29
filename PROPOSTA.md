# :checkered_flag: NOME DO PROJETO

Plataforma web que conecta moradores de Quixadá a profissionais autônomos (pedreiros, eletricistas, montadores de móveis, técnicos de informática, entre outros). Os profissionais divulgam seus serviços, e os clientes encontram, solicitam orçamento e avaliam quem prestou o trabalho.

## :technologist: Membros da equipe

- 569531 - Carlos Eduardo Teixeira Alves - SI
- 565382 - Geraldo Oliveira Pinho - SI
- 568458 - Gabriel Cavalcante Henrique Amorim - SI
- 568196 - João Davi Feitosa de Aquino Dantas - SI
- 567786 - Rafael Santos Silva - SI

## :bulb: Objetivo Geral
Desenvolver um sistema web que centralize a divulgação de serviços de profissionais autônomos da região de Quixadá, facilitando a busca por categoria e bairro, a solicitação de orçamentos e a construção de reputação por meio de avaliações de clientes reais.

## :eyes: Público-Alvo
Profissionais autônomos de Quixadá que precisam de visibilidade e clientes (pedreiros, eletricistas, encanadores, montadores de móveis, técnicos de informática, diaristas, entre outros).
Moradores e comerciantes da região que procuram profissionais de confiança para serviços residenciais ou comerciais.

## :star2: Impacto Esperado
Para os profissionais: mais visibilidade, alcance de novos clientes e reputação construída por avaliações, sem depender apenas de indicação boca a boca.
Para os clientes: menos tempo e incerteza na busca, com acesso a contato direto, faixa de preço dos serviços e opinião de quem já contratou.
Para a região: fortalecimento da economia local e valorização do trabalho autônomo.

## :people_holding_hands: Papéis ou tipos de usuário da aplicação

Visitante (não logado)	Navega pela área pública: busca e visualiza profissionais, serviços e avaliações.
Cliente	Usuário autenticado que solicita orçamentos, acompanha suas solicitações e avalia profissionais após a conclusão do serviço.
Profissional	Usuário autenticado que gerencia o próprio perfil e serviços e responde às solicitações recebidas.
Administrador	Gerencia todos os dados: usuários, categorias, bairros, aprovação de profissionais e moderação de avaliações.

> Tenha em mente que obrigatoriamente a aplicação deve possuir funcionalidades acessíveis a todos os tipos de usuário e outra funcionalidades restritas a certos tipos de usuários.

## :triangular_flag_on_post:	 Principais funcionalidades da aplicação

-> Acessíveis a todos (área pública)

Página inicial (/) com destaque de categorias e profissionais bem avaliados.
Listagem de profissionais com busca por nome, filtro por categoria e bairro, ordenação por nota e paginação.
Página de detalhes do profissional: bio, contato, serviços oferecidos e avaliações recebidas.

-> Restritas a usuários autenticados

Todos os logados

Cadastro, login e logout com autenticação JWT.
Edição dos próprios dados de conta.

Cliente

Enviar solicitação de orçamento a um profissional.
Acompanhar o status das solicitações (ENVIADA, ACEITA, RECUSADA, CONCLUIDA).
Avaliar o profissional (nota e comentário) após a solicitação concluída.

Profissional

Gerenciar o próprio perfil (bio, WhatsApp, categoria, bairro).
Cadastrar, editar e excluir seus serviços, com descrição e faixa de preço.
Aceitar, recusar e concluir as solicitações recebidas.

Administrador

Gerenciar usuários, categorias e bairros.
Aprovar ou bloquear perfis de profissionais.
Moderar avaliações.

-> Principais regras de negócio

Todo profissional novo inicia como PENDENTE e só aparece na área pública após aprovação do administrador.
Só é possível avaliar uma solicitação CONCLUIDA, com uma avaliação por solicitação.
Cliente não pode solicitar serviço a si mesmo nem a profissional pendente ou inativo.
Categoria com profissionais vinculados não pode ser excluída.
A média de notas do profissional é calculada automaticamente e exibida na listagem.

## :spiral_calendar: Entidades ou tabelas do sistema

- **Usuario:** dados de acesso e papel do usuário (ADMIN, PROFISSIONAL ou CLIENTE). Não depende de nenhuma outra entidade.
- **Categoria:** tipo de serviço prestado (pedreiro, eletricista, montador de móveis, técnico de informática...). Não depende de nenhuma outra entidade.
- **Bairro:** bairros e localidades de Quixadá, usados nos filtros de busca. Não depende de nenhuma outra entidade.
- **Profissional:** perfil, contato e status de aprovação. Relaciona-se com Usuario, Categoria e Bairro.
- **Servico:** serviço oferecido pelo profissional, com descrição e faixa de preço. Relaciona-se com Profissional.
- **Solicitacao:** pedido de orçamento com fluxo de status (ENVIADA, ACEITA, RECUSADA, CONCLUIDA). Relaciona-se com Cliente (Usuario), Profissional e Servico.
- **Avaliacao:** nota e comentário sobre um serviço concluído. Relaciona-se com Solicitacao.
