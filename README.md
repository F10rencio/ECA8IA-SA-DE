# Projeto: [Saúde 4.0: Robótica Assistiva]

### 1. Identificação do Grupo
* **Instituição:** Fundação Salvador Arena
* **Curso:** Engenharia de Controle e Automação
* **Grupo:** Grupo 8
* **Integrantes:** * Gustavo Florencio Lima Simião- RA: [061230041]
    * [Leonardo Rodolfo Bortoluci] - RA: [062220014]
    * [Julia Rodrigues Lima] - RA: [062220026]

---

### 2. Área Problema Selecionada
Selecione a trilha tecnológica do projeto (marque com um [x]):
* [x] **Saúde 4.0:** Robótica Assistiva (Controladores Inteligentes/Fuzzy)
* [ ] **Smart Grid:** Eficiência Energética e Descarbonização
* [ ] **Agtech:** Automação de Precisão e Visão Computacional
* [ ] **Logística Autônoma:** Coordenação de AGVs e Otimização de Rotas

---

### 3. Diagnóstico e Definição do Agente
Nesta seção, descrevemos o cenário de atuação e a modelagem do agente inteligente.

* **Contexto:**A Doença de Parkinson é uma doença neurológica progressiva que afeta principalmente o controle dos movimentos. Ela ocorre devido à degeneração de neurônios produtores de dopamina no cérebro.
  
* **Problema:** Devido à natureza não linear, dinâmica e incerta dos sistemas biomecânicos humanos, abordagens baseadas em controle clássico apresentam limitações significativas. A aplicação de técnicas de Inteligência Artificial, como Redes Neurais e Lógica Fuzzy, possibilita maior robustez, adaptabilidade e personalização, resultando em melhor desempenho funcional e qualidade de vida do paciente.
  
* **Impacto:** A aplicação de técnicas de Inteligência Artificial, como Redes Neurais e Lógica Fuzzy, possibilita maior robustez, adaptabilidade e personalização, resultando em melhor desempenho funcional e qualidade de vida do paciente..

#### Modelagem PEAS (Agente Inteligente)
| Componente | Descrição |
| :--- | :--- |
| **Performance (P)** | Para que uma solução inteligente voltada a pacientes com Doença de Parkinson seja considerada bem-sucedida, o agente deve perseguir metas objetivas relacionadas à redução de sintomas, melhoria funcional e segurança clínica. A principal meta é reduzir significativamente a amplitude e a frequência do tremor sem prejudicar o movimento voluntário. Isso significa que o sistema deve ser capaz de identificar corretamente o tremor e aplicar compensação ativa apenas quando necessário. Um critério de sucesso mensurável seria, por exemplo, uma redução percentual consistente da amplitude do tremor medida por sensores inerciais, mantendo a fluidez do movimento intencional.
| **Ambiente (E)** | O agente opera na Doença de Parkison
| **Atuadores (A)** |atuadores eletromecânicos, encoders e sensores de torque ou corrente, como motores ou servomotores acoplados a uma órtese ou exoesqueleto
| **Sensores (S) ** | Sensores Eletromiografia (EMG) de superfície - Permite diferenciar movimento voluntário de tremor,Unidade de Medição Inercial (IMU - acelerômetro + giroscópio) - Permite identificar padrão típico do tremor e medir sua intensidade, Giroscópio da IMU ou encoder no atuador - Necessário para aplicar compensação proporcional e estável e Sensor de torque ou corrente do motor - Garante controle seguro e evita sobrecompensação.

---

### 4. Arquitetura de Dados e IA
Definição das fontes de dados e da inteligência por trás da solução.

* **Origem dos Dados:** [Link para dataset no Kaggle/UCI ou descrição da fonte].
* **Lógica de IA:** [Técnica utilizada: ex: Redes Neurais, Lógica Fuzzy, Busca A*].
* **Justificativa:** Por que essa técnica é ideal para este problema específico?

---

### 5. Plano de Tratamento de Dados (ETL)
O fluxo de processamento dos dados segue estas etapas:
1. **Extração:** Coleta de dados via arquivos [CSV/JSON] ou simulação.
2. **Transformação:** Limpeza de nulos, normalização e engenharia de atributos.
3. **Carga:** Disponibilização dos dados para o treinamento do modelo de IA.

---

### 6. Estrutura do Repositório
Organização simplificada para o Milestone 1:
* `/data`: Arquivos de dados originais (raw) e tratados (processed).
* `/notebooks`: Experimentos iniciais e análise exploratória.
* `/scripts`: Códigos Python (.py) contendo a lógica do agente e do ETL.
* `requirements.txt`: Lista de bibliotecas para rodar o projeto.
* `README.md`: Documentação atual do projeto.

---

### 7. Instruções para Execução
Para reproduzir o ambiente e testar o diagnóstico:
1. Clone este repositório.
2. Instale as dependências:
   ```bash
   pip install -r requirements.txt
