### 小懒猫闲聊SDK的module.pyd

  module.pyd是小懒猫闲聊SDK的核心产品，这个功能不开源，可以下载pyd文件
  
  module.train(self,filename,module)函数：
  
    变量含义见主页。这个函数可以训练聊天机器人语料，生成h6文件。语料写法见主页。
    
  module.Best_train(self,filename,module)函数：
  
    变量含义见主页。这个函数可以使生成的h6文件更加轻便。
    
  module.chat(self,q,modulename)函数：
  
    这个函数只能使用train函数训练出来的文本，使用Best_train函数训练出来的会报错，返回答案，如果语料没有返回None
    
  module.Best_chat(self,q,modulename):
  
     这个函数可以使用train函数和Best_train函数训练出来的文本，返回答案，如果最佳匹配问题与问题的相似度低于0.25，会返回None
    
   
  
