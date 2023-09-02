# ProcessingTricks
This repo is created to record some praticial tricks before we start to train a deep model
# NLP领域
## 基本操作
### 特殊符号或标点去除
如果任务不涉及复杂的语言结构或者语境，可以根据任务的需要和文本的性质，使用string.replace()方法或re模块去除特殊符号或者标点。一方面符号会增加文本维度，但又不携带文本信息，除了可能增加噪声，还会增加计算和存储成本。  
```python
def clean_special(self, text): 
        cleaned_text = re.sub(r'[^\w\s]', '', text)
        return cleaned_text
```
### 去除停用词
所谓停用词，是指在文本处理中通常被忽略或移除的常见词汇，因为它们出现频率高，但往往没有提供关于文本主题的有用信息。所以存在和<特殊符号>一样的问题。   
★中文常见：的、是、了、在、和  
★英文常见：冠词（ "a"、"an"、"the"）、代词（"I"、"you"、"he"、"she"）、连词（"and"、"but"、"or"）、介词（"in"、"on"、"at"）、助动词（ "is"、"am"、"are"）、常见名词（ "thing"、"time"、"day"）  
是否去除停用词需要看任务，比如在文本分类和信息检索中需要对一些停用词去除，而在上下文和情感分析中就需要保留停用词。  
[常用中文停用词](https://github.com/goto456/stopwords)
```python
# 英文停用词
# $pip install nltk

from nltk.corpus import stopwords
words = stopwords.words('english')
print(words)
```


### 去除HTML标签
有很多文本数据集的源数据是来自从网页前端爬取的，里面有很多无意义的html标签，去除这些标签对于接下来的nlp任务是很有必要的。  
```python
# 使用正则
def clean_html(self, text):
        cleaned_text = re.sub(r'<[^>]+>', '', text)
        return cleaned_text
# 使用BeautifulSoup
from bs4 import BeautifulSoup
soup = BeautifulSoup(html,'html.parser')
print(soup.get_text())
```
### 词干提取

### 词形还原（Lemmatization）：使用词形还原算法（如WordNet Lemmatizer）将词汇还原为其词根形式，以获得更准确的词汇。

### 去除重复字符：去除文本中连续重复的字符，以减少文本中的噪声。

### 拼写检查与修复：使用拼写检查工具（如PySpellChecker或Autocorrect）来检测和纠正拼写错误。

### 去除数字：根据任务需要，可以选择去除文本中的数字或将其替换为特殊标记。

### 正则化文本：将文本中的同义词或近义词替换为统一的词汇，以减少词汇的多样性。



## 工具集
### Jionlp

### jieba
# CV领域
