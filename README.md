# A Survey of Efficient Attention Methods

**A Survey of Efficient Attention Methods: Hardware-efficient, Sparse, Compact, and Linear Attention**  
**PDF**: https://attention-survey.github.io/files/Attention_Survey.pdf  
Paper webpage: https://attention-survey.github.io

![](./png_figs/fig2.png)

This paper provides a comprehensive survey of **Efficient Attention Methods**, categorizing them into four classes.

-----

## Updates

 - **[2025/8/19]** 🎉 Our survey paper is now publicly available on [GitHub](https://attention-survey.github.io/files/Attention_Survey.pdf)! If you do find our resources helpful, please [cite our paper](#citation).

-----

## Class 1: Hardware-Efficient Attention

💡 **Core Idea**: Accelerate attention by leveraging hardware characteristics.

📝 **Overall Formulations**: 

Hardware-Efficient Attention for the prefilling stage can be formulated as:
 <img src="./png_figs/formula1.png" width="50%" height="50%">

Hardware-Efficient Attention for the decoding stage can be formulated as:
 <img src="./png_figs/formula2.png" width="50%" height="50%">

 ---

An example is **FlashAttention**, which tiles $Q, K, V$ to progressively compute the attention output $O$. Such a strategy avoids the I/O of $S, P$ matrices in the shape of $N \times N$.

 <img src="./png_figs/fig1.png" width="70%" height="70%">

---

The table below summarizes various hardware-efficient attention methods. 👇

![](./png_figs/table2.png)


-----

## Class2: Compact Attention

💡 **Core Idea**: Compressing the KV cache of attention by weight sharing or low rank decomposition while keeping computational cost unchanged, as with a full-sized KV cache. 

📝 **Overall Formulations**: 

 <img src="./png_figs/formula3.png" width="50%" height="50%">

---

 Below is a summarization of various approaches in compact attention. 👇

![](./png_figs/table3.png)


-----

## Class3: Sparse Attention

💡 **Core Idea**: Selectively performing a subset of computations in attention while omitting others.

📝 **Overall Formulations**: 

 <img src="./png_figs/formula4.png" width="90%" height="90%">

 ---

The table below summarizes various sparse attention methods. 👇

![](./png_figs/table4.png)

-----

## Class4: Linear Attention

💡 **Core Idea**: Redesigning the computational formulation of attention to achieve \(\mathcal{O}(N)\) time complexity. 

📝 **Overall Formulations**: 

 <img src="./png_figs/formula5.png" width="50%" height="50%">

---
### Computational Forms

Linear Attention can be implemented in three forms: **parallel**, **recurrent**, and **chunkwise**.

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

    📝 This table compares methods that utilize both the forget gate and the select gate. 👇

    ![](./png_figs/table6.png)
    

### A Special Case: Test-Time Training (TTT)

A unique approach, **Test-Time Training (TTT)**, treats the hidden states of linear attention as learnable parameters.

 <img src="./png_figs/fig5.png" width="70%" height="70%">

-----

## Citation

If you find our work helpful, please cite our paper:

```
@article{zhang2025efficient,
  title={Efficient Attention Methods: A Comprehensive Survey},
  author={Zhang, Jintao and Su, Rundong and Liu, Chunyu and Wei, Jia and Wang, Ziteng and Zhang, Pengle and Wang, Haoxu and Jiang, Huiqiang and Huang, Haofeng and Xiang, Chendong and Xi, Haocheng and Yang, Shuo and Li, Xingyang and Hu, Yuezhou and Fu, Tianyu and Zhao, Tianchen and Zhang, Yicheng and Jiang, Youhe and Chen, Chang and Jiang, Kai and Chen, Huayu and Zhao, Min and Xu, Xiaoming and Zhu, Jun and Chen, Jianfei},
  year={2025}
}
```
