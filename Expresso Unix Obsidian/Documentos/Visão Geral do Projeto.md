
O aplicativo funciona como um "cardápio" digital de serviços, similar a um de restaurante, mas para viagens e aluguel de veículos. A plataforma é um "white-label", o que significa que o design da interface é padronizado, mas a empresa pode personalizá-lo com suas próprias informações, como fotos e cores. A plataforma também permite que a empresa crie e gerencie suas próprias categorias de serviços, como "viagens" ou "aluguel".

A comunicação é um ponto central do projeto, com uma forte ênfase na integração com o WhatsApp. A plataforma visa resolver problemas como a desorganização de grupos e o excesso de contatos de clientes nos telefones dos motoristas, permitindo o envio de mensagens automatizadas e diretas para os clientes de forma individual.

---

## Tipos de Usuário e Funcionalidades

O projeto define três papéis de usuário principais, além do cliente final:

- ADM (Administrador): É o responsável pela empresa. Ele tem acesso total à plataforma, podendo visualizar e alterar todas as informações. O cadastro da empresa é feito pelos desenvolvedores do projeto, que criam a conta e fornecem o link, usuário e senha para o ADM.
    
- Funcionários da Gestão: Eles gerenciam as viagens e as reservas. Têm acesso aos dados das viagens, informações sobre os clientes que reservaram e pagaram (ou estão com pagamento pendente), e podem editar informações da viagem, com notificações automáticas enviadas aos clientes. Eles também podem cancelar passagens que não foram pagas dentro do prazo.
    
- Motorista: Este usuário tem acesso limitado, focado apenas em suas próprias viagens. Para cada viagem, ele pode ver o percurso, o veículo e uma lista de passageiros com seus números de WhatsApp para contato direto ou envio de mensagens automatizadas, como avisos de partida ou paradas.
    

---

### Jornada do Cliente

O cliente não precisa criar uma conta ou fazer login para usar a plataforma. O processo de reserva é simplificado:

1. Contato: O cliente entra em contato com a empresa, geralmente via WhatsApp.
    
2. Link de acesso: A empresa envia um link único para o cliente.
    
3. Reserva: Ao clicar no link, o cliente acessa a tela com os serviços disponíveis. Ele pode escolher o serviço, verificar detalhes como horários e assentos, e reservar a passagem. Para finalizar, ele informa seu nome, e-mail e número de telefone.
    
4. Pagamento: Há uma discussão sobre a implementação de pagamentos online na plataforma. Embora haja discordância, o consenso aponta para a necessidade de incluir opções como  
    PIX (via QR Code) e cartão de débito/crédito, pois o "ingresso online" é um atrativo vital.
    
5. Ingresso: Após o pagamento, o cliente recebe um ingresso gerado com suas informações (nome, e-mail, número de telefone). O ingresso é enviado tanto para o e-mail quanto para o WhatsApp do cliente.
    

---

### Considerações Técnicas e de TCC

- Customização: O projeto utiliza um sistema "white-label" para permitir customizações controladas, como cores e fotos, sem permitir que a empresa altere a estrutura principal da interface.
    
- Escopo: Para o TCC (Trabalho de Conclusão de Curso) e o manual de instruções, o projeto será focado em suas funcionalidades básicas para evitar complexidade excessiva, com a possibilidade de expansões futuras, como a adição de mais tipos de categorias.
    
- Segurança: A questão da segurança é abordada, principalmente no que diz respeito à "engenharia social" e ao risco de compartilhamento de senhas de ADM. Foi decidido que cada funcionário terá seu próprio perfil para maior controle de quem fez o quê.
    
- Notificações: As notificações são um recurso-chave. Qualquer alteração na viagem feita pela gestão deve ser comunicada automaticamente a todos os clientes cadastrados.
    

### Customização e Design

O projeto segue um modelo "white-label", o que significa que, embora a interface principal seja padronizada, as empresas podem personalizar elementos específicos para se alinharem à sua marca. A personalização se limita a:

- Cores do site: A empresa pode alterar a paleta de cores.
    
- Fotos de capa e perfil: É possível carregar imagens de capa e perfil da empresa.
    
- Fotos de serviços: Fotos específicas de cada serviço (como de veículos ou destinos) podem ser adicionadas.
    

A interface em si não pode ser modificada, pois a estrutura de design é fixa. O projeto também planeja oferecer categorias de serviços personalizáveis, mas, para o escopo do TCC, eles se limitarão a duas: "viagem" e "aluguel".

---

### Jornada do Cliente e Pagamentos

A jornada do cliente é projetada para ser simples e sem a necessidade de login:

- Reserva: O cliente recebe um link da empresa (geralmente via WhatsApp), clica nele e faz a reserva. Ele preenche apenas seu nome, e-mail e telefone para finalizar.
    
- Ingresso: O ingresso gerado é enviado para o e-mail e o WhatsApp do cliente. Isso garante que ele receba duas cópias para maior segurança e conveniência.
    
- Pagamento: A discussão sobre os métodos de pagamento se aprofundou. Foi decidido que o projeto deve aceitar PIX (via QR Code) e cartões de débito/crédito. O pagamento por boleto é uma opção, mas o sistema tem uma "feature" para cancelar automaticamente a reserva se o pagamento não for confirmado dentro de um prazo específico, liberando a vaga para outro cliente e enviando uma notificação automática sobre o cancelamento.
    

---

### Papéis de Usuário e Segurança

A plataforma foi pensada para evitar riscos de segurança relacionados ao compartilhamento de senhas:

- Perfis Individuais: Em vez de um único usuário e senha de administrador para todos, cada funcionário terá seu próprio perfil. Isso permite que a gestão da empresa tenha maior controle sobre as ações de cada pessoa, evitando problemas de "engenharia social" (quando senhas são compartilhadas indevidamente).
    
- Acesso Limitado do Motorista: O motorista tem acesso apenas a informações relacionadas às suas próprias viagens, como a rota, o veículo e a lista de passageiros. Ele não consegue ver informações de outras viagens ou de gestão.
    
- Gestão e Comunicação: A equipe de gestão tem o poder de ver quem pagou e quem ainda tem pagamento pendente. Eles também podem editar informações das viagens, com o sistema enviando notificações automáticas para os clientes sobre as alterações.
    

---

### Comunicação Automatizada

O projeto coloca grande ênfase na otimização da comunicação com o cliente:

- Integração com WhatsApp: O motorista pode enviar mensagens automáticas para os passageiros, como avisos de partida ou paradas.
    
- Fluxo de Notificações: As notificações são um aspecto central para evitar congestionamentos na equipe de gestão. Em vez de a equipe ter que contatar cada cliente individualmente, o sistema faz isso de forma automática, por exemplo, informando sobre o cancelamento de uma passagem devido a pagamento pendente.

# Resumo Detalhado do Projeto (TCC)

## Ideia Geral

- Um aplicativo web (white label) para empresas de transporte/serviços.  
      
    
- Funciona como um cardápio online personalizado: cada empresa recebe seu próprio link, login de ADM e opções de customização.  
      
    
- Front-end do cliente: mostra serviços/viagens disponíveis.  
      
    
- Back-end do ADM/gestão: permite cadastrar categorias, serviços, funcionários e controlar reservas.  
      
    

---

## Atores do Sistema

1. ADM (Administrador da empresa)  
      
    

- Cadastrado pela equipe do sistema (não pelo usuário).  
      
    
- Recebe login e senha (pode recuperar via e-mail).  
      
    
- Acessa via versão desktop e mobile.  
      
    
- Pode cadastrar/editar informações da empresa (foto, capa, descrição).  
      
    
- Pode cadastrar funcionários (gestão e motoristas).  
      
    

3. Funcionário – Gestão  
      
    

- Tem permissões limitadas.  
      
    
- Pode cadastrar serviços, gerenciar viagens, acompanhar pagamentos e contatos dos clientes.  
      
    
- Controla reservas pendentes e confirmações.  
      
    
- Tem acesso a histórico de viagens, presença, quem pagou/não pagou.  
      
    

5. Funcionário – Motorista  
      
    

- Acesso restrito.  
      
    
- Só visualiza viagens atribuídas a ele.  
      
    
- Tem lista de passageiros e notificações automáticas no WhatsApp.  
      
    
- Não vê dados pessoais completos (como número pessoal do cliente), apenas dispara mensagens pré-definidas.  
      
    

7. Cliente (passageiro)  
      
    

- Recebe link da empresa via WhatsApp.  
      
    
- Não faz login tradicional: informa telefone e nome para reservar.  
      
    
- Escolhe serviço/viagem, quantidade de assentos, faz pagamento e recebe ingresso digital (QR Code, e-mail e WhatsApp).  
      
    

---

## Fluxos Principais

### 1. Cadastro e Acesso

- Empresa → entra em contato → equipe do sistema cria conta ADM com link exclusivo.  
      
    
- ADM → acessa painel → configura empresa, cadastra funcionários.  
      
    
- Funcionários → recebem login próprio → acessam painel com permissões limitadas.  
      
    
- Cliente → recebe link → acessa tela de reservas.  
      
    

---

### 2. Gestão de Categorias e Serviços

- ADM/gestão podem criar categorias customizadas (ex: Viagens, Aluguel, Promoções).  
      
    
- Cada serviço cadastrado contém:  
      
    

- Nome, descrição, origem/destino.  
      
    
- Data e horário.  
      
    
- Quantidade de assentos.  
      
    
- Valor da passagem.  
      
    
- Imagem.  
      
    
- Motorista responsável e veículo.  
      
    

---

### 3. Reserva de Viagem (Cliente)

- Cliente abre link → escolhe serviço → insere telefone, nome e e-mail.  
      
    
- Pode comprar múltiplos ingressos (com possibilidade de cadastrar números extras).  
      
    
- Gera QR Code de pagamento.  
      
    
- Após pagamento confirmado → ingresso enviado por WhatsApp + e-mail.  
      
    

---

### 4. Pagamento

- Integração com APIs de pagamento (Mercado Pago, PicPay, etc).  
      
    
- Formas aceitas:  
      
    

- PIX (QR Code).  
      
    
- Cartão (débito/crédito).  
      
    
- Boleto (restrição: só válido se viagem não for próxima, por causa da compensação bancária).  
      
    

- Pagamento confirmado → ingresso automático → reserva validada.  
      
    
- Caso não pague → gestão pode cancelar vaga → liberar assentos.  
      
    

---

### 5. Comunicação

- Motorista → Cliente:  
      
    

- Envia notificações automáticas pré-definidas (ex: “O ônibus sairá em 15 min”).  
      
    
- Não tem acesso ao número pessoal do cliente.  
      
    

- Gestão → Cliente:  
      
    

- Pode entrar em contato diretamente (tem acesso a números e e-mails).  
      
    
- Envia mensagens automáticas em caso de alteração na viagem.  
      
    

---

### 6. Controle de Viagem

- Motorista:  
      
    

- Lista de passageiros.  
      
    
- Botão de confirmação de presença.  
      
    
- Mensagens rápidas via WhatsApp.  
      
    

- Gestão:  
      
    

- Relatórios de quem pagou/não pagou.  
      
    
- Cancelamento automático de boletos não pagos.  
      
    
- Histórico de viagens e presenças.  
      
    

---

## Decisões Importantes

- White Label: design padrão, mas com opções limitadas de customização (cores, capa, fotos, categorias).  
      
    
- Login diferenciado:  
      
    

- ADM e funcionários têm login.  
      
    
- Cliente usa apenas telefone.  
      
    

- Pagamentos:  
      
    

- PIX como padrão.  
      
    
- Cartão via API.  
      
    
- Boleto restrito a viagens futuras.  
      
    

- Segurança:  
      
    

- Evitar exposição de dados pessoais (motorista não vê número do cliente).  
      
    
- Senhas individuais para cada funcionário.  
      
    
- Histórico de modificações (quem fez o quê).  
      
    

- MVP (mínimo produto viável):  
      
    

- Cadastro empresa/ADM.  
      
    
- Cadastro de categorias e serviços.  
      
    
- Reserva de viagem.  
      
    
- Pagamento e geração de ingresso.  
      
    
- Comunicação via WhatsApp.  
      
    

---

## Entregável do TCC

- Manual do usuário com:  
      
    

- Telas principais (ADM, funcionário, cliente).  
      
    
- Fluxos básicos documentados.  
      
    
- Demonstração de reservas e pagamentos.  
      
    

Implementação mínima (MVP).  
**