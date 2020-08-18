# paddle
基于kaggle数据集的数据分析

1	目的
  创建模型：根据Kaggle比赛Crowdflower Search Results Relevance的数据集训练模型，使得模型能对用户输入的关键字和搜索引擎搜索结果的相关度进行评估。
  对模型进行展示：用户输入关键字，系统根据模型对资料库中的所有产品进行相关度的评估，按照相关度从高到低返回搜索结果。通过这种方式，让用户直观地感受模型的性能。
  协助评估搜索算法的性能：本项目为开源项目，通过模型对搜索引擎的返回结果进行评估，此项服务可以协助开发搜索算法的企业评估搜索算法的性能。
  
2 系统概述
  本项目是一个基于Python3.6的系统，运用TensorFlow, scikit-learn等机器学习库训练得到模型，通过模型对搜索结果进行相关度评估；同时，系统以“用户输入关键词，系统返回排序后的搜索结果”的形式，让用户能直接地感受到模型的准确性。
  
3 使用说明
  本项目使用Anaconda3提供的虚拟环境作为开发环境，前、后端所需要的环境依赖相差较大。若只要运行前端，则只需满足前端所需的环境依赖即可。
  
  3.1 前端
  如何运行前端？
  在终端中定位至源代码文件夹，运行
    python ./SearchSystem/Main_1.py
  前端环境要求如下：
  python=3.6.8
  wxpython=4.0.4
  pandas=0.25.0
  numpy=1.16.4
  pickle

  3.2 后端
  由于特征提取之后的文件较大，故提交物中已删去所有特征数据文件，仅保留根据特征生成的最后的训练、验证和测试集结果提交文件。  
  
  如何查看模型在验证集上的性能表现（Kappa系数）：(运行时间约10-15分钟)
  在终端中定位至源代码文件夹，运行
    python ./ModelSystem/Models/ModelsValidation.py
  如何生成提交文件：（运行时间约20-30分钟）
  在终端中定位至源代码文件夹，运行
  python ./ModelSystem/Models/GenerateNormalSubmission.py
  
  如何查看原始的数据文件：
  训练集：./ModelSystem/RawData/train.csv
  测试集：./ModelSystem/RawData/test.csv

  如何查看生成的提交文件（即测试集输出结果）：
  ./ModelSystem/Models/NormalSubmission_final.csv
  ./ModelSystem/Models/NormalSubmission_lir.csv
  ./ModelSystem/Models/NormalSubmission_ridge.csv
  ./ModelSystem/Models/NormalSubmission_svr.csv
  
  如何查看模型在测试集上的性能表现（Kappa系数）：
  提交生成的提交文件至网站
  https://www.kaggle.com/c/crowdflower-search-relevance/
  
  若要运行.py文件，进行数据预处理、特征工程、模型训练等整个完整的流程，则需时间4-5小时左右，其需要的环境配置如下，具体运行操作在《用户手册》第三章 后端 部分给出。


