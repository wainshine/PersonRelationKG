# ChinesePersonRelationGraph
ChinesePersonRelationGraph, person relationship extraction based on nlp methods.中文人物关系知识图谱项目,内容包括中文人物关系图谱构建,基于知识库的数据回标,基于远程监督与bootstrapping方法的人物关系抽取,基于知识图谱的知识问答等应用.

# 项目介绍
知识抽取(实体关系抽取)是知识图谱构建中的核心环节,实体关系抽取作为一项基本技术在自然语言处理应用中扮演着重要作用.
究其技术而言,主要分成两种三种主流方法:    
# 1, 基于规则的方法  
   在工业界大多还是使用的规则模板的方法,这个可以参考我的相关项目:  
   1)https://github.com/liuhuanyong/EventTriplesExtraction, 这是借助依存句法与语义角色标注的方法.       
   2)https://github.com/liuhuanyong/ComplexEventExtraction, 这个项目提供了复合事件的基本模式,可以初步筛选出候选的因果,反转等事件    
   3)https://github.com/liuhuanyong/SequentialEventExtration, 这个项目提供了一种基于VOB模式的顺承事件抽取方法,讲的是一种顺承关系 
   基于规则的方法,升级版的话,就是Bootstrapping了,可以通过用户自定义种子模板,不断迭代,最终扩充模式,但置信度这个问题不是很好解决    #
# 2, 基于学习的方法  
   这个在学术界用的比较多,从机器学习一直演变了到现在的各种深度学习模型,而在这种方法中,通常实体关系抽取问题转换成一个实体关系分类任务去做,主要可以分成一下几种.
   1)基于全监督的实体关系抽取  
   这个全监督,也就是说,基于完全标注数据的一种学习方式,例如著名的实体关系评测Semeval系列,给出了19种关系分类任务,ACE给出了17类的实体关系分类任务.针对这些任务,模型经历了CNN,LSTM,ATTENTION等,这里就不再说明.  
   2)基于噪声数据的远程监督实体关系抽取  
   全监督模型固然很好,但数据是一个很棘手的问题,因此就出现了远程监督的方法,所谓远程监督,个人理解就是已经存在的知识库进行数据回标,然后通过多实例学习进行一种容许噪声的监督方法.不过这种方法准确率不是很高,在NYT这个数据集上,PCNNS等工作都没有达到业业界可以使用的地步.当然,最新出现了联合训练的模型.    
   3)基于规则与学习模型融合的实体关系抽取  
   这种方式,在业界或许是一种出路,例如,将实体关系抽取中的实体识别部分交给学习模型去做序列标注,最后针对实体之间的关系,结合依存句法等语义规则去做,这个在解决实体的多种关系问题,可以去尝试.  
# 3, 当前问题 
但就针对全监督的实体关系抽取任务而言,在英文数据集上已经在刷各种state-of-art,但就中文而言,感觉还是一片贫瘠.在网上搜了很久,最终指搜到COAE2016的一个评测任务,但是,评测集不公开.因此,就抛出了本项目构建的几个初衷:  
1, 中文实体关系抽取数据集很少,能不能构建一个准确率可接受的数据集?    
2, 能不能浅显易懂地把那些"高大上"的远程监督,bootstrapping经历一遍?   
3, 人物关系数据在百科等平台上都有放出,或许可以做为远程监督的先验知识库?    
4, 能否提供一个实时动态更新的人物关系图谱方法?  
# 4,项目任务
因此,本项目将尝试完成以下几个任务:  
1, 完成一定规模的人物关系知识库, 作为公开数据集开放出去  
2, 走一遍实体关系回标,形成一个准确性相对允许的人物关系抽取数据集  
3, 走一遍基于学习方式实体关系抽取,查看一下效果,熟悉一下这个技术流程    
4, 走一便基于Bootstrapping的实体关系抽取,熟悉一下这个技术流程  
5, 基于构建起来的人物关系图谱,完成一个面向人物关系图谱的知识问答  

# 项目架构图
![image](https://github.com/liuhuanyong/ChinesePersonRelationGraph/blob/master/image/project_route.png)


# 人物关系基础知识库
# 刘备人物关系网
![image](https://github.com/liuhuanyong/ChinesePersonRelationGraph/blob/master/image/rel_graph1.png)

# 韩寒人物关系网
![image](https://github.com/liuhuanyong/ChinesePersonRelationGraph/blob/master/image/rel_graph2.png)







