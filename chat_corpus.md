### 闲聊SDK语料获取方法
  关于闲聊语料，网上有许多。如[chinese_corpus](https://github.com/codemayq/chinese_chatbot_corpus)
  
  关于闲聊api,网上有图灵机器人，腾讯智能闲聊，青云客机器人。
  
  以腾讯智能闲聊为例，可以搜索智能闲聊。找到腾讯的网页点进去，用QQ账号登录。然后创建应用，接入智能闲聊，记下APPKEY和APPID
  
  然后复制以下代码(APPKEY和APPID替换成你自己的)
  
                import requests as rq
                import time
                import random
                import string
                import urllib
                import hashlib

                APPKEY = 'xxxxxxxxxxx'
                APPID = 1234567  

               def get_sign(data):
                   lst = [i[0]+'='+urllib.parse.quote_plus(str(i[1])) for i in data.items()]
                   params = '&'.join(sorted(lst))
                   s = params + '&app_key=' + APPKEY
                   h = hashlib.md5(s.encode('utf8'))
                   return h.hexdigest().upper()


               def chat(question):    
                   url_chat = 'https://api.ai.qq.com/fcgi-bin/nlp/nlp_textchat'
                   nonce_str = ''.join(random.sample(string.ascii_letters + string.digits, 16))
                   data = {
                      'app_id': APPID,
                      'time_stamp': int(time.time()),
                      'nonce_str': nonce_str,
                      'session': '10000',
                     'question': question,
                   }
                   data['sign'] = get_sign(data)
                   r = rq.post(url_chat, data=data)
                   answer = r.json()['data']['answer']
                   return answer
               while True:
                   i = input()
                   a = chat(i)
                   print(a)

  然后与机器人闲聊，将机器人对话记录写为数据集进行训练

### 主页：
[主页](https://lazy-cat-xiaolanmao.github.io)
