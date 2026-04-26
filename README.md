# ⚽ Arsenal vs Manchester City — Dashboard Interativo
### Premier League 2025/26 · Análise Completa

---

## 📌 Sobre o Projeto

Dashboard interativo de análise de desempenho comparando **Arsenal FC** e **Manchester City** na Premier League 2025/26. O projeto foi desenvolvido inteiramente com tecnologias front-end nativas — sem frameworks, sem bibliotecas de UI — e consome dados reais via **SportRadar API**.

O objetivo foi transformar dados esportivos brutos em uma experiência visual rica, navegável e informativa, com identidade visual fiel às cores de cada clube.

---

## 🎯 Funcionalidades

### Navegação em 3 modos independentes

| Modo | Descrição |
|------|-----------|
| ⚡ **Comparação** | Visão lado a lado dos dois clubes — KPIs, forma recente, H2H, tabela da PL |
| 🔴 **Arsenal** | Página exclusiva do Arsenal com elenco, artilharia, jogos e próximas partidas |
| 🔵 **Man City** | Página exclusiva do City com elenco atualizado 25/26, artilharia e calendário |

Cada clique troca completamente o conteúdo da página, rola para o topo e aplica a paleta de cores do clube selecionado.

---

### Página Arsenal 🔴

- **8 jogadores em destaque** com posição, número de camisa, nacionalidade, gols e assistências na PL
- **Ranking de artilheiros** com barra proporcional (Gyökeres lidera com 12 gols)
- **Ranking de assistências** (Saka lidera com 6)
- **Últimos 8 resultados** com placar, adversário e badge V/E/D
- **Próximas 4 partidas** com probabilidade de vitória
- **Gráfico de barras** — gols marcados vs sofridos por rodada

### Página Man City 🔵

- **8 jogadores em destaque** com elenco real da temporada 25/26 (Donnarumma, Cherki, Reijnders, Bernardo Silva capitão — sem De Bruyne, sem Ortega)
- **Ranking de artilheiros** (Haaland lidera com 24 gols)
- **Ranking de assistências** (Foden e Haaland empatados com 7)
- **Últimos 8 resultados** com dados reais
- **Próximas partidas** com datas confirmadas
- **Gráfico de barras** — gols marcados vs sofridos por rodada

### Página Comparação ⚡

- **5 KPIs lado a lado** — Pontos, Vitórias, Empates, Derrotas, Aproveitamento
- **Split panel** com forma recente (últimas 5 rodadas), gols e aproveitamento de cada time
- **Gráfico de barras comparativo** — gols por rodada dos dois times
- **Donuts de distribuição** de resultados (V/E/D)
- **Gráfico de linha** — evolução de pontos por rodada
- **Card H2H** com resultado do confronto direto (City 2×1 Arsenal, 19/04/2026)
- **Tabela Top 5** da Premier League com destaques por cor

---

## 🛠️ Tecnologias Utilizadas

```
HTML5          → Estrutura semântica e acessível (atributos aria-label)
CSS3           → Grid, Flexbox, variáveis CSS, gradientes, animações
JavaScript ES5 → Navegação, event listeners, lógica de troca de páginas
Chart.js 4.4   → Gráficos de barras, linha e donut
SportRadar API → Dados reais de standings, scores e probabilidades
Google Fonts   → Barlow Condensed + DM Sans
```

> **Nota:** todo o JS foi escrito em ES5 puro (sem arrow functions, sem template literals) para garantir compatibilidade máxima com ambientes restritos, incluindo o visual HTML Content do Power BI.

---

## 🎨 Design

O visual foi construído do zero com CSS nativo, sem nenhuma biblioteca de UI.

- **Tema escuro** com fundo `#181820` e superfícies em `#1e1e28`
- **Paleta Arsenal** — vermelho `#EF0107` com gradiente para `#7a0004`
- **Paleta Man City** — azul `#6CABDD` com gradiente para `#1C2C5B`
- **Tipografia display** — Barlow Condensed (títulos e números grandes)
- **Tipografia corpo** — DM Sans (textos e labels)
- **Animação de entrada** — fadeUp em cada troca de página
- **Logos** dos clubes embedadas em base64 diretamente no HTML (arquivo único, sem dependências externas)

---

## 📊 Dados Utilizados

Todos os dados são reais, coletados via API e pesquisa em fontes oficiais:

| Fonte | Dados |
|-------|-------|
| **SportRadar API** | Standings, scores, resultados, probabilidades de vitória |
| **Arsenal.com** | Elenco oficial 25/26, números de camisa |
| **AiScore / FotMob** | Estatísticas individuais de gols e assistências por jogador |
| **Wikipedia** | Histórico da temporada, transferências, saídas |
| **Opta (via Premier League)** | xG, dados avançados |

**Recorte temporal:** Rodada 34 da Premier League 2025/26 (atualizado em 25/04/2026)

---

## 📁 Estrutura do Arquivo

O projeto é um **arquivo HTML único e autocontido** — sem pasta de assets, sem dependências externas para rodar. Basta abrir no navegador.

```
arsenal_vs_city_v4.html
│
├── <style>          → Todo o CSS (variáveis, componentes, animações)
│
├── .sw-bar          → Barra de navegação com 3 botões
│
├── #page-ars        → Página completa do Arsenal
│   ├── Hero (logo, nome, posição, KPIs)
│   ├── Cards de jogadores (8 destaques)
│   ├── Ranking artilheiros e assistências
│   ├── Últimos resultados
│   ├── Próximas partidas
│   └── Gráfico gols por rodada
│
├── #page-mci        → Página completa do Man City
│   └── (mesma estrutura do Arsenal)
│
├── #page-comp       → Página de comparação
│   ├── Hero VS (logos lado a lado)
│   ├── 5 KPIs comparativos
│   ├── Split panel forma recente
│   ├── Gráficos (barras, donut, linha)
│   ├── Card H2H
│   └── Tabela Top 5 PL
│
└── <script>         → JS ES5 (navegação + Chart.js)
```

---



**2. Navegar entre as páginas**
- Clique em **⚡ Comparação** para ver os dois clubes lado a lado
- Clique em **🔴 Arsenal** para a análise completa do Arsenal
- Clique em **🔵 Man City** para a análise completa do City

**3. Atualizar os dados**
- Os dados estáticos (gols, assistências, resultados) podem ser editados diretamente no HTML, nos blocos `scorer-row` e `match-row`
- Para integrar com uma API real em tempo real, basta substituir os valores estáticos por um `fetch()` na inicialização

---

## 👨‍💻 Desenvolvido por

**Guilherme de Lima**

Projeto desenvolvido como parte do portfólio de transição para a área de dados, demonstrando habilidades em:
- Consumo e tratamento de dados de APIs esportivas
- Visualização de dados
- Design de interfaces voltadas a análise (BI-style dashboards)
- Integração de dados reais em produtos front-end

---


*Dados atualizados até a Rodada 34 da Premier League 2025/26 · 25 de Abril de 2026*
