---
title: "5. Accelarate LLM generation by multi-threading"
excerpt: "Accelarate the matrix-vertor multiplication by multi-threading Using C"
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


Comparison: 
<table>
  <thead>
    <tr>
      <th>THREAD NUMBERS</th>
      <th>SPEED (TOK/S)</th>
      <th>USER TIME</th>
      <th>SYSTEM TIME</th>
      <th>USE TIME/SYSTEM TIME</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0(Sequential)</td>
      <td>53.090004</td>
      <td>4.8108</td>
      <td>0.1440</td>
      <td>33.4083</td>
    </tr>
    <tr>
      <td>1</td>
      <td>42.838019</td>
      <td>5.7963</td>
      <td>0.2465</td>
      <td>23.514</td>
    </tr>
    <tr>
      <td>2</td>
      <td>72.459666</td>
      <td>5.9634</td>
      <td>0.261</td>
      <td>22.848</td>
    </tr>
    <tr>
      <td>4</td>
      <td>114.901257</td>
      <td>6.3101</td>
      <td>0.3136</td>
      <td>20.121</td>
    </tr>
    <tr>
      <td>6</td>
      <td>134.524435</td>
      <td>6.6715</td>
      <td>0.5544</td>
      <td>12.033</td>
    </tr>
    <tr>
      <td>8</td>
      <td>158.220025</td>
      <td>6.8101</td>
      <td>0.6504</td>
      <td>10.4706</td>
    </tr>
    <tr>
      <td>10</td>
      <td>164.207826</td>
      <td>7.5318</td>
      <td>0.7231</td>
      <td>10.416</td>
    </tr>
    <tr>
      <td>12</td>
      <td>161.514196</td>
      <td>8.1322</td>
      <td>0.9558</td>
      <td>8.5083</td>
    </tr>
    <tr>
      <td>16</td>
      <td>158.220025</td>
      <td>10.0505</td>
      <td>1.1443</td>
      <td>8.7831</td>
    </tr>
  </tbody>
</table>











