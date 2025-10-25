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
      
    




