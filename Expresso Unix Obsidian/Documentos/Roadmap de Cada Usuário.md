**

# Motorista:

## Fluxo de telas e interações (passo a passo)

### 1 — Tela de login

- Campos: Matrícula/e-mail + senha. CTA claro: Entrar.  
      
    
- Mensagens comuns: “Credenciais incorretas”, “Conta bloqueada — contatar Gestão”.  
      
    
- Ao logar com sucesso, transição direta para o quadro de viagens do dia.  
      
    

### 2 — Quadro / Lista de Viagens (página inicial)

- Exibir somente viagens do dia por padrão; filtro rápido para Próximos dias e Minhas Viagens.  
      
    
- Cada card: horário em destaque, origem/destino, tempo até saída (contagem regressiva), badges (Atraso, Alterado).  
      
    
- Ações diretas no card (1 toque): Ver Detalhes, Enviar Aviso (menu rápido).  
      
    
- Comportamento: tocar fora de um cartão fecha menus; arrastar para atualizar (pull-to-refresh).  
      
    

### 3 — Detalhe da Viagem

- Seção superior com dados críticos (hora, rota, veículo).  
      
    
- Checklists obrigatórios listados com toggles (ex.: checar documentação, combustível).  
      
    
- Lista de passageiros compacta: nome, status pagamento, ícone do ingresso (ativo/usado).  
      
    
- Botões primários grandes: Iniciar Chamada, Scanner (QR), Iniciar Viagem, Registrar Incidente.  
      
    
- Indicação visual forte do número de ações pendentes (por ex., passageiros sem validação).  
      
    

### 4 — Iniciar Chamada / Boarding UI

- Tela modal ou full-screen com:  
      
    

- Contadores (reservados / embarcados / vagas).  
      
    
- Botão grande Abrir Scanner.  
      
    
- Botão secundário Marcar Manual.  
      
    

- Microfeedback: som curto + animação verde ao validar; animação vermelha no erro.  
      
    
- Mensagem curta quando começar: “Chamada iniciada — escaneie os ingressos”.  
      
    

### 5 — Scanner QR

- Tela com visão da câmera central e instruções curtas no topo: “Aponte a câmera para o QR do ingresso”.  
      
    
- Feedback em tempo real: caixa de foco, indicador de foco perdido (se câmera não conseguir ler).  
      
    
- Resultado direto: Embarcado (✔) ou Erro (✖) com motivo: “Ingresso inválido”, “Já utilizado”, “Pagamento pendente”.  
      
    
- Ações contextuais no erro: Tentar novamente, Marcar Manual, Reportar Incidente.  
      
    

### 6 — Marcar Manual

- Fluxo rápido: busca por nome/reserva (autocompletar) + confirmação (“Confirmar embarque de João Silva?”).  
      
    
- Exigir motivo (QR ilegível, sem celular, outro) em um campo curto — ajuda na auditoria.  
      
    
- Exibir badge “Manual” ao lado do passageiro (visível para Gestão).  
      
    

### 7 — Enviar Avisos

- Menu compacto com templates (pré-definidos): “Partida em 15 minutos”, “Atraso previsto”, etc.  
      
    
- Seleção de destinatários: Todos / Somente presentes / Selecionados.  
      
    
- Confirmação simples: “Enviar X mensagens?” → feedback de sucesso/pendente.  
      
    

### 8 — Iniciar Viagem / Em andamento

- Validação rápida do checklist; se algo crítico faltar, exibir aviso e permitir forçar com justificativa.  
      
    
- Mostrar timer de viagem e, se habilitado, opção de rastreamento (toggle).  
      
    
- Ações disponíveis durante viagem: registrar desembarque, adicionar parada, abrir ticket de incidente.  
      
    

### 9 — Registrar Incidente

- Modal com categorias (ex.: atraso, dano, problema com passageiro), campo para comentário e opção de anexar foto.  
      
    
- Enviar: cria um ticket para Gestão e confirma ao Motorista: “Incidente registrado — ID #1234”.  
      
    

### 10 — Finalizar Viagem

- Exibir resumo com métricas (ocupação final, ocorrências).  
      
    
- Checklist final: todos embarques/desembarques registrados? incidentes pendentes?  
      
    
- Ao finalizar, mostrar confirmação “Viagem finalizada com sucesso” e opção para ver relatório completo.
    

# Gestão ↔ Plataforma

(ou seja: ações que Gestão realiza e como a Plataforma deve reagir/mostrar isso)

## Pré-condições

- Gestão tem acesso à interface administrativa da Plataforma; vê viagens, reservas, tickets e relatórios.  
      
    
- A Plataforma mantém estados claros para viagens e reservas e histórico de todas as ações (visível na UI de Gestão).  
      
    
- Templates de mensagem e regras (prazos de boleto, políticas de reembolso) estão configuráveis pela Gestão.  
      
    

## Fluxos principais (o que Gestão faz → o que a Plataforma faz / mostra)

### A) Criar / Rascunho / Publicar viagem

- Gestão preenche formulário de viagem e escolhe Rascunho ou Publicar.  
      
    
- Plataforma (resposta):  
      
    

- Se Rascunho: salva e mostra apenas a Gestão; marca como não-visível ao Cliente.  
      
    
- Se Publicar: cria vagas/slots e passa a mostrar a viagem para Clientes; exibe confirmação para Gestão: “Viagem publicada — X vagas disponíveis”.  
      
    
- Sempre mostrar pré-visualização (how it looks to Cliente) antes da confirmação.  
      
    

- IHC para Gestão: botão grande “Publicar”, preview, contador de vagas e confirmação visual do estado (Rascunho / Publicada).  
      
    

### B) Atribuir Motorista / Veículo

- Gestão escolhe motorista/veículo para a viagem.  
      
    
- Plataforma (resposta):  
      
    

- Mostra aviso se houver conflito de agenda (quantos conflitos, quais) e pede confirmação para forçar.  
      
    
- Atualiza a viagem e coloca um aviso visível no card da viagem (“Motorista X atribuído / alteração pendente”).  
      
    
- Notifica o Motorista via plataforma (entrada no painel do Motorista).  
      
    

- IHC para Gestão: indicação clara de conflitos e botão “Confirmar Atribuição (forçar)”.  
      
    

### C) Publicação com notificação (opcional)

- Ao publicar, Gestão pode optar por notificar Clientes interessados.  
      
    
- Plataforma:  
      
    

- Mostra lista de destinatários afetados (contagem) e pré-visualização da mensagem.  
      
    
- Pede confirmação “Enviar agora para X clientes?”.  
      
    
- Registra no histórico que a notificação foi enviada (ou ficou agendada).  
      
    

- IHC: painel de confirmação com preview + botão “Enviar / Agendar”.  
      
    

### D) Editar viagem publicada (mudanças críticas)

- Gestão edita data/hora/rota ou descrição.  
      
    
- Plataforma:  
      
    

- Antes de aplicar mudanças críticas, calcula e mostra quantos Clientes serão afetados.  
      
    
- Gera rascunho automático da notificação para esses Clientes (texto editável).  
      
    
- Requer confirmação explícita: se confirmado, aplica mudança e envia as notificações (ou agenda).  
      
    
- Mostra banner na interface da viagem: “Alterada em dd/mm hh:mm — notificada X clientes”.  
      
    

- IHC: modal com lista de Clientes afetados + botão “Confirmar e notificar” + opção “Aplicar sem notificar (somente interno)” com justificativa.  
      
    

### E) Cancelar viagem

- Gestão clica “Cancelar viagem”.  
      
    
- Plataforma:  
      
    

- Mostra checklist de consequências (bloquear vendas, iniciar reembolso automático/manual, notificar Clientes).  
      
    
- Requer confirmação com texto (ex.: “Confirmar cancelamento — X clientes serão reembolsados”).  
      
    
- Depois de confirmado, marca viagem como Cancelada, avisa Clientes (mensagem padrão e banner na reserva) e exibe painel de reembolso com status por reserva.  
      
    

- IHC: modal de cancelamento com resumo das ações e botão final “Cancelar e notificar”.  
      
    

### F) Gerenciar Reservas / Pagamentos

- Gestão visualiza lista de reservas (filtros: Pago / Pendente / Cancelado).  
      
    
- Plataforma:  
      
    

- Mostra o estado de cada reserva e ações disponíveis (Confirmar manualmente, Cancelar e reembolsar, Reenviar ingresso).  
      
    
- Mantém regras visíveis (ex.: prazo de boleto, bloqueio de assento por X minutos).  
      
    
- Quando Gestão marca “confirmar manualmente”, Plataforma atualiza estado e registra ação no histórico.  
      
    

- IHC: tabela filtrável com ações rápidas e badge de estado.  
      
    

### G) Reemissão / Reenvio de ingresso

- Gestão solicita reenvio de ingresso para um Cliente.  
      
    
- Plataforma:  
      
    

- Exibe quantas reemissões já foram feitas e aplica limite se houver.  
      
    
- Reenvia ingresso e registra no histórico (quando, por quem).  
      
    
- Se limite atingido, oferece fluxo de suporte (abrir ticket).  
      
    

- IHC: botão “Reenviar ingresso” + contador de reenvios + aviso de limite.  
      
    

### H) Suporte / Tickets / Incidentes

- Gestão recebe tickets abertos por Clientes (ou por Motorista).  
      
    
- Plataforma:  
      
    

- Mostra ticket com contexto pré-preenchido (viagem, reserva, ingressos, mensagens relacionadas).  
      
    
- Permite Gestão responder, reencaminhar, resolver e acompanhar tempo de SLA.  
      
    
- Exibe status do ticket (Aberto / Em análise / Resolvido).  
      
    

- IHC: painel de tickets com filtros de prioridade e busca por protocolo.  
      
    

### I) Relatórios / Reconciliação (visível para Gestão)

- Gestão solicita relatórios (ocupação, vendas, reembolsos).  
      
    
- Plataforma:  
      
    

- Gera relatório e mostra progresso; quando pronto exibe download / preview.  
      
    
- Para reconciliação de pagamentos, mostra estado por reserva (Pago / Pendente / Cancelado / Reembolsado).  
      
    

- IHC: botão “Gerar relatório” + visualização do progresso e link para download.
    

# Cliente ↔ Plataforma

(ou seja: ações que Cliente realiza e como a Plataforma deve reagir/mostrar isso)

## Pré-condições

- Cliente acessa a Plataforma via link/landing ou através do site; não é obrigatório criar conta (fluxo guest).  
      
    
- Plataforma exibe disponibilidade atualizada e estado de cada reserva.  
      
    

## Fluxos principais (o que Cliente faz → o que a Plataforma faz / mostra)

### A) Visualizar viagem / decidir comprar

- Cliente vê listagem e detalhes (data/hora, pontos de embarque, preço, assentos restantes).  
      
    
- Plataforma:  
      
    

- Mostra disponibilidade em tempo real e o CTA (Reservar / Comprar).  
      
    
- Exibe informação útil (prazos, políticas) claramente.  
      
    

- IHC: página de viagem com botão grande “Reservar / Comprar” e informações de prazo.  
      
    

### B) Iniciar reserva / checkout

- Cliente preenche nome, telefone e e-mail (mínimo) e seleciona quantidade de ingressos.  
      
    
- Plataforma:  
      
    

- Reserva temporária de assentos por X minutos (mostrar contagem regressiva).  
      
    
- Exibe opções de pagamento e instruções (PIX, Cartão, Boleto).  
      
    
- Se escolher boleto, Plataforma mostra prazo de vencimento.  
      
    

- IHC: checkout em passos curtos com timer visível quando aplicável.  
      
    

### C) Pagamento e confirmação

- Cliente paga.  
      
    
- Plataforma:  
      
    

- Ao confirmar pagamento, gera ingresso(s) com QR e marca reserva como Pago.  
      
    
- Envia ingresso por WhatsApp e por e-mail (quando possível) e exibe tela de confirmação com botão “Baixar ingresso / Reenviar”.  
      
    
- Se pagamento ficar pendente (boleto), mostra estado “Pendente” e informa prazo para compensação; agenda cancelamento automático.  
      
    

- IHC: tela “Compra confirmada” com instruções e botões de ação.  
      
    

### D) Receber / Gerenciar ingresso

- Cliente abre o ingresso recebido.  
      
    
- Plataforma:  
      
    

- Mostra status do ingresso (Ativo / Inativo / Usado).  
      
    
- Oferece botão “Reenviar ingresso”, “Contatar suporte”, e histórico de notificações relacionadas à reserva.  
      
    
- Controla limite de reenvios (se houver) e informa o Cliente quando limite for atingido.  
      
    

- IHC: área da reserva com botão de reenvio e histórico de mensagens.  
      
    

### E) Dia da viagem — lembretes e alterações

- Plataforma envia lembretes (24h / 2h / 15min) e banners na reserva.  
      
    
- Se Gestão alterar/cancelar viagem, Plataforma:  
      
    

- Exibe banner chamativo na reserva com opções claras: Aceitar mudança, Solicitar reembolso, Falar com suporte.  
      
    
- Envia mensagem direta (WhatsApp / e-mail) com descrição da mudança e next steps.  
      
    

- IHC: banner com ações claras (Aceitar / Reembolso / Suporte).  
      
    

### F) No embarque — validação do ingresso

- Cliente apresenta QR.  
      
    
- Plataforma:  
      
    

- Antes do embarque, mostra se o ingresso está Ativo e pronto para validação.  
      
    
- Se ingresso inválido/pendente, Plataforma mostra instruções imediatas: “Seu pagamento está pendente — procure suporte” ou “Ingresso inválido — solicite reemissão”.  
      
    
- Quando Motorista valida (scanneia), Plataforma muda estado do ingresso para Usado e registra hora.  
      
    

- IHC: status visível e instrução rápida “Mostrar QR ao Motorista”.  
      
    

### G) Suporte / Tickets

- Cliente abre ticket via link na reserva/ingresso.  
      
    
- Plataforma:  
      
    

- Coleta dados essenciais (reserva, ingresso, mensagem) e cria protocolo.  
      
    
- Mostra ao Cliente o número do protocolo e o status do atendimento.  
      
    

- IHC: formulário de suporte simples + status do ticket com estimativa de resposta.  
      
    

### H) Reembolso / Cancelamento solicitado pelo Cliente

- Cliente solicita reembolso pela reserva.  
      
    
- Plataforma:  
      
    

- Exibe opções conforme política (automático ou análise manual) e um prazo estimado.  
      
    
- Atualiza status da reserva para “Reembolso solicitado” e mostra progresso até “Reembolsado”.  
      
    

- IHC: botão “Solicitar reembolso” + confirmação com prazo estimado e protocolo.  
      
    

## Estados visíveis ao Cliente (mínimos)

- Disponível / Reservado / Pago / Pendente / Ativo / Usado / Cancelado / Reembolso solicitado / Reembolsado
    

  
**