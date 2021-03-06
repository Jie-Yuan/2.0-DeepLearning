## 特征工程
- 根据Tfidf/词频OneHot
- total_length
- num_words
- num_unique_words
- words_vs_unique: num_unique_words/num_words
- num_exclamation_marks: 感叹号
- num_question_marks: 问号
- num_punctuation: 标点
- num_symbols
- num_smilies

---
## 文本清洗
### 1. 正则
```python
pattern_char = re.compile('[A-Za-z]+')
pattern_chinese = re.compile('[\u4e00-\u9fa5]+')
# pattern = re.compile('[^A-Za-z\u4e00-\u9fa5]+')
```

### 2. 清洗
```
pattern = re.compile('[^a-z\u4e00-\u9fa5]+')
pattern_en = re.compile('[a-zA-Z]+')
with open('./title_words.txt', 'w') as ws, open('./title_chars.txt', 'w') as cs:
    for line in tqdm_notebook(df.title, "Cut ..."):
            if 4 <= len(line) <= 64:
                _ = pattern.sub(' ', line)
                _ = list(filter(lambda x: ' ' not in x, jieba.cut(_)))
                ws.writelines(' '.join(_) + '\n')
                cs.writelines(' '.join(sum([[w] if pattern_en.findall(w) else list(w) for w in _], []))+'\n')
```

```python
import re
import jieba_fast as jieba
from pipe import *

def read(file):
    with open(file) as f:
        return f.read()

from tqdm import tqdm
class readIter(object):
    def __init__(self, path):
        self.path = path

    def __iter__(self):
        with open(self.path) as file:
            lines = tqdm(file, desc="Processing ")
            for line in lines:
                # assume there's one document per line, tokens separated by whitespace
                yield line.lower().split()

def write(text, file, overwrite=True):
    if overwrite:
        with open(file, 'w') as f:
            f.write(text)
    else:
        with open(file, 'a') as f:
            f.write(text)

pattern = re.compile('[^0-9A-Za-z\u4e00-\u9fa5]+')
cut = Pipe(lambda x: jieba.lcut(x))
sub = Pipe(lambda x: pattern.sub(' ', x))

read_path = '/DATA/1_DataCache/NLP/Corpus/new_zhwiki/wikiCorpus.txt'
wirte_path = '/DATA/1_DataCache/NLP/Corpus/new_zhwiki/wikiCleaned.txt'
write(text_clean(read_path), wirte_path)
```
