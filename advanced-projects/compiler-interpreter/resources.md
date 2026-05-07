# Resources for Compiler/Interpreter

## 📺 Video Tutorials

### Foundational (START HERE)
- [Crafting Interpreters (Full Free Course)](https://craftinginterpreters.com/) - Complete video + book - **MUST WATCH**
- [Build an Interpreter in Go (Full Series)](https://www.youtube.com/watch?v=cesSRfXqS1Q) - Thorsten Ball series (4+ hours)
- [Building a Compiler from Scratch in Rust](https://www.youtube.com/watch?v=1GLkQKSTXfs) - Backend University complete playlist (2025/2026 edition)

### Compiler Theory & Architecture
- [MIT 6.035 Computer Language Engineering](https://ocw.mit.edu/courses/6-035-computer-language-engineering-spring-2010/) - MIT OpenCourseWare - **EXCELLENT**
- [LLVM & Cranelift Tutorial](https://www.youtube.com/watch?v=m8G_S5LwlP4) - LLVM backends and modern code generation (2026 update)
- [Parser Combinators in Rust](https://www.youtube.com/watch?v=dO6cKUc1OFg) - Functional parsing approach
- [Compiler Design with ANTLR](https://www.youtube.com/watch?v=vFr5TDvI1sU) - Parser generator approach

### Advanced Topics
- [AST Interpretation & Compilation](https://www.youtube.com/watch?v=3LARDqqKXEU) - Tree-walking vs bytecode
- [Virtual Machine Design](https://www.youtube.com/watch?v=OjaAToVkoTw) - Stack-based VMs
- [Type Systems](https://www.youtube.com/watch?v=E8I19uA-wGY) - Type checking and inference
- [Garbage Collection](https://www.youtube.com/watch?v=xCV3pMh0qVk) - Memory management algorithms

## 📚 Written Tutorials & Books

### Free Online Resources
- **[Crafting Interpreters](https://craftinginterpreters.com/)** - Complete FREE book by Robert Nystrom - **START HERE**
  - Part 1: Build a tree-walking interpreter (Jlox in Java)
  - Part 2: Build a bytecode interpreter (Clox in C)
  - Interactive chapter walkthroughs with visualizations
  
- **[Writing an Interpreter in Go](https://interpreterbook.com/)** - Thorsten Ball
  - Complete Monkey language implementation
  - Step-by-step development
  - Available online (some chapters free)

### Classic Textbooks
- **[Compilers: Principles, Techniques, and Tools](https://en.wikipedia.org/wiki/Compilers:_Principles,_Techniques,_and_Tools)** (Dragon Book)
  - 2nd Edition by Aho, Lam, Sethi, Ullman (2006)
  - THE classic compiler textbook
  - Dense but comprehensive
  
- **[Engineering a Compiler](https://www.elsevier.com/books/engineering-a-compiler/cooper/978-0-12-415950-1)** - Cooper & Torczon
  - More practical than Dragon Book
  - Focuses on real-world implementation
  - 2nd Edition (2011)

### Academic Papers (Deep Dives)
- **[Recursive Descent Parsing](https://en.wikipedia.org/wiki/Recursive_descent_parser)** - Foundational technique
- **[LL Parsing](https://en.wikipedia.org/wiki/LL_parser)** - Top-down parsing algorithm
- **[LR Parsing](https://en.wikipedia.org/wiki/LR_parser)** - Bottom-up parsing (used in YACC)
- **[The Essence of Compilation](https://www.cs.cmu.edu/~fp/courses/15316-s22/lectures/) - CMU course**

### Implementation Guides
- **[Build Your Own Programming Language](https://www.freecodecamp.org/news/how-to-build-a-programming-language/)** - freeCodeCamp article
- **[Let's Build A Simple Interpreter](https://ruslanspivak.com/lsbasi-part1/)** - Ruslan Spivak series
- **[Writing an Interpreter with Rust](https://blog.mbedded.ninja/programming/languages/rust/writing-an-interpreter-in-rust/)** - Detailed Rust guide

## 🔧 Tools & Libraries

### Parser Generators (Reduce Manual Work)
- **[ANTLR (Another Tool for Language Recognition)](https://www.antlr.org/)** - Modern, generates parsers in multiple languages - **RECOMMENDED FOR BEGINNERS**
  - Web-based IDE: https://www.antlr.org/tools/ANTLRWorks
  - Generates lexer + parser automatically from grammar
  - Supports many target languages (Java, Python, JavaScript, Go, C++)
  - Documentation: https://github.com/antlr/antlr4/blob/master/doc/index.md
  
- **[Flex & Bison](https://www.gnu.org/software/flex/manual/)** - Classic Unix tools (C/C++ focused)
  - Flex: Lexical scanner generator
  - Bison: Parser generator (YACC-compatible)
  - Used in GCC and many production compilers
  - Learning curve: steep but powerful
  
- **[Lex & YACC](https://en.wikipedia.org/wiki/Lex_and_yacc)** - Original Unix tools
  - Foundation for modern parser generators
  - Historical interest, not recommended for new projects

### Parsing Libraries (Programmatic Approach)
- **[Pest](https://pest.rs/)** - Rust parser combinator library
  - PEG (Parsing Expression Grammar) based
  - Very beginner-friendly
  - Great error messages
  - GitHub: https://github.com/pest-parser/pest
  
- **[Nom](https://nom-rs.github.io/)** - Rust parser combinator library
  - Low-level, very fast
  - Bit-level parsing support
  - Production-used in many Rust projects
  
- **[Lark](https://lark-parser.readthedocs.io/)** - Python parsing library
  - Easy EBNF grammar syntax
  - Supports Earley, LALR, and CYK parsers
  - Great for Python-based implementations
  
- **[ANTLR Runtime Libraries](https://www.antlr.org/download/)** - Runtime support for all target languages

### AST & Code Generation
- **[Tree-sitter](https://tree-sitter.github.io/tree-sitter/)** - Fast, incremental parser library
  - Used in Neovim editor
  - Supports 30+ languages
  - Efficient for real-time code analysis
  
- **[LLVM](https://llvm.org/)** - Compiler infrastructure framework
  - Generate native code from intermediate representation
  - Used by: Clang, Swift, Rust, Julia, etc.
  - C++ API for code generation
  - Learning: https://llvm.org/docs/tutorial/
  
- **[GraalVM](https://www.graalvm.org/)** - Universal VM for multiple languages
  - Build your language on top of JVM
  - High-performance JIT compilation
  - Polyglot interoperability

### Testing & Debugging
- **[QuickCheck](https://hackage.haskell.org/package/QuickCheck)** (Haskell) - Property-based testing
- **[Hypothesis](https://hypothesis.readthedocs.io/)** (Python) - Property-based testing
- **[Proptest](https://docs.rs/proptest/)** (Rust) - Property-based testing
- **[Golden Tests](https://bkahlert.medium.com/golden-testing-4cc9e6c1f5a9)** - Compare output against reference files

## 💻 GitHub Repositories (Study & Learn)

### Official References (Production Compilers)
- **[Rust Compiler](https://github.com/rust-lang/rust)** - Modern systems language compiler
  - 1M+ lines of Rust code
  - Most actively developed compiler
  - Reference for type systems and error handling
  
- **[Go Compiler](https://github.com/golang/go)** - Blazingly fast compiler
  - Written in Go (self-hosted)
  - Great example of practical compiler design
  - Code generation to machine code
  
- **[Clang/LLVM](https://github.com/llvm/llvm-project)** - C/C++/Objective-C compiler
  - Based on LLVM infrastructure
  - Industry standard
  - Excellent documentation
  
- **[V8 (JavaScript)](https://github.com/v8/v8)** - Chrome's JavaScript engine
  - JIT compilation to machine code
  - Hidden class optimization
  - Generational garbage collection

### Educational Implementations (Easy to Understand)
- **[Crafting Interpreters - Lox](https://github.com/craftinginterpreters/lox)** - Reference implementation
  - Tree-walking interpreter (Jlox)
  - Bytecode VM (Clox)
  - Both fully commented
  - Perfect for learning
  
- **[Writing an Interpreter in Go - Monkey](https://github.com/thorsten/interpreterbook)** - Thorsten Ball's Monkey language
  - Complete working compiler
  - ~2000 lines of Go
  - Great learning resource
  
- **[Simple Interpreter](https://github.com/davidcallanan/py-myopl-code)** - David Callanan Python implementation
  - YouTube tutorial series companion
  - Step-by-step, very clear
  
- **[Kaleidoscope (LLVM Tutorial)](https://llvm.org/docs/tutorial/)** - Official LLVM tutorial language
  - Learn to use LLVM
  - Go from syntax → LLVM IR → native code
  - Multiple languages (C++, OCaml, JavaScript)

### Modern Language Examples
- **[TypeScript Compiler](https://github.com/microsoft/TypeScript)** - JavaScript superset
  - Type checking without compilation
  - Great error messages
  - 100K+ lines of TypeScript
  
- **[Python CPython](https://github.com/python/cpython)** - Official Python implementation
  - Bytecode VM approach
  - Garbage collection
  - C extension system
  
- **[Julia](https://github.com/JuliaLang/julia)** - Scientific computing language
  - Multi-dispatch type system
  - LLVM-based JIT
  - High-performance compilation

### Parser Generator Examples
- **[ANTLR Examples](https://github.com/antlr/grammars-v4)** - 300+ grammar examples
  - JSON, Python, Java, SQL parsers, etc.
  - Ready-to-use grammars
  - Great for learning EBNF syntax

## 📖 Learning Resources (Deep Dives)

### Formal Language Theory
- **[Context-Free Grammars](https://en.wikipedia.org/wiki/Context-free_grammar)** - Theoretical foundation
- **[Backus-Naur Form (BNF)](https://en.wikipedia.org/wiki/Backus%E2%80%93Naur_form)** - Grammar notation
- **[Parsing Expression Grammars (PEG)](https://en.wikipedia.org/wiki/Parsing_expression_grammar)** - Modern grammar formalism
- **[Formal Languages Course](https://www.coursera.org/learn/formal-languages-automata)** - Coursera (free audit)

### Simple Recursive Descent Parser
```Python

class Parser:
    def __init__(self, tokens):
        self.tokens = tokens
        self.pos = 0
    
    def parse(self):
        return self.expression()
    
    def expression(self):
        left = self.term()
        
        while self.current_token().type in [TokenType.PLUS, TokenType.MINUS]:
            op = self.current_token()
            self.pos += 1
            right = self.term()
            left = BinOp(left, op, right)
        
        return left
    
    def term(self):
        left = self.factor()
        
        while self.current_token().type in [TokenType.MULT, TokenType.DIV]:
            op = self.current_token()
            self.pos += 1
            right = self.factor()
            left = BinOp(left, op, right)
        
        return left
    
    def factor(self):
        token = self.current_token()
        
        if token.type == TokenType.NUMBER:
            self.pos += 1
            return Num(token.value)
        elif token.type == TokenType.LPAREN:
            self.pos += 1
            expr = self.expression()
            self.pos += 1  # skip RPAREN
            return expr
    
    def current_token(self):
        return self.tokens[self.pos]

class Num:
    def __init__(self, value):
        self.value = value

class BinOp:
    def __init__(self, left, op, right):
        self.left = left
        self.op = op
        self.right = right
```