# tfy (Template For You) 🚀

![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)
![C++](https://img.shields.io/badge/Standard-C%2B%2B23-success)
![Platform](https://img.shields.io/badge/Platform-macOS%20%7C%20Linux-lightgrey)

A high-velocity, minimalist C++ testing pipeline tailored for competitive programming and local algorithmic execution. 

`tfy` removes the friction of manual compilation and output verification. It automatically compiles your code, runs it against sample cases, catches runtime errors, and provides a clear, color-coded diff of your output versus the expected result.

## ✨ Features

* **Instant Compilation Modes:** Seamlessly switch between highly optimized Release builds (`-O3`) and deep Debug builds.
* **Intelligent Output Diffing:** Compares your output against expected results line-by-line with clear visual indicators for mismatches.
* **Deep Memory Debugging:** Built-in AddressSanitizer (ASAN) support to instantly track down Segfaults, memory leaks, and out-of-bounds errors.
* **Safety Nets:** Automatic Time Limit Exceeded (TLE) enforcement and detailed crash tracebacks.
* **Zero Dependencies:** A pure bash script that relies only on native tools (`g++` or `clang++`). Fully optimized for both Linux and macOS environments.

---

## 📦 Install

```bash
git clone [https://github.com/YOUR_USERNAME/tfy-pipeline.git](https://github.com/YOUR_USERNAME/tfy-pipeline.git)
cd tfy-pipeline
chmod +x tfy
sudo mv tfy /usr/local/bin/
```

## 🚀 Usage

Make sure you created these files in same directory:
1. input.txt
2. expected.txt
3. main.cpp 

**Run normally (Release mode / -O3):**
```bash
tfy main.cpp
```

**Run with Memory Debugging (AddressSanitizer):**
```bash
tfy -d main.cpp
```

**Set custom Time Limit (e.g., 5 seconds):**
```bash
tfy -t 5 main.cpp
```

### NOTE:
If you want to set main.cpp as default
Change first line of tfy() function from

## ✨ Under the Hood
* **Release:** `-std=c++23 -O3`
* **Debug:** `-std=c++23 -g -O0 -fsanitize=address,undefined`
* **Auto-detects** Segfaults, TLE (Timeout), and Floating Point Exceptions.
