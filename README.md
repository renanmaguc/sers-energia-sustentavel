# sers-energia-sustentavel
# Projeto SERS – Gestão Sustentável de Energia em um Escritório de TI

Este repositório reúne os artefatos do mini‑projeto desenvolvido para a disciplina **Soluções em Energias Renováveis e Sustentáveis (SERS)**.

## 1. Descrição do problema

O consumo de energia elétrica é um dos principais custos operacionais de escritórios de tecnologia da informação, que dependem fortemente de computadores, monitores, equipamentos de rede, climatização e iluminação.  
Ao mesmo tempo, organizações são pressionadas a adotar práticas mais sustentáveis, seja por exigências regulatórias, metas de ESG ou responsabilidade socioambiental.

Este projeto considera um pequeno escritório de TI e busca:

- Identificar padrões de consumo de energia ao longo de um mês;
- Detectar desperdícios, especialmente fora do horário de expediente;
- Simular melhorias baseadas em boas práticas e automação simples;
- Simular a adoção de um sistema de energia solar fotovoltaica.

## 2. Estrutura do repositório


```text
sers-energia-sustentavel/
├─ dados/
│  ├─ consumo_energia.csv          #dados simulados de consumo horário
├─ src/
│  ├─ SERS_projeto_energia.ipynb   #notebook principal com simulação e análises
├─ docs/
│  ├─ SERS_relatorio_energia.pdf   #relatório em PDF pronto para entrega
├─ README.md                       #este arquivo
```

## 3. Dados utilizados

Os dados de consumo foram **simulados** para representar o uso de energia em um escritório de TI durante 30 dias, com leituras de **hora em hora**.

Colunas principais do arquivo `consumo_energia.csv`:

- `data_hora` – data e hora da medição;
- `data` – apenas a data (aaaa-mm-dd);
- `hora` – hora do dia (0 a 23);
- `dia_da_semana` – dia da semana (0 = segunda, ..., 6 = domingo);
- `eh_dia_util` – indica se é dia útil (True/False);
- `em_horario_trabalho` – indica se está dentro do horário de expediente (8h–18h em dias úteis);
- `kwh` – consumo estimado em kWh naquele intervalo de uma hora;
- `kwh_ajustado` – consumo após aplicação das ações de eficiência (ajustes de uso).

## 4. Código e simulações

O arquivo principal é:

- `src/SERS_projeto_energia.ipynb`

Ele contém:

1. **Simulação dos dados de consumo**
   - Geração de dados horários para um mês;
   - Identificação de dias úteis, fins de semana e horários de trabalho.

2. **Análise exploratória**
   - Consumo diário total;
   - Consumo médio por hora do dia;
   - Proporção de consumo em horário de trabalho vs fora do expediente.

3. **Desenvolvimento da solução – Ajustes de uso (Opção A do trabalho)**
   - Simulação de boas práticas e automação simples:
     - desligamento automático de computadores;
     - sensores de presença para iluminação;
     - ajuste do horário de operação do ar‑condicionado.
   - A modelagem considera uma redução de **50%** no consumo fora do expediente.
   - São calculados:
     - consumo original;
     - consumo após ajustes;
     - economia em kWh e em percentual.

4. **Desenvolvimento da solução – Energia solar (Opção C do trabalho)**
   - Simulação de um sistema fotovoltaico capaz de gerar cerca de **35%** do consumo mensal original;
   - Cálculo da nova demanda de energia da rede elétrica nos cenários:
     - antes das ações;
     - apenas com ajustes de uso;
     - ajustes de uso + energia solar.

5. **Comparação de cenários**
   - Gráfico de barras comparando os três cenários;
   - Discussão dos impactos na redução de consumo.

## 5. Como executar o notebook

Você pode executar o notebook de duas formas:

### 5.1. Google Colab

1. Envie o arquivo `SERS_projeto_energia.ipynb` para o Colab;
2. Faça upload também da pasta `dados/` com o arquivo `consumo_energia.csv` (ou deixe o próprio notebook gerar o CSV);
3. Execute as células na ordem em que aparecem.

### 5.2. Localmente (Jupyter / VSCode)

1. Certifique‑se de ter Python 3 instalado.
2. Instale as dependências (por exemplo, usando `pip`):

```bash
pip install pandas numpy matplotlib
```

3. Abra o projeto em seu ambiente preferido (Jupyter Notebook, JupyterLab ou VSCode com suporte a notebooks).
4. Abra o arquivo `src/SERS_projeto_energia.ipynb`.
5. Execute as células na ordem.

## 6. Relatório em PDF

O relatório final do projeto está em:

- `docs/SERS_relatorio_energia.pdf`

Ele apresenta:

- Introdução e motivação do problema;
- Descrição do cenário e dos dados;
- Metodologia utilizada;
- Resultados e comparação de cenários (antes e depois das ações);
- Discussão e conclusão.
