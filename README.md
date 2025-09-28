# Biblioteca de Banners e Apresentações — Treelab & GEMMF (UFVJM)

Este repositório publica, via **GitHub Pages**, uma vitrine simples e responsiva para **banners, apresentações e textos (resumos/metodologias)** de eventos científicos e outras atividades dos grupos **GEMMF** e **Treelab**.

---

## 🌐 Site (GitHub Pages)

<a href="https://gemmf-ufvjm.github.io/apresentacoes/" target="_blank">
  🌐 Acesse a GitHub Page do projeto
</a>

<a href="https://gemmf-ufvjm.github.io/apresentacoes/" target="_blank">
  <img width="787" height="898" alt="image" src="https://github.com/user-attachments/assets/258eda7a-ec31-4144-b309-21e8bf90ee96" />
</a>

---

## 📬 Contato — GEMMF

* 📧 E-mail: **[gemmf.def@ufvjm.edu.br](mailto:gemmf.def@ufvjm.edu.br)**
* 📷 Instagram: **@gemmf_ufvjm**
* 🌐 Site: [https://gemmfdef.wixsite.com/gemmf](https://gemmfdef.wixsite.com/gemmf)

---

## 📁 Organização do repositório

```
apresentacoes/
├── index.html                  # Aplicação (UI + lógica de carregamento)
├── assets/                     # ARQUIVOS dos eventos (imagens, pdfs, pptx)
│   └── <evento_ano>/           # Uma pasta POR evento (ex.: mensuflor_2025/)
│       ├── ... .jpg/.png
│       ├── ... .pdf            # banner (opcional)
│       ├── ... .pptx           # slides (opcional)
│       └── ... .pdf            # texto/resumo/metodologia (opcional)
└── json/
    └── banners/
        ├── index.json          # ATUALIZADO AUTOMATICAMENTE (não editar)
        ├── mensuflor_2025.json # JSON do evento (1+ itens)
        └── outro_evento.json
```

> **Não modifique `json/banners/index.json`.** Uma **GitHub Action** atualiza esse arquivo automaticamente, listando todos os `.json` presentes em `json/banners/`.

---

## 🧱 Padrões em `assets/`

* Crie **uma pasta por evento** dentro de `assets/` (ex.: `assets/mensuflor_2025/`).
* Dentro dela, suba:

  * **Imagem** `.jpg`/`.png` do banner (capa),
  * **PDF** do banner (opcional),
  * **PPTX** da apresentação (opcional),
  * **Texto** (PDF de resumo/metodologia, opcional).

**Sugestão de nomenclatura** (consistente e descritiva; *case-sensitive* em GitHub):

```
assets/mensuflor_2025/
├── gradientes_de_altura_do_dossel-Gustavo2025.jpg
├── gradientes_de_altura_do_dossel_banner-Gustavo2025.pdf
├── gradientes_de_altura_do_dossel-Gustavo2025.pptx
└── gradientes_de_altura_do_dossel-Gustavo2025.pdf       # Texto/Resumo
```

> O botão **Dados** pode apontar para **Drive/Zenodo/outro repositório**; o botão **GitHub** pode apontar para este ou outro repositório.

---

## 🧾 JSONs em `json/banners/`

* Crie **um arquivo `.json` por evento** (recomendado) contendo **um array** com 1+ banners **ou** divida em JSONs menores (todos detectados automaticamente pela Action).
* Os caminhos (`img`, `pdf`, `pptx`, `texto`) devem ser **relativos ao repositório** (ex.: `assets/mensuflor_2025/...`).

### Esquema de campos

**Obrigatórios**

* `titulo` *(string)*
* `img` *(string — caminho da imagem de capa em `assets/...`)*

**Altamente recomendados**

* `autores` *(string)*
* `evento` *(string)*
* `data` *(YYYY-MM-DD)*
* `tema` *(array de strings — ex.: `["Amazônia", "LiDAR"]`)*
* `descricao` *(string)*

**Links opcionais**

* `pdf` *(string)* — PDF do banner
* `pptx` *(string)* — apresentação
* `texto` *(string)* — **PDF** de resumo/metodologia
* `repo` **ou** `github` *(string)* — repositório com código
* `dados` *(string)* — link para dados (Drive/Zenodo/etc.)

**Categoria (define as abas)**

* `categoria` *(string, minúsculo)* — uma das:
  `inicio` (padrão), `eventos_internos`, `eventos_externos`, `aulas`, `apresentacoes`, `3p`.

### Exemplo

```json
[
  {
    "titulo": "Gradientes de altura do dossel entre as regiões fitoecológicas da Amazônia",
    "autores": "Gustavo Mourão; Eric Gorgens",
    "evento": "MensuFlor 2025",
    "tema": ["Amazônia", "Altura", "LiDAR"],
    "data": "2025-03-10",
    "descricao": "Estimativa de altura média e máxima do dossel em cada fitofisionomia do IBGE",
    "img": "assets/mensuflor_2025/gradientes_de_altura_do_dossel-Gustavo2025.jpg",
    "pdf": "assets/mensuflor_2025/gradientes_de_altura_do_dossel_banner-Gustavo2025.pdf",
    "pptx": "assets/mensuflor_2025/gradientes_de_altura_do_dossel-Gustavo2025.pptx",
    "texto": "assets/mensuflor_2025/gradientes_de_altura_do_dossel-Gustavo2025.pdf",
    "repo": "https://github.com/SEU_USER/SEU_REPO",
    "dados": "https://drive.google.com/SEU_LINK_DE_DADOS",
    "categoria": "eventos_externos"
  },
  {
    "titulo": "Regionalização da Amazônia a partir de variáveis ambientais",
    "autores": "Gustavo Mourão; Igor Rocha; Eric Gorgens",
    "evento": "MensuFlor 2025",
    "tema": ["Amazônia", "Cluster"],
    "data": "2025-03-10",
    "descricao": "Divisão da Amazônia Brasileira em 11 regiões",
    "img": "assets/mensuflor_2025/regionalizacao_da_amazônia-Gustavo2025.jpg",
    "pdf": "assets/mensuflor_2025/regionalizacao_da_amazônia_banner-Gustavo2025.pdf",
    "pptx": "assets/mensuflor_2025/regionalizacao_da_amazônia-Gustavo2025.pptx",
    "texto": "assets/mensuflor_2025/regionalizacao_da_amazônia-Gustavo2025.pdf",
    "github": "https://github.com/SEU_USER/OUTRO_REPO",
    "categoria": "eventos_externos"
  }
]
```

---

## 🔎 Como a interface organiza o conteúdo

* **Abas por categoria**: `início`, `eventos_internos`, `eventos_externos`, `aulas`, `apresentacoes`, `3p`.
* **Menu sanduíche (lateral)**: lista automaticamente os **eventos** presentes nos JSONs.
* **Filtros**: por **Evento**, **Tema**, **Data (de/até)** + **Ordenação**; há também **busca por texto**.
* **Paginação automática**: exibe **4 linhas por página** (a quantidade por página se ajusta ao número de colunas da grade em cada resolução).

---

## 🧯 Dúvidas / Solução de problemas

* **Não apareceu no site**: verifique caminhos *case-sensitive*, existência dos arquivos e se o JSON está bem-formado. O `index.json` é atualizado pela Action — não edite manualmente.
* **Imagem não carrega**: tente abrir o caminho do `img` diretamente no navegador; corrija se retornar 404.
* **Links Dados/GitHub**: podem apontar para qualquer repositório ou serviço (Drive/Zenodo/etc.).
