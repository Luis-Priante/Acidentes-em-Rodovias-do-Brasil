# Acidentes-em-Rodovias-do-Brasil
O Brasil registra milhares de acidentes de trânsito por ano em rodovias federais, com alto custo humano (mortos e feridos) e econômico (saúde pública, seguros, perda de produtividade). Uma boa análise de dados pode apoiar políticas públicas, campanhas de educação no trânsito e decisões de investimento em infraestrutura.
# Problema sugerido  
**Tema:** Acidentes de trânsito em rodovias federais do Brasil no ano de 2026

## 1. Dissertação sobre o problema

### Descrição detalhada
O Brasil registra milhares de acidentes de trânsito por ano em rodovias federais, com alto custo humano (mortos e feridos) e econômico (saúde pública, seguros, perda de produtividade).

Os dados da Polícia Rodoviária Federal (PRF) trazem, para cada ocorrência, informações como: data, horário, estado/rodovia, tipo de acidente, condições climáticas, tipo de veículo, gravidade (feridos, mortos) etc.

### Importância e relevância
- Segurança viária é um problema de saúde pública: reduzir acidentes significa salvar vidas e reduzir custos com internações e reabilitação.  
- Governos e concessionárias precisam de evidências para priorizar ações (fiscalização em horários críticos, melhorias em trechos perigosos, campanhas educativas específicas).  
- Uma boa análise de dados pode apoiar políticas públicas, campanhas de educação no trânsito e decisões de investimento em infraestrutura.

### Como a análise de dados pode ajudar
- Identificar padrões de risco: horários, dias da semana, tipos de pista, tipos de veículo mais envolvidos, tipos de acidentes.  
- Mapear trechos críticos (rodovias/UF com maior concentração de acidentes graves).  
- Verificar se há associação entre tipo de causa (ex.: ultrapassagem indevida, velocidade) e gravidade do acidente.  
- A partir disso, propor ações: reforço de fiscalização em horários críticos, melhoria de sinalização, campanhas focadas em motociclistas etc.

---

## 2. Fontes de dados públicas e não confidenciais

### Fonte principal – PRF (rodovias federais)

**Dados abertos de acidentes da PRF (BAT – Boletim de Acidente de Trânsito)**  
- Descrição: base nacional de acidentes em rodovias federais, com arquivos CSV anuais, agrupados por ocorrência e por pessoa (vítimas).  
- Tipo de dado: estruturado (CSV).  
- Acesso:  
  - [Arquivo CSV – Exemplo](https://drive.google.com/file/d/1EsGox0UnBWSaM6mrkNSUlYUOecubLCsh/view)

**Dicionário de dados – Acidentes (PRF)**  
- Descrição: documento com a explicação dos campos da base (códigos de tipo de acidente, gravidade, UF etc.).  
- Tipo de dado: documento auxiliar (PDF/HTML), não estruturado.  
- Acesso: link “Dicionário de Dados – Acidentes” na mesma página de dados abertos da PRF.  
- Método: download direto (PDF/HTML).

---

## 3. Análise Exploratória de Dados (EDA) – Roteiro

Analisado os meses de janeiro e fevereiro do ano vigente (2026), pois são os dados que até o momento estão disponibilizados no site da PRF no arquivo “Acidentes por ocorrência”.

### 3.1 Limpeza e pré-processamento

**Ferramentas possíveis:** Google Planilhas.

**Passos típicos:**
- Importar o CSV:  
  - Google Planilhas: `Arquivo > Importar` (ou carregar para o Drive e abrir).  
- Ajustar separador decimal e formato de data/hora.  
- Criar campo a partir do estado da ocorrência UF e período.

### 3.2 Análise descritiva

**Medidas gerais:**
- Total de acidentes no ano.  
- Percentual de acidentes com mortos.

**Distribuições e padrões:**
- Acidentes por UF..  
- Acidentes por tipo de acidente (colisão frontal, saída de pista, atropelamento etc.).  
- Quantidade de acidentes totais e acidentes com mortes.  
- Distribuição por quantidade de acidentes por gravidade (feridos graves, feridos leves, ilesos etc.).

### 3.3 Identificação de variáveis importantes e correlações

**Análises:**
- Tabelas cruzadas (ex.: gravidade × tipo de acidente).

---

## 4. Relatório de Insights

### Estrutura sugerida

#### 4.1 Resumo executivo (1 página)
- Problema e contexto.  
- Base utilizada (PRF, ano X).  
- Método resumido.  
- Principais 3–5 achados (bullet points).

#### 4.2 Metodologia
- Fontes de dados e período analisado.  
- Ferramentas usadas (Planilhas).  
- Principais etapas de limpeza e tratamento.

#### 4.3 Principais resultados (com gráficos/tabelas)
**Exemplos de possíveis insights (a confirmar com os dados reais):**
- Maior concentração de acidentes graves em determinados estados/rodovias.  
- Tipos de acidente que mais geram mortes (ex.: colisão frontal, atropelamento).  

#### 4.4 Discussão e relevância para a problemática
- Relacionar os padrões encontrados com fatores:
  - Comportamentais (velocidade, cansaço, álcool).  
  - De infraestrutura (pistas simples, curvas).  
  - De fiscalização.
- Indicar como esses achados podem orientar:
  - Campanhas educativas segmentadas.  
  - Reforço de fiscalização em horários/locais críticos.  
  - Projetos de engenharia de tráfego (duplicação, iluminação, sinalização).

#### 4.5 Sugestões de ações ou soluções
- Priorizar fiscalização de velocidade e álcool em rodovias e horários críticos.  
- Melhorar sinalização em trechos com muita colisão traseira.  
- Criar campanhas específicas para motociclistas, se forem muito afetados.

---

## 5. Visualização de dados no Looker Studio

### 5.1 Preparação
- Carregar o CSV final (já limpo) para o Google Drive ou gravar em uma planilha Google.  
- No Looker Studio, criar uma **nova fonte de dados** conectando à planilha.

### 5.2 Gráficos e dashboards

No mesmo painel (dashboard), incluir:

#### Indicadores principais (scorecards)
- Total de acidentes.  
- Total de mortos, feridos graves, feridos leves e ilesos.  
- Taxa de acidentes com morte (%).

#### Séries temporais

- Linha separando acidentes totais e acidentes com morte.

#### Distribuição geográfica
- Mapa por UF (ou por estado) mostrando:
  - Quantidade de acidentes, ou  
  - Quantidade de mortos.

#### Gráficos Pizza
- Acidentes por tipo de acidente.  

#### Filtros interativos
- Filtro por período.  
- Filtro por UF.

### Relatório Looker Studio

- Acesse o relatório completo aqui: [Abrir relatório no Looker Studio](https://datastudio.google.com/s/vAC4GFhTq6w)

