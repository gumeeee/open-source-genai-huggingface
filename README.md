# Open Source Generative AI com HuggingFace

Repositório de estudos sobre **IA Generativa com modelos open-source** utilizando o ecossistema HuggingFace. O conteúdo é organizado em notebooks Jupyter (compatíveis com Google Colab) e cobre desde conceitos introdutórios até a construção de um produto end-to-end.

## Assuntos Abordados

### 1. Introdução ao Google Colab e Geração de Imagens com Stable Diffusion
**Notebook:** `week-3-day-1.ipynb` / `week-3-day-1-colab.ipynb`

- Configuração do Google Colab com GPU T4
- Autenticação com o HuggingFace Hub
- Geração de imagens a partir de texto (text-to-image) com modelos de difusão
- Parâmetros de inferência: inference steps e guidance scale
- **Modelos:** `stabilityai/sdxl-turbo`, `stabilityai/stable-diffusion-xl-base-1.0`

### 2. Pipelines do HuggingFace — API de Alto Nível para Inferência
**Notebook:** `week-3-day-2-pipelines.ipynb`

- Diferença entre treinamento e inferência
- API `pipeline()` do HuggingFace Transformers
- Tarefas de NLP:
  - Análise de sentimento
  - Reconhecimento de Entidades Nomeadas (NER)
  - Perguntas e Respostas (QA)
  - Sumarização de texto
  - Tradução (inglês → francês, inglês → alemão)
  - Classificação zero-shot
  - Geração de texto
- Tarefas multimodais:
  - Geração de imagens com diffusers
  - Geração de áudio (text-to-speech)
- Uso de datasets do HuggingFace

### 3. API de Baixo Nível — Modelos, Tokenizers e Quantização
**Notebook:** `week_3_day_4_models.ipynb`

- API de baixo nível do HuggingFace Transformers (AutoTokenizer, AutoModelForCausalLM)
- Chat templates e prompts de geração
- Quantização em 4 bits com BitsAndBytesConfig (NF4, double quantization)
- Medição de footprint de memória dos modelos
- Arquitetura interna de Transformers (embedding, decoder layers, self-attention, MLP, LM head)
- Streaming de saída com TextStreamer
- Gerenciamento de memória GPU
- **Modelos comparados:** Llama 3.1/3.2 (Meta), Phi-4 (Microsoft), Gemma 3 (Google), Qwen3 (Alibaba), DeepSeek-R1

### 4. Produto End-to-End — Atas de Reunião a partir de Áudio
**Notebook:** `week-3-day-5-meeting-minutes-product.ipynb`

- Transcrição automática de áudio (ASR) com Whisper
- Comparação entre abordagem open-source (Whisper via HuggingFace) e proprietária (OpenAI API)
- Engenharia de prompts para saída estruturada
- Pipeline completo: Áudio → Transcrição → Análise com LLM → Ata em Markdown
- Quantização 4-bit para rodar Llama localmente
- **Modelos:** `openai/whisper-medium.en`, `meta-llama/Llama-3.2-3B-Instruct`

## Tecnologias e Bibliotecas

| Biblioteca | Uso |
|---|---|
| `transformers` | Modelos de linguagem, tokenizers, pipelines |
| `diffusers` | Modelos de difusão para geração de imagens |
| `datasets` | Carregamento de datasets do HuggingFace Hub |
| `bitsandbytes` | Quantização de modelos (4-bit) |
| `accelerate` | Otimização de carregamento de modelos |
| `torch` | Backend de deep learning |
| `openai` | API proprietária (comparação) |
| `huggingface_hub` | Autenticação e acesso ao Hub |

## Como Executar

1. Abra os notebooks no [Google Colab](https://colab.research.google.com/) (recomendado com GPU T4)
2. Configure um token do HuggingFace em Settings > Secrets com a chave `HF_TOKEN`
3. Execute as células sequencialmente

## Pré-requisitos

- Conta no [HuggingFace](https://huggingface.co/) com token de acesso
- Acesso aprovado aos modelos gated (ex: Llama)
- Google Colab com runtime GPU (T4 gratuita é suficiente para a maioria dos notebooks)
