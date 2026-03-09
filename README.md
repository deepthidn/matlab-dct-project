# Algorithm for Calculation of the Discrete Cosine Transform by Paired Transform


# 📌 Overview

This project implements an efficient algorithm for computing the **8-point Type-II Discrete Cosine Transform (DCT)** using the **Paired Transform** technique, based on research by Grigoryan *(IEEE Transactions on Signal Processing, 2005)*. Instead of computing the DCT the traditional way using nested loops over all N points, this algorithm splits the 8-point DCT into smaller 4-point, 2-point, and 1-point Type-IV sub-transforms, drastically reducing the number of arithmetic operations required while producing identical results.



# 🎯 Objectives

- Implement the Type-II DCT using the Paired Transform algorithm in MATLAB
- Compare computational efficiency between the Normal DCT and Paired DCT methods
- Verify correctness of output against MATLAB's built-in `dct()` function
- Count and compare total additions, multiplications, and execution time for both methods

---

## 🧠 How It Works

The paired transform breaks the 8-point DCT into a set of shorter sub-transforms:

```
8-point Type-II DCT
        |
  ┌─────┴──────┐
4-point      4-point
Type-IV      Type-IV
  |              |
2-point      1-point
Type-IV      Type-IV
```

This hierarchical decomposition eliminates redundant computations, making it significantly faster and more efficient than the direct DCT formula.

---

# 📊 Results

Both methods produce **identical DCT coefficients**, verified against MATLAB's built-in `dct()` function.

| Metric | Normal DCT | Paired DCT | Savings |
|---|---|---|---|
| Additions | 192 | 84 | **108** |
| Multiplications | 256 | 82 | **174** |
| Execution Time | ~0.002027s | ~0.001380s | **~0.000647s** |

> Results may vary slightly due to random input generation on each run.

---

## 🚀 How to Run

1. Open **MATLAB** (Desktop or Online at [matlab.mathworks.com](https://matlab.mathworks.com))
2. Copy and paste the script into a new `.m` file or the Command Window
3. Run the script — a random 8-point input is **generated automatically**
4. View the output — both Normal and Paired DCT results are displayed with full comparison


---

# 💡 Why It Matters

DCT is the backbone of widely used compression standards like **JPEG** (images) and **MP3** (audio). Reducing its computational complexity directly improves performance in:

- Real-time signal processing systems
- Hardware-based embedded applications
- High-speed image and video compression pipelines

---

## 📚 Reference

> Artyom M. Grigoryan, *"An Algorithm for Calculation of the Discrete Cosine Transform by Paired Transform"*, IEEE Transactions on Signal Processing, VOL. 53, NO. 1, January 2005.

---

## 🛠️ Tech Stack

- **MATLAB** (R2023 or any version with Signal Processing Toolbox)
