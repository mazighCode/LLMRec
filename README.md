# LLMRec: Large Language Models with Graph Augmentation for Recommendation

PyTorch implementation for WSDM 2024 paper [LLMRec: Large Language Models with Graph Augmentation for Recommendation](https://llmrec.files.wordpress.com/2023/10/wsdm2024_llmrec_large_language_models_with_graph_augmentation_for_recommendation.pdf).



[Wei Wei](#), [Xubin Ren](https://rxubin.com/), [Jiabin Tang](https://tjb-tech.github.io/), [Qingyong Wang](#), [Lixin Su](#), [Suqi Cheng](#), [Junfeng Wang](#), [Dawei Yin](https://www.yindawei.com/) and [Chao Huang](https://sites.google.com/view/chaoh/home)*.
(*Correspondence)

**[Data Intelligence Lab](https://sites.google.com/view/chaoh/home)@[University of Hong Kong](https://www.hku.hk/)**, Baidu Inc.

<a href='https://llmrec.github.io/'><img src='https://img.shields.io/badge/Project-Page-Green'></a>
<a href='https://llmrec.github.io/'><img src='https://img.shields.io/badge/Demo-Page-purple'></a>
<a href='https://llmrec.files.wordpress.com/2023/10/wsdm2024_llmrec_large_language_models_with_graph_augmentation_for_recommendation.pdf'><img src='https://img.shields.io/badge/Paper-PDF-orange'></a> 
[![YouTube](https://badges.aleen42.com/src/youtube.svg)](https://www.youtube.com/channel/UC1wKlPPlP9zKGYk62yR0K_g)


This repository hosts the code, original data and augmented data of **LLMRec**.

-----------

<p align="center">
<img src="./llmrec_framework.png" alt="LLMRec" />
</p>

LLMRec is a novel framework that enhances recommenders by applying three simple yet effective LLM-based graph augmentation strategies to recommendation system. LLMRec is to make the most of the content within online platforms (e.g., Netflix, MovieLens) to augment interaction graph by i) reinforcing u-i interactive edges, ii) enhancing item node attributes, and iii) conducting user node profiling, intuitively from the natural language perspective.



## 🎉 News 📢📢  

- [x] [2023.10.27] 🚀🚀 Release the script for constructing the prompt.

- [x] [2023.10.27] 🚀🚀 Release LLM-augmented textual data(by gpt-3.5-turbo-0613), and LLM-augmented embedding(by text-embedding-ada-002).

- [x] [2023.10.27] 🔥🔥 The full paper of our LLMRec is available at [LLMRec: Large Language Models with Graph Augmentation for Recommendation](https://llmrec.files.wordpress.com/2023/10/wsdm2024_llmrec_large_language_models_with_graph_augmentation_for_recommendation.pdf).

- [x] [2023.10.27] 🚀🚀 Release the code of LLMRec.




<h2>Dependencies </h2>

```
pip install -r requirments.txt
```


<h2>Usage </h2>

<h4>Stage 1: LLM-based Data Augmentation</h4>

```
cd LLMRec/LLM_augmentation/
python ./try_gpt_ui_aug.py
python ./try_gpt_user_profiling.py
python ./try_gpt_i_attribute_generate_aug.py
```

<h4>Stage 2: Recommender training with LLM-augmented Data</h4>

```
cd LLMRec/
python ./main.py --dataset {DATASET}
```
Supported datasets:  `netflix`, `movielens`


<h2> Datasets </h2>

  ```
  ├─ LLMRec/ 
      ├── data/
        ├── netflix/
        ...
  ```

<h4> Orinigal Datasets </h4>

| Dataset       | Netflix |                             | MovieLens                                |
|---------------|---------|-----------------------------|------------------------------------------|
| Graph         | Ori.    | U                           | I                                        |
|               |         | 13187                       | 17366                                    |
|               | Aug.    | E                           | 26374                                    |
| Ori. Sparsity |         | 99.970%                     | 99.915%                                  |
| Att.          | Ori.    | U: None                     | I: year, title                           |
|               | Aug.    | U[1536]                     | age, gender, liked genre, disliked genre |
|               |         | I[1536]                     | director, country, language              |
| Modality      |         | Textual[768], Visiual [512] | Textual [768], Visiual [512]             |


<h4> Augmented Datasets</h4>




<h2> Prompt & Completion Example </h2>


<h4> LLM-based Implicit Feedback Augmentation </h4>
> Prompt 
>> ...

> Completion
>> ...





<h4> LLM-based User Profile Augmentation </h4>
> Prompt 
>> ...

> Completion
>> ...



<h4> LLM-based Item Attributes Augmentation </h4>
> Prompt 
>> ...

> Completion
>> ...



<h1> Citing </h1>

If you find this work helpful to your research, please kindly consider citing our paper.


```
@inproceedings{wei2023llmrec,
  title={LLMRec: Large Language Models with Graph Augmentation for Recommendation},
  author={Wei, Wei and Ren, Xubin and Tang, Jaibin and Wang, Qingyong and Su, Lixin and Cheng, Suqi and Wang, Junfeng and Yin, Dawei and Huang, Chao},
  journal={arXiv preprint arXiv:2308.05697},
  year={2023}
}
```



## Acknowledgement

The structure of this code is largely based on [MMSSL](https://github.com/HKUDS/MMSSL), [LATTICE](https://github.com/CRIPAC-DIG/LATTICE). Thank them for their work.

