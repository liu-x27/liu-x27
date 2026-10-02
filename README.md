## Xinyu Liu

M.S. Software Engineering Systems at **Northeastern University**, Arlington VA
(Dec 2028). B.Eng. Software Engineering, **Xi'an Jiaotong University**.
Looking for a **Summer 2027 SWE internship** — DC metro or remote. A Fall 2027 co-op
works too.

Most of what I build ends up being about the same thing: **systems that fail without
raising.** A dictionary that silently outranks real words with typos. A decoder that
loops forever instead of erroring. A labelling tool that saves a failed model call as a
label. A safety gate that goes on reporting success after the component it depends on
has quietly stopped answering.

Each project below has a page that tells its story in a few minutes, and a README that
says what was measured, on what, and what was not tested.

<table>
<tr>
<td width="50%" valign="top">

<a href="https://liu-x27.github.io/mini-claude-code/"><picture><source media="(prefers-color-scheme: dark)" srcset="https://liu-x27.github.io/mini-claude-code/brand/lockup-dark.svg"><img alt="mini-claude-code" src="https://liu-x27.github.io/mini-claude-code/brand/lockup-light.svg" height="50"></picture></a>

**Doesn't ask about `wc -l`. Does ask about `rm -rf`.**
A readable coding-agent harness on the Claude API, whose risk gate asks a local model
four narrow questions about each shell command. On 153 commands it had never seen:
**0 of 76 unsafe ones cleared**, 38% of the safe ones run without a prompt.

[Project page](https://liu-x27.github.io/mini-claude-code/) · [Code](https://github.com/liu-x27/mini-claude-code) · TypeScript · MCP · ACP

</td>
<td width="50%" valign="top">

<a href="https://liu-x27.github.io/XavierJev/"><picture><source media="(prefers-color-scheme: dark)" srcset="https://liu-x27.github.io/XavierJev/brand/lockup-dark.svg"><img alt="XavierJev" src="https://liu-x27.github.io/XavierJev/brand/lockup-light.svg" height="36"></picture></a>

**Ask for `Y` or `N`. Read the ratio, not the prose.**
The decision layer behind that gate, as its own library: yes/no, one-of-*n* and rubric
questions read off one token's probabilities. Of the 1,181 real commands it cleared,
every one read by hand, **6 should have been asked**.

[Project page](https://liu-x27.github.io/XavierJev/) · [Code](https://github.com/liu-x27/XavierJev) · TypeScript · Claude Code plugin

</td>
</tr>
<tr>
<td width="50%" valign="top">

<a href="https://liu-x27.github.io/lexica/"><picture><source media="(prefers-color-scheme: dark)" srcset="https://liu-x27.github.io/lexica/brand/lockup-dark.svg"><img alt="Lexica" src="https://liu-x27.github.io/lexica/brand/lockup-light.svg" height="38"></picture></a>

**`recieve` still resolves. It just ranks below `receive`.**
A 3.4-million-entry offline English–Chinese dictionary and a lecture captioner I use
daily, on Windows and Android from one source tree. One rule ranks down the
**3.24 million entries no source vouches for**; captions run at 9.1× real time.

[Project page](https://liu-x27.github.io/lexica/) · [Code](https://github.com/liu-x27/lexica) · Electron · SQLite · whisper.cpp · Kotlin

</td>
<td width="50%" valign="top">

<a href="https://liu-x27.github.io/crowd-annotation-platform/"><picture><source media="(prefers-color-scheme: dark)" srcset="https://liu-x27.github.io/crowd-annotation-platform/brand/lockup-dark.svg"><img alt="Crowd Annotation" src="https://liu-x27.github.io/crowd-annotation-platform/brand/lockup-light.svg" height="46"></picture></a>

**Label with a model. Keep what it said separate.**
A text annotation platform where model drafts are stored apart from human labels.
Rewritten after migrating v1's own database showed that **only 91 of the 3,063 labels**
its README called reviewed one at a time were made at a human pace.

[Project page](https://liu-x27.github.io/crowd-annotation-platform/) · [Code](https://github.com/liu-x27/crowd-annotation-platform) · TypeScript · Postgres · React

</td>
</tr>
<tr>
<td colspan="2" valign="top">

<a href="https://liu-x27.github.io/spire-jev/"><picture><source media="(prefers-color-scheme: dark)" srcset="https://liu-x27.github.io/spire-jev/brand/lockup-dark.svg"><img alt="spire-jev" src="https://liu-x27.github.io/spire-jev/brand/lockup-light.svg" height="50"></picture></a>

**A narrow win, not a win rate.**
A bot that plays Slay the Spire 2 in the real game: all five characters, whole runs, no
human input. A simulator of the game's combat, checked against the game card by card,
searches each turn in well under a millisecond at the median. It has won twice at
Ascension 10, and **0 of 90** on the seeds no change was tuned on; its pages say both.
Players can run it inside their own game from the Steam Workshop
([Jev 自动爬塔](https://steamcommunity.com/sharedfiles/filedetails/?id=3808798192)).

[Project page](https://liu-x27.github.io/spire-jev/) · [Code](https://github.com/liu-x27/spire-jev) · TypeScript · C# · Steam Workshop

</td>
</tr>
</table>

---

TypeScript · JavaScript · Python · React · Node · Electron · Kotlin · PostgreSQL · SQLite

Reach me at `liu.x27@northeastern.edu`.
