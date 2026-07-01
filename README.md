# 🏢 GT - Ativo Imobilizado (Setor Lapa) - ETL de Inventário

## 📋 Descrição do Projeto
Este repositório contém o notebook de processamento de dados destinado à consolidação do inventário de bens imobilizados. O script realiza a Extração, Transformação e Carregamento (ETL) dos dados, unificando os relatórios de ativos físicos com os respetivos cadastros de dependências e hierarquias regionais (Setor Lapa e Anhanguera), preparando a base para análise avançada e armazenamento.

## ✨ Funcionalidades Principais
* **Extração de Dados:** Importação de múltiplas folhas de cálculo (Excel) contendo o relatório de bens, cadastro de dependências e grupos do setor.
* **Limpeza e Normalização (Data Cleaning):** * Utilização de Expressões Regulares (Regex) para extração de padrões e separação de códigos de unidades (ex: `BR 21-0056`).
  * Normalização de texto: remoção de acentos ortográficos e caracteres especiais das descrições dos ativos.
  * Padronização de chaves de cruzamento.
* **Enriquecimento de Dados (Joins):** Cruzamento da base principal de inventário com as tabelas de localização e hierarquia através de *Left Joins*, garantindo a integridade dos registos.
* **Preparação para Exportação:** Renomeação e tratamento de colunas para garantir compatibilidade com estruturas de bases de dados (ex: formatação para tabelas Delta).
* **Exportação Automatizada:** Geração de um ficheiro `.zip` final para descarregamento direto para a diretoria local (`inventario_2026`).

## 🛠️ Tecnologias Utilizadas
* **Linguagem:** Python
* **Bibliotecas Principais:** `pandas`, `re` (Regex), `os`, `shutil`
* **Ambiente de Execução:** Jupyter Notebook / Databricks

## 🚀 Como Utilizar
1. Certifique-se de que as folhas de cálculo de origem (*inputs*) estão devidamente posicionadas nos caminhos referenciados no script.
2. Execute todas as células do `notebook_CCB.ipynb` sequencialmente.
3. Após o processamento (cruzamento e limpeza de mais de 9.000 registos), o script apresentará um botão interativo no ecrã.
4. Clique no botão para descarregar o ficheiro ZIP consolidado, que será guardado na diretoria configurada para o inventário de 2026.

## 📂 Estrutura das Fontes de Dados
O processo consolida três fontes principais:
1. **Relatório de Bens:** Base bruta com a listagem de ativos (equipamentos, mobiliário, etc.).
2. **Cadastro de Dependências:** Informações de endereço e nomenclatura completa das unidades (Casas de Oração).
3. **Grupos do Setor:** Mapeamento hierárquico das administrações regionais.

---
*Desenvolvido para automatização e otimização da gestão corporativa de ativos imobilizados.*
