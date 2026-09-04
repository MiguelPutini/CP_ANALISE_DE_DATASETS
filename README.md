# Análise de Dados no Setor de Energia
## Soluções em Energias Renováveis e Sustentáveis — Ciência da Computação

Atividade prática focada na preparação, inspeção e análise de diferentes conjuntos de dados do setor de energia utilizando **Orange Data Mining**, **Python** e **Pandas**.

---

## Objetivo da Atividade
Aplicar procedimentos de pré-processamento, limpeza, filtragem e análise exploratória inicial em datasets reais do setor energético, relacionando cada operação estatística e computacional ao contexto prático de eficiência energética, geração renovável e consumo residencial/industrial.

---

## Organização Geral da Atividade

A resolução de cada caso prático divide-se em duas etapas principais:

1. **Etapa A — Orange Data Mining:**
   - Carregamento, inspeção inicial no *Data Table* e verificação da integridade dos dados (valores ausentes).
   - Seleção de atributos relevantes (*Select Columns*).
   - Amostragem aleatória dos registros (*Data Sampler*).
   - Exportação do conjunto preparado em formato CSV.

2. **Etapa B — Python / Pandas:**
   - Carregamento da amostra exportada.
   - Organização, inspeção inicial (`head`, `shape`, `info`, `describe`) e renomeação de colunas.
   - Cálculo de métricas de referência (valores máximos, médias, limiares percentuais).
   - Criação de subconjuntos de dados (*DataFrames*) baseados em múltiplos critérios e filtros condicionais.
   - Contagem de registros, cálculo de percentuais e interpretação analítica dos resultados.

---

## Datasets e Situações Práticas

Cada grupo de trabalho deve selecionar um dos datasets abaixo conforme a indicação e resolver a situação específica correspondente.

---

### Dataset 1 — Appliances Energy Prediction (UCI)
* **Descrição:** Consumo de eletrodomésticos em uma residência, associado a temperatura, umidade e condições ambientais.
* **Situação:** Análise do comportamento de uma residência de baixo consumo para identificar períodos de consumo elevado dos eletrodomésticos e observar as condições de temperatura e umidade associadas.
* **Etapa A (Orange Data Mining):**
  - Carregar `energydata_complete.csv`.
  - Utilizar *Select Columns* para manter `Appliances`, `lights`, pelo menos três atributos de temperatura e três de umidade.
  - Verificar valores ausentes.
  - Gerar amostra aleatória de 10% (*Data Sampler*) e exportar em CSV.
* **Etapa B (Python / Pandas):**
  - Carregar a amostra e apresentar `head()`, `shape`, `info()` e `describe()`.
  - Renomear `Appliances` para `Consumo_Eletrodomesticos` e simplificar pelo menos três atributos ambientais.
  - Determinar o maior consumo de eletrodomésticos registrado e calcular um limiar de 70% do valor máximo.
  - Criar um DataFrame com registros acima desse limiar, contando a quantidade e o percentual em relação à amostra.
  - Calcular a temperatura média de `T1` e criar um segundo DataFrame contendo simultaneamente consumo > 70% do máximo e temperatura acima da média.
  - Comparar os dois DataFrames e interpretar o efeito da inclusão da temperatura como critério restritivo.

---

### Dataset 2 — Steel Industry Energy Consumption (UCI)
* **Descrição:** Consumo energético de uma indústria siderúrgica, com potência reativa, fator de potência, emissões de CO2 e classificação de carga.
* **Situação:** Localizar situações de consumo elevado e verificar se coincidem com condições de carga elevada (`Maximum Load`) ou valores desfavoráveis de fator de potência.
* **Etapa A (Orange Data Mining):**
  - Carregar o dataset no *File*.
  - Utilizar *Select Columns* para manter `Usage_kWh`, variáveis de potência reativa, fatores de potência, `WeekStatus`, `Day_of_week` e `Load_Type`.
  - Inspecionar valores de `Load_Type` e `WeekStatus`.
  - Verificar valores ausentes.
  - Gerar amostra aleatória de 20% e exportar em CSV.
* **Etapa B (Python / Pandas):**
  - Carregar a amostra, renomear `Usage_kWh` para `Consumo_kWh` e simplificar os atributos de fator de potência.
  - Apresentar inspeção inicial (`head`, `shape`, `info`, `describe`).
  - Determinar o maior consumo e calcular o limiar de 75% do máximo.
  - Criar DataFrame com registros acima de 75% do consumo máximo e calcular contagem e percentual.
  - Verificar quantos registros pertencem à categoria `Maximum Load`.
  - Definir um limite coerente para um dos fatores de potência e criar um novo DataFrame com consumo elevado e fator de potência crítico.
  - Explicar a relevância operacional desse segundo conjunto para a equipe de gestão de energia.

---

### Dataset 3 — Power Consumption of Tetouan City (UCI)
* **Descrição:** Consumo elétrico de três zonas de distribuição da cidade de Tétouan, associado a variáveis meteorológicas.
* **Situação:** Identificar qual das três zonas apresenta o maior pico de consumo e observar as condições ambientais nos momentos de maior demanda.
* **Etapa A (Orange Data Mining):**
  - Carregar o dataset.
  - Utilizar *Select Columns* para manter as três variáveis de consumo, `Temperature`, `Humidity` e `Wind Speed`.
  - Inspecionar escalas de valores das zonas de consumo e verificar valores ausentes.
  - Gerar amostra aleatória de 15% e exportar em CSV.
* **Etapa B (Python / Pandas):**
  - Renomear as três variáveis de consumo para `Consumo_Zona_1`, `Consumo_Zona_2` e `Consumo_Zona_3`.
  - Determinar o consumo máximo em cada zona e identificar qual delas apresenta o maior pico na amostra.
  - Para a zona identificada, calcular 70% do pico máximo e filtrar os registros acima desse limiar (quantidade e percentual).
  - Calcular a temperatura média e criar um segundo DataFrame combinando consumo acima do limiar e temperatura acima da média.
  - Comparar os conjuntos e explicar o impacto da condição ambiental na filtragem dos dados.

---

### Dataset 4 — Solar Power Generation Data (Kaggle)
* **Descrição:** Dados de geração e sensores de usinas fotovoltaicas, com medições em inversores e sensores ambientais.
* **Situação:** Localizar períodos de alta geração em usina fotovoltaica e identificar quais inversores aparecem com maior frequência nesses momentos.
* **Etapa A (Orange Data Mining):**
  - Carregar o arquivo de geração da planta.
  - Utilizar *Select Columns* para manter `DATE_TIME`, `SOURCE_KEY`, `DC_POWER`, `AC_POWER`, `DAILY_YIELD` e `TOTAL_YIELD`.
  - Inspecionar registros com potência zero e faixa de valores de `AC_POWER`.
  - Gerar amostra aleatória de 20% e exportar em CSV.
* **Etapa B (Python / Pandas):**
  - Carregar a amostra e renomear colunas para `Potencia_CC`, `Potencia_CA` e `Geracao_Diaria`.
  - Apresentar inspeção inicial (`head`, `shape`, `info`, `describe`).
  - Determinar a maior potência CA e calcular limiar de 70% do máximo.
  - Criar DataFrame com registros acima do limite (quantidade e percentual).
  - Utilizar `value_counts()` em `SOURCE_KEY` para identificar o inversor mais frequente nos registros de alta geração e interpretar o achado.

---

### Dataset 5 — Wind & Solar Energy Production (Kaggle)
* **Descrição:** Produção de energia eólica e solar, permitindo comparar o comportamento das duas fontes renováveis.
* **Situação:** Comparar períodos de alta produção solar e eólica utilizando escalas normalizadas em relação ao máximo de cada fonte.
* **Etapa A (Orange Data Mining):**
  - Carregar o dataset e selecionar atributos temporais e de produção solar e eólica.
  - Observar mínimos, máximos e verificar valores ausentes.
  - Gerar amostra aleatória de 20% e exportar em CSV.
* **Etapa B (Python / Pandas):**
  - Renomear variáveis para `Geracao_Solar` e `Geracao_Eolica`.
  - Determinar o valor máximo de cada fonte e calcular 70% do máximo para ambas separadamente.
  - Criar DataFrames distintos para alta geração solar e eólica (contagem e percentuais).
  - Comparar qual fonte apresenta maior frequência acima de 70% do seu próprio máximo.
  - Explicar por que não se deve utilizar um valor numérico absoluto único como limite para ambas as fontes sem considerar suas escalas.

---

### Dataset 6 — Individual Household Electric Power Consumption (UCI)
* **Descrição:** Medições detalhadas de consumo elétrico residencial, tensão, corrente, potência ativa, potência reativa e submedições.
* **Situação:** Identificar episódios de demanda residencial elevada que também apresentem corrente elétrica acima do comportamento médio.
* **Etapa A (Orange Data Mining):**
  - Carregar o dataset original completo (sem amostra anterior).
  - Inspecionar dados e tratar valores ausentes.
  - Utilizar *Select Columns* para manter `Global_active_power`, `Global_reactive_power`, `Voltage`, `Global_intensity` e os três atributos `Sub_metering`.
  - Gerar nova amostra aleatória de 10% dos dados tratados e exportar em CSV.
* **Etapa B (Python / Pandas):**
  - Carregar a nova amostra e simplificar os nomes dos atributos.
  - Determinar a potência ativa máxima e calcular limiar de 75% do máximo (filtrar, contar e percentual).
  - Calcular a corrente média da amostra.
  - Criar segundo DataFrame combinando potência ativa > 75% do máximo e corrente acima da média.
  - Comparar os conjuntos e explicar o effecto da inclusão da corrente como segunda condição analítica.

---

## Orientações de Entrega
* Todos os exercícios de programação e análise devem ser resolvidos e entregues em um **único arquivo de Notebook Python (`.ipynb`)**.
* O notebook deve conter os códigos executáveis, as saídas obtidas e as respostas interpretativas para cada questão do dataset atribuído ao grupo.
