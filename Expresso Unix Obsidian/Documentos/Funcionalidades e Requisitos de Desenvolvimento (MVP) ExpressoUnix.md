

## I. Arquitetura, Customização e Acesso

Design Responsivo (Web App): Garante que a plataforma possa ser acessada e utilizada eficientemente tanto em computadores quanto em dispositivos móveis (Web App).  

Perfis de Usuário Individuais: Implementação obrigatória de login e senha exclusivos para ADM, Gestão e Motorista, essencial para rastreabilidade de ações e segurança, evitando o compartilhamento de credenciais.  

Log de Auditoria Transacional: Rastreamento de todas as modificações críticas feitas pelos perfis ADM e Gestão, conferindo rastreabilidade e responsabilidade por todas as ações executadas.  

Acesso do Cliente via Link Único: O cliente acessa a interface de agendamento de serviços diretamente por um link enviado pela empresa (principalmente via WhatsApp), eliminando a necessidade de login ou criação de conta.  

Tela de Erro no Login: Exibir uma tela clara para informar o usuário sobre falhas na autenticação dos perfis ADM e Gestão.  

Tela de Perfil da Empresa (Suporte): Adição de uma tela institucional customizável que inclui informações de suporte, contatos de atendimento e uma seção de Perguntas Frequentes (FAQ).  

Customização da Paleta de Cores: Funcionalidade para o ADM alterar e personalizar a paleta de cores do web app, seguindo a arquitetura white-label.  

Upload de Imagens (Branding): Suporte para carregamento de fotos de capa, fotos de perfil da empresa e imagens específicas para cada serviço oferecido.  

  
  

## II. Gestão e Cadastro

Cadastro de Funcionários (ADM): Capacidade do ADM de cadastrar novos colaboradores (Gestão ou Motorista), atribuindo-lhes o perfil e as permissões adequadas (Gestão ou Motorista).  

Cadastro de Categorias Customizadas: Funcionalidade para criar, nomear e gerenciar categorias de serviços (ex: Viagem, Aluguel).  

CRUD de Serviços/Viagens: Tela para cadastrar, editar e excluir serviços, capturando dados logísticos como origem/destino, data, horário, valor, quantidade total de assentos, motorista responsável e veículo.  

Lista de Serviços Ativos e Finalizados: Visualização de todos os serviços organizados em abas distintas para facilitar o controle operacional.  

Edição de Viagem com Notificação Automática: Ao editar informações críticas de uma viagem (data, horário, rota), o sistema deve disparar automaticamente notificações a todos os clientes afetados pela alteração. (WHATSAPP) 

## III. Reserva e Pagamento

Reserva Simplificada: Fluxo de reserva que exige que o cliente preencha apenas nome, e-mail e número de telefone para finalizar, focando na usabilidade sem fricção.  

Compra de Múltiplos Ingressos: Funcionalidade que permite ao cliente comprar múltiplos bilhetes em uma única transação, com a opção de cadastrar números de telefone extras, se necessário.  

Tratamento de Erro de Capacidade: Implementação de uma tela de erro específica quando o cliente tentar selecionar uma quantidade de bilhetes que exceda o número de assentos disponíveis.  

Integração PIX (QR Code Dinâmico): Suporte obrigatório para pagamento via PIX por meio de QR Code dinâmico, facilitando a compensação instantânea.  

Integração Cartão (Débito/Crédito): Suporte para pagamento via Cartão, exigindo integração com Gateways de pagamento.  

Boleto Bancário (Opção de Pagamento): Suporte para pagamento via boleto bancário, com a restrição de que só deve ser oferecido para viagens com prazo suficiente para a compensação bancária.  

Geração de Ingresso Digital (QR Code): Criação de um ingresso único por passageiro, contendo dados essenciais e um QR Code de validação.  

Envio Redundante do Ingresso: Envio automático e imediato do ingresso para o e-mail e o WhatsApp cadastrados pelo cliente, atuando como redundância operacional.  

Cancelamento Automático de Boleto: Implementação de um serviço de scheduler no back-end para cancelar automaticamente reservas feitas via boleto que não foram confirmadas dentro de um prazo específico, liberando o assento e notificando o cliente.  

## IV. Módulo Operacional do Motorista

Validação de Ingresso por QR Code: Tela específica para o motorista verificar o ingresso do cliente por meio da leitura do QR Code no momento do embarque.  

Desativação Imediata do QR Code: O QR Code deve ser desativado no sistema imediatamente após sua leitura e validação pelo motorista, prevenindo a reutilização ou fraude.  

Lista de Passageiros e Check-in: Acesso à Lista de Presença Motorista e funcionalidade para marcar o check-in dos passageiros embarcados.  

Registro de Paradas no Trajeto: Capacidade de o motorista registrar paradas específicas no percurso da viagem.  

Feature 'Criar Parada' com Nova Lista de Presença: A funcionalidade de criar uma parada ao longo do trajeto deve gerar automaticamente uma nova lista de presença ou reativar o processo de check-in para controle em pontos intermediários.  

Tratamento de Erro de Finalização de Lista: O sistema deve exibir um erro caso o motorista tente finalizar a chamada da lista de presença quando esta ainda estiver incompleta.  

Comunicação Motorista via API (Privacidade): O motorista dispara mensagens padronizadas (ex: "O ônibus partirá em quinze minutos") por meio de uma API, garantindo a entrega ao WhatsApp dos passageiros sem expor o número pessoal do motorista.  

## V. Relatórios e Gestão

Relatório de Status de Reserva: Visibilidade para a Gestão de quem reservou, quem pagou e quem está com pagamento pendente.  

Funcionalidade de Cancelamento (Gestão): Capacidade da Gestão de cancelar passagens com pagamento pendente, liberando a vaga.  

Relatórios Estratégicos de BI: Métricas analíticas sobre a taxa de ocupação dos veículos, identificação dos dias/horários de maior e menor movimento e desempenho de motoristas para auxiliar na tomada de decisões.  

Controle Financeiro Centralizado: Acompanhamento e consulta centralizada de todos os pagamentos realizados.   

  
  

IV. Observações e Extras

  

Mudança de Categoria de Viagens: Na criação da viagem e na edição o usuario é capaz de adicionar ou retirar mais de uma categoria da viagem

  

Informações de Login: O usuario entrará no aplicativo usando o email ou cpf.

  
**