## Xinyu Liu

M.S. Software Engineering Systems at **Northeastern University**, Arlington VA
(Dec 2028). B.Eng. Software Engineering, **Xi'an Jiaotong University**.
Looking for a **Summer 2027 / Fall 2027 SWE internship or co-op** — DC metro or remote.

Most of what I build ends up being about the same thing: **systems that fail without
raising.** A dictionary that silently outranks real words with typos. A decoder that
loops forever instead of erroring. A research pipeline that reported a 12-point
improvement it had memorised. A safety gate that goes on reporting success after the
component it depends on has quietly stopped answering.

Noticing is half of it. The other half is measuring whether the fix worked, on data
chosen before the fix existed — which is usually where the flattering number turns out
to have been about the test set.

---

### What that looks like in practice

An agent asking permission for every shell command trains you to turn permissions off.
So a small model scores each call first, and only the ones that earn it reach you:

```
› Run exactly: wc -l src/agent.ts
  Risk gate allowed Bash — worst P=0.074 (exfiltrates) < 0.2
  ⚙ Bash — wc -l src/agent.ts        ok in 88ms
  506

› Clean the build. Run exactly: rm -rf dist
  Risk gate deferred Bash — P(destroys-data)=0.995 is not below 0.2
  ⚠ Permission required for Bash
```

The web UI does the same thing with a pill on each tool call, which is the only trace
the gate leaves when it works — an absence is not something anyone notices.

---

### Projects

#### [mini-claude-code](https://github.com/liu-x27/mini-claude-code) · TypeScript

A small, readable agent framework on the Claude API — agentic loop, 7 tools, permissions,
session persistence, driven from a REPL, a web UI or as a library. Building the REPL is
what exposed three design faults in the framework underneath it.

On top of it, a decision layer that answers the agent's own control-flow questions with
a number the model did not choose — the probability mass over two label tokens, read out
of the logprobs — instead of prose. That is the risk gate above, plus a model router that
picks a cheap or a strong tier per request. The scores are not calibrated and are not
claimed to be; they are ordered well enough to put a threshold on, which is all the gate
needs. Every failure path in both resolves to the
safe side — a judge that times out gets you asked, not obeyed.

**Zero false allows on a 153-command set it had never seen.** Measured on 457 hand-labelled
commands and 105 requests across six sets, with the held-out column printed beside the
tuned one — including the router's, which is four times worse out of sample and says so.

#### [llm-distill-study](https://github.com/liu-x27/llm-distill-study) · Python · PyTorch

A knowledge-distillation pipeline and a post-mortem of the seven ways it produced
confident wrong numbers without ever raising an error.

**An unchecked `done_reason == "length"` inverted a teacher-scale comparison**, and a
test-set leak inflated an accuracy by 12.46 points. Both conclusions are retracted in
the README rather than quietly dropped.

#### [lexica](https://github.com/liu-x27/lexica) · JavaScript · Electron · Kotlin

A 3.4-million-entry offline dictionary and a real-time lecture captioner, both running
with the network cable pulled out. One source tree ships to Windows and Android — a
CommonJS shim and a Kotlin SQL bridge let the dictionary, wordbook and quiz modules run
unmodified in a WebView, with a byte-equality test holding the shared renderer in place.

**Speech recognition went from 0.58× to 4.0× real time**, which is the difference
between captions that keep up with a lecture and captions that fall behind it.

#### [crowd-annotation-platform](https://github.com/liu-x27/crowd-annotation-platform) · React · Node · MongoDB

Role-based text annotation with local LLM pre-labelling and a multi-round review queue.
It produced the corpora behind the distillation study, storing human and model labels as
separate sources — which is the correct behaviour, and is what made the downstream
split's leak possible to find and to localise.

---

TypeScript · Python · Java · React · Node · Electron · PyTorch · MongoDB

Reach me at `liu.x27@northeastern.edu`.
