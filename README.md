# Alley Cats and Boxes
A free textbook on allegories, category theory, and modal logic.

## Instructions
### Document
1. Edit document (including `\documentclass`, `\begin{document}`, and `\end{document}` in `files/XXXX.tex`
2. From `crucible`, execute `./mkPaper XXXX`. Run with `-v` flag for verbose. (TODO: fix Makefile so that the `-b` flag compiles with bibtex). If running without the `-v` flag, the output should look something like:
```
Compiling XXXX.pdf..........
```
new `.`'s should be continually printed - if the printing halts for more than a few seconds, this likely indicates an error. The compilation should then be terminated, and rerun with the `-v` flag.

3. If the compilation was successful, check `outbox` for `XXXX.pdf`

## Tentative List of Topics
- Expressions, Sets, Functions, and Relations
- Functions versus Relations
- Partially-Ordered Sets
- Comparing and Composing Relations
- Transposition and Inverse
- Equivalence Relations and Quotients
- Kripke Semantics for Basic Modal Logic
- Bisimulations
- Propositional Dynamic Logic
- Modal Logic of Partial Functions
- Topological Modal Logic
- Kripke Frames and Definability
- First-Order Modal Logic
- Kripke Semantics for Intuitionistic Logic
- Modular Lattices
- Allegories
- Back-and-Forth Classes
- Regular Categories and Allegories
- Tabulation, Division, and Distribution
- Power and Quotient Allegories
- Syntactic Allegories
- Enrichment
- Bicategories of Relations
- Monoidal Categories
- The Allegory of Categories
- Allegories in Homotopy Type Theory
- Dynamic Topological Logic
- Program Construction and Refined Frame Theory
- Topological First-Order Modal Logic
- IPL and STLC
- Regular Logic
- Kripke-Joyal Semantics
- Hyperdoctrines
- Reflective Subcategories and Modalities
- (Co)monads and Modality
- Modal Type Theory
