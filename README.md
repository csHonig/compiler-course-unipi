# Languages, Compilers and Interpreters (Lab) - 3 CFU
**Teacher**: Letterio Galletta

**Contact**: *name.surname*(at)imtlucca.it

**Office hours**: contact me by e-mail

**Page of theory part of the course held by Prof. Roberta Gori**: http://pages.di.unipi.it/gori/Linguaggi-Compilatori2020/

## Course description
The course will present tools and techniques used in the implementation of programming languages. 
In particular, the course will guide students in the implementation of a compiler for a small 
subset of language C, called *MicroC*, and of an interpreter of a small functional language, called *FUN*. During the lectures students will work on programming assignments covering different aspects of language implementation. The programming language adopted for the exercises and the project is OCaml. At the end of the course students who completed all the assignments will have developed an simple interpreter and a compiler. 


## Learning objectives

After completing the course, students will have  
* Known the basics of the functional programming language OCaml;
* Implemented parsers using state-of-the-art parsers generators; 
* Designed and implemented semantic analyses for a functional and an imperative languages;
* Used the LLVM toolchain for generating and optimize code; 
* Had some fun along the way! :smile: 

## Program of the course

* Introduction to functional programming and to OCaml language;
* Lexing and parsing using `ocamllex` and `menhir`;
* Semantic analysis implementation: type checking, scope management, control-flow analysis;
* Introduction to LLVM infrastructure and LLVM intermediate language;
* Code generation.

## Lectures
This table specifies the lecture schedule with topics and materials.

See [these instructions](instructions.md) to set up your programming environment. 

| Date  | Topics | Slides | Examples | Assignments| 
| ------|------- | -------|----------|------------|
| 9/25  | Intro to OCaml: functions, string</br> REPL, compilation |  [Intro to the lab](ocaml-material/slides/lab-presentation.pdf)</br>[OCaml Tutorial](http://www.cs.columbia.edu/~sedwards/classes/2018/4115-fall/ocaml.pdf)</br>[OCaml Tools](ocaml-material/slides/ocaml-tools.pdf) | [ocaml-basics.ml](ocaml-material/code/ocaml-basics.ml)   | [Exercises 1](ocaml-material/exercises/exercises-1.md)       |
| 10/2 | Intro to OCaml: lists, tuples, records,</br> algebraic data types, pattern matching     | [OCaml Tutorial](http://www.cs.columbia.edu/~sedwards/classes/2018/4115-fall/ocaml.pdf)    | [ocaml-basics.ml](ocaml-material/code/ocaml-basics.ml)       | [Exercises 2](ocaml-material/exercises/exercises-2.md)
| 10/9 | - Intro to OCaml: module, imperative features.</br> - The interpreter of *FUN* | [OCaml Tutorial](http://www.cs.columbia.edu/~sedwards/classes/2018/4115-fall/ocaml.pdf)</br> [The interpreter of FUN](ocaml-material/slides/fun-interpreter.pdf) | [vector.mli](ocaml-material/code/vector.mli)</br>[vector.ml](ocaml-material/code/vector.ml)</br> [fun.ml](ocaml-material/code/fun.ml) | [Exercises 3](ocaml-material/exercises/exercises-3.md) |         
| 10/15 | - Discussion on previous programming assignments </br> - Introduction to lexing with `ocamllex` | [Lexing with ocamllex](frontend-material/slides/lexical-analysis.pdf) | - | - |
| 10/23 | Tutorial on `ocamllex` | [Lexing with ocamllex](frontend-material/slides/lexical-analysis.pdf) | [cwd.mll](frontend-material/code/cwd.mll) </br> [count.mll](frontend-material/code/count.mll) </br> [count_fun.mll](frontend-material/code/count_fun.mll) </br> [stokens.mll](frontend-material/code/stokens.mll) </br> [stokens_pos.mll](frontend-material/code/stokens_pos.mll) </br> [comments.mll](frontend-material/code/comments.mll) </br> [csv_simple.mll](frontend-material/code/csv_simple.mll) </br> [toy_lang.mll](frontend-material/code/toy_lang.mll) | [Exercises 4](frontend-material/exercises/exercises-lexing.md) 
| 10/30 | Tutorial on `menhir` | [Syntactic analysis with `menhir`](frontend-material/slides/syntactic-analysis.pdf) | [calc](frontend-material/code/calc) </br> [calc-alias](https://gitlab.inria.fr/fpottier/menhir/-/tree/master/demos/calc-alias) </br> [calc-ast](frontend-material/code/calc-ast) </br> [calc-ast-pos](frontend-material/code/calc-ast-pos) </br> [calc-two](https://gitlab.inria.fr/fpottier/menhir/-/tree/master/demos/calc-two) </br> [calc-multi](frontend-material/code/calc-multi) </br> [calc-incremental](https://gitlab.inria.fr/fpottier/menhir/-/tree/master/demos/calc-incremental) </br> [json](frontend-material/code/json)  | [Exercise 5](frontend-material/exercises/exercises-parsing.md)|  
| 11/06 | - Parsing with `menhir`</br> - Discussion on previous programming assignments</br> - Presentation of MicroC project | [Syntactic analysis with `menhir`](frontend-material/slides/syntactic-analysis.pdf)</br> [Introduction to MicroC](frontend-material/slides/intro-microc.pdf) | [FUN parser](frontend-material/code/fun-parser) solutions of exercises 4.5 & 5.4</br>  [IoT-Lysa parser](https://bitbucket.org/lillo/iotlysa/src/master/) for an example of parser using [FParsec](https://www.quanttec.com/fparsec/) | [MicroC parser](microc/microc-parsing/) |
| 11/13 | Type analysis | [Type analysis](semantic-analysis-material/slides/type-analysis.pdf) | [FUN type checker](semantic-analysis-material/code/fun-types) </br>  [Incremental MinCaml](https://github.com/matteobusi/incremental-mincaml) </br> [CADL](https://github.com/freek9807/CADL) | [Exercises 6](semantic-analysis-material/exercises/exercises-types.md) |
| 11/20 | Control-flow analysis | [CFA analysis](semantic-analysis-material/slides/cfa-analysis.pdf) | [FUN CFA analysis](semantic-analysis-material/code/fun-cfa) |  [Exercises 7](semantic-analysis-material/exercises/exercises-cfa.md) |
| 11/27 | Semantic analysis for MicroC |[Semantic analysis for MicroC](semantic-analysis-material/slides/microc-semantic-analysis.pdf)  | - |  [MicroC analyzer](microc/microc-semantic-analysis) |
| 12/04 | Introduction to LLVM | [LLVM Infrastructure](codegen-material/slides/intro-llvm.pdf) | [add.c](codegen-material/code/add.c) </br> [add.ll](codegen-material/code/add.ll) </br> [main.c](codegen-material/code/main.c) </br> [fun-decl.ll](codegen-material/code/fun-decl.ll) </br> [global-local.ll](codegen-material/code/global-local.ll) </br> [local-vars.ll](codegen-material/code/local-vars.ll) </br> [arithmetic.ll](codegen-material/code/arithmetic.ll) </br> [conditional.ll](codegen-material/code/conditional.ll) </br> [phi-instruction.ll](codegen-material/code/phi-instruction.ll) </br> [call.ll](codegen-material/code/call.ll) </br> [array-struct.ll](codegen-material/code/array-struct.ll) </br> [gep.c](codegen-material/code/gep.c) </br> [gep.ll](codegen-material/code/gep.ll) </br> [deps.ll](codegen-material/code/deps.ll)| [Exercises 8](codegen-material/exercises/exercises-llvm-ir.md) |
| 12/11 | ... | ... | ... | ... |

## Final project
The final project of the course consists in implementing a compiler for MicroC. 
See [here](microc/microc-project.md) for the instructions.

## Material

### Software
Programming assignments will use the following pieces of sotfware:
* [OCaml](https://ocaml.org/) - try to install the latest version. All the code shown during the course is tested with **the version 4.10.1**. 
* [Opam](https://opam.ocaml.org/) - OCaml package manager.
* [Menhir](http://gallium.inria.fr/~fpottier/menhir/) - a LR(1) parser generator for the OCaml programming language.
* [Clang](https://clang.llvm.org/) - a compiler for C programs.
* [LLVM](http://llvm.org/) - The LLVM compiler infrastructure. All the code shown during the course is tested with **the version 10.0**.
* [rlwrap](https://github.com/hanslub42/rlwrap) - a small utility to improve the editing capability of the OCaml REPL.

### Online Resources
* OCaml [user manual](http://caml.inria.fr/pub/docs/manual-ocaml/index.html)
* [OCaml Discourse](https://discuss.ocaml.org/) community
* [OCamlverse](https://ocamlverse.github.io/)
* The book [Functional Programming in OCaml](https://www.cs.cornell.edu/courses/cs3110/2019sp/textbook/)
* The book [Real World OCaml](https://dev.realworldocaml.org/)
* The book [OCaml Scientific Computing](https://ocaml.xyz/book/)
* [OCaml MOOC](https://www.youtube.com/playlist?list=PLALAWXhLW3667sFw1Lfo3LmHC7CFib2EN)
* An [interactive tutorial](https://learngitbranching.js.org/) on using `git`
* [LLVM Language Reference Manual](http://llvm.org/docs/LangRef.html)
* [The Programming Languages Zoo - A potpourri of programming languages](http://plzoo.andrej.com/)
* [Compiler Explorer](https://godbolt.org/)
* [Resources for Amateur Compiler Writers](https://c9x.me/compile/bib/)

### Further resources

[Here](references.md) you find a list of further references that complete and deepen the various topics covered during the course.
A rich collection of articles related to the course can be found in [Prof. Matt Might's blog](http://matt.might.net/articles/).
