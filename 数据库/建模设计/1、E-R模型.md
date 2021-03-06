### E-R模型

#### 设计中的抽象

不同层次抽象

* 现实层(客观存在) =>抽象层(观念世界/信息世界，描述现实世界的一种观点) =>...(信息世界的若干层抽象)... =>逻辑层(计算机世界：独立于物理设备) =>物理层(计算机世界：不同物理设备的具体实现）
* 越抽象，语义信息越少，概括性越高，越反映共性信息，表征的范围越大
* 检验抽象正确性的方法：能够依据现实抽象出来(抽象化)，同时也能够依据抽象的信息和抽象规则还原为被抽象对象(具体化)。



基本思想数据模型与概念模型

* 表达计算机世界的模型称数据模型；表达信息世界的模型称概念数据模型，简称概念模型，信息世界是对现实世界的理解与抽象

* 不同层面的抽象：现实世界 -> 概念/信息世界 -> 计算机世界逻辑世界(语义结构) -> 物理世界(存储结构)



抽象过程

* **理解-区分-命名-表达**



![在这里插入图片描述](https://img-blog.csdnimg.cn/20201127085736874.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MzkzNDYwNw==,size_16,color_FFFFFF,t_70#pic_center)




#### 基本思想

E-R模型的基本观点：

* 世界是由一组称作实体实体的基本对象和这些对象之间的联系联系构成的



E-R模型给出了一组基本概念，用这组概念可以刻画信息世界

* 实体
  * 实体：客观存在并可相互区分的事物
  * 实体有类(实体，实体的型)和个体(实体的实例，实体的值)的概念
  * 实体用属性来刻画

* 属性
  * 实体所具有的某一方面特性
  * 属性还有很多类型
    * 单一属性与复合属性,
      * 复合属性示例：家庭住址：省份, 详细住址
      * 在关系模型中，复合属性一定要转化为单一属性(关系的第1范式)
    * 单值属性和多值属性：每个实例的该属性值是一个还是多个
      * 多值属性示例： 电话号码，一个人可能有多个电话号码
      * 在关系模型中，多值属性一定要转化为单值属性(关系的第1范式)
     * 可空值属性和非空值属性：每个实例的该属性值可以是或不能是空值
     * 导出属性：由其他属性计算而得（例如由“出生年份” 可以得出“年龄”）

* 联系

  * 指一个实体的实例和其他实体实例之间所可能发生的联系
* 参与发生联系的实体的数目，称为联系的度或元。

  * 联系有一元联系、二元联系和多元联系
    * 最常见的：二元联系（两个实体之间发生联系），有一对一、一对多和多对多联系
  * 联系的基数（Cardinalities）：实体实例之间的联系的数量，即一个实体的实例通过一个联系能与另一实体中相关联的实例的数目

    * 常见的映射基数如上，有一对一的（1:1），一对多的（1:m），多对多的（m:n）几种情况
* 进一步，联系的基数还要区分是0个、1个、不定数目的多个还是固定数目的多个(即，对每个实体的实例而言是否必须存在)
  * 完全参与联系，即该端实例至少有一个参与到联系中,最小基数为1(1..m)；
  * 部分参与联系，即该端实例可以不参与联系，最小基数为0(0..m）

* 关键字/码
  * 实体中能够用其值唯一区分开



#### Chen方法

基本图元

* 实体：矩形框 

* 属性：椭圆
  * 多值属性：双线椭圆
  * 导出属性：虚线椭圆
* 关键字/码：下划线
* 连接实体和属性：直线
* 联系：菱形框
* 连接实体与联系：直线
* 连接联系和属性：直线
* 复合关键字：标有相同数字
* 多组关键字：标有不同数字

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201127085756652.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MzkzNDYwNw==,size_16,color_FFFFFF,t_70#pic_center)




不同“联系”的区分方法

* 1:1联系：箭头直线，由联系指向实体
* 1:m联系：指向1端为箭头直线，指向多端为无箭头直线
* m:n联系：无箭头直线
* 完全参与联系：双直线
* 部分参与联系：单直线

![在这里插入图片描述](https://img-blog.csdnimg.cn/2020112708581458.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MzkzNDYwNw==,size_16,color_FFFFFF,t_70#pic_center)




1:1, 1:m, m:n的联系也可以如下区分：

* 1端实体-直线旁标1
* 多端实体-直线旁标m或n
  * 完全/部分参与联系也可以标注最小基数..最大基数进行区分，最小基数0的为部分参与联系，最小基数1的为完全参与联系
* 直线旁标1..1, 0..1, 1..m, 0..m：

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201127085828327.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MzkzNDYwNw==,size_16,color_FFFFFF,t_70#pic_center)






#### Crow’s foot方法

图元

* 实体：矩形框，实体的名称写在横线上面

* 属性：实体框横线的下面

* 关键字：属性下加下划线

  ![在这里插入图片描述](https://img-blog.csdnimg.cn/20201127085845883.png#pic_center)


* 联系：菱形框表示，也可以将菱形框省略而直接以联系名来替代

  ![在这里插入图片描述](https://img-blog.csdnimg.cn/20201127085907200.png#pic_center)

* 联系的基数表示方法

  ![在这里插入图片描述](https://img-blog.csdnimg.cn/20201127085922829.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MzkzNDYwNw==,size_16,color_FFFFFF,t_70#pic_center)




#### 建模步骤

Step1 理解需求，寻找实体

Step2 用属性刻画实体

Step3 确定实体的关键字

Step4 分析实体之间的联系
