# Playing Telephone with AI — Replication Pack

This repo contains the inputs, prompts, and raw outputs used to study how uninformed use of ready-made AI tools can produce wrong educational materials. We simulate a common workflow and show where modality handling and stochastic outputs matter, plus a simple mitigation: transcribe images to text before retrieval.

---

## Study in one paragraph

We used a widely adopted knowledge-extraction tool (Google NotebookLM, Pro) on a reasoning task: **count September trips** in a short **multi-city travel itinerary**. The same source was delivered in four forms: **(1) all text**, **(2) text + postcard image**, **(3) text + transcribed image**, **(4) text + table**. In our setting, NotebookLM retrieved as **text-only**, so **image-only facts were ignored**; **repeated runs** on identical text yielded **different totals**; **tables** were stable but **undercounted** when rules were implicit. **Transcribing the image to text** before ingestion fixed the misses and stabilized answers. For local transcription, **Qwen 3 VL** models were tested; **30B _Thinking_** was closest to Gemini Pro but still stochastic, and **Thinking** variants beat **Instruct** for image→text.

---

## Repository structure

