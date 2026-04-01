# 🚀 Portfólio de Automação e RPA

Este repositório reúne a documentação técnica e estudos de caso de soluções de **Automação de Processos (RPA)** e **Inteligência Artificial** que desenvolvi para otimizar fluxos de trabalho no setor público.

> **⚠️ Nota de Confidencialidade:**
> Devido à natureza governamental e regras de propriedade intelectual, os códigos-fonte destes projetos são privados. Este portfólio apresenta a **arquitetura**, **desafios técnicos**, **tecnologias empregadas** e os **resultados quantitativos** de cada solução.

---

# 📂 Projetos em Destaque

## Central de Viagens - Automação de Análise de Solicitações

### 1. Visão Geral
Robô de automação (RPA) desenvolvido em Python para análise e validação autônoma de solicitações de viagem. O sistema realiza a verificação de conflitos (férias, licenças e restrições) integrando-se a plataformas web e sistemas legados de RH.

### 2. Tecnologias Utilizadas
| Categoria | Tecnologia |
| :--- | :--- |
| **Interface Web** | Streamlit |
| **Automação Web** | Selenium (undetected-chromedriver) |
| **Automação Desktop** | PyWinAuto e PyAutoGUI |
| **Processamento de Dados** | Pandas e OpenPyXL |
| **Manipulação de PDF** | PyPDF2 |


![Interface](assets/Central%20de%20Viagens.png)
(RPA em funcionamento)

### 3. Arquitetura e Módulos
O projeto adota uma estrutura modular para facilitar a manutenção:
* **`run.py`**: Launcher da aplicação Streamlit.
* **`main.py`**: Orquestrador do loop de automação e lógica de persistência.
* **`funcoes_central_de_viagens.py`**: Gerencia a interação web com o portal de viagens.
* **`funcoes_meta4.py`**: Módulo responsável pela automação do sistema desktop de RH.
* **`analise_viagem.py`**: Engine de lógica de negócio e identificação de conflitos de datas.
* **`gerador_de_base.py`**: Utilitário para conversão de bases Excel para CSV otimizado.

### 4. Resultados e Impacto
* **Volume de Processamento**: 3.457 análises executadas em 3,5 meses.
* **Eficiência**: Média de 32,6 análises diárias, com picos de 107 atendimentos em um único dia.
* **Autonomia**: 96,6% das solicitações são resolvidas sem intervenção humana.
* **Otimização de Tempo**: Redução do tempo de análise de 15 minutos para poucos segundos por processo.



## DIOE - Automação de Análise do Diário Oficial do Estado

### 1. Visão Geral
Solução de RPA projetada para monitorar, baixar e filtrar atos administrativos do Diário Oficial do Estado do Paraná. O sistema utiliza Inteligência Artificial para interpretar textos jurídicos e extrair dados estruturados de interesse da Divisão de Recursos Humanos.

### 2. Funcionalidades Chave
* **Web Scraping & OCR**: Download automático com quebra de CAPTCHA baseada em visão computacional.
* **Filtragem Inteligente**: Localização de páginas via Regex e palavras-chave específicas (IAT, SEAP/QPPE).
* **Análise com IA**: Integração com Google Gemini 2.5 Flash para extração semântica de nomeações e exonerações.
* **Relatórios Automáticos**: Geração de arquivos CSV/PDF e envio via e-mail corporativo.

### 3. Módulos Técnicos
* **`baixar_diario.py`**: Scraper headless com monitoramento de diretório.
* **`leitor_captcha.py`**: Pipeline de processamento de imagem com OpenCV e EasyOCR.
* **`analisador_de_atos.py`**: Engine de Prompt Engineering para integração com a API do Gemini.
* **`conversor.py`**: Manipulação e sanitização de PDFs via PyMuPDF (fitz).
* **`expresso_dioe.py`**: Automação da interface web de correio eletrônico.

### 4. Fluxo Operacional
O robô verifica a existência de novos diários, resolve desafios de segurança, processa o texto bruto, utiliza IA para filtrar apenas atos relevantes e distribui os resultados para os destinatários configurados.



## RPA Lurdes - Extração e Análise Cognitiva de Protocolos

### 1. Visão Geral
Aplicação desktop voltada para a automação da extração e conferência de dados de servidores públicos. O sistema automatiza o download de processos do sistema e-Protocolo e utiliza IA para ler documentos não estruturados, como RGs, CNHs e Diplomas.

### 2. Arquitetura do Sistema
* **Interface (GUI)**: Desenvolvida em Tkinter para gerenciamento de lotes de protocolos.
* **Análise Cognitiva**: Uso da API Google Gemini para transformação de documentos PDF em JSON estruturado.
* **Sincronização**: Módulo `drive_sync.py` para manutenção de dados em nuvem via Google Drive API (OAuth2).
* **Resiliência**: Lógica de "Retry" para falhas de API e tratamento de PDFs corrompidos.

### 3. Destaques Técnicos
* **Identificação Inteligente**: Extração de CPF, dados bancários e formação acadêmica de imagens e PDFs digitalizados.
* **Segurança**: Gerenciamento de tokens de autenticação e credenciais de rede.
* **Performance**: Processamento em threads separadas para garantir a fluidez da interface durante a execução.



## Painel de Protocolos - Monitor e Dashboard de e-Protocolo

### 1. Visão Geral
Dashboard rotativo projetado para monitoramento em tempo real de fluxos de trabalho governamentais. O sistema consolida dados de diversos setores e os exibe em uma interface moderna, facilitando a gestão de carga de trabalho.

### 2. Arquitetura de Concorrência (Multithreading)
O sistema opera com três fluxos simultâneos:
1.  **Thread Principal (PyQt6)**: Interface gráfica e renderização do dashboard.
2.  **Worker de Extração**: Ciclo de automação web via Selenium em segundo plano.
3.  **Thread de Inteligência**: Motor analítico assíncrono para cálculo de métricas e processamento de histórico.

### 3. Inteligência e Persistência
* **Motor de Decisão**: Utiliza `TfidfVectorizer` e **Similaridade de Cosseno** para sugerir responsáveis por protocolos com base no histórico.
* **Algoritmo Hill Climbing**: Ajuste dinâmico de thresholds para otimização da distribuição de tarefas.
* **Banco de Dados**: Migração de CSV para **SQLite** com suporte a acesso concorrente (thread-safe).
* **Segurança**: Criptografia simétrica (AES) para proteção de credenciais sensíveis armazenadas localmente.

### 4. Funcionalidades de Gestão
* Visualização rotativa (carrossel) para TVs corporativas.
* Cálculo de Score de Reputação baseado em prazos e volume.
* Logs em tempo real para auditoria de processos.
---



## 🛠️ Stack Tecnológico Geral

![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![Selenium](https://img.shields.io/badge/-selenium-%43B02A?style=for-the-badge&logo=selenium&logoColor=white)
![SQLite](https://img.shields.io/badge/sqlite-%23003B57.svg?style=for-the-badge&logo=sqlite&logoColor=white)
![Google Gemini](https://img.shields.io/badge/Google%20Gemini-8E75B2?style=for-the-badge&logo=google%20bard&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=for-the-badge&logo=Streamlit&logoColor=white)
![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white)
![PyQt](https://img.shields.io/badge/Qt-%23217346.svg?style=for-the-badge&logo=Qt&logoColor=white)
