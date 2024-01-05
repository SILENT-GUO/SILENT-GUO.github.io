---
title: "Accelarate LLM generation by multi-threading"
excerpt: " THREAD NUMBERS | SPEED (TOK/S) | USER TIME | SYSTEM TIME | USE TIME/SYSTEM TIME <br/>
| 0(Sequential)  | 53.090004     | 4.8108    | 0.1440      | 33.4083              <br/>
| 1              | 42.838019     | 5.7963    | 0.2465      | 23.514               <br/>
| 2              | 72.459666     | 5.9634    | 0.261       | 22.848               <br/>
| 4              | 114.901257    | 6.3101    | 0.3136      | 20.121               <br/>
| 6              | 134.524435    | 6.6715    | 0.5544      | 12.033               <br/>
| 8              | 158.220025    | 6.8101    | 0.6504      | 10.4706              <br/>
| 10             | 164.207826    | 7.5318    | 0.7231      | 10.416               <br/>
| 12             | 161.514196    | 8.1322    | 0.9558      | 8.5083               <br/>
| 16             | 158.220025    | 10.0505   | 1.1443      | 8.7831               
"
collection: portfolio
---
Author: Guo Zebin

Platform: Linux

Source code: [code](https://github.com/SILENT-GUO/LLM-Accelaration-by-Multithreading)

Author: Guo Zebin

This project accelerate LLM inferencing by using multi-threading in matrix-vector multiplications when using transformer.
This is the second programming assignment of HKU COMP3230 course.

## How to run it:
Platform: Linux (workbench2 in school server)

Compile the code: 
```
gcc -o llama2_3035770915 llama2_3035770915.c utilities.c -O2 -pthread -lm
```
Run the code:
```
./llama2_3035770915 42 <thr_count>
```
+ 42 is the random seed for text generation, different seeds correspond to different text, you can choose any integer between 1 to 100.
+ thr_count is the number of thread. When thread number is low, increasing the thread number will result in faster generation speed, but the thread handling overhead may forestall the accelaration when the thread number is high. Please refer to report_3035770915.pdf for detailed thread number comparison.









