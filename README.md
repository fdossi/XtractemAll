# 📦 XtractemAll: XtractemAll: Extrator Recursivo de Dados em Nuvem

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/fdossi/XtractemAll/blob/main/XtractemAll.ipynb)

**XtractemAll** é um notebook Jupyter otimizado para rodar no Google Colab, projetado para extrair recursivamente grandes volumes de arquivos compactados (especialmente **Google Takeout**) diretamente no seu Google Drive.

## 🚀 Funcionalidades

* **Extração Recursiva:** Se um arquivo zip contém outro zip (ou rar, tar, etc.) dentro, o script extrai tudo até sobrar apenas os arquivos finais.
* **Suporte Multi-Formato:** Suporta nativamente `.zip`, `.rar`, `.7z`, `.tar`, `.tar.gz`, `.tgz` e `.gz`.
* **Instalação Automática:** Instala dependências de sistema (`p7zip-full`, `unrar`) automaticamente no ambiente Colab.
* **Limpeza Inteligente:** Usa uma pasta temporária de trabalho para evitar fragmentação no Drive durante o processo e move apenas os arquivos finais extraídos.
* **Processamento em Lote:** Ideal para arquivos divididos em partes (ex: `takeout-001.tgz`, `takeout-002.tgz`).

## 🛠️ Como Usar

1.  Clique no botão **"Open in Colab"** acima (após publicar no GitHub).
2.  Execute a **Célula 1** para preparar o ambiente e montar o Google Drive.
3.  Na **Célula 2**, configure os caminhos e nomes dos arquivos:
    * `BASE_DRIVE_PATH`: Pasta onde estão seus arquivos compactados.
    * `OUTPUT_ROOT_DIR`: Onde os arquivos extraídos serão salvos.
    * `PREFIXO_ARQUIVO`: O início do nome do arquivo (ex: `takeout-`).
    * `START_NUM` e `END_NUM`: O intervalo das partes a processar.
4.  Execute as células restantes para iniciar a extração.

## ⚙️ Requisitos

Este script foi desenhado para o **Google Colab**.
* Conta Google (para acesso ao Drive).
* Espaço suficiente no Google Drive para os arquivos extraídos.

**Bibliotecas Python utilizadas:**
* `os`, `shutil`, `pathlib` (Gerenciamento de arquivos)
* `tarfile`, `gzip`, `zipfile` (Extração nativa)
* `subprocess` (Chamada de ferramentas do sistema)

**Ferramentas de Sistema (instaladas via script):**
* `p7zip-full`
* `unrar`

## ⚠️ Aviso Importante

Este script manipula arquivos diretamente no seu Google Drive. Embora ele seja projetado para deletar apenas arquivos temporários na pasta de trabalho (`/content/work`), **sempre tenha um backup** dos seus dados originais antes de realizar operações em massa.

## 📄 Licença

Este projeto está licenciado sob a licença MIT - veja o arquivo [LICENSE](LICENSE) para mais detalhes.
