## 大规模行人检索竞赛（Large-Scale Pedestrian Retrieval Competition, LSPR Competition）

### 1. 竞赛目的与意义

行人检索可以帮助用户依据查询条件（如属性值或图片）找到特定视频、图像中出现的感兴趣行人目标，是智能视觉监控系统的重要终端应用之一，在公共安全领域具有极强的实用价值。当前，行人检索相关研究，如行人再识别、行人属性识别等方向，发展迅速，国内外研究者众多，文章方法层出不穷。然而，大多数研究还主要集中在算法层面，试图解决行人属性识别或行人再识别模型中面临的诸多技术难点（如低分辨率、遮挡及姿态变化等），以提供算法的鲁棒性及识别精度。目前还缺乏对从原始视频到行人检索“端到端”应用系统的性能评价标准与测试方法。

针对以上情况，本竞赛将提供一个面向真实监控的大规模行人检索性能评估基准。一方面，用于考察与行人检索相关的行人属性识别与行人再识别算法对不同目标尺度、姿态变化及遮挡条件下的识别性能；同时，还将提供一个大规模视频解析平台——ISEE系统，用于考察行人属性识别及行人再识别算法模型与行人检测算法模型集成后的系统性能，这将更直接地以“端到端”形式考察行人检索系统性能，有利于发现算法集成中影响系统整体性能的瓶颈问题，探索待查询集中大规模干扰样本对检索性能的影响，并形成行人检索系统的评测标准与测试方法。

### 2. 组织方式

- **组织方**：中国科学院自动化研究所，山东科技大学
- **联系方式**：张彰老师zzhang@nlpr.ia.ac.cn；单彩峰老师shancf@cas-air.cn
- **赞助方**：根尖智能科技有限公司

### 3. 竞赛参与者要求

国内外内各科研机构，包括各个高校、研究所、公司研究院均可参加。

### 4. 报名方式

仅接受以团队形式通过邮件报名参赛，每个参赛队伍人员不超过5人，每名参赛选手只能参加1个参赛队。参赛团队签署竞赛协议书并经单位盖章，扫描版发邮件至竞赛联系人邮箱da.li@cripac.ia.ac.cn。

- 邮件标题格式：“PRCV 2020大规模行人检索竞赛+参赛队名称”
- 邮件内容包括：团队基本信息；负责人信息；参赛人数；联系方式（手机及邮箱）；参赛内容；单位盖章的竞赛协议书扫描版。
- 报名截止日期：2020年7月1日。

组织方收到邮件并与报名者确认后，报名成功。

![报名信息表](/images/table-registration.jpg)
- 注：参赛内容包括——(1) PR-A; (2) PR-ID

### 5. 主要时间节点（北京时间）

- 05月01日-07月01日：参赛报名及邮件资格确认（**截止时间7月1日23时59分**）。
- 05月31日-07月15日：数据集开放（以网盘形式提供下载，下载链接以邮件形式发送到参赛队伍的预留邮箱，请在数据开放时间内尽快完成数据下载，遇到问题请及时与组织方联系）。
- 06月01日-08月31日：各参赛队在规定时间内完成参赛任务，并提交结果及模型（正式提交次数**不超过**两次，截止时间为08月31日23时59分；结果应以规定格式保存，提交地址会以邮件形式通知；模型提交时应附有详细说明文档，包括其所用框架、依赖环境等；建议用户提交第一版正式模型前，预先提交一版（**不作为正式提交**），以确保测试环境的正常运行）。
- 09月01日-09月24日：组委会根据测试数据集，对用户提交的模型进行评测，评比各队名次。
- 09月25日：公布竞赛结果。
- 10月16日：研讨会召开。

### 6. 竞赛数据、硬件资源与使用方式

#### 6.1 竞赛数据

竞赛中将提供大规模行人检索数据集（RAP-LSPRC），该数据集为RAP数据集的子集，包含超过68000张行人样本图片，每个样本都标注了72个细粒度属性，例如性别、发型、鞋子类型以及附属物类型等；同时数据集中共标注了2589个行人身份标签。下表中列出了数据集的一些基本信息：

![标记数据基本信息](/images/labeled-data-info.jpg)

样本示例：

![标记数据样本示例](/images/labeled-data-samples.jpg)

除了上述标注数据，还基于RAP-LSPRC中属性识别及行人再识别测试集对应的39278张完整图像数据，使用Faster-RCNN提取了243553个行人样本，并结合标注信息设计了超过千万的与行人属性或行人相似性相关的“问题（Query）”，利用“视觉图灵测试”的方法（“问-答”）进行行人属性检索和行人ID检索的系统测试。一些基本信息如下：

![问答数据统计信息](/images/QA-data.jpg)

示例：

![问答数据样本示例](/images/QA-samples.jpg)

#### 6.2 硬件与系统资源

中科院自动化所将提供一个集群（约5台GPU工作站）和一套大规模视频解析平台（ISEE）负责对参赛团队提交的算法模型进行验证与系统测试。

- 服务器配置：
  + CPU: Intel(R) Xeon(R) CPU E5-2620 v4 @ 2.10GHz
  + GPU: Titan Xp (12GB)
  + 内存: 128GB
  + 操作系统: CentOS7
  
#### 6.3 使用方式

竞赛数据集将以网盘形式供参赛团队下载使用，其中包含真实值标注的训练集与验证集用于算法模型训练与参数调试，测试集数据用于模型性能测试。**竞赛数据集仅供本竞赛使用，不得用于商业产品开发使用，未经许可不得转发他人使用**。

竞赛系统测试部分将使用的约4万张完整图片以及视觉问答中设计的Queries将不向参赛队开放。

### 7. 任务设置

本竞赛包含“行人属性检索”以及“行人ID检索”两个任务，参赛团队可任选一个或两个任务参加竞赛。具体设置如下：

- 任务1：行人属性检索（PR-A）。
参赛团队利用提供的行人RAP数据集，训练行人属性识别模型，对待评测的行人图片计算属性置信度。在评测时，分为“算法评测”与“系统评测”两个阶段。
  + **算法评测阶段（PR-A-RAP）**：根据预先设定好的属性查询条件（包括单个属性条件查询和由2~4个属性条件的组合查询，同数据集一同公开），在所提供的测试数据集中，按照置信度将图片样本由高到低排序。提交检索结果后，由竞赛组织方根据测试数据集的标注值进行评测。
  + **系统评测阶段（PR-A-SYS）**：由组织方利用ISEE平台，将参赛队提交的属性识别算法模型与行人检测模型进行集成，对输入的完整图片进行处理。之后，根据处理结果进行视觉问答测试。该测试将利用检测到的行人框与不同属性值结合，生成“该行人目标是否具有某些属性”的二值问题（超过500万），在解析结果（检测到的行人框及属性值）中进行查询，返回“是”或“否”的二值回答，并与问题的真实值进行对比，计算系统评测性能。

- 任务2：行人ID检索（PR-ID）。
参赛团队利用行人RAP数据集，训练行人再识别模型，对待评测的两张行人图片计算属于同一身份ID的相似度。评测时，分为“算法评测”与“系统评测”两个阶段。
  + **算法评测阶段（PR-ID-RAP）**：由RAP测试集中每张行人图片当做查询条件，按照属于同一身份ID的相似度将测试集中图片样本由高到低排序。提交检索结果后，由竞赛组织方根据测试数据集的标注值进行评测。
  + **系统评测阶段（PR-ID-SYS）**：由组织方利用ISEE平台，将参赛队提交的行人再识别算法模型与行人检测模型进行集成，对完整输入图片进行处理，根据处理结果为行人框建立Top-K的ID相似关系。之后，进行视觉问答测试。该测试将检测到的不同行人框与相似性关系相结合，生成“两者是否属于同一ID关系”的二值查询问题（超过1700万），根据解析结果返回“是”或“否”的二值回答，与查询问题的真实值进行对比，计算系统评测性能。

### 8. 结果评价方法

以上竞赛任务，各自评价方式如下：

+ 任务1：行人属性检索（PR-A）
  - 算法评测（PR-A-RAP）：将根据属性查询条件所返回样本的排序结果与真实值进行对比，计算标准mAP指标值作为行人属性检索性能评价指标。
  - 系统评测（PR-A-SYS）：根据问答真实值与返回的二值结果进行对比，计算属性问答的F-Score，作为最终系统性能指标。
  
+ 任务2：行人ID检索（PR-ID）
  - 算法评测（PR-ID-RAP）：根据标准行人再识别性能评价指标mAP衡量行人ID检索性能。
  - 系统评测（PR-ID-SYS）：根据问答真实值与返回的二值结果进行对比，计算ReID问答的F-Score，作为最终系统性能指标。
  
**算法评测中AP指标计算方法：**

<a href="https://www.codecogs.com/eqnedit.php?latex=AP=\frac{\sum_{r=1}^{N}P(r)\times&space;rel(r)}{K}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?AP=\frac{\sum_{r=1}^{N}P(r)\times&space;rel(r)}{K}" title="AP=\frac{\sum_{r=1}^{N}P(r)\times rel(r)}{K}" /></a>

其中P(r)为Rank-r的precision；rel(r)为binary函数，当且仅当Rank-r的返回结果满足查询条件函数值为1，否则为0；K为满足查询条件的样本总数。mAP即对所有查询的AP做平均。需要注意的是，在评测PR-ID-RAP时，我们仅检索与Query图像不在同一摄像机的其他行人图片。

**系统评测中F-Score指标计算方法：**

- PR-A-SYS：

<a href="https://www.codecogs.com/eqnedit.php?latex=prec_{i}=\frac{N_{tp}^{i}}{N_{tp}^{i}&plus;N_{fp}^{i}},recall_{i}=\frac{N_{tp}^{i}}{N_{p}^{i}}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?prec_{i}=\frac{N_{tp}^{i}}{N_{tp}^{i}&plus;N_{fp}^{i}},recall_{i}=\frac{N_{tp}^{i}}{N_{p}^{i}}" title="prec_{i}=\frac{N_{tp}^{i}}{N_{tp}^{i}+N_{fp}^{i}},recall_{i}=\frac{N_{tp}^{i}}{N_{p}^{i}}" /></a>

<a href="https://www.codecogs.com/eqnedit.php?latex=F_{1i}&space;=&space;\frac{2\ast&space;prec_{i}\ast&space;recall_{i}}{prec_{i}&plus;recall_{i}},F_{1}=\frac{1}{n_c}\sum_{i=1}^{n_c}F_{1i}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?F_{1i}&space;=&space;\frac{2\ast&space;prec_{i}\ast&space;recall_{i}}{prec_{i}&plus;recall_{i}},F_{1}=\frac{1}{n_c}\sum_{i=1}^{n_c}F_{1i}" title="F_{1i} = \frac{2\ast prec_{i}\ast recall_{i}}{prec_{i}+recall_{i}},F_{1}=\frac{1}{n_c}\sum_{i=1}^{n_c}F_{1i}" /></a>

其中，i表示第i组查询条件；<a href="https://www.codecogs.com/eqnedit.php?latex=n_c" target="_blank"><img src="https://latex.codecogs.com/gif.latex?n_c" title="n_c" /></a>为查询条件的总数目；<a href="https://www.codecogs.com/eqnedit.php?latex=N_{tp}^{i}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?N_{tp}^{i}" title="N_{tp}^{i}" /></a>表示由第i组查询条件生成的Positive Queries中被正确回答的数目，即True Positives的数量；<a href="https://www.codecogs.com/eqnedit.php?latex=N_{fp}^{i}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?N_{fp}^{i}" title="N_{fp}^{i}" /></a>表示由第i组查询条件生成的Negative Queries中被错误回答的数目，即False Positives的数量；<a href="https://www.codecogs.com/eqnedit.php?latex=N_{p}^{i}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?N_{p}^{i}" title="N_{p}^{i}" /></a>表示由第i组查询条件生成的Positive Queries的总数。

- PR-ID-SYS：

<a href="https://www.codecogs.com/eqnedit.php?latex=prec=\frac{N_{tp}}{N_{tp}&plus;N_{fp}},racall=\frac{N_{tp}}{N_{p}}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?prec=\frac{N_{tp}}{N_{tp}&plus;N_{fp}},racall=\frac{N_{tp}}{N_{p}}" title="prec=\frac{N_{tp}}{N_{tp}+N_{fp}},racall=\frac{N_{tp}}{N_{p}}" /></a>

<a href="https://www.codecogs.com/eqnedit.php?latex=F_{1}=\frac{2\ast&space;prec\ast&space;recall}{prec&plus;recall}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?F_{1}=\frac{2\ast&space;prec\ast&space;recall}{prec&plus;recall}" title="F_{1}=\frac{2\ast prec\ast recall}{prec+recall}" /></a>

其中，<a href="https://www.codecogs.com/eqnedit.php?latex=N_{tp}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?N_{tp}" title="N_{tp}" /></a>表示全部Positive Queries中被正确回答的数目，即True Positives的数目；<a href="https://www.codecogs.com/eqnedit.php?latex=N_{fp}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?N_{fp}" title="N_{fp}" /></a>表示全部Negative Queries中被错误回答的数目，即False Positives的数目；而<a href="https://www.codecogs.com/eqnedit.php?latex=N_{p}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?N_{p}" title="N_{p}" /></a>则表示全部Positive Queries的数目。

### 9.结果提交方式

无论参加哪项竞赛任务，参赛团队提交的结果都必须包含“识别结果”与“算法模型”两部分，同时在竞赛研讨会召开前，需要提交参赛相关技术说明文档。

- **识别结果**：参赛团队在RAP-LSPRC测试集上的识别结果，以指定文件格式上传竞赛组织方。

  + (1) PR-A-RAP
  
  识别结果格式：
  
  """
  <query_index>,<image_index_1>,<confidence_1>,<image_index_2>,<confidence_2>, ..., <image_index_N>,<confidence_N>
  """
  
  注：
    * 1) 一条查询结果保存一行，各项之间以逗号隔开，并请以.csv后缀命名。
    * 2) query_index为查询条件索引，请以与我们提供的查询条件顺序保持一致。
    * 3) image_index_i为识别结果的图像索引，索引顺序请与测试集中图像顺序保持一致, N为测试样本数量。
    * 4) confidence_i为置信度，与image_index_i一一对应，结果应根据置信度由高到低排列。
    
  + (2) PR-ID-RAP
  
  识别结果格式：同(1) PR-A-RAP
  
  注：此处query_index应与测试图像顺序保持一致
  
- 算法模型：参数团队还需提交符合指定接口格式的属性识别或行人再识别算法模型，供结果验证和进一步系统测试。

- 其他注意事项：

  + 针对每个评测任务，每只参赛团队最多提交2份识别结果和2种算法模型。
  + 系统只支持C/C++，python代码，且运行环境仅为Linux (CentOS7)。
  + 请提供可以正常运行的模型调用样例。
  + [链接](https://github.com/LSPRC/PRCV2020-LSPRC)中提供了竞赛任务的C/C++及python接口。无论何种代码请都包含initialize, recognize/detect, release三个方法，并给出相应的说明文档和可以正常运行的样例代码。
  + 支持pytorch、tensorflow、mxnet或caffe深度学习框架。
  + 如果包含自定义Layer，请务必提供源代码或封装好的动态链接库，说明依赖库等信息。
  + 提供的行人再识别代码中需返回最后的特征层，而非Rank结果。
  + 不得使用所提供数据以外的行人属性或行人再识别相关数据集辅助模型训练。
  
### 10. 奖项设置或奖励方法

在2个竞赛任务、2种评测方式共4个环节中，对性能指标排名前三名的参赛队伍，授予由竞赛组织方签发的冠、亚、季军获奖证书，并予以一定物质奖励（其中，每个环节第一名奖金1万元，第二名奖金5000元，第三名奖金2500元，共计奖金总额7万元）。

### 11. 知识产权归属

- 参赛团队提交算法及可执行模型的知识产权归参赛团队所有，竞赛视频、图像数据由中科院自动化所所有。
- 各参赛队在赛前需签订数据使用协议，承诺本竞赛提供的数据集仅能用于本竞赛，不用于除本竞赛外的任何其他用途。
- 各参赛队需要承诺本队提交的结果可重复，组织方承诺履行保密义务，并不用于除本比赛外的任何其他用途。
- 参赛队伍应保证所提供的方案、算法属于自有知识产权。组织方对参赛队伍因使用本队提供/完成的算法和结果而产生的任何实际侵权或者被任何第三方指控侵权概不负责。一旦上述情况和事件发生参赛队伍必须承担一切相关法律责任和经济赔偿责任并保护组织方免于承担该等责任。

### 12. 参赛团队注册方式

本竞赛将邀请所有参赛团队参加PRCV期间举行的研讨会。参会的团队注册可与PRCV注册方式相同，标明参加竞赛研讨会，并支付注册费用。

### 13. 竞赛协议下载链接

- [竞赛协议]()
