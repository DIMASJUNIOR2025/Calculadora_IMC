# 🧮 Calculadora de Perfil

> Aplicação web interativa de análise de saúde pessoal — convertida de um notebook Python/Jupyter para HTML5 puro, sem dependências externas de framework.

---

## 📋 Descrição

A **Calculadora de Perfil** coleta dados pessoais do usuário (nome, idade, peso e altura) e exibe uma análise completa com:

- Verificação de **maioridade** e elegibilidade para voto
- **Classificação de altura** (Baixo / Mediano / Alto)
- Cálculo e **classificação do IMC** em 6 categorias
- **Barra visual animada** do IMC com marcador posicionado dinamicamente

O projeto foi originalmente desenvolvido como notebook Python (com `ipywidgets`) e migrado para uma interface web autossuficiente em HTML5 + CSS3 + JavaScript vanilla.

---

## 🗂️ Estrutura de Arquivos

```
📦 calculadora-perfil/
├── calculadora_perfil.html   # Aplicação completa (único arquivo)
└── README.md                 # Esta documentação
```

> Todo o CSS e JavaScript estão embutidos no arquivo HTML — não há arquivos separados nem dependências locais.

---

## 🚀 Como Usar

### Opção 1 — Abrir diretamente no navegador

1. Extraia o arquivo `.zip` (se necessário)
2. Dê duplo clique em `calculadora_perfil.html`
3. O arquivo abrirá no seu navegador padrão

> ✅ Compatível com Chrome, Firefox, Edge e Safari (versões modernas).

### Opção 2 — Servidor local (opcional)

Se preferir rodar via servidor:

```bash
# Python 3
python -m http.server 8080

# Node.js (com npx)
npx serve .
```

Depois acesse `http://localhost:8080/calculadora_perfil.html`.

---

## 🧩 Funcionalidades

| Funcionalidade | Descrição |
|---|---|
| Campo de nome | Texto livre; usado na saudação personalizada |
| Slider de idade | Controle deslizante de 0 a 120 anos com valor em tempo real |
| Campo de peso | Entrada numérica em kg (ex: `70.5`) |
| Campo de altura | Entrada numérica em metros (ex: `1.75`) |
| Botão Calcular | Processa os dados e exibe os resultados com scroll automático |
| Cards de resultado | 4 cards coloridos: Idade, Peso, Altura e IMC |
| Barra do IMC | Marcador animado posicionado na escala de 6 categorias |

---

## 📊 Lógica de Classificação

### Maioridade

| Condição | Resultado |
|---|---|
| Idade ≥ 18 | Maior de idade · Pode votar |
| Idade < 18 | Menor de idade · Não pode votar |

### Altura

| Faixa | Classificação |
|---|---|
| ≤ 1,65 m | Baixo(a) |
| 1,66 m – 1,79 m | Mediano(a) |
| ≥ 1,80 m | Alto(a) |

### IMC — Índice de Massa Corporal

> Fórmula: `IMC = peso (kg) ÷ altura² (m)`

| IMC | Classificação | Cor indicadora |
|---|---|---|
| < 18,5 | Abaixo do peso | 🔵 Azul |
| 18,5 – 24,9 | Peso normal | 🟢 Verde |
| 25,0 – 29,9 | Sobrepeso | 🟡 Amarelo |
| 30,0 – 34,9 | Obesidade Grau I | 🔴 Vermelho claro |
| 35,0 – 39,9 | Obesidade Grau II | 🔴 Vermelho |
| ≥ 40,0 | Obesidade Grau III (Mórbida) | 🔴 Vermelho escuro |

---

## 🎨 Design & Tecnologias

| Camada | Tecnologia |
|---|---|
| Linguagem | HTML5 + CSS3 + JavaScript (ES6+) |
| Fontes | [DM Serif Display](https://fonts.google.com/specimen/DM+Serif+Display) + [DM Sans](https://fonts.google.com/specimen/DM+Sans) via Google Fonts |
| Tema | Dark mode com variáveis CSS (`--bg`, `--accent`, `--ok`, `--warn`, `--danger`) |
| Layout | Flexbox + CSS Grid responsivo |
| Animações | CSS keyframes (`fadeDown`, `fadeUp`) + transição cubic-bezier no marcador IMC |
| Framework | Nenhum — JavaScript vanilla puro |

### Paleta de Cores

```
--bg       #0d0f14   Fundo principal
--surface  #161922   Superfícies de input
--card     #1c2030   Cards e painéis
--accent   #4f8ef7   Azul destaque
--ok       #34d399   Verde (positivo)
--warn     #fbbf24   Amarelo (atenção)
--danger   #f87171   Vermelho (risco)
```

---

## 📱 Responsividade

A interface adapta-se automaticamente a telas menores que `420px`:

- Os cards de resultado passam de **2 colunas** para **1 coluna**
- O padding interno dos cards é reduzido
- O slider e inputs mantêm usabilidade em toque

---

## 🔗 Origem do Projeto

Este projeto foi convertido de um notebook **Python / Jupyter** que utilizava:

- `input()` e `print()` para interação via terminal
- `ipywidgets` para interface gráfica no Jupyter (sliders, botões, output)
- `IPython.display.HTML` para estilização CSS inline

A migração para HTML5 eliminou todas essas dependências, tornando a aplicação **portátil e executável em qualquer navegador** sem instalação de Python ou Jupyter.

---

## 📄 Licença

Projeto de uso livre para fins educacionais e pessoais.
