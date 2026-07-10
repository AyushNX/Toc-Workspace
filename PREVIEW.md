# 🌌 Latest Machine: DFA: Starts with 'x'
**Machine Type:** DFA
**Source:** `automata/fa/dfa_starts_a.json`

### 📋 Transition Table
| State | x | y |
| :--- | :---: | :---: |
| **q0** (Start) | q1 | q2 |
| **q1** (Final) | q1 | q1 |
| **q2** | q2 | q2 |

### 🎨 Visual Logic Diagram
```text
   [q0]      -- x -->     (q1*)    
   [q0]      -- y -->     [q2]     
   (q1*)     -- x -->     (q1*)    
   (q1*)     -- y -->     (q1*)    
   [q2]      -- x -->     [q2]     
   [q2]      -- y -->     [q2]
```
Generated automatically by Toc-Suite Visualizer Engine.
