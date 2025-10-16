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
    

  