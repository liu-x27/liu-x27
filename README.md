## Xinyu Liu

M.S. Software Engineering Systems at **Northeastern University**, Arlington VA
(Dec 2028). B.Eng. Software Engineering, **Xi'an Jiaotong University**.

Most of what I build ends up being about the same thing: **systems that fail without
raising.** A dictionary that silently outranks real words with typos. A decoder that
loops forever instead of erroring. A research pipeline that reported a 12-point
improvement it had memorised. The interesting work is usually in noticing.

---

#### [mini-claude-code](https://github.com/liu-x27/mini-claude-code) · TypeScript

A small, readable agent framework on the Claude API — agentic loop, 7 tools, a
permission system, session persistence. Driven from a REPL, a web UI, or as a library.
Building the REPL is what exposed three design faults in the framework underneath it.

#### [llm-distill-study](https://github.com/liu-x27/llm-distill-study) · Python

A knowledge-distillation pipeline and a post-mortem of the seven ways it produced
confident wrong numbers without ever raising an error — including an unchecked
`done_reason == "length"` that inverted a teacher-scale comparison, and a test-set leak
that inflated an accuracy by 12.46 points.

#### [lexica](https://github.com/liu-x27/lexica) · JavaScript · Electron · Kotlin

A 3.4-million-entry offline dictionary and a real-time lecture captioner, both running
with the network cable pulled out. Speech recognition went from 0.58× to 4.0× real time;
one source tree ships to Windows and Android with a byte-equality test holding the
shared renderer in place.

#### [crowd-annotation-platform](https://github.com/liu-x27/crowd-annotation-platform) · React · Node · MongoDB

Role-based crowdsourced text annotation with local LLM pre-labelling and a multi-round
review queue. The upstream half of the distillation study — it produced the corpora.

---

Currently looking for **Summer 2027 / Fall 2027 SWE internship or co-op**, DC metro area
or remote. Reach me at `liu.x27@northeastern.edu`.
