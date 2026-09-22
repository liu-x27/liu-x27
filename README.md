## Xinyu Liu

M.S. Software Engineering Systems at **Northeastern University**, Arlington VA
(Dec 2028). B.Eng. Software Engineering, **Xi'an Jiaotong University**.
Looking for a **Summer 2027 SWE internship** — DC metro or remote. A Fall 2027 co-op
works too.

Most of what I build ends up being about the same thing: **systems that fail without
raising.** A dictionary that silently outranks real words with typos. A decoder that
loops forever instead of erroring. A safety gate that goes on reporting success after
the component it depends on has quietly stopped answering.

Start with **[mini-claude-code](https://github.com/liu-x27/mini-claude-code)** — an agent
framework whose shell approvals are scored by a small model and measured on held-out
commands — or **[lexica](https://github.com/liu-x27/lexica)**, an offline dictionary and
lecture captioner I use daily.

---

### What that looks like in practice

An agent asking permission for every shell command trains you to turn permissions off.
So a small model scores each call first: low-scoring ones run, the rest still ask you:

```
› Run exactly: wc -l src/agent.ts
  Risk gate allowed Bash — worst P=0.074 (exfiltrates) < 0.2
  ⚙ Bash — wc -l src/agent.ts        ok in 88ms
  506

› Clean the build. Run exactly: rm -rf dist
  Risk gate deferred Bash — P(destroys-data)=0.995 is not below 0.2
  ⚠ Permission required for Bash
```

---

### Projects

#### [mini-claude-code](https://github.com/liu-x27/mini-claude-code) · TypeScript

A small, readable agent framework on the Claude API — agentic loop, 7 tools, permissions,
session persistence, driven from a REPL, a web UI or as a library. Building the REPL is
what exposed three design faults in the framework underneath it.

On top of it, a decision layer that answers the agent's own control-flow questions with a
number the model did not choose — the probability mass over two label tokens, read out of
the logprobs — instead of prose. That is the risk gate above, plus a model router that
picks a cheap or a strong tier per request. The scores are not calibrated and are not
claimed to be — the gate thresholds them, and the held-out runs report both sides: safe
commands cleared, and unsafe ones auto-approved. Every backend failure resolves to the
safe side: a judge that times out gets you asked, not obeyed.

**On the newest held-out set it cleared 26 of 77 safe commands and allowed 0 of 76 unsafe
ones.** An earlier held-out set has one false allow, and the README prints that row too.
Measured across 457 hand-labelled commands and 105 requests over six sets, with the
held-out column beside the tuned one — including the router's, which is four times worse
out of sample and says so.

#### [lexica](https://github.com/liu-x27/lexica) · JavaScript · Electron · Kotlin

A 3.4-million-entry offline dictionary and a real-time lecture captioner, both running
with the network cable pulled out. One source tree ships to Windows and Android — a
CommonJS shim and a Kotlin SQL bridge let the dictionary, wordbook and quiz modules run
unmodified in a WebView, with a byte-equality test holding the shared renderer in place.

**Audio processing went from 0.58× to 4.0× real time**, which is the difference between
captions that keep up with a lecture and captions that fall behind it.

#### [crowd-annotation-platform](https://github.com/liu-x27/crowd-annotation-platform) · React · Node · MongoDB

Role-based text annotation with local LLM pre-labelling and a multi-round review queue.
It holds 14 tasks and 94,469 samples, of which **3,063 went through the review queue by
hand**; model pre-labels are stored as a separate source and never merged into the human
ones. Used by one annotator, which the README states rather than leaving to be inferred.

---

TypeScript · JavaScript · Python · React · Node · Electron · Kotlin · MongoDB

Reach me at `liu.x27@northeastern.edu`.
