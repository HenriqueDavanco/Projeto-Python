🚀 Pipeline de Cotações Cambiais com Python + LLM
Este projeto implementa uma pipeline completa para coletar, processar e analisar taxas de câmbio, integrando um modelo de linguagem grande (LLM) para gerar insights executivos. O projeto foi desenvolvido como parte do MBA em Data Engineering, focado em "Python Programming for Data Engineers".

✨ Objetivo do Projeto
O principal objetivo é demonstrar a construção de uma pipeline de dados end-to-end, cobrindo:

Ingestão: Coleta de dados de taxas de câmbio da API https://www.exchangerate-api.com/.

Transformação: Normalização e validação dos dados, garantindo sua qualidade.

Carga: Armazenamento dos dados processados em formato Parquet na camada gold.

Enriquecimento com LLM: Geração de resumos e insights em linguagem natural, utilizando o Google Gemini, voltados para usuários de negócio.

Testes e Observabilidade: Implementação de testes unitários e logging estruturado para garantir a robustez e monitoramento da pipeline.

📦 Estrutura do Projeto


├── src/                      # Código fonte da pipeline
│   ├── ingest.py             # Coleta de dados da API
│   ├── transform.py          # Normalização e validação
│   ├── load.py               # Carregamento para Parquet
│   ├── llm_enrichment.py     # Integração com a LLM (Google Gemini)
│   ├── utils.py              # Funções auxiliares (configuração, logging)
│   └── main.py               # Orquestrador principal (executa a pipeline)
├── raw/                      # Dados JSON brutos da API
├── silver/                   # Dados normalizados (opcional, para depuração)
├── gold/                     # Dados finais em formato Parquet
├── reports/                  # Relatórios/insights gerados pela LLM
├── .env                      # Variáveis de ambiente (chaves de API)
├── requirements.txt          # Dependências do Python
├── README.md                 # Documentação do projeto
└── tests/                    # Testes unitários
    ├── test_ingest.py        # Testes para a etapa de ingestão
    ├── test_transform.py     # Testes para a etapa de transformação
    └── __init__.py           # Inicializa o diretório como pacote Python


    

⚙️ Setup e Configuração
Siga os passos abaixo para configurar e executar o projeto.

1. Clonar o Repositório (Exemplo)
git clone <URL_DO_SEU_REPOSITORIO>
cd pipeline-cotacoes-cambiais

2. Criar e Ativar o Ambiente Virtual
É altamente recomendado usar um ambiente virtual para gerenciar as dependências.

python -m venv venv
# No Windows
.\venv\Scripts\activate
# No macOS/Linux
source venv/bin/activate

3. Instalar as Dependências
pip install -r requirements.txt

4. Configurar Variáveis de Ambiente (.env)
Crie um arquivo chamado .env na raiz do projeto (no mesmo nível do README.md) e adicione suas chaves de API:

EXCHANGE_RATE_API_KEY=SUA_CHAVE_DA_EXCHANGERATE_API
GEMINI_API_KEY=SUA_CHAVE_DA_API_GEMINI

EXCHANGE_RATE_API_KEY: Obtenha esta chave registrando-se gratuitamente em exchangerate-api.com.

GEMINI_API_KEY: Obtenha esta chave através do Google AI Studio ou da console do Google Cloud.

▶️ Como Executar
Após o setup, você pode executar a pipeline completa através do script main.py:

python src/main.py

Ao executar, você verá logs estruturados no console, indicando o progresso e o status de cada etapa. Os relatórios gerados pela LLM serão impressos no console e salvos na pasta reports/.

✅ Testes
Para executar os testes unitários, certifique-se de que o pytest está instalado (incluído no requirements.txt) e execute a partir da raiz do projeto:

pytest tests/

Isso executará todos os testes definidos na pasta tests/ e reportará os resultados.

📋 Entregáveis
Código no GitHub: O repositório contém todo o código fonte da pipeline.

README.md: Este documento detalha o setup, execução e configuração.

Arquivos Finais (/gold/): Contêm os dados de cotações cambiais limpos e processados em formato Parquet.

Exemplo: gold/exchange_rates_YYYY-MM-DD.parquet

Relatórios/insights da LLM (/reports/): Arquivos JSON contendo os resumos e detalhes gerados pela LLM.

Exemplo: reports/llm_insights_YYYY-MM-DD.json

📊 Critérios de Avaliação Atendidos
30% Pipeline (ETL completo): Implementação das etapas de Ingestão (ingest.py), Transformação (transform.py) e Carga (load.py) com fluxo orquestrado por main.py.

15% Qualidade e robustez (testes + logging):

Testes Unitários: Presentes na pasta tests/, cobrindo as validações de dados e o fluxo de ingestão/transformação.

Logging Estruturado: Utilização da biblioteca logging com formato JSON (src/utils.py), registrando informações (INFO) e erros (ERROR) em todas as etapas, incluindo o logging de prompt/response da LLM para auditoria.

15% Documentação e clareza no README: Este README.md fornece instruções claras de setup, execução e explica a estrutura do projeto.

10% Uso inteligente/estratégico da LLM: A LLM (Google Gemini) é utilizada para interpretar o dataset diário, gerando um resumo executivo com a variação das principais moedas e insights acionáveis para usuários de negócio, conforme o requisito do projeto.

15% Criatividade extra (ex.: dashboards ou análises adicionais): (Opcional - Adicione aqui se implementar um dashboard Streamlit, por exemplo.)

🗓️ Regras de Entrega e Apresentação

Este projeto está configurado para ser entregue com o código no GitHub e este README.md completo. A apresentação ao vivo seria uma oportunidade para demonstrar o funcionamento da pipeline e os insights gerados.

