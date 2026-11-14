# 💻 Introduction to Programming & How Code Executes

> What a program is, what the machine running it looks like, and how human-readable code relates to what the CPU actually does.

---

## 📑 Table of Contents

1. [What Is Programming?](#1-what-is-programming)
2. [The Machine You're Talking To](#2-the-machine-youre-talking-to)
3. [Levels of Languages](#3-levels-of-languages)

---

## 1. What Is Programming?

**Programming** is writing precise instructions that a computer can carry out to solve a problem.

A computer has no common sense. It does *exactly* what it's told, in exactly the order it's told, and nothing more.

### 🫖 Instructions for a person vs. a computer

| 🧑 To a person | 🤖 To a computer |
|:---:|:---|
| | **1️⃣** Fill kettle with 300 ml water |
| | **2️⃣** Switch kettle on |
| | **3️⃣** Wait until water reaches 100 °C |
| ***"Make me some tea."*** | **4️⃣** Put 1 tea bag in the cup |
| | **5️⃣** Pour the water into the cup |
| | **6️⃣** Wait 180 seconds |
| | **7️⃣** Remove the tea bag |
| *They fill in the rest from context* | *Every step must be spelled out* |

---

### 🧩 Anatomy of a program

Every program, from a calculator to an operating system, combines three ingredients:

| 🟦 **DATA** | 🟩 **INSTRUCTIONS** | 🟧 **CONTROL FLOW** |
|:---:|:---:|:---:|
| *what we work on* | *what we do to it* | *in what order* |
| `42` | `add` | one after another |
| `"Alice"` | `compare` | if / else |
| `True` | `store` | repeat (loops) |
| `[3, 1, 2]` | `print` | call a function |

---

### 🧱 The core building blocks

| Concept       | Meaning                                    | Python example                 |
|---------------|--------------------------------------------|--------------------------------|
| Values / data | Numbers, text, true/false, collections     | `42`, `"hi"`, `True`, `[1,2]`  |
| Variables     | Names bound to values                      | `total = 0`                    |
| Operations    | Arithmetic, comparison, logic              | `a + b`, `x > 5`, `p and q`    |
| Sequence      | Do this, then that                         | one line after another         |
| Selection     | Choose a path                              | `if / elif / else`             |
| Iteration     | Repeat                                     | `for`, `while`                 |
| Abstraction   | Package logic under a name                 | `def area(r): ...`             |
| I/O           | Talk to the outside world                  | `input()`, `print()`, files    |

---

### 🏷️ Variables are labels on memory boxes

A useful mental picture: memory is a long row of numbered boxes, and a variable is a **label** stuck on one of them.

```python
age   = 25
name  = "Ravi"
price = 9.99
```

| | 📦 Box 1000 | 📦 Box 1001 | 📦 Box 1002 | 📦 Box 1003 | 📦 Box 1004 |
|---|:---:|:---:|:---:|:---:|:---:|
| **Value stored** | `25` | `"Ravi"` | `9.99` | *empty* | *empty* |
| **Label (name)** | 🏷️ **age** | 🏷️ **name** | 🏷️ **price** | | |

> 💡 Python's real model is a bit richer (names *refer to objects*), but this is the right first picture.

---

### 🧠 Algorithm vs code

An **algorithm** is the idea; **code** is that idea written in a particular language.

| Algorithm (plain English)   | Python                     | C                                  |
|-----------------------------|----------------------------|------------------------------------|
| Start a total at 0          | `total = 0`                | `int total = 0;`                   |
| For each number from 1 to 5 | `for i in range(1, 6):`    | `for (int i = 1; i <= 5; i++) {`   |
| … add it to the total       | `    total += i`           | `    total += i; }`                |
| Show the total              | `print(total)`             | `printf("%d\n", total);`           |

Both print `15`. Different syntax, identical algorithm.

---

## 2. The Machine You're Talking To

### 🖥️ What's inside a computer

| | Component | What it does |
|:---:|---|---|
| 🟪 | **CPU · Control Unit** | Reads each instruction and directs the rest of the CPU |
| 🟥 | **CPU · ALU** (Arithmetic Logic Unit) | Does the actual work: `+ − × ÷ < > == AND OR NOT` |
| 🟦 | **CPU · Registers** | A few tiny, ultra-fast slots holding values in use *right now*. Includes the **PC** (Program Counter): the address of the next instruction |
| 🔷 | **CPU · Cache** (L1 / L2 / L3) | Small, fast copies of recently used data |
| 🟩 | **RAM** | Main memory: holds running programs' code and data. Cleared when power is off |
| 🟧 | **SSD / Disk** | Keeps files permanently |
| ⬜ | **I/O devices** | Keyboard, mouse, screen, network: talking to the outside world |

### 👨‍🍳 The kitchen analogy

| Part | Kitchen equivalent |
|---|---|
| 🟪🟥 **CPU** | 👨‍🍳 The chef |
| 🟦 **Registers** | 🥕 Ingredients in the chef's hands |
| 🔷 **Cache** | 🍽️ The countertop |
| 🟩 **RAM** | 🧊 The fridge |
| 🟧 **SSD / Disk** | 🏪 The supermarket |
| ⬜ **I/O devices** | 🚪 The restaurant's door and waiters |

---

### 🔢 The CPU only understands machine code

The CPU doesn't understand Python, C, or English. It understands only **machine code**: small binary instructions defined by its **Instruction Set Architecture (ISA)**, for example **x86-64** (most PCs) or **ARM64** (phones, Apple Silicon).

Each instruction does something tiny:

| Instruction type | What it does                          | Example (assembly) |
|------------------|---------------------------------------|--------------------|
| 📥 Load          | Copy a value from RAM into a register | `mov eax, [x]`     |
| ➕ Arithmetic    | Compute using registers               | `add eax, 5`       |
| 📤 Store         | Copy a register back into RAM         | `mov [x], eax`     |
| ⚖️ Compare       | Check a condition                     | `cmp eax, 10`      |
| 🔀 Jump          | Continue from a different instruction | `jl loop_start`    |

---

### 🔬 Watching the CPU run `x = x + 5`

One line of Python becomes **three** machine instructions. `x` lives at memory address `2000` and starts at `10`.
🟨 marks the value that changed in each step.

| | ⚪ Before | 1️⃣ LOAD | 2️⃣ ADD | 3️⃣ STORE |
|---|:---:|:---:|:---:|:---:|
| **Instruction** | — | `mov eax, [2000]` | `add eax, 5` | `mov [2000], eax` |
| **Register EAX** | `?` | 🟨 **`10`** | 🟨 **`15`** | `15` |
| **Register PC** | `400` | `403` | `406` | `409` |
| **RAM [2000]** (this is `x`) | `10` | `10` | `10` | 🟨 **`15`** |
| **What happened** | *x is 10 in memory* | *x copied into EAX* | *ALU adds 5* | *result saved to x* |

Notice the **PC** changing every step: it always holds the address of the *next* instruction. Real programs run **billions** of these per second.

---

### ⚡ The memory hierarchy

The closer data is to the CPU, the faster it is to reach, but the smaller and more expensive that storage is.

| Level | Size | Access time | Speed |
|---|:---:|:---:|---|
| 🟦 **Registers** | bytes | < 1 ns | 🟢🟢🟢🟢🟢🟢 |
| 🟦 **L1 cache** | ~64 KB | ~1 ns | 🟢🟢🟢🟢🟢 |
| 🔷 **L2 cache** | ~1 MB | ~4 ns | 🟢🟢🟢🟢 |
| 🔷 **L3 cache** | ~32 MB | ~15 ns | 🟢🟢🟢 |
| 🟩 **RAM** | GBs | ~100 ns | 🟡🟡 |
| 🟧 **SSD** | TBs | ~100,000 ns | 🔴 |

---

### ⏱️ If one CPU cycle took 1 second…

Those numbers are hard to feel, so scale them up. How long would the CPU wait for data? *(bars on a log scale)*

| Where the data is | Wait time | |
|---|:---:|---|
| Register | **1 second** | `█` |
| L1 cache | **3 seconds** | `███` |
| L2 cache | **14 seconds** | `█████` |
| L3 cache | **1 minute** | `███████` |
| RAM | **5 minutes** | `█████████` |
| SSD | **4 days** | `██████████████████` |
| Network | **years** | `████████████████████████████` |

This is why two programs doing the "same" work can differ wildly in speed: one keeps its data near the CPU, the other keeps fetching from far away.

---

## 3. Levels of Languages

Programming languages sit on a ladder. Higher rungs are easier for people; lower rungs are closer to what the CPU actually runs.

### 🪜 The ladder of programming languages

| Rung | Level | Languages | Sample code | Character |
|:---:|---|---|---|---|
| 🟩 | **High-level** | Python · JavaScript · Java · C# · Ruby | `total = price * qty` | Readable, portable, memory managed for you |
| 🟦 | **Mid-level** | C · C++ · Rust · Go | `int total = price * qty;` | Fast, more control, more responsibility |
| 🟪 | **Assembly** | One version per CPU family | `mov eax,[price]` `imul eax,[qty]` | One line ≈ one CPU instruction |
| 🟥 | **Machine code** | Raw bytes | `8B 05 1C 00 00 00 0F AF 05 …` | The only thing the CPU executes |

> 🟩 top = **easiest for humans** · 🟥 bottom = **closest to the machine**

---

### 🔁 The same task at every level

**Task:** add 5 to `x`.

| Level         | Code                                             | Who reads it comfortably |
|---------------|--------------------------------------------------|--------------------------|
| 🟩 Python     | `x = x + 5`                                      | Almost anyone            |
| 🟦 C          | `x = x + 5;` (with `int x;` declared earlier)    | Programmers              |
| 🟪 Assembly   | `mov eax,[x]` · `add eax,5` · `mov [x],eax`      | Systems specialists      |
| 🟥 Machine code | `8B 05 .. .. .. .. 83 C0 05 89 05 .. .. .. ..` | The CPU                  |

---

### 🙈 What each level hides from you

Every level is an **abstraction**: it hides details of the level below so you can think about the problem instead of the machine.

| You write in… | You **don't** have to think about… | You **do** still think about… |
|---|---|---|
| 🟩 Python | Registers, memory addresses, freeing memory, CPU type, integer size | Logic, data structures, algorithms |
| 🟦 C | Registers, CPU instructions | Memory allocation/freeing, types, pointers |
| 🟪 Assembly | Binary encoding of instructions | Registers, addresses, every single step |
| 🟥 Machine code | Nothing; this is the bottom | Everything |

---

### ⚖️ The trade-off

| Language | Productivity & safety | Control & raw speed |
|---|---|---|
| 🟩 Python | 🟩🟩🟩🟩🟩 | 🟦⬜⬜⬜⬜ |
| ☕ Java | 🟩🟩🟩🟩⬜ | 🟦🟦🟦⬜⬜ |
| 🟦 C / Rust | 🟩🟩⬜⬜⬜ | 🟦🟦🟦🟦⬜ |
| 🟪 Assembly | 🟩⬜⬜⬜⬜ | 🟦🟦🟦🟦🟦 |

*(illustrative, not measurements)*

- **High-level:** less code, fewer crash-type bugs, runs on any OS/CPU with the right interpreter, but less control over performance.
- **Low-level:** maximum speed and control, but more code, more ways to make dangerous mistakes, and tied to specific hardware.

---

### 🎯 Why this matters for you

Whatever language you write in, the CPU **only ever runs machine code**. Every high-level line you write must eventually be translated down this ladder by a **compiler**, an **interpreter**, or a combination of both. Knowing the ladder exists is the key to understanding performance, errors, and what a language is really doing on your behalf.

---

## ✅ Quick Summary

| # | Idea |
|:---:|---|
| 1 | A program is **data + instructions + control flow**, expressing an algorithm. |
| 2 | Computers follow instructions **literally**; every step must be explicit. |
| 3 | The CPU executes tiny **machine-code** instructions using **registers**, guided by the **program counter**. |
| 4 | Data **closer to the CPU** (registers, cache) is dramatically faster to reach than RAM or disk. |
| 5 | Languages form a **ladder of abstraction**, from human-friendly Python down to raw machine code. |
| 6 | Higher levels trade **control and raw speed** for **productivity, safety and portability**. |
