# projeto-copiloto-de-vendas-FYS
Projeto de criação do FYS Bakery Copilot: um agente de IA (AGENTS.md) que ajuda vendedores da Heineken a mapear, priorizar e ativar padarias na cidade de SP para ofertar o refrigerante FYS. Ele analisa o público local, a proximidade com rotas de entrega existentes e gera mensagens curtas no tom da FYS via WhatsApp para agilizar e baratear as vendas B2B.
Projeto final desenvolvido para o desafio **"Copiloto de Vendas com IA para Atendimento ao Cliente"** da DIO.
Este projeto foi estruturado no **padrão oficial de Agentes de IA (AGENTS.md)**, tornando-o totalmente funcional e pronto para rodar em qualquer harness compatível (como Google Antigravity, Claude Code, etc.).

---

## 🎯 O Tema Escolhido
O mercado brasileiro contaconta com aproximadamente 72 mil padarias, sendo que 21% delas estão concentradas no estado de São Paulo. Esse canal representa uma oportunidade massiva para o consumo de refrigerantes de dose única (single serve, como latas). 
A força de vendas da Heineken possui foco histórico em bares, restaurantes e casas noturnas devido ao volume de vendas de cerveja. O canal de **padarias** (essencial para o consumo diário de refrigerantes) muitas vezes carece de atenção dedicada. A marca FYS possui menos de 1% de participação nesse canal, um cenário que deve ser trabalhado. 

O usuário principal da solução é o **vendedor da Heineken**.

Nossa solução resolve o problema identificado do canal **padarias** otimizando o tempo do **vendedor Heineken** por meio de:
1. **Mapeamento de padarias:** No mundo real, esse copiloto usaria dados de geolocalização (como a API do Google Places), bancos de dados de empresas para listar as padarias ou até mesmo monitoramento de redes sociais, e, depois, usaria IA para priorizar e criar as mensagens. Para este Desafio de Projeto da DIO, foi criado um protótipo funcional simulando esse fluxo. Nesse protótipo foi feita a classificação das padarias com maior sinergia (público consumidor compatível com FYS) e menor custo logístico (proximidade física com rotas Heineken ativas). Foram mapeadas padarias da cidade de São Paulo porque essa é uma região com volume alto de consumo de refrigerante single serve sem cola e baixa penetração da FYS nesse mercado dessa região. 
2. **Abordagem B2B Simplificada:** Geração de mensagens curtas, sinceras, profissionais e com foco em conveniência logística para serem enviadas via WhatsApp pelo **vendendor Heineken** para o cliente **padaria**.

---

## 📂 Estrutura do Repositório (Padrão de Agente)

```text
projeto-copiloto-fys/
├── README.md                      # Esta apresentação do projeto
├── AGENTS.md                      # Definição e regras de comportamento do Agente
└── agent/
    ├── persona.md                 # Tom de voz e regras de comunicação (O que evitar)
    └── knowledge/
        ├── fys-brand.md           # Contexto da marca FYS e diferenciais do produto
        └── padarias.json          # Banco de dados simulado com padarias mapeadas
```

---

## 🛠️ Detalhes dos Componentes do Agente

### 1. 🤖 Definição do Agente (`AGENTS.md`)
O arquivo [AGENTS.md](file:///c:/Users/leand/OneDrive/Documentos/Ana%20Projeto%20Copiloto/dio-agent-main/dio-agent-main/projeto-copiloto-fys/AGENTS.md) na raiz do projeto instrui o harness a carregar a identidade do **FYS Bakery Copilot**. Ele define a lógica de priorização comercial (Alta, Média ou Baixa) baseada no público e na proximidade de rotas Heineken.

### 2. 🎭 Personalidade B2B (`agent/persona.md`)
O arquivo [persona.md](file:///c:/Users/leand/OneDrive/Documentos/Ana%20Projeto%20Copiloto/dio-agent-main/dio-agent-main/projeto-copiloto-fys/agent/persona.md) calibra a comunicação. Ele traz regras de tom de voz sincero e direto ao ponto, além de **restrições críticas sobre o que evitar** (como tom irônico excessivo, uso de gírias, palavras rudes, clichês de vendas corporativas e textos longos).

### 3. 📚 Base de Conhecimento (`agent/knowledge/`)
- **[fys-brand.md](file:///c:/Users/leand/OneDrive/Documentos/Ana%20Projeto%20Copiloto/dio-agent-main/dio-agent-main/projeto-copiloto-fys/agent/knowledge/fys-brand.md):** Apresenta os diferenciais de FYS (50% menos açúcar, menos gás e mais leveza) e a força logística do grupo Heineken.
- **[padarias.json](file:///c:/Users/leand/OneDrive/Documentos/Ana%20Projeto%20Copiloto/dio-agent-main/dio-agent-main/projeto-copiloto-fys/agent/knowledge/padarias.json):** Banco de dados em formato de vetor estruturado simulando 5 padarias de São Paulo, seus públicos predominantes e sua proximidade logística.

---

## 🚀 Exemplo Real de Simulação do Agente

Quando o vendedor insere os dados de uma padaria como a **Padaria Pão de Ouro**:
- **Público:** Jovens profissionais e estudantes (adoram novidades e combos rápidos)
- **Logística:** Próximo a um parceiro Heineken ativo na mesma rua.

### Resposta Gerada pelo Agente:

🔴 **Padaria Pão de Ouro**
- **Prioridade:** **Alta**
- **Justificativa:** A padaria não vende FYS atualmente e atende a um público jovem e corporativo que busca praticidade e está muito alinhado com o perfil do refrigerante. Além disso, a visita é logisticamente ideal, pois fica na mesma rua de um cliente parceiro já atendido pela Heineken.

💬 **Sugestão de Mensagem (WhatsApp):**
> *"Olá, tudo bem? Aqui é o [Nome do Vendedor], da Heineken.
> 
> Reparei que o público do seu almoço e lanches tem bastante a cara de FYS — nosso refrigerante com menos açúcar e menos gás. Como atendemos a região de Pinheiros com entregas semanais frequentes, a logística de entrega para você seria super rápida.
> 
> O que acha de eu deixar um fardo de cortesia para você e sua equipe testarem com os clientes? Se fizer sentido, posso passar aí nesta quarta-feira para deixar com você."*

### Possíveis melhorias futuras:
* O banco de dados das padarias pode ser bem mais robusto do que o protótipo apresentado. Pode conter mais informações e características sobre cada padaria e sua localização, com atualizações em tempo real.  

* O FYS Bakery Copilot não fica restrito às mensagens iniciais como no exemplo real acima. Ele é um agente para acompanhar os clientes do canal padaria por todo o ciclo de vendas, inclusive para reativação de possíveis padarias que deixaram de comprar FYS.  

* É possível integrar vários banco de dados e, com a IA, cruzar esses dados, analisar e planejar ações promocionais e eventos de degustação/experimentação em padarias mapeadas. Uma estratégia para melhorar também o sell out no canal padaria e ajudar a marca FYS a ser mais relevante e conhecida no mercado como um todo. 
