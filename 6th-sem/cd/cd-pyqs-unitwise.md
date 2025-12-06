# Compiler Design - Previous Years' Questions (Unit-wise)

This file contains previous years' questions from Compiler Design exams (2021-2024) organized by unit.

## UNIT 1: Introduction to Compilers

### Short Questions (2.5 Marks)

1. **Language Processor** (2023, 2024)
   - Explain Language Processors (2023)
   - Briefly explain Language Processor (2024)

2. **Applications of Compiler** (2022)
   - Write short notes on Applications of compiler

3. **Compiler Definition** (2021)
   - Write short notes on Compiler

4. **Compiler Construction Tools** (2022)
   - Write short notes on Compiler construction tools

5. **Input Buffering** (2022, 2024)
   - What is the role of input buffer in lexical analysis? (2022)
   - Explain Input Buffering (2024)

6. **Role of Lexical Analyzer** (2023)
   - Explain the Role of lexical analyzer

7. **Tokens, Patterns and Lexemes** (2021)
   - Differentiate between tokens, patterns and lexemes

8. **Regular Expression** (2021, 2022)
   - Explain the role of regular expression (2021)
   - Write short notes on Notations for regular expressions (2022)

### Long Questions (15 Marks)

1. **Phases of Compiler** (2021, 2022, 2023, 2024)
   - "Explain different phases of compiler." (2021)
   - "Describe the phases of compiler." (2022)
   - "What do you mean by Compiler? Explain various Phases of Compiler." (2023, 10 marks)
   - "Discuss the working of different phases of compiler in detail." (2024)

2. **Lexical Analysis**
   - "What is Lexical analysis?" (2022, 9 marks)
   - "Explain implementation of lexical analyzer." (2023, 5 marks)

3. **Finite Automata and Regular Expressions**
   - "What is Finite Automata? Convert NFA (a|b)* abb into equivalent DFA." (2021)
   - "Construct a Finite Automata equivalent to the regular expression: (a|b)* | (ab)*b | a*(bb)*" (2023, 10 marks)

4. **Compiler Construction Tools**
   - "Explain various compiler construction tools." (2023, 5 marks)
   - "Explain Compiler Construction Tools." (2024)

## UNIT 2: Syntax Analysis

### Short Questions (2.5 Marks)

1. **Ambiguous Grammar** (2021, 2022)
   - Write a short note on ambiguous grammar (2021)
   - Write short notes on Ambiguous grammar (2022)

2. **Predictive Parsing** (2024)
   - Briefly explain Predictive Parsing

3. **Recursive Descent Parser** (2023)
   - Explain Recursive Descent Parser

4. **Handle Pruning** (2023)
   - Explain Handle pruning

### Long Questions (15 Marks)

1. **Top-Down Parsing** (2022, 2023, 2024)
   - "Explain top-down parsing with a suitable example." (2022)
   - "What are the problems associated with Top Down Parsing?" (2023, 7.5 marks)
   - "Explain the top-down parsing with a suitable example." (2024)

2. **Context-Free Grammar (CFG)** (2021)
   - "What is CFG?" (7.5 marks)
   - "Explain how regular expressions are used for token specification." (7.5 marks)

3. **Parsing Techniques**
   - "Explain the parsing techniques with a hierarchical diagram." (2023, 7.5 marks)
   - "Perform shift-reduce parsing for string id1 + id2 + id3 for the grammar E → E + E | E * E | id." (2021)
   - "Explain operator precedence parsing in detail. Explain with the help of example." (2023)

4. **FIRST and FOLLOW Functions** (2022, 2023)
   - "Calculate the first and follow for the following grammar: E → E+E | E*E | (E) | id" (2022)
   - "Write Rules to construct FIRST Function and FOLLOW Function. Consider Grammar: E→E+T|T, T→T*F|F, F→(E)|id" (2023, 7.5 marks)

5. **LL(1) Grammar** (2024)
   - "To check whether the given grammar is LL(1) or not. 
     S → (L)
     S → a
     L → S L'
     L' → ε'
     L' → , S L" (2024)

## UNIT 3: Syntax-Directed Translation and LR Parsing

### Short Questions (2.5 Marks)

1. **Three Address Code** (2024)
   - Briefly explain Three address code

2. **Syntax Tree** (2024)
   - Briefly explain Syntax Tree

3. **Rules to Construct LR(0) Items** (2023)
   - Explain Rules to construct the LR(0) items

### Long Questions (15 Marks)

1. **Syntax-Directed Translation** (2021, 2024)
   - "Explain the concept of syntax directed translation scheme." (2021, 6 marks)
   - "What is Syntax directed Translation Scheme? Also explain the implementation of Syntax directed translation." (2024)

2. **Three Address Code, Quadruples, and Triples** (2021, 2023)
   - "Explain three address codes, quadruples and triples." (2021, 9 marks)
   - "Explain three address code, quadruples and triples." (2023, 5 marks)

3. **LR Parsing** (2021, 2022, 2023, 2024)
   - "Construct the SLR parsing table for the grammar: E → E + T | T, T → T * F | F, F → (E) | id" (2021)
   - "Explain the making of LR (0) parsing table for the following grammar: E → E*B | E+B | B, B → 0 | 1" (2022)
   - "Prepare a canonical parsing table for the given grammar: S→CC, C→cC/d" (2023, 10 marks)
   - "Construct SLR parsing table for the following grammar: R→R+a|b" (2023, 7.5 marks)
   - "Explain the following parsers in detail: LR parser and Canonical LR parser" (2024)

4. **Comparison of LR Parser Variants** (2022)
   - "How CLR parser differs from LALR parser? Please explain." (2022)

## UNIT 4: Code Generation and Optimization

### Short Questions (2.5 Marks)

1. **Machine Dependent Code** (2024)
   - Briefly explain Machine dependent code

2. **Hash Table** (2024)
   - Briefly explain Hash Table

3. **Forms of Object Code** (2023)
   - Explain Forms of objects code

4. **Register Allocation** (2021)
   - What is register allocation in code generation?

5. **Phrase Level Error Recovery** (2021)
   - What is phrase level error recovery?

6. **Benefits of Intermediate Code Generation** (2022)
   - Write short notes on Benefits of Intermediate code generation

7. **Code Generation** (2022)
   - Write short notes on Code generation

### Long Questions (15 Marks)

1. **Symbol Table** (2021, 2023, 2024)
   - "Explain the importance of symbol tables in compiler design." (2021, 8 marks)
   - "What is the use of symbol table? Explain the various data structures associated with symbol table." (2023, 8 marks)
   - "Write a short note on Symbol Table." (2024)

2. **Error Detection and Recovery** (2021, 2023, 2024)
   - "List the various errors recovered strategies." (2021, 7 marks)
   - "Explain the various types of errors generated during the various phases of the compiler. How do we recover from these errors?" (2023, 7 marks)
   - "Explain the various types of errors generated during the various phases of the compiler. How do we recover from these errors?" (2024)

3. **Code Generation** (2021, 2022)
   - "What is code generation? Explain the various strategies for code generation." (2021)
   - "Explain code generation in detail." (2022)

4. **Code Optimization** (2022, 2023, 2024)
   - "What are the various strategies for code optimization?" (2022)
   - "Various machine independent code optimization techniques." (2023, 7.5 marks)
   - "Write a short note on Code optimization." (2024)

5. **Register Allocation** (2023)
   - "Register allocation for temporary and user defined variables." (2023, 7.5 marks)
