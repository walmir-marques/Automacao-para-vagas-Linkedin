# Projeto de Web Scraping - Vagas de Emprego do LinkedIn

Este é um projeto de **Web Scraping** que coleta vagas de emprego do **LinkedIn**, salva as informações em um banco de dados **PostgreSQL** hospedado no **Supabase**, e visa ser automatizado para rodar uma vez por dia, futuramente na **AWS**.

## 🚀 Tecnologias Utilizadas

- **Python**: Linguagem principal para desenvolver o script de scraping e interagir com o banco de dados.
- **BeautifulSoup**: Biblioteca para fazer o scraping da página web do LinkedIn e extrair as informações desejadas.
- **Supabase**: Plataforma para hospedar o banco de dados PostgreSQL, onde as vagas de emprego são armazenadas.
- **PostgreSQL**: Banco de dados relacional utilizado para armazenar as vagas extraídas.
- **Datetime**: Biblioteca usada para registrar a data de inserção das vagas no banco de dados.
- **Pandas**: Utilizado para manipulação e organização dos dados extraídos em um formato estruturado antes de inseri-los no banco de dados.
- **AWS** (Futuro): A ideia é colocar o projeto na AWS para realizar a automação diária do processo de scraping.

## 📋 Como Funciona

1. O **script de scraping** utiliza a biblioteca **BeautifulSoup** para acessar as páginas de vagas de emprego no LinkedIn.
2. As informações extraídas incluem: título da vaga, nome da empresa, localização, tempo de publicação, link da vaga e da empresa, entre outras.
3. Esses dados são armazenados em um **DataFrame** utilizando o **Pandas** e, posteriormente, inseridos no banco de dados **PostgreSQL** através da integração com o **Supabase**.
4. O projeto possui uma lógica de **upsert**, o que significa que, se a vaga já estiver cadastrada (identificada pelo link único da vaga), ela será atualizada. Caso contrário, uma nova vaga será inserida.
5. **Futuro**: Uma vez por dia, o processo de scraping será automatizado, hospedado na **AWS**, para garantir que os dados sejam sempre atualizados sem intervenção manual.

## 🔧 Como Rodar o Projeto

1. **Clone este repositório**:
   ```bash
   git clone https://github.com/seu-usuario/nome-do-repositorio.git
   cd nome-do-repositorio
   
2. **Instale as dependências:**:
   ```bash
    pip install -r requirements.txt

3. **Configure sua chave de API do Supabase:**:
   - Crie uma conta no Supabase.
   - Crie um novo projeto e configure o banco de dados PostgreSQL
   - Obtenha a URL do projeto e a chava da API para autenticar sua conexão.

4. **Acesse os dados no Supabase:**: 
   ```bash
    python script_de_scraping.py

5. **Execute o script:**: Depois de executar o script, você poderá ver as vagas salvas no seu banco de dados PostgreSQL.

6. ## 🧠 O Que Aprendi

- **Web Scraping com BeautifulSoup**: Como extrair dados estruturados de páginas web de maneira eficiente e ética.
- **Integração com Supabase**: Como conectar Python ao Supabase para armazenar dados em um banco de dados PostgreSQL.
- **Automação de Processos**: A ideia de automatizar o scraping e armazenar dados de forma contínua, reduzindo a necessidade de intervenção manual.
- **Trabalhando com APIs**: Como usar a chave da API do Supabase para interagir com o banco de dados diretamente.
- **Melhoria contínua**: Como otimizar o código para lidar com erros e garantir que as informações sejam sempre atualizadas de forma eficiente.

## ⚙️ Planejamento Futuro

- **Automação na AWS**: No futuro, o projeto será hospedado na AWS e configurado para rodar automaticamente uma vez por dia, utilizando o **AWS Lambda** ou **EC2** para executar o script de scraping.
- **Melhoria no Scraping**: Planejo melhorar o script para lidar com diferentes tipos de páginas de vagas e otimizar o processo de extração de dados.
- **Escalabilidade**: A ideia é escalar o projeto para coletar vagas de múltiplas fontes, além do LinkedIn.

## 📅 Melhorias Futuras

1. **Automação Completa**: Colocar o processo em execução diária automaticamente usando **AWS Lambda** ou **Amazon EC2**.
2. **Scraping de Múltiplos Sites**: Expandir o scraper para coletar vagas de outros sites de emprego, como **Glassdoor**, **Indeed**, entre outros.
3. **Interface de Visualização**: Criar um painel para visualizar as vagas coletadas, talvez com **Dash** ou **Streamlit**, e disponibilizar uma interface para monitoramento.
4. **Notificações**: Configurar notificações por e-mail ou **Telegram** para alertar quando novas vagas forem inseridas.
