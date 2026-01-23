# 🚀 Portfólio de Automação e RPA

Este repositório reúne a documentação técnica e estudos de caso de soluções de **Automação de Processos (RPA)** e **Inteligência Artificial** que desenvolvi para otimizar fluxos de trabalho no setor público.

> **⚠️ Nota de Confidencialidade:**
> Devido à natureza governamental e regras de propriedade intelectual, os códigos-fonte destes projetos são privados. Este portfólio apresenta a **arquitetura**, **desafios técnicos**, **tecnologias empregadas** e os **resultados quantitativos** de cada solução.

---

## 📂 Projetos em Destaque

### 1. [Central de Viagens - Automação de Análises](docs/central-viagens.md)
**O Desafio:** Analisar, manualmente e diariamente, dezenas de solicitações de viagem, cruzando dados de sistemas Web, Desktop (Meta4) e planilhas.
* **Solução:** Robô autônomo que valida regras de negócio, férias e licenças, aprovando ou reprovando pedidos automaticamente.
  ![Interface](assets/Central%20de%20Viagens.png)
* **Impacto:** Mais de 3.400 solicitações processadas em 3,5 meses com **96,6% de aprovação automática** (sem intervenção humana).
* **Techs:** `Python` `Selenium` `Streamlit` `PyWinAuto` `Pandas`

### 2. [Monitor Inteligente do Diário Oficial (DIOE)](docs/dioe.md)
**O Desafio:** Identificar atos administrativos (Decretos, Portarias) relevântes para o setor em um diário oficial extenso.
* **Solução:** Pipeline de ETL que realiza resolução de desafios visuais via visão computacional e utiliza **IA Generativa (Google Gemini)** para ler e extrair dados dos atos, enviando relatórios por e-mail.
* **Techs:** `Google Gemini API` `OpenCV` `EasyOCR` `Selenium Wire`

### 3. [Lurdes - Análise Cognitiva de Protocolos](docs/lurdes.md)
**O Desafio:** Conferência manual de documentos digitalizados (RG, Diplomas, CNH) para processos de RH.
* **Solução:** Aplicação Desktop que baixa processos em lote, usa IA para extrair dados não estruturados de PDFs e sincroniza tudo com Google Drive.
* **Techs:** `Tkinter` `Google Drive API` `Gemini 2.5 Flash` `OAuth2`

### 4. [Painel de Monitoramento de Protocolos](docs/painel-protocolos.md)
**O Desafio:** Falta de visibilidade em tempo real sobre a carga de trabalho e pendências da equipe.
* **Solução:** Dashboard rotativo para TV corporativa que extrai dados do sistema e-Protocolo em background e exibe métricas de produtividade e alertas visuais.
* **Techs:** `PyQt6` `Web Scraping` `Dashboard` `Multithreading`

---

## 🛠️ Stack Tecnológico Geral

![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![Selenium](https://img.shields.io/badge/-selenium-%43B02A?style=for-the-badge&logo=selenium&logoColor=white)
![Google Gemini](https://img.shields.io/badge/Google%20Gemini-8E75B2?style=for-the-badge&logo=google%20bard&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=for-the-badge&logo=Streamlit&logoColor=white)
![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white)
![PyQt](https://img.shields.io/badge/Qt-%23217346.svg?style=for-the-badge&logo=Qt&logoColor=white)
