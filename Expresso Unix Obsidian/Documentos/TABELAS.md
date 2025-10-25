### **gestao**

| Campo         | Tipo                  | Observações                           |
| ------------- | --------------------- | ------------------------------------- |
| id_gestor     | INT (PK)              | Identificador único do gestor         |
| nome          | VARCHAR(120)          | Nome completo                         |
| email         | VARCHAR(150)          | Obrigatório                           |
| telefone      | VARCHAR(20)           | WhatsApp obrigatório                  |
| senha_hash    | VARCHAR(255)          | Hash da senha de acesso               |
| tipo_gestor   | ENUM('Gestao', 'ADM') | Define o nível de acesso e privilégio |
| ativo         | BOOLEAN               | Gestor ativo/inativo                  |
| criado_em     | DATETIME              | Registro de criação                   |
| atualizado_em | DATETIME              | Última atualização                    |
### **clientes**

|Campo|Tipo|Observações|
|---|---|---|
|id_cliente|INT (PK)|Identificador único do cliente|
|nome|VARCHAR(120)|Nome completo|
|telefone|VARCHAR(20)|WhatsApp obrigatório|
|email|VARCHAR(150)|Opcional — usado apenas para notificações|
|ativo|BOOLEAN|Cliente ativo/inativo|
|criado_em|DATETIME|Data de criação do registro|
|atualizado_em|DATETIME|Última atualização|
|documento_id|VARCHAR(30)|CPF ou RG (opcional para controle de identidade)|

---

### **motoristas**

| Campo         | Tipo                          | Observações                      |
| ------------- | ----------------------------- | -------------------------------- |
| id_motorista  | INT (PK)                      | Identificador único do motorista |
| nome          | VARCHAR(120)                  | Nome completo                    |
| telefone      | VARCHAR(20)                   | WhatsApp obrigatório             |
| email         | VARCHAR(150)                  | Obrigatório                      |
| senha_hash    | VARCHAR(255)                  | Hash da senha de acesso          |
| cnh           | VARCHAR(20)                   | Número da CNH                    |
| validade_cnh  | DATE                          | Validade da CNH                  |
| categoria_cnh | ENUM('A', 'B', 'C', 'D', 'E') | Categoria da CNH                 |
| ativo         | BOOLEAN                       | Motorista ativo/inativo          |
| criado_em     | DATETIME                      | Data de criação                  |
| atualizado_em | DATETIME                      | Última atualização               |



---

### **2. viagens**

| Campo                 | Tipo                                                    | Observações                |
| --------------------- | ------------------------------------------------------- | -------------------------- |
| id_viagem             | INT (PK)                                                | Identificador da viagem    |
| origem                | VARCHAR(100)                                            | Cidade ou ponto de partida |
| destino               | VARCHAR(100)                                            | Cidade de destino          |
| data_saida            | DATETIME                                                | Data/hora de saída         |
| data_chegada_prevista | DATETIME                                                | Data/hora prevista         |
| preco                 | DECIMAL(10,2)                                           | Valor por ingresso         |
| vagas_totais          | INT                                                     | Capacidade total           |
| vagas_disponiveis     | INT                                                     | Atualizado conforme vendas |
| status                | ENUM('Rascunho', 'Publicada', 'Cancelada', 'Concluida') | Estado atual               |
| id_motorista          | INT (FK → usuarios.id_usuario)                          | Motorista designado        |
| criado_por            | INT (FK → usuarios.id_usuario)                          | Gestão que criou           |
| criado_em             | DATETIME                                                | Data de criação            |
| atualizado_em         | DATETIME                                                | Última edição (para logs)  |

---

###  **3. reserva**

| Campo             | Tipo                                                              | Observações              |
| ----------------- | ----------------------------------------------------------------- | ------------------------ |
| id_reserva        | INT (PK)                                                          | Identificador da reserva |
| id_cliente        | INT (FK → usuarios.id_usuario)                                    | Cliente que reservou     |
| id_viagem         | INT (FK → viagens.id_viagem)                                      | Viagem associada         |
| quantidade        | INT                                                               | Quantidade de ingressos  |
| status            | ENUM('Reservado', 'Pago', 'Pendente', 'Cancelado', 'Reembolsado') | Estado da reserva        |
| metodo_pagamento  | ENUM('PIX', 'Boleto', 'Cartao')                                   | Tipo de pagamento        |
| valor_total       | DECIMAL(10,2)                                                     | Total calculado          |
| codigo_pix        | VARCHAR(120)                                                      | Se aplicável             |
| vencimento_boleto | DATETIME                                                          | Se aplicável             |
| criado_em         | DATETIME                                                          | Data de criação          |
| atualizado_em     | DATETIME                                                          | Última atualização       |

---

### **4. passagem**

| Campo         | Tipo                              | Observações                  |
| ------------- | --------------------------------- | ---------------------------- |
| id_ingresso   | INT (PK)                          | Identificador único          |
| id_reserva    | INT (FK → reservas.id_reserva)    | Reserva associada            |
| codigo_qr     | VARCHAR(255)                      | Código gerado (hash ou UUID) |
| status        | ENUM('Ativo', 'Usado', 'Inativo') | Estado atual                 |
| validado_em   | DATETIME                          | Data/hora da validação       |
| validado_por  | INT (FK → usuarios.id_usuario)    | Motorista responsável        |
| reenviado_em  | DATETIME                          | Última reemissão             |
| reenviado_por | INT (FK → usuarios.id_usuario)    | Gestão responsável           |
| criado_em     | DATETIME                          | Geração inicial              |

---

###  **5. checklist_viagem**

| Campo          | Tipo                           | Observações                   |
| -------------- | ------------------------------ | ----------------------------- |
| id_checklist   | INT (PK)                       | Identificador                 |
| id_viagem      | INT (FK → viagens.id_viagem)   | Viagem vinculada              |
| item           | VARCHAR(120)                   | Ex: “Documentação verificada” |
| status         | BOOLEAN                        | Marcado / não marcado         |
| atualizado_em  | DATETIME                       | Última alteração              |
| atualizado_por | INT (FK → usuarios.id_usuario) | Motorista que alterou         |

---

###  **6. incidentes**

| Campo        | Tipo                                          | Observações          |
| ------------ | --------------------------------------------- | -------------------- |
| id_incidente | INT (PK)                                      | Identificador        |
| id_viagem    | INT (FK → viagens.id_viagem)                  | Viagem associada     |
| id_motorista | INT (FK → usuarios.id_usuario)                | Quem reportou        |
| tipo         | ENUM('Atraso', 'Dano', 'Ocorrência', 'Outro') | Tipo de incidente    |
| descricao    | TEXT                                          | Detalhe do incidente |
| foto_url     | VARCHAR(255)                                  | Opcional             |
| criado_em    | DATETIME                                      | Data de registro     |

---

###  **7. auditoria_logs**

| Campo       | Tipo                                                                  | Observações                         |
| ----------- | --------------------------------------------------------------------- | ----------------------------------- |
| id_log      | INT (PK)                                                              | Identificador                       |
| id_usuario  | INT (FK → usuarios.id_usuario)                                        | Quem fez a ação                     |
| entidade    | VARCHAR(50)                                                           | Ex: “viagem”, “reserva”, “ingresso” |
| id_entidade | INT                                                                   | ID do item afetado                  |
| acao        | ENUM('Criar', 'Editar', 'Excluir', 'Validar', 'Cancelar', 'Reenviar') | Tipo de ação                        |
| timestamp   | DATETIME                                                              | Data e hora do evento               |
| detalhes    | TEXT                                                                  | JSON ou texto descritivo            |

---

###  **8. tickets_suporte**

| Campo         | Tipo                                      | Observações                    |
| ------------- | ----------------------------------------- | ------------------------------ |
| id_ticket     | INT (PK)                                  | Identificador                  |
| id_usuario    | INT (FK → usuarios.id_usuario)            | Cliente ou Motorista que abriu |
| id_reserva    | INT (FK → reservas.id_reserva)            | Opcional                       |
| assunto       | VARCHAR(100)                              | Título curto                   |
| mensagem      | TEXT                                      | Corpo da mensagem              |
| status        | ENUM('Aberto', 'Em análise', 'Resolvido') | Estado do ticket               |
| prioridade    | ENUM('Baixa', 'Média', 'Alta')            | Priorização                    |
| criado_em     | DATETIME                                  | Data de criação                |
| atualizado_em | DATETIME                                  | Última resposta                |
| resolvido_por | INT (FK → usuarios.id_usuario)            | Gestão/ADM responsável         |

---

###  **9. relatorios_cache (opcional MVP)**

| Campo        | Tipo                                    | Observações             |
| ------------ | --------------------------------------- | ----------------------- |
| id_relatorio | INT (PK)                                | Identificador           |
| tipo         | ENUM('Vendas', 'Viagens', 'Reembolsos') | Tipo de relatório       |
| parametros   | TEXT                                    | JSON de filtros         |
| gerado_por   | INT (FK → usuarios.id_usuario)          | Gestão que solicitou    |
| criado_em    | DATETIME                                | Data de geração         |
| arquivo_url  | VARCHAR(255)                            | Caminho para o download |

---

##  **Relacionamentos principais**

- `usuarios (1,N) viagens` — Gestão cria viagens.
    
- `usuarios (1,N) reservas` — Clientes fazem reservas.
    
- `reservas (1,N) ingressos` — Uma reserva pode gerar vários ingressos.
    
- `viagens (1,N) incidentes` — Motorista registra ocorrências.
    
- `usuarios (1,N) auditoria_logs` — Todas as ações ficam rastreadas