# cudacore_site

The static research site for [cudacore](https://github.com/Krishpraj?tab=repositories&q=cudacore) — a from-scratch LLM inference engine written in C++/CUDA, broken into seven components, each in its own repo.

This site explains what an LLM inference engine is, in plain English, and links out to each component's source code. It's aimed at people who can code but have never opened a transformer before.

## Live site

Once GitHub Pages is enabled on this repo, the site is at:

**https://krishpraj.github.io/cudacore_site/**

## Local preview

It's plain HTML + CSS, no build step:

```bash
# from this folder
python -m http.server 8000
# then open http://localhost:8000
```

## Structure

```
cudacore_site/
├── index.html              landing page — what an inference engine is, the loop, links to components
├── style.css               shared styles
└── components/
    ├── tokenizer.html      stage 1 — text ↔ token IDs
    ├── kernels.html        stage 2 — CPU math primitives
    ├── model.html          stage 2 — Llama-style forward pass
    ├── kv_cache.html       stage 3 — past K/V storage
    ├── cuda.html           stage 4 — GPU kernels
    ├── sampler.html        stage 2→5 — greedy / temperature / top-k / top-p
    └── server.html         stage 5→7 — streaming, HTTP, continuous batching
```

## Component repos

| # | Component | Repo |
|---|-----------|------|
| 1 | Tokenizer | [cudacore_tokenizer](https://github.com/Krishpraj/cudacore_tokenizer) |
| 2 | Kernels (CPU) | [cudacore_kernels](https://github.com/Krishpraj/cudacore_kernels) |
| 3 | Model | [cudacore_model](https://github.com/Krishpraj/cudacore_model) |
| 4 | KV cache | [cudacore_kv_cache](https://github.com/Krishpraj/cudacore_kv_cache) |
| 5 | CUDA kernels | [cudacore_cuda](https://github.com/Krishpraj/cudacore_cuda) |
| 6 | Sampler | [cudacore_sampler](https://github.com/Krishpraj/cudacore_sampler) |
| 7 | Server | [cudacore_server](https://github.com/Krishpraj/cudacore_server) |
