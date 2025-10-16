

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
    