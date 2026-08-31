# The Integrated CS Degree: Merging TeachYourselfCS + OSSU Into One Rigorous, Free, Self-Study Curriculum

## TL;DR
- **One merged program, TYCS as the spine, OSSU as the scaffolding.** The nine-subject TeachYourselfCS (TYCS) sequence — chosen for depth and coherence — is the backbone; OSSU contributes the pieces TYCS omits (formal math with graded problem sets, theory of computation, software engineering, security, ethics) plus a rigorous prerequisite programming ladder. This produces ~13 stages, not 22 overlapping courses.
- **The July 2025 Coursera audit shutdown reshaped the decision.** Because OSSU lost free audit access to virtually all its Coursera courses in July 2025, the merged curriculum deliberately prefers permanently-free, university-hosted resources (MIT OCW, CMU/Stanford/Berkeley/Princeton course pages, Nand2Tetris, OSTEP) over Coursera wherever a choice exists — which happens to also be the more rigorous, project-heavy option.
- **Given your CS50 + SICP Ch.1 background and systems/security direction, you skip most of Stage 0–1, review Stage 1, and go deep on the systems spine** (CS:APP, OSTEP+xv6, CS144, CMU 15-445, 6.5840) plus a substantive MIT 6.858 security stage. Realistic completion at your sustainable 15–20 h/week: **~3.5–4.5 years**; at 30 h/week, ~2.25 years.

---

## Part 1 — Curriculum Philosophy: How TYCS and OSSU Were Merged

**The core problem with each curriculum alone.** TYCS is a curated, opinionated 9-subject list built for working engineers who already program; it optimizes for depth-per-hour and names the single best book + video series per subject. Its weaknesses: it assumes you can already program well, it under-specifies mathematics (a reading list, not a graded course), it has no theory-of-computation, software-engineering, or security component, and it provides no assessment structure. OSSU is the opposite: a broad, degree-shaped curriculum with explicit prerequisites, ordering, math, theory, security, ethics, and a final project — but it historically leaned heavily on Coursera/edX MOOCs, several of which have been retired or paywalled, and it spreads some subjects thin (e.g., databases and OS were single MOOCs rather than the deep treatments TYCS points to).

**The merge principle: TYCS chooses the resource; OSSU chooses the skeleton.** For every subject that both cover, I compared the two resources head-to-head and kept the one with (a) greater academic depth, (b) permanent free access, and (c) real, independently-gradeable projects. In almost every systems subject, this favored the TYCS pick (CS:APP over a MOOC; OSTEP+xv6 over a lecture-only OS MOOC; CS144 over Kurose lectures alone; DDIA + MIT 6.5840 over nothing in OSSU). For structure — what to study before what, where math slots in, and the non-negotiable inclusion of theory/SE/security/ethics — I kept OSSU's degree shape.

**The Coursera collapse (July–August 2025) was decisive.** OSSU's own FAQ now states verbatim: *"In July of 2025, Coursera removed audit access for the vast majority of their courses, including all of the Coursera courses that OSSU included in its curriculum at the time. Unless something changes at Coursera, OSSU will no longer be recommending their courses."* The mechanism was announced by Coursera CMO Tim Hannan in an official blog post on August 8, 2025: *"This new model replaces our audit experience and gives learners the ability to preview the first module of nearly every course on Coursera for free."* OSSU is now actively searching for replacements (its FAQ: *"We are currently reviewing options for free resources that can replace the Coursera courses that are still in the curriculum"*), tracked in GitHub Issue #1352 ("No coursera courses can be audited anymore, only previewed (first module only)," opened Aug 11, 2025) and RFC Issue #1395 ("Replace all the Coursera links with free quality alternatives"). This makes several OSSU primaries (Systematic Program Design/HtDP-on-edX, Software Architecture, Principles of Secure Coding, the Databases mini-courses, Parallel Programming) unreliable for a free self-study plan. Wherever an OSSU pick was Coursera-only, I substituted a permanently-free university-hosted equivalent — which is consistently the more rigorous option anyway.

**Bias toward systems depth (your stated direction).** You are heading to Linux sysadmin + security (RHCSA → Security+ → eJPT → CySA+ → OSCP). Where two equally rigorous options existed, I chose the one building C/Linux/systems muscle: Nand2Tetris **and** CS:APP (not one or the other), OSTEP **with** the xv6 kernel labs, CS144's from-scratch TCP/IP stack, and a real Computer Systems Security stage (MIT 6.858) rather than OSSU's retired Coursera security block. This keeps the degree general and rigorous while front-loading exactly the foundations OSCP-track work rewards.

**Anti-bloat rule.** When two resources taught the same thing, I picked one. You will not do both Skiena and Sedgewick and Roughgarden for algorithms; you do Sedgewick/Wayne's `algs4` (best free autograded assignments) as primary with Roughgarden as optional reference. You will not do both Nand2Tetris and CS:APP for the *same* layer — they're sequenced because they cover *different* layers (gates→CPU vs. C→assembly→memory→OS interface).

---

## Part 2 — Duplicate / Overlap Analysis

| Topic | TeachYourselfCS | OSSU | Overlap | Decision | Reason |
|---|---|---|---|---|---|
| Intro programming | SICP (Scheme) + Berkeley 61A (Harvey) | Intro to CS & Programming w/ Python (MITx 6.00.1x) | High | **Keep SICP/61A as primary; you SKIP intro — you did CS50 + SICP Ch.1** | SICP is deeper; you've already met the intro bar |
| Programming paradigms | (SICP covers FP/abstraction) | SPD + Class-based + **UW CSE341** | Medium | **Keep UW CSE341 (permanently free); drop Coursera-bound SPD/Class-based** | CSE341 (Grossman) is the rigorous, free paradigms course; SPD/HtDP now Coursera/edX-fragile |
| Math for CS (discrete) | *Mathematics for CS* + MIT 6.042 videos | MIT 6.042J (OCW) | **Exact duplicate** | **Keep MIT 6.042J once** | Same resource; use OCW Fall 2010 for exams/psets |
| Calculus | (not required) | MITx 18.01 Calc 1A/1B/1C | None | **Optional/prereq only** | CS needs limited calculus |
| Linear algebra | 3Blue1Brown + Strang | 3B1B + MIT 18.06 | **Exact duplicate** | **Keep 3B1B → MIT 18.06 once** | Identical picks |
| Algorithms & DS | Skiena (ADM) + videos + Leetcode | Stanford Algorithms (Roughgarden) 1&2 | High | **Primary: Princeton algs4 (Sedgewick/Wayne) autograded; Skiena + Roughgarden as references** | algs4 has the best free autograded assignments; "implementation over watching" |
| Computer architecture | CS:APP + Berkeley 61C; Nand2Tetris intro | Nand2Tetris I&II; MIT 6.004 (adv) | High | **Sequence both: Nand2Tetris (build up) → CS:APP + 61C (dig down)** | Different abstraction layers; not redundant |
| Operating systems | OSTEP + xv6 labs; Berkeley CS162 | OSTEP (OSSU's own course page) | **Exact duplicate (OSTEP)** | **Keep OSTEP once; primary labs = MIT 6.1810 xv6; CS162 Pintos optional-adv** | Both name OSTEP; xv6 labs are the canonical free projects |
| Networking | Kurose & Ross + Stanford CS144 | Kurose & Ross (UMass) + Wireshark labs | High | **Book: Kurose/Ross; primary project: Stanford CS144 TCP/IP stack** | CS144 is the serious "implement TCP" project OSSU lacks |
| Databases | Berkeley CS186 + Red Book papers | Stanford "Databases" mini-courses | Medium | **Primary: CMU 15-445 (Pavlo) + BusTub projects**; Red Book optional-adv | 15-445 is free on YouTube with the best free DB implementation projects |
| Languages & compilers | Crafting Interpreters + Aiken (edX) | Stanford Compilers (Aiken) + Haskell/Prolog | High | **Primary: Crafting Interpreters (build 2 interpreters); Aiken free on YouTube as theory** | Crafting Interpreters is the best free build-it resource |
| Theory of computation | (absent) | MIT 18.404J (Sipser) OCW | TYCS gap | **Add MIT 18.404J** | Fills a genuine TYCS hole; OCW has videos+psets |
| Distributed systems | DDIA + MIT 6.824/6.5840 | (only in Advanced electives) | TYCS deeper | **Keep DDIA + MIT 6.5840 labs (Go/Raft)** | Canonical; OSSU barely covers it |
| Software engineering | (absent) | UBC SE Intro (edX/free UBC CPSC310 mirror) | TYCS gap | **Add: UBC CPSC 310 materials (free GitHub mirror)** | Fills TYCS hole with a real project course |
| Security | (absent) | Core Security (all Coursera — now paywalled) | TYCS gap; OSSU broken | **Add MIT 6.858 (free OCW videos+labs) as primary** | Rebuilds the dead OSSU security block with a rigorous free course |
| Ethics | (absent) | Core Ethics (Coursera) | TYCS gap | **Optional readings; low priority for self-study** | Valuable but not gradeable free; keep light |
| CS tools (shell/git/vim) | (absent) | MIT "Missing Semester" | TYCS gap | **Add Missing Semester (free MIT)** | High ROI; directly serves your sysadmin path |

---

## Part 3 — Final Integrated Curriculum (in order)

Overlap label per subject: 🟢 STUDY FULLY / 🟡 REVIEW ONLY / 🔴 SKIP–DUPLICATE / 🔵 OPTIONAL/ADVANCED.

### Stage 0 — Prerequisites & Tooling
**0A. Programming maturity check — 🟡 REVIEW ONLY (you've done CS50 + SICP Ch.1)**
- *Why:* Confirms you can decompose problems, use recursion, and reason about abstraction before the systems gauntlet.
- *Prereqs:* none.
- *Primary:* Finish **SICP Chapters 2–3** (free HTML: https://sarabander.github.io/sicp/html/index.xhtml) with **Berkeley 61A / Brian Harvey lectures** (https://archive.org/details/ucberkeley-webcast-PL3E89002AA9B9879E). *You already did Ch.1 — review its exercises, then continue.*
- *Secondary (only if SICP grates):* DeNero's **Composing Programs** (Python, https://www.composingprograms.com/) with **cs61a.org** current assignments.
- *TYCS source:* Programming (SICP / 61A). *OSSU source:* Intro CS (6.00.1x) — **skipped as duplicate**.
- *Practice:* SICP Ch.2–3 exercises (~40) + ~20 warm-ups on exercism (https://exercism.org). *Projects:* SICP symbolic differentiation; metacircular evaluator (Ch.4 intro, optional). *Weekly:* 6–8 h, ~3–5 weeks (reviewing, not learning from zero).

**0B. Missing Semester (shell, scripting, git, vim, debugging) — 🟢 STUDY FULLY**
- *Why:* Directly serves both CS work and your RHCSA/OSCP path; TYCS ignores tooling.
- *Primary:* **MIT "The Missing Semester of Your CS Education"** (https://missing.csail.mit.edu/) — free, with exercises. *OSSU source:* CS Tools (same). *TYCS source:* none.
- *Practice:* every lecture's exercises (~11 sets). *Weekly:* 10–12 h for ~2 weeks.

### Stage 1 — Programming Languages & Paradigms
**1. Programming Languages (FP, static/dynamic typing, PL concepts) — 🟢 STUDY FULLY**
- *Why:* Learning *about* languages (types, scope, evaluation, FP) generalizes across every future language; OSSU rightly requires it, TYCS folds it into SICP + compilers.
- *Prereqs:* Stage 0.
- *Primary:* **UW CSE 341, Programming Languages** (Dan Grossman), full free materials incl. Spring 2019 lectures/assignments: https://courses.cs.washington.edu/courses/cse341/19sp/ (SML, Racket, Ruby). [github](https://github.com/ossu/computer-science)
- *TYCS source:* implicit in SICP/compilers. *OSSU source:* CSE341 (kept) + SPD/Class-based (dropped as Coursera-fragile & partly redundant with SICP).
- *Overlap:* 🟡 The OO/design content of OSSU's dropped courses is picked up later in Software Engineering.
- *Practice:* ~7 substantial autogradable homeworks across SML/Racket/Ruby. *Project:* extend the homework interpreters. *Weekly:* 8–10 h, ~9–11 weeks.

### Stage 2 — Mathematics for Computer Science
**2A. Discrete Mathematics / Math for CS — 🟢 STUDY FULLY (both curricula point to the same course)**
- *Why:* Logic, proofs, induction, sets, combinatorics, graph theory, discrete probability, number theory — the analytical language of algorithms, theory, and cryptography.
- *Prereqs:* high-school algebra; proof skill grows here.
- *Primary:* **MIT 6.042J Mathematics for Computer Science** — book-length notes (*Mathematics for Computer Science*, Lehman/Leighton/Meyer, https://courses.csail.mit.edu/6.042/spring18/mcs.pdf) + **OCW Fall 2010 video lectures, problem sets, exams w/ solutions** (https://ocw.mit.edu/courses/6-042j-mathematics-for-computer-science-fall-2010/).
- *TYCS source:* Math for CS (exact same). *OSSU source:* MIT 6.042J (exact same). **Merged to one.**
- *Practice:* all 6.042 problem sets (~10) + in-class problems. *Exams:* OCW Fall 2010 midterm + finals (2004/2006/2008) with solutions. [mit](https://www.ocw.mit.edu/courses/6-042j-mathematics-for-computer-science-fall-2010/pages/exams) *Weekly:* 8–10 h, ~13–15 weeks.

**2B. Linear Algebra — 🔵 OPTIONAL/ADVANCED (do before graphics/ML electives)**
- *Primary:* **3Blue1Brown "Essence of Linear Algebra"** (https://www.youtube.com/playlist?list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab) → **MIT 18.06** (https://ocw.mit.edu/courses/18-06sc-linear-algebra-fall-2011/). *Both curricula agree.* Defer unless pursuing ML/graphics.

**2C. Calculus / Probability — 🔵 OPTIONAL.** Only if math is shaky (MITx 18.01) or before a probability-heavy elective (Harvard Stat110, https://stat110.hsites.harvard.edu/). Not on the critical path for your systems/security direction.

### Stage 3 — Data Structures & Algorithms
**3. Algorithms & Data Structures — 🟢 STUDY FULLY**
- *Why:* The single highest-leverage problem-solving skill; foundation for every later subject.
- *Prereqs:* Stage 0 programming; Stage 2A (concurrent is fine; 6.042 sharpens analysis).
- *Primary:* **Princeton `algs4` — Sedgewick & Wayne**, free textbook site + creative programming assignments with a rigorous autograder: https://algs4.cs.princeton.edu/home/ (Coursera "Algorithms Part I & II" are the video companion — still free for this specific pair per Princeton policy, https://online.princeton.edu/algorithms-part-i).
- *Secondary (reference only):* Skiena's *Algorithm Design Manual* (TYCS pick) + Skiena video lectures (https://www3.cs.stonybrook.edu/~skiena/373/videos/); Roughgarden's *Algorithms Illuminated* (OSSU pick, https://www.algorithmsilluminated.org/). [teachyourselfcs](https://teachyourselfcs.com/)
- *TYCS source:* Skiena + Leetcode. *OSSU source:* Roughgarden (Stanford Algorithms). **Merged: algs4 primary (best free autograded implementation work), others optional.**
- *Practice:* 6–8 flagship algs4 assignments (Percolation, Deques/Randomized Queues, Collinear Points, 8-Puzzle/A*, Kd-Trees, WordNet, Seam Carving, Burrows–Wheeler) + **~75–100 LeetCode problems** (https://leetcode.com) for interview fluency. *Weekly:* 8–10 h, ~16–20 weeks.

### Stage 4 — Computer Architecture & Organization
**4A. From NAND to a working computer — 🟢 STUDY FULLY**
- *Why:* Builds the bottom-up mental model (gates → ALU → CPU → assembler → VM → compiler → OS) so higher abstractions stop being magic.
- *Prereqs:* Stage 0.
- *Primary:* **Nand2Tetris (The Elements of Computing Systems)** — free projects & lectures: https://www.nand2tetris.org/course. Do Projects 1–6 (Part I: hardware→assembler) minimum; Part II (VM→compiler→OS) is excellent and overlaps Stage 9.
- *TYCS source:* Nand2Tetris (gentle intro). *OSSU source:* Nand2Tetris I & II.
- *Practice/Projects:* the 12 built-in projects (with .tst/.cmp test scripts) are the assessment. *Weekly:* 7–10 h, ~7–9 weeks (Part I), +6 weeks if doing Part II.

**4B. Computer Systems: A Programmer's Perspective (C, assembly, memory, caches) — 🟢 STUDY FULLY (systems spine)**
- *Why:* The most neglected area among self-taught engineers [teachyourselfcs](https://teachyourselfcs.com/) and the keystone of your systems/security path — teaches how C maps to x86-64, the stack, buffer overflows, caches, linking, and the OS interface.
- *Prereqs:* Stage 0; C picked up here.
- *Primary:* **CS:APP, 3rd ed.** (Bryant & O'Hallaron) — book site + course-mapping: http://csapp.cs.cmu.edu/3e/home.html; chapters 1–6 for architecture core. **Self-study labs (Data, Bomb, Attack, Cache, Shell, Malloc, Proxy):** http://csapp.cs.cmu.edu/3e/labs.html.
- *Secondary (video):* **Berkeley CS61C "Great Ideas in Computer Architecture"** — current site https://cs61c.org (past lectures on Internet Archive).
- *TYCS source:* CS:APP + 61C. *OSSU source:* MIT 6.004 (advanced) — kept as 🔵 optional-advanced (https://ocw.mit.edu/courses/6-004-computation-structures-spring-2017/).
- *Practice/Projects:* **Bomb Lab** (reverse-engineer assembly w/ gdb), **Attack Lab** (buffer-overflow + ROP — directly OSCP-relevant), **Malloc Lab** (write a memory allocator), [GitHub](https://github.com/mwfj/CMU_15213_CSAPP3E_Lab) **Shell Lab** (write a shell). *Weekly:* 8–12 h, ~12–15 weeks.

### Stage 5 — Operating Systems
**5. Operating Systems — 🟢 STUDY FULLY (systems spine)**
- *Why:* Almost all your code runs under an OS; [teachyourselfcs](https://teachyourselfcs.com/) understanding processes, threads, scheduling, virtual memory, concurrency, and file systems is essential for both CS and sysadmin/security.
- *Prereqs:* Stage 4B (CS:APP), C fluency.
- *Primary book:* **Operating Systems: Three Easy Pieces (OSTEP)** — free: https://pages.cs.wisc.edu/~remzi/OSTEP/. Homeworks: https://github.com/remzi-arpacidusseau/ostep-homework ; C/kernel projects: https://github.com/remzi-arpacidusseau/ostep-projects.
- *Primary labs:* **MIT 6.1810 xv6 (RISC-V) labs** — free, self-contained, with the xv6 book: https://pdos.csail.mit.edu/6.1810/2024/ (labs: syscalls, page tables, traps, copy-on-write, locks, file system, mmap, net driver). [MIT](https://pdos.csail.mit.edu/6.828/2026/)
- *Secondary/advanced:* **Berkeley CS162 Pintos** projects (threads, user programs, file systems) — https://cs162.org — 🔵 optional-advanced, more open-ended design.
- *TYCS source:* OSTEP + xv6 + CS162. *OSSU source:* OSTEP (OSSU's own course page). **Merged: OSTEP once; xv6 labs primary.**
- *Practice/Projects:* OSTEP simulations/homeworks (~20, self-grading via `-c`) + **ostep-projects** (shell, memory allocator, MapReduce, xv6 scheduler) + **xv6 labs** (~9). *Weekly:* 10–12 h, ~12–15 weeks. The heaviest, most valuable systems stage for you.

### Stage 6 — Computer Networking
**6. Computer Networking — 🟢 STUDY FULLY (systems spine)**
- *Why:* The Internet is the platform; you'll finally understand the protocols you've worked around for years — essential for security/pentest work.
- *Prereqs:* Stage 3 (basic DS), some C/C++.
- *Primary book:* **Computer Networking: A Top-Down Approach** (Kurose & Ross) with the free UMass lectures + **Wireshark labs**: https://gaia.cs.umass.edu/kurose_ross/wireshark.php.
- *Primary project:* **Stanford CS144 "Introduction to Computer Networking"** — build a working TCP/IP stack in modern C++ from scratch: https://cs144.github.io/ (video playlist https://www.youtube.com/playlist?list=PL6RdenZrxrw9inR-IJv-erlOKRHjymxMN).
- *TYCS source:* Kurose/Ross + CS144. *OSSU source:* Kurose/Ross (UMass) + Wireshark labs. **Merged: same book; CS144 adds the serious build project OSSU lacks.**
- *Practice/Projects:* Wireshark labs (~8) + **CS144 checkpoints 0–7** (byte-stream reassembler → TCP receiver → TCP sender → IP router → full stack). [GitHub](https://github.com/PKUFlyingPig/CS144-Computer-Network) [Studocu](https://www.studocu.com/en-us/course/stanford-university/introduction-to-computer-networking/1013910) *Weekly:* 8–12 h, ~10–13 weeks.

### Stage 7 — Databases
**7. Database Systems — 🟢 STUDY FULLY**
- *Why:* Data sits at the heart of most significant programs; few engineers understand how an RDBMS actually works internally. [teachyourselfcs](https://teachyourselfcs.com/)
- *Prereqs:* Stage 3 (data structures), strong C++ for the projects.
- *Primary:* **CMU 15-445/645 Intro to Database Systems (Andy Pavlo)** — full free lectures (Fall 2024 playlist https://www.youtube.com/playlist?list=PLSE8ODhjZXjYDBpQnSymaectKjxCy6BYq), slides/notes https://15445.courses.cs.cmu.edu/fall2024/, and **BusTub projects** (buffer pool manager, B+Tree index, query execution, concurrency control) https://github.com/cmu-db/bustub. [CS DIY](https://csdiy.wiki/en/%E6%95%B0%E6%8D%AE%E5%BA%93%E7%B3%BB%E7%BB%9F/15445/) [CMU 15-445/645](https://15445.courses.cs.cmu.edu/fall2024/project4/)
- *Secondary/advanced:* TYCS's **Berkeley CS186 (Hellerstein)** lectures (https://www.youtube.com/user/CS186Berkeley/videos), the **"Architecture of a Database System"** paper (http://db.cs.berkeley.edu/papers/fntdb07-architecture.pdf), and the **Red Book** (http://www.redbook.io/) — 🔵 optional-advanced. [teachyourselfcs](https://teachyourselfcs.com/)
- *TYCS source:* CS186 + Red Book papers. *OSSU source:* Stanford Databases mini-courses (edX/Coursera — SQL modeling). **Merged: 15-445 primary (best free implementation projects); Stanford's free SQL mini-courses on edX optional for pure SQL/modeling practice.**
- *Practice/Projects:* **BusTub Projects #0–#4** (C++ Primer → Buffer Pool → B+Tree → Query Execution → Concurrency Control). [CMU 15-445/645 +3](https://15445.courses.cs.cmu.edu/fall2024/project4/) *Weekly:* 10–12 h, ~12–14 weeks.

### Stage 8 — Theory of Computation
**8. Theory of Computation — 🟢 STUDY FULLY (fills a TYCS gap)**
- *Why:* Finite automata, regular/context-free languages, Turing machines, decidability, and NP-completeness define the limits of computation and sharpen your proof skills.
- *Prereqs:* Stage 2A (6.042), Stage 3 (algorithms).
- *Primary:* **MIT 18.404J Theory of Computation (Michael Sipser)** — OCW Fall 2020 with 26 video lectures, readings, problem sets: https://ocw.mit.edu/courses/18-404j-theory-of-computation-fall-2020/. [teachyourselfcs](https://teachyourselfcs.com/) Textbook: Sipser, *Introduction to the Theory of Computation* (paid; older editions cheap — buy used, as TYCS advises).
- *TYCS source:* none (gap). *OSSU source:* MIT 18.404J (Advanced theory).
- *Practice/Exams:* OCW problem sets; the companion 6.045 site (https://people.csail.mit.edu/rrw/6.045-2020/) gives a grading rubric of midterm 25% / final 35% / homework 40%. *Weekly:* 8–10 h, ~13 weeks.

### Stage 9 — Programming Languages & Compilers
**9. Compilers & Interpreters — 🟢 STUDY FULLY**
- *Why:* Understanding lexing, parsing, type checking, and code generation makes you fluent in *any* new language and demystifies the tools you use daily.
- *Prereqs:* Stage 1 (PL), Stage 3 (DS), Stage 4B (assembly/memory helps for codegen).
- *Primary:* **Crafting Interpreters (Bob Nystrom)** — free, build a tree-walking interpreter (jlox) then a bytecode VM in C (clox): https://craftinginterpreters.com/contents.html. [teachyourselfcs](https://teachyourselfcs.com/)
- *Secondary (theory/lectures):* **Stanford Compilers (Alex Aiken)** — free on edX (audit) https://www.edx.org/learn/computer-science/stanford-university-compilers and YouTube https://www.youtube.com/playlist?list=PLEAYkSg4uSQ3yc_zf_f1GOxl5CZo0LVBb, with the COOL compiler project. Dragon Book as reference only.
- *TYCS source:* Crafting Interpreters + Aiken. *OSSU source:* Aiken (Stanford Compilers) + Haskell/Prolog electives. **Merged: Crafting Interpreters primary (build-it), Aiken as theory companion.**
- *Practice/Projects:* build **both** interpreters in Crafting Interpreters (the whole book) + optionally Aiken's **COOL compiler**. *Weekly:* 8–12 h, ~12–16 weeks.

### Stage 10 — Software Engineering
**10. Software Engineering — 🟢 STUDY FULLY (fills a TYCS gap)**
- *Why:* Specifications, testing, refactoring, architecture, and working in a large existing codebase — the discipline of building software others can maintain.
- *Prereqs:* Core programming + a sizable prior project (you'll have several by now).
- *Primary:* **UBC CPSC 310 Software Engineering** — free public materials/mirror: https://github.com/ubccpsc/310/blob/main/resources/README.md (the edX "Software Engineering: Introduction" is the video companion).
- *Secondary:* continuous-testing/debugging practice via OSSU's **Software Testing / Software Debugging** (Udacity, free YouTube playlists) — 🔵 optional.
- *TYCS source:* none (gap). *OSSU source:* Core applications (SE Intro) + Advanced programming (testing/debugging).
- *Practice/Project:* the multi-week UBC project (build and test a real full-stack query system). *Weekly:* 8–10 h, ~6–10 weeks.

### Stage 11 — Distributed Systems
**11. Distributed Systems — 🟢 STUDY FULLY**
- *Why:* Most modern systems are distributed; you must reason about replication, consistency, consensus, and partial failure.
- *Prereqs:* Stages 5, 6 (OS + networking) — the key TYCS-stated prerequisites.
- *Primary book:* **Designing Data-Intensive Applications (Martin Kleppmann)** — the best practitioner text (paid; no free legal full version — see Part 7 note).
- *Primary labs:* **MIT 6.5840 (formerly 6.824) Distributed Systems** — free schedule, papers, and Go labs (MapReduce → Raft → fault-tolerant KV → sharded KV): https://pdos.csail.mit.edu/6.824/ (lectures on YouTube). [MIT PDOS](https://pdos.csail.mit.edu/6.824/schedule.html)
- *Secondary/free-book alternative:* van Steen & Tanenbaum, *Distributed Systems 3e* (free PDF: https://www.distributed-systems.net/index.php/books/ds3/); paper list https://pdos.csail.mit.edu/6.824/schedule.html. [teachyourselfcs](https://teachyourselfcs.com/)
- *TYCS source:* DDIA + 6.824. *OSSU source:* only glancing (Advanced). **Merged: TYCS's deeper treatment kept wholesale.**
- *Practice/Projects:* **6.5840 Labs 1–5** (implement Raft from scratch, build a sharded fault-tolerant KV store in Go) — among the hardest, most rewarding projects in the whole curriculum. *Weekly:* 10–14 h, ~14–18 weeks.

### Stage 12 — Computer Security Foundations
**12. Computer Systems Security — 🟢 STUDY FULLY (rebuilds OSSU's dead security block; central to your goals)**
- *Why:* Threat modeling, buffer overflows/ROP, privilege separation, web attacks, and applied crypto — the CS foundation beneath Security+/eJPT/OSCP.
- *Prereqs:* Stages 4B, 5, 6 (CS:APP, OS, networking).
- *Primary:* **MIT 6.858 Computer Systems Security** (Zeldovich & Mickens) — free on OCW Fall 2014 with video lectures, notes, exams+solutions, and downloadable labs: https://ocw.mit.edu/courses/6-858-computer-systems-security-fall-2014/ (Lab 1 buffer-overflow PDF downloadable from that page). Current live labs (2020–2026, HTML) at https://css.csail.mit.edu/6.5660/2026/ and older labs e.g. https://css.csail.mit.edu/6.858/2022/labs/lab1.html. [Mit](https://css.csail.mit.edu/6.858/2018/labs/lab1.html)
- *Secondary (free videos + labs):* **UMD "Software Security" (Michael Hicks)** self-hosted free re-host with YouTube lectures, slides, quizzes, and VM-based projects (buffer overflow, web security, static analysis): https://mhicks.me/courses/software-security/. [mhicks](https://mhicks.me/courses/software-security/)
- *Tertiary (free slides/projects):* **Stanford CS155 Computer & Network Security** (Boneh & Durumeric) — https://cs155.stanford.edu/ (slides + projects free; videos paywalled).
- *TYCS source:* none (gap). *OSSU source:* Core Security (all Coursera — **now paywalled/broken**, replaced here).
- *Practice/Projects:* MIT 6.858 labs (buffer overflow/ROP, privilege separation, symbolic-execution bug finding, web attacks/defenses) [Mit](https://css.csail.mit.edu/6.858/2018/labs/lab1.html) **plus the CS:APP Attack Lab** (https://csapp.cs.cmu.edu/3e/attacklab.pdf) as a buffer-overflow/ROP drill. *Weekly:* 8–12 h, ~10–13 weeks.

### Stage 13 — Advanced / Elective CS Topics — 🔵 OPTIONAL/ADVANCED
Pick per interest; for your track, prioritize the systems/security electives:
- **Advanced architecture:** MIT 6.004 Computation Structures (https://ocw.mit.edu/courses/6-004-computation-structures-spring-2017/).
- **Advanced OS/kernel:** Berkeley CS162 Pintos (deferred from Stage 5).
- **Advanced security:** Stanford CS155 full projects; KU Leuven "Web Security Fundamentals" (edX, if free); Linux Foundation "Secure Software Development" series (edX audit).
- **Databases deep dive:** the Red Book + CMU 15-721 Advanced DB (Pavlo, free YouTube).
- **AI/ML (if desired):** Berkeley CS188 AI + Pacman projects (http://ai.berkeley.edu/); Andrew Ng ML. [teachyourselfcs](https://teachyourselfcs.com/)
- **Final capstone (OSSU requirement):** a substantial original systems/security project — e.g., extend xv6 with a real feature, build a small database or key-value store, implement a network service, or write a static analyzer — demonstrating integrated mastery.

---

## Mastery Criteria (per subject: Basic → Working → Mastery)
Apply these three tiers to gate each stage:
- **Programming (0–1):** *Basic* — explain recursion, higher-order functions, environments/closures. *Working* — implement interpreters and non-trivial recursive/data-abstraction programs. *Mastery* — extend an interpreter with new constructs and reason about evaluation order and types unaided.
- **Math (2A):** *Basic* — state and read proofs (induction, contradiction). *Working* — solve combinatorics/graph/probability problem sets. *Mastery* — construct original correct proofs on unseen problems.
- **Algorithms (3):** *Basic* — explain Big-O and canonical structures. *Working* — implement and analyze sorts, trees, graphs, DP. *Mastery* — design/analyze a correct efficient algorithm for a novel problem and pass the algs4 autograder without hints.
- **Architecture (4):** *Basic* — describe the gates→CPU→OS stack. *Working* — read/write x86-64 assembly, reason about caches/stack. *Mastery* — defuse Bomb/Attack labs and write a working allocator/shell unaided.
- **OS (5):** *Basic* — explain processes, threads, VM, scheduling. *Working* — complete OSTEP homeworks + basic xv6 labs. *Mastery* — add a real kernel feature to xv6 without a walkthrough.
- **Networking (6):** *Basic* — explain the layered model and TCP handshake. *Working* — analyze traffic in Wireshark; pass early CS144 checkpoints. *Mastery* — a working from-scratch TCP/IP stack that talks to a real peer.
- **Databases (7):** *Basic* — explain relational model, indexing, transactions. *Working* — BusTub buffer pool + B+Tree. *Mastery* — correct concurrency control passing all local tests.
- **Theory (8):** *Basic* — classify languages, describe TMs. *Working* — prove regularity/non-regularity, do reductions. *Mastery* — original decidability/NP-completeness proofs.
- **Compilers (9):** *Basic* — explain lexing/parsing/codegen. *Working* — finish jlox. *Mastery* — finish clox (bytecode VM) and add a language feature unaided.
- **Distributed (11):** *Basic* — explain replication/consensus/CAP. *Working* — MapReduce + Raft leader election. *Mastery* — full Raft + sharded KV passing 100× stress runs.
- **Security (12):** *Basic* — explain threat models and common vulnerability classes. *Working* — complete 6.858 labs. *Mastery* — craft a working exploit and a defense unaided (Attack Lab + 6.858 web labs).

---

## Part 4 — Exams & Assessments (real, free, with links)

Per-stage gate. **Readiness rule to advance: score ≥ 70–80% on the stage final AND complete the stage's main project without following a step-by-step tutorial.**

| Stage | Real exams / problem sets (free) | Link |
|---|---|---|
| 2A Math for CS | 6.042 midterm + finals (2004/06/08) w/ solutions; 10 psets | https://ocw.mit.edu/courses/6-042j-mathematics-for-computer-science-fall-2010/pages/exams |
| 3 Algorithms | algs4 autograder scores per assignment; Princeton exercises | https://algs4.cs.princeton.edu/home/ |
| 4A Nand2Tetris | Built-in project test scripts (.tst/.cmp) | https://www.nand2tetris.org/course |
| 4B CS:APP | Self-study labs are the practical exam | http://csapp.cs.cmu.edu/3e/labs.html |
| 5 OS | ostep-homework simulators (self-grading via `-c`); xv6 lab test suites | https://github.com/remzi-arpacidusseau/ostep-homework |
| 6 Networking | CS144 checkpoint test suites; Wireshark lab questions | https://cs144.github.io/ |
| 7 Databases | BusTub local test suites | https://15445.courses.cs.cmu.edu/fall2024/ |
| 8 Theory | 18.404 problem sets; 6.045 grading rubric (midterm/final) | https://ocw.mit.edu/courses/18-404j-theory-of-computation-fall-2020/ |
| 9 Compilers | Crafting Interpreters challenges; Aiken quizzes/midterm/final (edX) | https://craftinginterpreters.com/contents.html |
| 11 Distributed | 6.5840 lab test suites (run 100× for Raft stability) | https://pdos.csail.mit.edu/6.824/ |
| 12 Security | 6.858 exams + solutions (OCW 2014); lab check scripts | https://ocw.mit.edu/courses/6-858-computer-systems-security-fall-2014/ |

**Per-stage examination system (template):** *Midterm* — half the stage's problem sets + a concept quiz drawn from the course's own past exams. *Final* — the course's real final (where free, per table) with a 70–80% pass bar. *Practical exam* — complete the stage's main lab/project unaided. *Project assessment* — code passes the official test suite/autograder; you can explain every design decision.

---

## Part 5 — Projects (serious, independent-implementation, per subject)

Every project below requires you to build, not follow. Beginner/intermediate → main → advanced per stage:

- **Programming (0/1):** SICP metacircular evaluator → CSE341 interpreter homeworks → extend an interpreter with new language features.
- **Algorithms (3):** algs4 Percolation/Deques → 8-Puzzle A* solver, Kd-Tree nearest-neighbor → Seam Carving + Burrows–Wheeler data compressor.
- **Architecture (4):** Nand2Tetris ALU/CPU → full Hack computer + assembler → CS:APP **Bomb Lab** & **Attack Lab** → **Malloc Lab** (memory allocator) → **Shell Lab** (a shell).
- **Operating Systems (5):** ostep-projects Unix shell → **memory allocator** and **MapReduce** → **xv6 labs** (page tables, copy-on-write fork, file system, network driver) → (advanced) Pintos threads/userprog/filesys.
- **Networking (6):** CS144 byte-stream reassembler → **TCP sender/receiver** → **IP router** → full working TCP/IP stack talking to a real server.
- **Databases (7):** BusTub buffer pool manager → **B+Tree index** → **query execution engine** → **concurrency control (MVCC)**.
- **Compilers (9):** Crafting Interpreters jlox (tree-walk) → **clox bytecode VM in C** → (advanced) Aiken **COOL compiler** to MIPS.
- **Software Engineering (10):** UBC CPSC 310 full-stack query-system project with a real test suite.
- **Distributed Systems (11):** 6.5840 MapReduce → **Raft consensus from scratch** → **fault-tolerant sharded key-value store**.
- **Security (12):** 6.858 buffer-overflow/ROP exploit → privilege-separation refactor → web attack/defense lab → CS:APP Attack Lab.
- **Capstone (13):** an original systems/security project (extend xv6, build a mini-DBMS or KV store, implement a network protocol, or a static analyzer).

**Suggested per-subject grading (modifiable):** Theory/proofs 15% · Problem sets 20% · Programming assignments 25% · Exams 15% · Main project 25%. For pure-systems stages (OS, DB, distributed, security), shift toward projects: Projects 45% · Programming assignments 25% · Exams 15% · Problem sets 15%.

---

## Part 6 — Mathematics: Exactly Where It Fits

- **Essential, on the critical path:** **Discrete math (MIT 6.042J)** — logic, proof techniques, induction, set theory, combinatorics, graph theory, discrete probability, and the number theory behind cryptography. Do this at **Stage 2**, before or alongside Algorithms (Stage 3) and required before Theory (Stage 8). This is the *only* math both curricula treat as mandatory, and rightly so.
- **Useful, do just-in-time:** **Linear algebra (3B1B → MIT 18.06)** — needed only for graphics/ML electives and some numerical work; defer to Stage 2B/13 unless an elective demands it. **Probability/statistics** beyond 6.042's discrete-probability chapter (Harvard Stat110) — useful for ML, randomized algorithms, and systems performance analysis; optional.
- **Optional / prerequisite-only:** **Calculus (MITx 18.01)** — CS uses limited calculus (asymptotics, some probability, continuous optimization in ML). Do only if your math is rusty or before a calculus-dependent elective. **Number theory** beyond 6.042 — only if you go deep into cryptography.
- **Explicitly excluded:** advanced pure-math tracks with no CS payoff for your goals (real analysis, abstract algebra beyond number-theory basics, differential equations except for robotics/control electives). OSSU's "Advanced math" block is elective; skip unless an elective needs it.

---

## Part 7 — Programming Languages: Which and Why

Deliberately few languages, each earning its place:

- **Programming fundamentals / paradigms:** **Scheme/Racket** (SICP) and **SML + Ruby** (CSE341) — chosen to *stretch* your model of computation (FP, macros, static vs. dynamic typing), not for job use. Learn them for the ideas.
- **Algorithms:** **Java** (algs4 requires Java for its autograder). Excellent for teaching data structures cleanly; you keep Java as a second general-purpose language.
- **Systems programming, computer architecture, operating systems:** **C** (CS:APP, OSTEP/xv6, ostep-projects). The most important language for your entire trajectory — C + x86-64/RISC-V assembly is where sysadmin, kernel, and security work live. Invest heavily here.
- **Networking & databases:** **modern C++** (CS144, CMU BusTub). Both projects double as a serious modern-C++ education.
- **Compilers:** **Java** (jlox) then **C** (clox) in Crafting Interpreters; optionally C++/Java for Aiken's COOL project.
- **Distributed systems:** **Go** (MIT 6.5840) — goroutines/channels make concurrency and RPC tractable; the canonical language for this course.
- **Security:** **C** (exploitation labs) + **Python** for tooling — aligns directly with eJPT/OSCP workflows.
- **Glue/scripting throughout:** **Python** and **Bash** (Missing Semester) for automation and your sysadmin path.

TYCS's own advice applies: once you've learned programming deeply and studied compilers, picking up a new language is a weekend's work. [teachyourselfcs](https://teachyourselfcs.com/) Do **not** collect languages; learn these because a specific rigorous course uses them.

**Paid-resource honesty (your free-first preference):** The curriculum is ~95% free. Two genuinely-best resources are paid books: **Designing Data-Intensive Applications** (Stage 11 — no free legal full text; buy it, it's worth it) and **Sipser's Theory of Computation** (Stage 8 — buy a used older edition cheaply, as TYCS recommends; the OCW notes/videos cover most content free). Skiena's *Algorithm Design Manual* (paid) is optional since algs4 is free. Everything else — every primary course, lab, and exam above — is free and university-hosted.

---

## Part 8 — Dependency Graph (recommended learning order)

```
Stage 0 (Programming review: SICP Ch.2-3 / 61A)  ──►  Stage 0B (Missing Semester)
        │
        ├──────────────►  Stage 1 (Programming Languages, CSE341)
        │
        ├──────────────►  Stage 2A (Discrete Math, 6.042J) ──┐
        │                                                     │
        ▼                                                     ▼
  Stage 4A (Nand2Tetris) ──► Stage 4B (CS:APP + 61C)     Stage 3 (Algorithms, algs4)
        │                          │                          │
        │                          │                          ├──► Stage 8 (Theory, 18.404)
        │                          ▼                          │
        │                    Stage 5 (OS: OSTEP + xv6)        ├──► Stage 7 (Databases, 15-445)
        │                          │                          │
        │                          ▼                          └──► Stage 9 (Compilers, Crafting Interp.)
        │                    Stage 6 (Networking, CS144)            (also uses Stage 4B)
        │                          │
        │                          ▼
        │                    Stage 11 (Distributed, 6.5840)   ◄── needs Stage 5 + Stage 6
        │
        └──► Stage 4B + 5 + 6  ──► Stage 12 (Security, 6.858)

  Stage 10 (Software Engineering) — after several projects exist (≈ after Stage 7)
  Stage 2B/2C (Linear Algebra / Calculus / Probability) — just-in-time before electives
  Stage 13 (Electives + Capstone) — last
```
Hard prerequisites (from TYCS + course pages): **architecture (4) before OS (5) and databases (7)**; **OS (5) + networking (6) before distributed systems (11)**; **CS:APP/OS/networking before security (12)**; **discrete math (2A) before theory (8)**; **algorithms (3) before databases/compilers/theory**.

---

## Part 9 — Master Curriculum Table

| Stage | Subject | Primary Resource | Secondary | TYCS | OSSU | S/R/Skip | Exercises | Exams | Projects | Est. Time (15–20 h/wk) | Key Link |
|---|---|---|---|---|---|---|---|---|---|---|---|
| 0A | Programming review | SICP Ch.2–3 + 61A (Harvey) | Composing Programs | ✔ | ✔ (skip Intro) | 🟡 | ~40 + 20 warmups | — | Metacircular eval | 3–5 wk | sarabander.github.io/sicp |
| 0B | CS Tools | MIT Missing Semester | — | ✖ | ✔ | 🟢 | ~11 sets | — | — | 2 wk | missing.csail.mit.edu |
| 1 | Programming Languages | UW CSE341 (Grossman) | — | (SICP) | ✔ | 🟢 | ~7 HWs | course quizzes | extend interpreters | 9–11 wk | courses.cs.washington.edu/courses/cse341/19sp |
| 2A | Discrete Math | MIT 6.042J | — | ✔ | ✔ | 🟢 | ~10 psets | midterm+finals | — | 13–15 wk | ocw.mit.edu/…6-042j…fall-2010 |
| 2B/C | Linear Alg / Calc / Prob | 3B1B → MIT 18.06 | Stat110 | ✔ | ✔ | 🔵 | as needed | — | — | JIT | ocw.mit.edu/…18-06sc |
| 3 | Algorithms & DS | Princeton algs4 | Skiena / Roughgarden | ✔ | ✔ | 🟢 | 6–8 + ~75–100 LeetCode | autograder | 8-Puzzle, Seam Carving | 16–20 wk | algs4.cs.princeton.edu |
| 4A | Architecture (build up) | Nand2Tetris | — | ✔ | ✔ | 🟢 | 12 projects | test scripts | Hack computer + assembler | 7–9 wk (+6 Part II) | nand2tetris.org/course |
| 4B | Architecture (dig down) | CS:APP 3e | Berkeley CS61C | ✔ | (6.004) | 🟢 | Ch.1–6 | labs | Bomb/Attack/Malloc/Shell | 12–15 wk | csapp.cs.cmu.edu/3e |
| 5 | Operating Systems | OSTEP + MIT 6.1810 xv6 | Berkeley CS162 | ✔ | ✔ | 🟢 | ~20 HWs | lab suites | xv6 labs, allocator, MapReduce | 12–15 wk | pages.cs.wisc.edu/~remzi/OSTEP |
| 6 | Networking | Kurose/Ross + Stanford CS144 | — | ✔ | ✔ | 🟢 | ~8 Wireshark | checkpoint suites | TCP/IP stack (0–7) | 10–13 wk | cs144.github.io |
| 7 | Databases | CMU 15-445 + BusTub | CS186 / Red Book | ✔ | ✔ | 🟢 | — | local tests | BusTub #0–#4 | 12–14 wk | 15445.courses.cs.cmu.edu/fall2024 |
| 8 | Theory of Computation | MIT 18.404J (Sipser) | — | ✖ | ✔ | 🟢 | psets | midterm+final | proofs | 13 wk | ocw.mit.edu/…18-404j…fall-2020 |
| 9 | Compilers | Crafting Interpreters | Aiken (edX/YT) | ✔ | ✔ | 🟢 | challenges | Aiken exams | jlox + clox (+COOL) | 12–16 wk | craftinginterpreters.com |
| 10 | Software Engineering | UBC CPSC 310 | Testing/Debugging (YT) | ✖ | ✔ | 🟢 | — | — | full-stack query system | 6–10 wk | github.com/ubccpsc/310 |
| 11 | Distributed Systems | DDIA + MIT 6.5840 | van Steen/Tanenbaum | ✔ | (adv) | 🟢 | papers | lab suites (100×) | Raft + sharded KV | 14–18 wk | pdos.csail.mit.edu/6.824 |
| 12 | Security | MIT 6.858 (OCW 2014) | UMD SwSec / CS155 | ✖ | ✔ (broken) | 🟢 | quizzes | OCW exams | 6.858 labs + Attack Lab | 10–13 wk | ocw.mit.edu/…6-858…fall-2014 |
| 13 | Electives + Capstone | per interest | — | ✔ | ✔ | 🔵 | — | — | original systems/security project | open | — |

---

## Part 9 (cont.) — Time Estimates (realistic; do not underestimate)

Total workload for the **required core (Stages 0–12, excluding heavy electives)** is roughly **1,900–2,300 hours** of focused work — in the same ballpark as OSSU's own stated estimate (*"It is possible to finish within about 2 years if you plan carefully and devote roughly 20 hours/week"*), but larger here because the merged systems projects (xv6, CS144, BusTub, Raft, 6.858 labs) are deeper than OSSU's original MOOC assignments. Because you skip Intro CS and only review Stage 0 programming, subtract ~120–150 hours.

Assume ~2,050 net hours for you (post-skip). Real life includes breaks and re-work, so effective throughput is ~85% of nominal hours:

| Pace | Nominal weeks | Calendar estimate (with ~15% slack) |
|---|---|---|
| **15 h/week** | ~137 weeks | **~3.7–4.5 years** |
| **20 h/week** | ~103 weeks | **~2.8–3.3 years** |
| **25 h/week** | ~82 weeks | **~2.2–2.6 years** |
| **30 h/week** | ~68 weeks | **~1.9–2.25 years** |

At your realistic **15–20 h/week evening pace, plan for roughly 3.5–4.5 years.** The heaviest stages (OS, Distributed Systems, Databases, CS:APP) each take 3–4 months alone at that pace — a feature, not a bug: depth is the goal. If you must compress, the two highest-ROI stages to never shortchange are **CS:APP (4B)** and **OS (5)**; the most compressible are **Theory (8)** and **electives (13)**.

---

## Part 10 — Final Master Checklist (trackable)

Copy into Obsidian; check as you go. Advance only when the stage's readiness rule is met (≥70–80% on final AND main project done tutorial-free).

**Stage 0 — Prereqs & Tooling**
- [ ] SICP Ch.2–3 read + exercises (Ch.1 reviewed) — 🟡
- [ ] Metacircular evaluator built
- [ ] Missing Semester: all lectures + exercises — 🟢

**Stage 1 — Programming Languages**
- [ ] CSE341: SML section + homeworks
- [ ] CSE341: Racket section + homeworks
- [ ] CSE341: Ruby section + homeworks

**Stage 2 — Mathematics**
- [ ] 6.042J: all 10 problem sets
- [ ] 6.042J: midterm ≥70%, final ≥70%
- [ ] (opt) 3B1B + MIT 18.06 linear algebra
- [ ] (opt) Calculus / Stat110 if needed by an elective

**Stage 3 — Algorithms & Data Structures**
- [ ] algs4 assignments 1–4 (Percolation, Deques, Collinear, 8-Puzzle)
- [ ] algs4 assignments 5–8 (Kd-Trees, WordNet, Seam Carving, Burrows–Wheeler)
- [ ] ~75–100 LeetCode problems

**Stage 4 — Architecture**
- [ ] Nand2Tetris Projects 1–6 (Part I)
- [ ] (opt) Nand2Tetris Part II (7–12)
- [ ] CS:APP Ch.1–6 + Data Lab, Bomb Lab, Attack Lab
- [ ] CS:APP Cache Lab, Shell Lab, Malloc Lab
- [ ] (opt) Berkeley 61C / MIT 6.004

**Stage 5 — Operating Systems**
- [ ] OSTEP read + homework simulators
- [ ] ostep-projects: shell, memory allocator, MapReduce
- [ ] xv6 labs: syscalls, page tables, traps, CoW, locks, file system, net
- [ ] (opt-adv) Pintos

**Stage 6 — Networking**
- [ ] Kurose/Ross read + Wireshark labs
- [ ] CS144 checkpoints 0–7 (full TCP/IP stack)

**Stage 7 — Databases**
- [ ] CMU 15-445 lectures
- [ ] BusTub Projects #0–#4
- [ ] (opt-adv) Red Book + CS186

**Stage 8 — Theory of Computation**
- [ ] 18.404J lectures + problem sets
- [ ] Midterm ≥70%, final ≥70%

**Stage 9 — Compilers**
- [ ] Crafting Interpreters: jlox (complete)
- [ ] Crafting Interpreters: clox (complete)
- [ ] (opt) Aiken lectures + COOL compiler

**Stage 10 — Software Engineering**
- [ ] UBC CPSC 310 materials + full project
- [ ] (opt) Software Testing / Debugging playlists

**Stage 11 — Distributed Systems**
- [ ] DDIA read
- [ ] 6.5840 Lab 1 (MapReduce)
- [ ] 6.5840 Lab 3 (Raft) — passes 100× runs
- [ ] 6.5840 Labs 4–5 (fault-tolerant + sharded KV)

**Stage 12 — Security**
- [ ] 6.858 lectures + notes + exams
- [ ] 6.858 labs (buffer overflow/ROP → web defenses)
- [ ] CS:APP Attack Lab
- [ ] (opt) UMD Software Security / Stanford CS155

**Stage 13 — Electives & Capstone**
- [ ] Chosen systems/security electives
- [ ] Original capstone project shipped + documented

---

## Recommendations (staged, concrete, with thresholds)

1. **Start now with Stage 0B (Missing Semester, ~2 weeks) in parallel with reviewing SICP Ch.2–3.** This gives immediate sysadmin-relevant wins while you re-limber your programming. *Threshold to move on:* you can script a non-trivial shell task and use git/vim comfortably, and you've completed SICP Ch.2–3 exercises.
2. **Do Stage 2A (Discrete Math) and Stage 3 (Algorithms) partly in parallel**, exactly as OSSU suggests running math alongside core courses. Math first-mover gives you proof fluency; algorithms gives math motivation. *Threshold:* ≥70% on the 6.042 final AND all core algs4 assignments passing the autograder before starting systems.
3. **Treat Stages 4B→5→6 (CS:APP → OS → Networking) as the non-negotiable systems core** and budget the most time here — this is where your OSCP-track payoff is highest. *Threshold to advance each:* main lab/project completed without a walkthrough (Attack Lab defused; an xv6 feature added; CS144 stack talking to a real server).
4. **Insert Stage 12 (Security) immediately after the systems core**, not at the very end, so it reinforces CS:APP/OS/networking while fresh and dovetails with your Security+/eJPT study. Run your certifications (RHCSA→OSCP) *in parallel* as applied practice — they complement, not replace, these foundations.
5. **Defer Theory (8), Compilers (9), SWE (10), and electives (13)** to after the systems core unless motivation flags — they're intellectually essential but less time-sensitive to your career direction. *Change this ordering if* you discover a love for languages/theory, in which case pull Stage 9 earlier (it only needs Stages 1, 3, 4B).
6. **Benchmarks that change the plan:** if you're consistently exceeding 20 h/week and passing gates on first attempt, pull the 25 h/week timeline and add security electives (CS155 projects). If you're falling behind or a stage's project defeats you repeatedly, *slow down* — re-do the prerequisite labs rather than pushing forward; the gates exist precisely to prevent brittle knowledge.

---

## Caveats
- **Link durability:** All primary links were verified live as of August 31, 2026, but university course pages roll over yearly (e.g., MIT 6.1810 and CMU 15-445 publish new "fallXXXX"/year URLs each term; MIT 6.858 is now numbered 6.5660). If a dated URL 404s, increment the year or use the course root (pdos.csail.mit.edu/6.1810, 15445.courses.cs.cmu.edu, css.csail.mit.edu). The **textbooks, OCW archives, Nand2Tetris, OSTEP, algs4, and Crafting Interpreters are permanently hosted** and stable.
- **Coursera dependency:** OSSU lost free audit access to its Coursera courses in July 2025 (Coursera replaced "audit" with a first-module-only "preview" model, announced by CMO Tim Hannan on Aug 8, 2025); I routed around this. The Princeton Algorithms videos and Stanford Compilers (edX) remain free to audit *for now* but are used only as optional companions to permanently-free primaries, so the curriculum survives even if they close.
- **Academic-integrity note:** Student solution repos (BusTub, xv6, CS144, 6.5840) exist publicly, but course staff explicitly request you not copy or re-post solutions. [Mit](https://css.csail.mit.edu/6.5660/2026/general.html) Use them only when truly stuck; the learning is in the struggle.
- **Paid items:** Only DDIA and Sipser's textbook are genuinely worth buying; everything else is free. Do not pay for certificates — they carry no weight for self-study and (per Princeton/OSSU policy) many of these courses issue none anyway.
- **This is a CS degree, not a security course:** the security and systems emphasis is calibrated to your goals without narrowing the program — you still get full theory, algorithms, PL, compilers, and software engineering. Your certification path (RHCSA→OSCP) runs *in parallel* and is not a substitute for these foundations.