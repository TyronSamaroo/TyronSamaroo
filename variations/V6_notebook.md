<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=soft&color=0:0e1116,50:1a1f29,100:0e1116&height=180&section=header&text=Tyron%20Samaroo&fontColor=e6edf3&fontSize=54&fontAlignY=45&desc=ML%20%C3%97%20systems%20%C2%B7%20compilers%20%C2%B7%20NYC&descAlignY=68&descSize=16&fontFamily=Fira%20Sans" alt="header" />
</p>

<p align="center">
  <a href="https://tyronsamaroo.dev">tyronsamaroo.dev</a>
  &nbsp;·&nbsp;
  <a href="mailto:tyronsamaroo@gmail.com">tyronsamaroo@gmail.com</a>
  &nbsp;·&nbsp;
  <a href="https://www.linkedin.com/in/tyronsamaroo">linkedin.com/in/tyronsamaroo</a>
</p>

---

I'm a software engineer who builds things at the seam where ML meets systems — neural nets that read sign language from a webcam, compilers written from scratch, scrapers with zero dependencies. I care most about the decisions *inside* a project: what did you choose, what did you choose against, and why.

This page is a field notebook — open questions I'm chewing on, experiments I've run, and what's on my desk right now.

---

## Current threads

> **Can a compressed vision model reliably translate ASL letters on-device at 24 fps without a GPU?** &nbsp; The accuracy ceiling of `ASL-Alpha` was about 87% — and the last 13% was almost entirely handshape ambiguity (B vs D, M vs N), not model capacity. I'm increasingly convinced *data* beats *architecture* for this class of problem.

> **What's the minimum-viable compiler that still teaches you the whole pipeline?** &nbsp; `TinyJ` was my attempt at the answer — lexer → parser → AST → codegen, end-to-end, nothing skipped. The parser is the boring part. Codegen is where you actually learn how computers work.

> **Where does "zero dependencies" stop being discipline and start being performance art?** &nbsp; `EtsyScraper` used only the Java JDK — no HTTP client library, no HTML parser. Doing it taught me what libraries actually *hide* from you. Doing it *twice* would be silly.

> **How do LLMs change the shape of search?** &nbsp; Ranking vs. dialogue. Interpretability vs. fluency. I've been returning to this one a lot — partly because it feels less settled than the hype suggests.

---

## Experiments

**[ASL-Alpha-NeuralNet](https://github.com/TyronSamaroo/ASL-Alpha-NeuralNet)** &nbsp;·&nbsp; `Python · TensorFlow · CV`
CNN trained on webcam frames for ASL letter recognition. Plateaued at ~87% accuracy, bottlenecked by handshape ambiguity in the training data, not model size. Finding: *data curation was more impactful than any architecture change I tried.*

**[Compiler-TinyJ](https://github.com/TyronSamaroo/Compiler-TinyJ)** &nbsp;·&nbsp; `Java · Compilers`
A Java-subset compiler — complete pipeline from source text to executable output, built from scratch. Finding: *writing codegen by hand changes how you read every language spec afterward.*

**[EtsyScraper](https://github.com/TyronSamaroo/EtsyScraper)** &nbsp;·&nbsp; `Java · HTTP · Parsing`
Production-grade scraper using only the Java standard library. Raw sockets for HTTP, hand-rolled HTML traversal, manual session handling. Finding: *constraint-driven projects are the fastest way to understand a stack.*

**[Palate](https://github.com/TyronSamaroo/Palate)** &nbsp;·&nbsp; `React · Node · JS`
Full-stack food discovery app. The interesting part wasn't the CRUD — it was modeling *taste* as latent preference instead of explicit tag matching.

**[SearchEngine](https://github.com/TyronSamaroo/SearchEngine)** &nbsp;·&nbsp; `JavaScript · IR`
Tiny inverted-index search with a hand-written query parser. Finding: *classical ranking still beats "just cosine similarity" when you need to explain why a result showed up.*

**[Stock_App_Flask](https://github.com/TyronSamaroo/Stock_App_Flask)** &nbsp;·&nbsp; `Python · Flask · APIs`
Market data tracker. Ended up being a study in caching — 90% of the work lived in the caching layer, not the app itself.

---

## On my desk

- *Designing Data-Intensive Applications* — Kleppmann. Re-reading for the distributed-systems thread.
- *Compilers: Principles, Techniques, and Tools* — the Dragon Book. Returning to it after TinyJ with fresh eyes.
- *The Unix Programming Environment* — Kernighan & Pike. Still the best primer on tool-building ever written.
- Papers on LLM serving, quantization, and agent coordination — loosely collected, not systematic yet.

---

## Working on now

Sharpening distributed systems fundamentals. Exploring LLM infrastructure — serving, quantization, routing. Open to conversations, collaborations, and roles, especially at the **ML × systems** crossover. The fastest way in is <a href="mailto:tyronsamaroo@gmail.com">email</a>.

<p>&nbsp;</p>
<p align="center"><sub>— Tyron</sub></p>

<p><img src="https://capsule-render.vercel.app/api?type=soft&color=0:0e1116,50:1a1f29,100:0e1116&height=60&section=footer" alt="footer"/></p>
