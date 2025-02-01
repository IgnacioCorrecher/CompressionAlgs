# Python Compression Algorithms Exercises

## Introduction

This repository contains a series of exercises designed to help you learn and implement various compression algorithms from scratch using Python. The exercises gradually increase in difficulty, starting with basic bit manipulation and binary I/O and progressing to more advanced techniques such as Huffman coding, LZW, and arithmetic coding. Whether you're a beginner looking to understand the fundamentals or an experienced developer interested in algorithm optimization, these exercises will guide you through practical, hands-on implementations.

## Table of Contents

1. [Exercise 1: Bit Manipulation & Binary I/O](#exercise-1-bit-manipulation--binary-io)
2. [Exercise 2: Run-Length Encoding (RLE)](#exercise-2-run-length-encoding-rle)
3. [Exercise 3: Huffman Coding](#exercise-3-huffman-coding)
4. [Exercise 4: Dictionary-Based Compression (LZW)](#exercise-4-dictionary-based-compression-lzw)
5. [Exercise 5: Arithmetic Coding (Simplified)](#exercise-5-arithmetic-coding-simplified)
6. [Exercise 6: Performance Comparison & Visualization](#exercise-6-performance-comparison--visualization)
7. [Exercise 7: Extending & Refining Your Algorithms](#exercise-7-extending--refining-your-algorithms)
8. [Exercise 8: Exploring Real-World Algorithms (Optional Challenge)](#exercise-8-exploring-real-world-algorithms-optional-challenge)
9. [Additional Resources](#additional-resources)

---

## Exercise 1: Bit Manipulation & Binary I/O

**Objective:**  
Learn to represent and manipulate data at the bit level, which is a fundamental skill in data compression.

**Tasks:**

-   **Binary Conversion:**
    -   Write a function to convert a string into its binary representation.
    -   Write a reverse function to convert binary back to the original text.
-   **File I/O with Binary Data:**
    -   Read a text file, convert its contents to binary, and write the binary data to a new file.
    -   Read the binary file and convert it back to text.

**Hints:**  
Use built-in functions such as `ord()`, `bin()`, and `int()`. Utilize Python’s byte-level file I/O modes (`'rb'` and `'wb'`).

---

## Exercise 2: Run-Length Encoding (RLE)

**Objective:**  
Implement a simple compression algorithm using Run-Length Encoding (RLE) to compress sequences of repeated characters.

**Tasks:**

-   **Compression Function:**
    -   Create `compress_rle(data: str) -> str` that replaces sequences of repeated characters with a single character followed by the count.
    -   _Example:_ `"AAAABBBCCDAA"` becomes `"4A3B2C1D2A"`.
-   **Decompression Function:**
    -   Create `decompress_rle(data: str) -> str` to reverse the process.
-   **Testing:**
    -   Test your functions on various inputs, including edge cases.

**Hints:**  
Consider using regular expressions for parsing during decompression and handle edge cases (e.g., single characters or numeric characters in the data).

---

## Exercise 3: Huffman Coding

**Objective:**  
Implement Huffman Coding, a variable-length coding algorithm that compresses data based on character frequency.

**Tasks:**

-   **Frequency Table:**
    -   Write a function `build_frequency_table(data: str) -> dict` to count character occurrences.
-   **Building the Huffman Tree:**
    -   Implement a function to build a Huffman tree using a priority queue (Python’s `heapq` module).
    -   Define a simple `Node` class or use tuples for tree nodes.
-   **Generate Codes:**
    -   Write a function `generate_codes(tree) -> dict` that traverses the tree and assigns a unique binary code to each character.
-   **Compression & Decompression:**
    -   Create `compress_huffman(data: str, codes: dict) -> str` to convert text into a binary string.
    -   Create `decompress_huffman(encoded: str, tree) -> str` to recover the original text.
-   **Testing:**
    -   Validate that decompression returns the original text and evaluate the compression ratio.

**Hints:**  
Make sure to store or transmit the Huffman tree (or its equivalent code mapping) with the compressed data.

---

## Exercise 4: Dictionary-Based Compression (LZW)

**Objective:**  
Implement the LZW algorithm, which builds a dynamic dictionary of patterns encountered in the input data.

**Tasks:**

-   **LZW Compression:**
    -   Write a function `compress_lzw(data: str) -> list` that outputs a list of numerical codes.
    -   Initialize the dictionary with all possible single characters.
-   **LZW Decompression:**
    -   Write a function `decompress_lzw(compressed: list) -> str` that reconstructs the original text.
-   **Testing:**
    -   Test your implementation on various inputs and analyze the dictionary’s evolution.

**Hints:**  
Ensure that the dictionary is updated consistently during both compression and decompression. Visualizing the dictionary can aid in understanding the process.

---

## Exercise 5: Arithmetic Coding (Simplified)

**Objective:**  
Delve into arithmetic coding, a method that represents an entire message as a fraction between 0 and 1 based on cumulative probabilities.

**Tasks:**

-   **Probability Table:**
    -   Compute a probability table for the characters in your input text.
-   **Encoding:**
    -   Implement a simplified arithmetic encoder that assigns an interval \([low, high)\) for the message.
-   **Decoding:**
    -   Write a corresponding decoder that recovers the original message given the final interval and probability table.
-   **Testing:**
    -   Validate the encoder and decoder on short texts, taking care with precision.

**Hints:**  
Start with a fixed probability table and consider using Python’s `decimal` module to handle precision issues.

---

## Exercise 6: Performance Comparison & Visualization

**Objective:**  
Compare the performance of your implemented algorithms in terms of compression ratio and runtime.

**Tasks:**

-   **Benchmarking:**
    -   Create a script that compresses a text file using each algorithm.
    -   Record metrics such as the compression ratio (compressed size vs. original size) and runtime.
-   **Visualization:**
    -   Use `matplotlib` to graph the performance comparisons.
-   **Analysis:**
    -   Provide insights into why certain algorithms perform better on specific types of data.

**Hints:**  
Utilize Python’s `time` module or `timeit` for runtime measurements and test on a variety of data sets including highly repetitive and non-repetitive texts.

---

## Exercise 7: Extending & Refining Your Algorithms

**Objective:**  
Enhance your compression algorithms to handle real-world scenarios and improve robustness.

**Tasks:**

-   **Binary Data Support:**
    -   Adapt your compressors to handle binary data (not just text).
-   **Error Handling & Robustness:**
    -   Add error checking for cases such as corrupted or incomplete data.
-   **Streaming & Chunking:**
    -   Modify your algorithms to process data in chunks for large files or streaming applications.
-   **Unit Testing:**
    -   Write unit tests using frameworks like `unittest` or `pytest` to ensure that compression followed by decompression always yields the original data.

**Hints:**  
Focus on modularizing your code to simplify testing and debugging.

---

## Exercise 8: Exploring Real-World Algorithms (Optional Challenge)

**Objective:**  
Investigate advanced real-world compression techniques by exploring a simplified version of the DEFLATE algorithm.

**Tasks:**

-   **Research DEFLATE:**
    -   Study the DEFLATE algorithm, which combines LZ77 and Huffman coding.
-   **Simplified Implementation:**
    -   Implement a version that applies a sliding-window (LZ77-like) compression followed by Huffman coding.
-   **Testing & Comparison:**
    -   Compare your implementation with Python’s built-in `zlib` library.

**Hints:**  
Break the problem into smaller parts and focus on understanding the underlying principles rather than perfect optimization.

---

## Additional Resources

-   **Books:**
    -   _Data Compression: The Complete Reference_ by David Salomon
-   **Online Articles & Tutorials:**
    -   Look for detailed guides on Huffman coding, LZW, and arithmetic coding.
-   **Open Source Projects:**
    -   Explore [zlib](https://github.com/madler/zlib) for a real-world example of compression in practice.

---

By working through these exercises, you will build a solid foundation in both the theory and practical implementation of compression algorithms in Python. Enjoy your journey into the world of data compression and happy coding!
