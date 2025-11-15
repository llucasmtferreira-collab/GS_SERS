# GS_SERS
GLOBAL SOLUTION – SOLUÇÕES EM ENERGIAS RENOVÁVEIS E SUSTENTÁVEIS


#  Descrição Clara da Solução

A solução desenvolvida consiste em uma análise estatística, energética e exploratória completa aplicada a um conjunto de dados contendo medições horárias de consumo elétrico e temperatura de um estabelecimento comercial ao longo de um ano inteiro. O objetivo central é fornecer uma visão clara, fundamentada e acionável sobre como o estabelecimento utiliza energia ao longo do tempo — identificando padrões, horários críticos, oportunidades de economia e potenciais desperdícios.

---

##  Descrição da Base de Dados

A base utilizada contém dados horários de consumo de energia e temperatura ao longo de um ano completo. Cada registro representa uma medição realizada em um determinado horário, permitindo analisar padrões diários, semanais e mensais.

**Total de registros:** 8.784  
**Total de variáveis:** 17 (após criação das colunas derivadas)

### **Variáveis principais**
- **consumo** – consumo bruto em Wh  
- **consumo_kwh** – conversão para kWh  
- **temperatura** – temperatura do ambiente  
- **data_hora** – data e hora da medição  
- **hora_do_dia** – hora extraída da coluna de data  
- **dia_da_semana** – número do dia da semana (0 a 6)  
- **mes_do_ano** – número do mês (1 a 12)  
- **nome_do_mes** – mês em texto  
- **nome_do_dia** – dia da semana em texto  
- **fim_de_semana** – variável indicando se o dia é sábado/domingo  
- **periodo_do_dia** – madrugada, manhã, tarde ou noite  
- **media_movel_24h** – média móvel de 24 horas  
- **media_movel_7d** – média móvel de 7 dias  

### **Fonte dos dados**
 ** O arquivo está disponível na pasta `/Fonte` deste repositório.**
 
 ---

##  1. Leitura e Preparação dos Dados
O dataset (.csv) foi carregado no Google Colab e passou por:
- Conversão da coluna de datas.
- Criação de colunas derivadas (hora, dia da semana, nome do mês etc.).
- Verificação de consistência.
- Cálculo do consumo por hora e por dia.

Essas etapas estruturam o dataset para as análises posteriores.

---

##  2. Estatísticas Descritivas
Foram calculadas métricas essenciais:
- Média, mediana, moda.
- Mínimo, máximo e amplitude.
- Quartis e percentis.

Essas estatísticas revelam o comportamento geral do consumo, permitindo detectar valores atípicos ou flutuações significativas.

---

##  3. Análises Gráficas
Foram criados gráficos como:
- Boxplots por hora.
- Boxplots por dia da semana.
- Série temporal do consumo ao longo do ano.

Os gráficos indicaram que o consumo do comércio é **regular e previsível**, sem grandes variações mensais.

---

##  4. Identificação de Desperdícios (Bloco 7.1)
Utilizei critérios estatísticos para detectar picos anormais:

- **Picos anormais detectados:** 0  
- **Percentual de picos no ano:** 0%  
- **Horas com maior consumo:** entre 12h e 16h  
- **Dias com maior consumo:** sábado e sexta  

Também avaliamos a relação entre temperatura e consumo:

- **Correlação:** 0.434  
  - Acima de 0.3 → influência moderada e relevante.

---

##  5. Simulação de Ajustes Operacionais (Bloco 7.2)
Foram simuladas duas estratégias de redução do consumo:

###  Redução de 10% nos horários de pico  
Economia estimada: **0.1654 kWh**

###  Ajustes no consumo dos fins de semana  
Economia estimada: **0.2480 kWh**

###  Economia total estimada  
**0.4134 kWh/ano**

---

##  6. Ganhos Ambientais e Econômicos (Bloco 7.3)
Considerando o fator médio de emissão de CO₂ e o preço médio da energia:

- **Redução anual de CO₂:** 0.1964 kg  
- **Economia financeira:** R$ 0.39/ano  

Os valores são pequenos devido ao tamanho reduzido do dataset, mas ilustram corretamente o impacto dos ajustes.

---

##  7. Conclusão Geral
A solução permitiu:

- Entender o padrão de consumo do comércio.
- Verificar que **não existem desperdícios severos**.
- Identificar horários e dias de maior gasto.
- Propor ajustes simples e realistas para redução.
- Estimar ganhos ambientais e financeiros.
- Gerar um relatório completo e totalmente replicável no Google Colab.

Essa análise oferece ao estabelecimento uma visão clara do seu comportamento energético e de possíveis oportunidades de melhoria.


#  Orientações de Execução

### 1. Acesse o Google Colab
Abra o navegador e entre em:  
https://colab.research.google.com

---

### 2. Crie um novo notebook
No canto inferior direito da página inicial, clique em:  
**New Notebook** (ou **Novo notebook**)

---

### 3. Baixe os dados deste repositório
No GitHub, abra a pasta **/Fonte**.  
Faça o download do arquivo **CSV** disponibilizado ou utilize o link indicado no arquivo `Link da origem dos dados.md`.

---

### 4. Envie o CSV para o Colab
No notebook do Colab:

1. Clique no ícone de **pasta** (à esquerda).  
2. Clique no botão **Upload**  
3. Selecione o arquivo CSV que você baixou.

---

### 5. Carregue o arquivo no Python
Com o arquivo enviado, basta rodar a célula com:

df = pd.read_csv("energy_consumption_levels.csv")

---

### 6. Execute as células na ordem
Clique em cada célula e pressione **Shift + Enter**, ou utilize o menu:
**Runtime > Run all** (Executar tudo).

### 7. Acompanhe os resultados
Os gráficos, análises e tabelas aparecerão logo abaixo das células conforme forem executadas.

---

Pronto!  
O notebook vai gerar automaticamente todas as métricas, análises, gráficos e simulações do projeto.

#  Estrutura do Repositório

```
GS_SERS/
├─ Fonte/ # Arquivos de dados (CSV)
│ └─ consumo_comercio.csv
│ └─ Link da origem dos dados.md # Documento com a fonte oficial do dataset
│
├─ Códigos/ # Notebooks e scripts utilizados no projeto
│ └─ analise_consumo.ipynb
│
└─ README.md # Documentação principal do projeto
```

### Descrição das pastas

- **Fonte/**  
  Contém o arquivo CSV utilizado na análise e um arquivo indicando a fonte original dos dados.

- **Códigos/**  
  Inclui o notebook `.ipynb` com toda a análise, gráficos e etapas utilizadas no projeto.

- **README.md**  
  Documento principal contendo a explicação da solução, como executar o projeto, estrutura e detalhes gerais.
