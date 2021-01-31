### 用小懒猫闲聊SDK中的module.pyd构建闲聊模型

  module.pyd是小懒猫闲聊SDK中的构建模型的部分。我们可以利用它来构建聊天机器人。
  
  第一步，我们选用module.Best_train(self,filename,modulename)函数进行训练，数据集格式见主页。打开notepad编写，编写好文件后，保存为txt文件(不能保存为其他格式，否则会报错)。
  
  第二步下载SDK,打开PythonIDLE,在SDK的同级目录下创建py文件。
  
  第三步，使用from module import module,不能直接导入。接着使用modele.Best_train训练数据集（注意：filename填写文件不包括.txt文件后缀），每训练一条预料都会显示‘次数/##########/100%’，如果最后显
  
示的次数小于数据集语料数，检查数据集编写是否有误，训练完成后会在目录下生成h6文件

  第四步编写循环，把用户的输入用module.Best_chat(self,q,modulename)(注意：modulename填写模型名不包括.h6文件后缀)处理，返回答案。如果数据集最佳匹配问题与问题的相似度低于0.25会返回None。这时可以
  
用if自定义返回，避免None 

  这个聊天机器人就编写好了。
### 主页：
[主页](https://lazy-cat-xiaolanmao.github.io)
