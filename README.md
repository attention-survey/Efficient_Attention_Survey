# Efficient Attention Methods: A Comprehensive Survey

Efficient Attention Methods: A Comprehensive Survey  
Paper Link: https://github.com/attention-survey/Efficient_Attention_Survey/blob/main/resource/Attention_Survey.pdf



![](./png_figs/fig2.png)

This survey provides a comprehensive overview of **Efficient Attention Methods**, categorizing them into four main classes.

-----

## 📅 Updates

 - **[2025/8/20]** 🎉 Our survey paper is now publicly available on [GitHub](./resources/paper.pdf)! If you do find our resources helpful, please [cite our paper](#citation).


-----

## Class 1: Hardware-Efficient Attention

💡 **Core Idea**: Accelerate attention by leveraging
hardware characteristics.

📝 **Overall Formulations**: 

Hardware-Efficient Attention of the prefilling stage can be formulated as:
 <img src="./png_figs/formula1.png" width="50%" height="50%">

Hardware-Efficient Attention of the decoding stage can be formulated as:
 <img src="./png_figs/formula2.png" width="50%" height="50%">

 ---

An example is **FlashAttention**, which tiles $Q, K, V$ to progressively compute the attention output $O$. Such a strategy avoids the I/O of $S, P$ matrices in the shape of $N \times N$.

 <img src="./png_figs/fig1.png" width="70%" height="70%">

---

The table below summarizes various hardware-efficient attention methods. 👇

![](./png_figs/table2.png)


-----

### Class2: Compact Attention Methods

💡 **Core Idea**: Compressing the KV cache
of attention by weight sharing or low rank decomposition while keeping computational
cost unchanged, as with a full-sized KV cache. 

📝 **Overall Formulations**: 

 <img src="./png_figs/formula3.png" width="50%" height="50%">

---

 Below is a comparison of various approaches in compact attention. 👇

![](./png_figs/table3.png)


-----

### Class3: Sparse Attention

💡 **Core Idea**: Selectively performing certain computations in attention while omitting others.

📝 **Overall Formulations**: 

 <img src="./png_figs/formula4.png" width="90%" height="90%">

 ---

The table below summarizes various sparse attention methods. 👇

![](./png_figs/table4.png)

-----

## Class4: Linear Attention Methods

💡 **Core Idea**: Modifying the
computational logic of attention to reduce its complexity to $O(N)$. 

📝 **Overall Formulations**: 

 <img src="./png_figs/formula5.png" width="50%" height="50%">

---
### Computational Forms

Linear Attention can be implemented in three primary forms: **parallel**, **recurrent**, and **chunkwise**.

![](./png_figs/fig3.png)

---

### Gating Mechanisms

Many linear attention methods incorporate **forget gates** and **select gates**.

 <img src="./png_figs/fig4.png" width="70%" height="70%">

Based on the presence of these gates, we can classify linear attention methods as follows:

1.  **Naive Linear Attention (No Gates)**

    📝 The table below summarizes naive attention methods. 👇

    ![](./png_figs/table5.png)


2.  **Linear Attention with a Forget Gate**

    📝 This table compares methods that use a forget gate. 👇

    ![](./png_figs/table6.png)


3.  **Linear Attention with Forget and Select Gates**

    📝 This table compares methods that utilize both forget gate and select gate. 👇

    ![](./png_figs/table6.png)
    

### A Special Case: Test-Time Training (TTT)

A unique approach, **Test-Time Training (TTT)**, treats the hidden states of linear attention as learnable parameters.

 <img src="./png_figs/fig5.png" width="70%" height="70%">

-----

## 📜 Citation

If you find our work helpful, please consider citing our paper:

```
@article{zhang2025efficient,
  title={Efficient Attention Methods: A Comprehensive Survey},
  author={Jintao Zhang and Rundong Su and Chunyu Liu and Jia Wei and Ziteng Wang and Pengle Zhang and Haoxu Wang and Huiqiang Jiang and Haofeng Huang and Chendong Xiang and Haocheng Xi and Shuo Yang and Xingyang Li and Yuezhou Hu and Tianyu Fu and Tianchen Zhao and Yicheng Zhang and Youhe Jiang and Chang Chen and Kai Jiang and Huayu Chen and Min Zhao and Xiaoming Xu and Jun Zhu and Jianfei Chen},
  year={2025}
}
```