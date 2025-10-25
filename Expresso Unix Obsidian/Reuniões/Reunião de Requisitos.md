## **Relatório de Reunião – Definições do Sistema de Viagens**

**Data:** não informada  
**Tema principal:** Refinamento das funcionalidades do sistema de gestão de viagens (MVP)  
**Participantes:** Equipe de desenvolvimento (nomes não identificados)

---

### **1. Estrutura de papéis e permissões**

- **Gestão:** responsável por todas as operações relacionadas à viagem — criação, controle de reservas, acompanhamento de pagamentos e liberação de vagas.
    
- **Administrador (ADM):** possui todas as funções da gestão, mas com acesso ampliado:
    
    - Adicionar e gerenciar funcionários.
        
    - Verificar logs e auditorias de usuários.
        
    - Monitorar ações realizadas no sistema.
        
- Foi decidido que **logs e auditorias** ficarão sob responsabilidade do **ADM**, e **não da gestão**.
    

---

### **2. Escopo do MVP**

- A equipe reforçou a importância de **reduzir complexidade** e focar nas **funcionalidades essenciais** para a versão inicial.
    
- **Customizações visuais (cores e temas)** serão removidas do MVP, mantendo design padrão semelhante a grandes plataformas (como iFood e Google).
    
- **Histórico de edições** será mantido por motivos de **segurança**, armazenado diretamente no banco de dados com timestamps.
    
- Funcionalidades consideradas **não essenciais para o MVP**:
    
    - Customização de interface.
        
    - BI e relatórios complexos.
        
    - Registro detalhado de paradas de viagem (pode ser adicionado futuramente).
        

---

### **3. Funcionalidades principais**

#### **Gestão / ADM**

- Cadastrar, atribuir e gerenciar funcionários.
    
- Controlar reservas e pagamentos (com conciliação via GetIF).
    
- Criar, editar e excluir viagens.
    
- Filtrar viagens por estado, destino, datas e horários.
    
- Gerar relatórios simples (vendas, horários, quantidade de viagens por mês).
    

#### **Motorista**

- Acesso a login e autenticação.
    
- Visualizar lista de viagens atribuídas.
    
- Fazer check-in, chamada e marcar presença dos passageiros.
    
- Validar QR Codes de embarque.
    
- Registrar incidentes e ocorrências com comentários e fotos.
    
- Encerrar viagem e gerar resumo de ocupação e ocorrências.
    

---

### **4. Experiência do Cliente**

A maior parte da discussão girou em torno de **como o cliente acessará e reservará viagens**.

#### **Modelos debatidos:**

1. **Acesso via link único** enviado pela gestão ou empresa:
    
    - O cliente clica no link e é direcionado **diretamente para a página da viagem** específica.
        
    - Facilita o fluxo e reduz etapas.
        
    - Elimina a necessidade de login ou busca manual.
        
2. **Tela de serviços (lista de viagens):**
    
    - Funcionalidade considerada **secundária**.
        
    - Apenas será usada se o cliente desejar procurar viagens manualmente.
        
    - Ideal para casos em que o cliente ainda não tem destino ou data definidos.
        

#### **Discussão sobre UX (experiência do usuário):**

- Houve divergência sobre a naturalidade do fluxo.
    
    - Um dos pontos levantados: o cliente pode achar estranho precisar preencher dados e fazer login após já conversar com o atendente.
        
    - Outro argumento foi que o **link direto simplifica a jornada**, tornando o processo mais fluido.
        
- Conclusão: **fluxo do link direto** será adotado, com opção de **lista secundária** em situações específicas.
    
- Exemplo comparativo usado: **experiência de compra no Sympla**, onde o cliente apenas clica, preenche os dados e finaliza.
    

---

### **5. Cadastro de passageiros**

- Possibilidade de **compra de múltiplos ingressos** por um único usuário.
    
- Inclusão opcional de e-mail, mas **número de WhatsApp será obrigatório** (canal principal de contato).
    
- Gestão poderá **cadastrar passageiros manualmente** (individual ou em lote), garantindo acessibilidade a clientes que não dominam tecnologia.
    

---

### **6. Automação e comunicação**

- Foi sugerido uso de **chatbots (bot de atendimento)** para automatizar parte do fluxo:
    
    - O bot cumprimenta o cliente, coleta informações básicas e gera o link da viagem.
        
    - Ideia considerada interessante, mas adiada para após o MVP.
        
- **WhatsApp** será o principal meio de comunicação entre cliente e empresa.
    

---

### **7. Considerações finais**

- O grupo destacou a **urgência** do cronograma: a pré-banca está próxima e o sistema ainda não está funcional.
    
- Foco deve permanecer em **concluir o MVP estável** antes de qualquer expansão de escopo.
    
- As decisões sobre UX e automação podem ser refinadas após o protótipo inicial.
    

---

### **8. Conclusão**

A reunião consolidou a visão do sistema em três pilares:

1. **Simplicidade funcional:** eliminar o que não é essencial para o MVP.
    
2. **Experiência do usuário clara:** fluxo direto, sem fricção.
    
3. **Base sólida para expansão:** manter estrutura de logs, relatórios e permissões bem definidas.


## ALTERAÇÕES APLICADAS

---

### 🟦 **Gestão.md**

**Resumo das mudanças:**

1. **Escopo reduzido (MVP)**
    
    - Remover qualquer menção a BI avançado, relatórios complexos e customização de interface.
        
    - Adicionar observação no topo: “Escopo limitado ao MVP — foco em funções essenciais”.
        
2. **Adicionar permissões administrativas (ADM)**
    
    - Especificar que o ADM também pode:
        
        - Gerenciar funcionários (criar, editar, desativar).
            
        - Visualizar logs e auditorias de ações de usuários.
            
        - Monitorar alterações no sistema.
            
3. **Logs e segurança**
    
    - Adicionar seção nova:
        
        `### Segurança e Auditoria - Todas as ações de Gestão e ADM são registradas com timestamp e ID do usuário. - Histórico de alterações visível no painel de administração. - Funções críticas exigem confirmação e são marcadas como “Auditoráveis”.`
        
4. **Remover/ajustar BI**
    
    - Substituir o item “Relatórios / Reconciliação” por “Relatórios simples (vendas, horários, ocupação)”.
        

---

### 🟩 **Motorista.md**

**Resumo das mudanças:**

1. **Simplificar escopo para MVP**
    
    - Remover “adicionar parada” e “rastreamento” (ficam para versão futura).
        
    - Manter foco em: login, lista de viagens, chamada, QR Code, incidentes e finalização.
        
2. **Nova seção:**
    
    `### Registrar Chamada / Check-in - Motorista inicia chamada e valida ingressos via QR ou manualmente. - Cada validação é registrada com hora e tipo (manual/automático). - Ocorrências e incidentes podem ser registrados durante a viagem.`
    
3. **Incluir integração com logs**
    
    - Adicionar que toda validação e marcação manual gera entrada no histórico para o ADM.
        
4. **Remover fluxos não-MVP**
    
    - Retirar menções a “rastreamento habilitado”, “adicionar parada”, e “template de mensagens padronizadas”, mantendo apenas “avisos rápidos”.
        

---

### 🟨 **Cliente.md**

**Resumo das mudanças:**

1. **Fluxo de acesso via link único**
    
    - Adicionar no início:
        
        `- Cliente acessa o sistema principalmente via link direto enviado pela Gestão (link único). - A tela de lista de viagens é secundária e usada apenas quando o cliente deseja explorar opções.`
        
2. **Simplificação de cadastro**
    
    - Manter apenas **nome** e **telefone (WhatsApp obrigatório)**.
        
    - Tornar e-mail opcional.
        
3. **Remover passo de login**
    
    - Garantir que o fluxo funcione no modo “guest”.
        
4. **Atualizar seção de reserva**
    
    - Especificar:
        
        - O cliente pode comprar múltiplos ingressos de uma só vez.
            
        - O sistema envia QR Codes via WhatsApp.
            
        - Gestão pode reenviar ingressos manualmente.
            
5. **Ajustar jornada**
    
    - Reescrever a parte inicial (“Visualizar viagem / decidir comprar”) para refletir que o cliente **não pesquisa** — ele **acessa diretamente** a viagem específica.
        
6. **Adicionar observação sobre UX**
    
    - No final:
        
        `> Observação: o fluxo de compra foi desenhado para minimizar atrito — o cliente acessa via link, preenche poucos dados e finaliza o pagamento rapidamente, similar à experiência do Sympla.`
        

---

## 🧱 RESULTADO FINAL (resumo técnico)

|Documento|Ação principal|Novas seções|Itens removidos|
|---|---|---|---|
|**Gestão.md**|Adicionar ADM, logs e segurança|“Segurança e Auditoria”|BI, customização|
|**Motorista.md**|Simplificar MVP e registrar logs|“Registrar Chamada / Check-in”|Rastreamento, parada|
|**Cliente.md**|Acesso via link único e WhatsApp obrigatório|Observação UX e fluxo direto|Login, exploração livre|