#  Distributed Machine Learning System Material

<!-- :books: [**"Read enough so you start developing intuitions and then trust your intuitions and go for it!"** ](https://www.deeplearning.ai/hodl-geoffrey-hinton/) :books:  ​<br/>  Prof. Geoffrey Hinton, University of Toronto -->


<!-- 
1. automated dimention reduction, data partition, data sampling, etc to split the work to multiple nodes or reduce the training data set size without reduced accuracy

2. same as above, but feature engineering(v) -->


This Page is Materials Zoo for Distributed Machine Learning Systems Course in Graduate School of Data Science, Seoul National University. If there's any wrong content, missing links, please tell me by e-mail so that we can amend.<br>

<p style="text-align:right;">Written By Woo Lee - woochulee@snu.ac.kr</p>

***

## Parallel Computing
> (Last Update: Sep 26, 2020)  

***
| S.No | Title                              | Authors                       |Type | Links     
| ---- | ----------------------------------------------------- | ---------------------------------------------- | ------------------------------------------------------------ | ---------------------------| 
| 1.   | **Dask for Python**              | Dask    | Docs |  [LINK](https://docs.dask.org/en/latest/) |
| 2.   | **Parallel Computing in Python**              | Coding Tech   | Video  | [LINK](https://www.youtube.com/watch?v=xYuQi7PTAcc)


***

## Feature Engineering
> (Last Update: Sep 24, 2020)  

***
| S.No | Title                              | Authors                       |Type | Links     
| ---- | ----------------------------------------------------- | ---------------------------------------------- | ------------------------------------------------------------ | ---------------------------| 
| 1.   | **Feature Engineering Tutorial**              | Kaggle    | Docs |  [LINK](https://www.kaggle.com/learn/feature-engineering) |
| 2.   | **Feature Engineering Explained**              | KDnuggets   | Blog  | [LINK](https://www.kdnuggets.com/2018/12/feature-engineering-explained.html)
| 3.   | **A Practical Guide to Feature Engineering in Python**              | Heartbeat  | Docs  |[LINK](https://heartbeat.fritz.ai/a-practical-guide-to-feature-engineering-in-python-8326e40747c8)

***

## Dimension Reduction
> (Last Update: Sep 24, 2020)  

***
| S.No | Title                              | Authors                       |Type | Links     
| ---- | ----------------------------------------------------- | ---------------------------------------------- | ------------------------------------------------------------ | ---------------------------| 
| 1.   | **Dimensionality Reduction Algorithms With Python**              | Machine Learning Mastery       | Blog |  [LINK](https://machinelearningmastery.com/dimensionality-reduction-algorithms-with-python/) |
| 2.   | **Seven Techniques for Data Dimensionality Reduction KDD2009**              | Apache   | Blog  | [LINK](https://www.kdnuggets.com/2015/05/7-methods-data-dimensionality-reduction.html)
| 3.   | **An Actual Survey of Dimensionality Reduction**              | Alireza Sarveniazi   | Paper  |[LINK](https://www.researchgate.net/publication/276495528_An_Actual_Survey_of_Dimensionality_Reduction)

***

## MapReduce
> (Last Update: Sep 24, 2020)  

***
| S.No | Title                              | Authors                       |Type | Links     
| ---- | ----------------------------------------------------- | ---------------------------------------------- | ------------------------------------------------------------ | ---------------------------| 
| 1.   | **What is MapReduce?**              | GURU99       | Blog |  [LINK](https://www.guru99.com/introduction-to-mapreduce.html) |
| 2.   | **Apache Hadoop Map Reduce Tutorial**              | Apache      | Docs     |  [LINK](https://hadoop.apache.org/docs/current/hadoop-mapreduce-client/hadoop-mapreduce-client-core/MapReduceTutorial.html) |
| 3.   | **MapReduce explained**              | IBM Cloudant | Video    |  [LINK](https://www.youtube.com/watch?v=lgWy7BwIKKQ) | 

***

## Tensorflow
> (Last Update: Sep 7, 2020)  

***

| S.No | Title                              | Authors                       |Type | Links                                               | etc            |
| ---- | ----------------------------------------------------- | ---------------------------------------------- | ------------------------------------------------------------ | ---------------------------| ---------------------------------- | 
| 1.   | **Tensorflow_official_documentation_korean**              | Google Tensorflow       | Docs |  [LINK](https://www.tensorflow.org/?hl=ko) | `None`  | 
| 2.   | **Tensorflow_official_documentation_english**              | Google Tensorflow     | Docs     |  [LINK](https://www.tensorflow.org/?hl=en) | `None`  | 
| 3.   | **Introduction to Tensorflow**              | Google Tensorflow      | Video    |  [LINK](https://www.youtube.com/watch?v=5ECD8J3dvDQ) | `None`  | 

***

## Spark ML Lib
> (Last Update: Sep 7, 2020)  

***

| S.No | Title                              | Authors                       |Type | Links                                               | etc            |
| ---- | ----------------------------------------------------- | ---------------------------------------------- | ------------------------------------------------------------ | ---------------------------| ---------------------------------- | 
| 1.   | **PYPI_Pyspark**              | Python       | Docs |  [LINK](https://pypi.org/project/pyspark/) | `None`  | 
| 2.   | **Apache Spark™ ML and Distributed Learning (1/5) ~ (5/5)**              | DataBricks     | Video     |  [LINK](https://youtu.be/TeFXA2imXCs) | `None`  | 
| 3.   | **What is Apache Spark?**              | DataBricks      | Video    |  [LINK](https://www.youtube.com/watch?v=p8FGC49N-zM) | `None`  | 
| 4.   | **Spark Python API Docs**              | Python       | Docs |  [LINK](https://spark.apache.org/docs/latest/api/python/index.html) | `None`  | 

## Papers
> (Last Update: Sep 7, 2020)  

***

| S.No | Title                              | Authors                       | arxiv number                                               | PaperPDF                                               | Conference | Year            |
| ---- | ----------------------------------------------------- | ---------------------------------------------- | ------------------------------------------------------------ | ---------------------------| ---------------------------------- | --------------- |
| 1.   | **More Effective Distributed ML via a Stale Synchronous Parallel Parameter Server**              | Qirong Ho, James Cipar, Henggang Cui, Seunghak Lee, Jin Kyu Kim, Phillip B. Gibbons, Garth A. Gibson, Greg Ganger, Eric P. Xing         | `None`  | [Paper](http://www.cs.cmu.edu/~seunghak/SSPTable_NIPS2013.pdf) | NIPS | 2013 |
| 2.   | **Asymptotically Exact, Embarrassingly Parallel MCMC**                       | Willie Neiswanger, Chong Wang, Eric P. Xing                      | [1311.4780](https://arxiv.org/abs/1311.4780) | [Paper](https://arxiv.org/pdf/1311.4780.pdf)| UAI  | 2014            |
| 3.   | **LightLDA: Big Topic Models on Modest Compute Clusters**                           | Jinhui Yuan, Fei Gao, Qirong Ho, Wei Dai, Jinliang Wei, Xun Zheng, Eric P. Xing, Tie-yan Liu, Wei-Ying Ma            | [1412.1576](https://arxiv.org/abs/1412.1576) | [Paper](https://arxiv.org/pdf/1412.1576.pdf)|  WWW | 2015            |
| 4.   | **SaberLDA: Sparsity-Aware Learning of Topic Models on GPUs**                      | Kaiwei Li, Jianfei Chen, Wenguang Chen, Jun Zhu                     | [1610.02496](https://arxiv.org/abs/1610.02496)        | [Paper](https://arxiv.org/pdf/1610.02496.pdf) |ASPLOS | 2017            |
| 5.   | **Large Scale Distributed Deep Networks**               | Jeffrey Dean, Greg Corrado, Rajat Monga, Kai Chen, Matthieu Devin, Mark Mao, Marc’aurelio Ranzato, Andrew Senior, Paul Tucker, Ke Yang, Quoc V. Le, Andrew Y. Ng.           |         `None`            |   [Paper](https://papers.nips.cc/paper/4687-large-scale-distributed-deep-networks.pdf)                                                  |  NIPS | 2012            |
| 6.   | **Deep Learning with COTS HPC**                     | Adam Coates, Brody Huval, Tao Wang, David Wu, Bryan Catanzaro, Andrew Ng.             | `None`                         | [Paper](https://www.cs.virginia.edu/dwu4/papers/DeepLearningCOTS.pdf)|  ICML | 2013            |
| 7.   | **STRADS: A Distributed Framework for Scheduled Model Parallel Machine Learning**                            | Jin Kyu Kim, Qirong Ho, Seunghak Lee, Xun Zheng, Wei Dai, Garth A. Gibson, Eric P. Xing.                   | `None`                                                       | [Paper](http://www.cs.cmu.edu/~epxing/papers/2016/Kim_etal_EuroSys16.pdf) | EuroSys | 2016         |

***

## Textbooks / Videos (For Background of ML)
> (Last Update: Sep 7, 2020)  

***

| S.No | Title                              | Authors                       |ISBN | Links                                               | etc            |
| ---- | ----------------------------------------------------- | ---------------------------------------------- | ------------------------------------------------------------ | ---------------------------| ---------------------------------- | 
| 1.   | **Pattern Recognition and Machine Learning (Information Science and Statistics)**              | Christopher M. Bishop       | ISBN-13: 978-0387310732 |  [PDF](http://users.isr.ist.utl.pt/~wurmd/Livros/school/Bishop%20-%20Pattern%20Recognition%20And%20Machine%20Learning%20-%20Springer%20%202006.pdf) | `None`  | 
| 2.   | **Machine Learning**              | Tom M Mitchell     | ISBN-13: 978-1259096952     | [SITE](http://www.cs.cmu.edu/~tom/10701_sp11/lectures.shtml)  | `None`  | 
| 3.   | **Deep Learning (Adaptive Computation and Machine Learning series)**              | Ian Goodfellow, Yoshua Bengio, Aaron Courville      | ISBN-13: 978-0262035613    |  [PDF](https://www.deeplearningbook.org/) | `None`  | 
| 4.   | **Reinforcement Learning: An Introduction (Adaptive Computation and Machine Learning series) second edition**              | Richard S.Sutton, Andrew G. Barto       | ISBN-13: 978-0262039246 |  [LINK](https://web.stanford.edu/class/psych209/Readings/SuttonBartoIPRLBook2ndEd.pdf) | `None`  | 
| 5.   | **Machine Learning**              | Andrew Ng     | video |  [LINK](https://www.youtube.com/watch?v=PPLop4L2eGk&list=PLLssT5z_DsK-&ab_channel=ArtificialIntelligence-AllinOne) | `None`  | 
