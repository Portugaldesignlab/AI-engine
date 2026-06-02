# Buscador de Motores de IA (versão PT, estática)

Versão em **português**, num único ficheiro, sem build. Tudo (interface, catálogo de motores, chat e lógica de recomendação) está em `public/index.html` e corre 100% no navegador — sem servidor, sem chave de API, sem login.

Inclui dois catálogos:

1. **Motores generalistas** — Claude, GPT, Gemini, Grok e modelos open-source (DeepSeek, Kimi, Qwen, Llama, Gemma, Mistral).
2. **Motores de nicho no GitHub (por setor)** — projetos open-source reais para tarefas especializadas, cada um com link de repositório e uma sugestão de pesquisa no GitHub:
   - **Agricultura** — PlantVillage / deteção de doenças em plantas
   - **Geoespacial / Satélite** — TorchGeo (Microsoft)
   - **Transporte / Condução autónoma** — openpilot (comma.ai) + CARLA
   - **Construção / Engenharia civil** — Awesome-Crack-Detection + CODEBRIM
   - **Saúde / Imagiologia médica** — MONAI + nnU-Net
   - **Clima / Meteorologia** — GraphCast (Google DeepMind)

O chat entende português: escreva "detetar doenças nas plantas", "fissuras em betão", "previsão do tempo", etc., e ele recomenda o projeto de setor certo + um modelo generalista para complementar.

## Ficheiros

```
public/
  index.html      ← a aplicação completa (PT)
vercel.json        ← serve a pasta public/ como site estático
README.md
```

## Publicar no Vercel a partir do GitHub

1. Crie um repositório no GitHub e carregue estes ficheiros (mantenha a pasta `public/` e o `vercel.json` na raiz).
2. Vá a **vercel.com → Add New → Project** e importe o repositório.
3. Framework Preset: **Other** (sem passo de build). Deixe o Build Command vazio.
4. Clique em **Deploy**. O site fica em `o-seu-projeto.vercel.app`.

## Testar localmente

Abra `public/index.html` no navegador, ou:

```bash
cd public && python3 -m http.server 8000   # depois visite http://localhost:8000
```

## Editar os motores e setores

Em `public/index.html`, dentro do `<script>`, edite os arrays `ENGINES` (modelos gerais) e `SECTORS` (projetos de nicho). Cada projeto de setor tem `repo` (link GitHub), `search` (sugestão de pesquisa) e `keywords` (palavras que ativam a recomendação no chat).

Dados refletem o estado da arte em junho de 2026 — confirme preços e limites no site de cada fornecedor.
