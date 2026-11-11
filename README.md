<div align="center">

# RAMSONS INFINITE

**Uma experiência digital em WebGL, desenvolvida pelo CIOB Studio**

Cena 3D em tempo real · Site 100% estático · Sem dependências · Sem build

</div>

---

## 🎬 Sobre

**RAMSONS INFINITE** é uma experiência digital imersiva criada pelo **CIOB Studio**: uma cena WebGL executada integralmente no navegador, que apresenta a marca **RAMSONS** em um ambiente tridimensional infinito e em constante transformação.

Sem menus, cliques ou controles — a experiência evolui sozinha, alternando estados visuais em um ciclo contínuo, sobre uma identidade cromática corporativa em tons de vermelho profundo e preto.

O projeto é distribuído como um site **100% estático**: toda a estrutura, os estilos e a lógica vivem em um único arquivo `index.html`, sem etapa de compilação e sem dependências para instalar.

## 🔄 Estados da experiência

| Estado | Descrição |
| --- | --- |
| **CORE** | O logotipo RAMSONS flutua no centro da cena, acompanhado pelo campo de partículas |
| **LIQUID** | A câmera se eleva e revela um piso metálico ondulante, animado por ondas em tempo real |
| **PARTICLES** | Ponto de vista alto sobre o sistema de ~8.000 partículas luminosas |
| **GEOMETRIC** | Logotipo, esculturas abstratas e partículas dividem a cena |

Cada estado permanece entre **12 e 20 segundos**; o próximo é escolhido aleatoriamente, e a câmera desliza suavemente até o novo enquadramento.

## ✨ Destaques técnicos

- Renderização 3D em tempo real via **WebGL**, acelerada por GPU
- Pós-processamento cinematográfico com **Unreal Bloom** (`EffectComposer` + `UnrealBloomPass`)
- **Tone mapping Reinhard** com exposição elevada para realce dos brilhos
- Piso metálico com deformação de vértices animada por ondas senoidais
- Sistema de **~8.000 partículas** com cores por vértice e *additive blending*
- **20 esculturas icosaédricas** metálicas em rotação contínua
- **Luz pontual vermelha em órbita contínua** e neblina exponencial para profundidade atmosférica
- Ciclo automático de estados de câmera, sem interação obrigatória
- Layout responsivo de tela cheia, com redimensionamento dinâmico

## 🧪 Tecnologias

| Tecnologia | Papel no projeto |
| --- | --- |
| [Three.js](https://threejs.org) `0.160.0` | Motor 3D (WebGL), carregado via CDN com *import maps* |
| WebGL | Renderização no navegador |
| `EffectComposer` + `UnrealBloomPass` | Pós-processamento (brilho cinematográfico) |
| JavaScript (ES Modules) | Toda a lógica da experiência |
| Canvas 2D | Geração procedural da textura do logotipo |
| HTML5 + CSS3 | Estrutura e layout de tela cheia |

> **Sem frameworks, sem bundlers, sem npm** — as bibliotecas são carregadas de CDN (unpkg) por meio de *import maps* nativos do navegador.

## 📁 Estrutura

```
ramsons-infinite-ciob/
├── index.html          # Experiência completa (estrutura + estilos + lógica)
├── README.md           # Documentação
├── .gitignore          # Exclusões do Git
└── package-lock.json   # Lockfile residual do npm (sem dependências; nada precisa ser instalado)
```

## 🚀 Executando localmente

Basta abrir o arquivo `index.html` em um navegador moderno com suporte a WebGL (Chrome, Edge, Firefox ou Safari atualizados).

Opcionalmente, sirva o diretório com um servidor estático:

```bash
python -m http.server 8000
# acesse http://localhost:8000
```

## ☁️ Implantação na Cloudflare Pages

1. Acesse **Workers & Pages → Create → Pages → Connect to Git** e selecione este repositório.
2. Configure a compilação:
   - **Framework preset:** `None`
   - **Build command:** *(vazio — não há etapa de compilação)*
   - **Build output directory:** `/` (raiz do repositório)
3. Clique em **Save and Deploy** — a experiência ficará disponível em um subdomínio `*.pages.dev`.

## 🏛️ Créditos

**RAMSONS INFINITE** — experiência digital desenvolvida pelo **CIOB Studio**.

© CIOB Studio · RAMSONS INFINITE
