# Importador LCDPR — Nilma Contabilidade

App de página única (`index.html`, HTML/CSS/JS puro, sem build) para importar os relatórios do SIEG
(**Detalhamento de Produtos** e **CT-e**), classificar cada lançamento automaticamente e exportar a
planilha pronta para importação no Alterdata (mesmo layout de colunas do LCDPR).

## Como usar

Abra `index.html` diretamente no navegador (duplo clique) — não precisa de servidor nem instalação.
Todos os dados (regras, plano de contas, lançamentos) ficam salvos no `localStorage` do navegador.

1. **Importar & Conferir** — arraste os `.xlsx` do SIEG. O app identifica o tipo de cada arquivo,
   agrupa por documento, descarta notas canceladas/de outro destinatário e classifica cada lançamento.
2. Lançamentos sem regra correspondente ficam marcados **REVISAR** — escolha a categoria certa na
   coluna "Categoria rápida" da tabela.
3. **Fornecedores, NCM & Categorias** — cadastre regras de classificação. Prioridade: NCM do produto →
   palavra-chave no produto → CNPJ do fornecedor.
4. **Baixar planilha .xls** — gera o arquivo no layout de colunas usado para importar no Alterdata.

## Classificação

A ordem de prioridade (para notas de compra) é: **NCM > palavra-chave no produto > fornecedor**.
Para CT-e (fretes), a ordem é: **fornecedor (transportadora) > categoria padrão configurada**.

## Backup

Em Configuração Geral é possível exportar/importar um backup `.json` com todas as regras e cadastros
(sem os lançamentos importados).
