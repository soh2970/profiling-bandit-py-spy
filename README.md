# profiling-bandit-py-spy
# Overview
This project analyzes the runtime performance of **Bandit**, an open-source Python Static Application Security Testing (SAST) tool, by profiling its execution with **py-spy** while scanning the Flask codebase.
The goal was to understand where Bandit spends the majority of its execution time and identify potential optimization opportunities within its static analysis pipeline.

# Technologies
- Python
- Bandit (PyCQA)
- py-spy
- Flask
- Abstract Syntax Trees (AST)
- Static Application Security Testing (SAST)

# Skills Demonstrated
- Security Tool Analysis
- Static Code Analysis
- Python Performance Profiling
- AST Analysis
- Open Source Development
- Performance Optimization
- Software Engineering

# Methodology
1. Installed and configured Bandit.
2. Cloned the Flask repository.
3. Executed Bandit recursively against the Flask source code.
4. Recorded execution using py-spy.
5. Generated a flame graph.
6. Identified runtime hotspots.
7. Evaluated opportunities for improving performance.

# Results

The profiling showed that Bandit's runtime is primarily dominated by:
- AST parsing
- Security rule execution
- Plugin traversal

Secondary overhead included:
- Module imports
- Configuration loading
- Plugin initialization

The flame graph suggests that repeated AST traversal across plugins is the largest contributor to execution time and may benefit from optimization through shared traversals or cached intermediate results.

# Sample Output
<img width="1200" height="1258" alt="bandit_flamegraph" src="https://github.com/user-attachments/assets/358437a6-52cc-4e22-b91b-6893293563ef" />
<?xml version="1.0" standalone="no"?><!DOCTYPE svg PUBLIC "-//W3C//DTD SVG 1.1//EN" "http://www.w3.org/Graphics/SVG/1.1/DTD/svg11.dtd"><svg version="1.1" width="1200" height="1258" onload="init(evt)" viewBox="0 0 1200 1258" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:fg="http://github.com/jonhoo/inferno"><!--Flame graph stack visualization. See https://github.com/brendangregg/FlameGraph for latest version, and http://www.brendangregg.com/flamegraphs.html for examples.--><!--NOTES: --><defs><linearGradient id="background" y1="0" y2="1" x1="0" x2="0"><stop stop-color="#eeeeee" offset="5%"/><stop stop-color="#eeeeb0" offset="95%"/></linearGradient></defs>

# Lessons Learned
This project provided practical experience with:
- profiling production security software
- understanding how SAST tools operate internally
- analyzing Python execution performance
- interpreting flame graphs
- identifying optimization opportunities in large codebases
