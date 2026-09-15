# david-ai-lab
diverse notebooks that search to implement or experiment methods in ai.

All 13 notebooks were cleaned 2026-09-15: import fixes, empty/duplicate cell removal,
portable CUDA/Colab guards, header docs inside each notebook. Original code style
(terse comments, short names like `xd`, `moderu`, `monkee`) preserved — every altered
line is marked `# fix:` / `# TODO`.

## quickstart
```powershell
pip install -r requirements.txt
# open any notebook, Run All top-to-bottom
# reduce epochs/train_steps for a smoke test; place Kaggle csvs next to notebook if offline
```

## sections
- supervised-learning/computer-vision/
  - `hrmmodel.ipynb` (was `hrmmodel (1).ipynb`) — HRM/Mamba hybrid on LAION patches
  - `mambabedding.ipynb` (was `mambabedding (1).ipynb`) — MambaVideo + TinyViT LoRA, UCF101
  - `object_detection_swin.ipynb` (was `Object_detection_swint.ipynb`) — Swin detector, synthetic circles
  - `tempseq_with_numbers.ipynb` (was `Tempseqwithnumbers (1).ipynb`) — digit ResBlock CNN, synthetic
  - `mobilevit_lora_action.ipynb` (was `untitled91 (2).ipynb`) — MobileViT + LoRA action classifier
- supervised-learning/nlp/
  - `semantic_similarity.ipynb` — anime/movie overview matching (GloVe + attention)
  - `roleplay.ipynb` — Qwen2.5-0.5B LoRA roleplay SFT (most portable)
  - `qwen_agent_sft_experiments.ipynb` (was `notebook74ee1fd78b.ipynb`) — Qwen/SmolLM DPO/XLoRA/fusion log
  - `movie_semantic_search.ipynb` (was `notebook17a20c79f0.ipynb`) — transformer cosine search
- unsupervised-learning/
  - `ddpgresnet.ipynb`, `resnetppo.ipynb`, `sacresnet.ipynb` — ResNet visual actor-critic, monkee game
- documents/doc-code/
  - `proyecto_grafos.ipynb` (was `Proyecto_Grafos_0.ipynb`) — Qwen embeddings + ForceAtlas2 graph
- supervised-learning/regression/ — empty (placeholder)

## what was fixed per notebook
- header markdown: purpose, requirements, how-to-run, style note
- section dividers: Setup / Data / Model / Training (original code untouched below each)
- `import matplo` → `matplotlib.pyplot`; `skimage` → explicit `skimage.io/transform`
- `torch.set_default_tensor_type(cuda)` → `set_default_dtype(float32)` portable
- `google.colab` drive/files → try/except local fallback
- commented gibberish/incomplete cells (`dpatcheso.shapd`, `testlayer=`, `ia3conf=`, `¿`, empty `def search`, empty `with`)
- removed empty + exact-duplicate cells (e.g. duplicate `SwinModel`); converted stray raw cell
- filenames sanitized (no spaces/parens); see list above
