Расклад карт делают многие, но кто из этих задумывался, что реально за этим стоит? К чему все эти перестановки?

"Да это же бинарная классификация!" - подумал Федя, рассмотрев внимательно лежащие перед ними карты, но не таро. - "Есть люди, верящие картам, и люди, считающие их совершенно антинаучными, вследствие чего абсолютно бесполезными"

Вырожденный эллипс Инна лишь с таинственной улыбкой посмотрела в его глаза, чем повергла бедного шестигранника в ещё большую задумчивость... [shuffled.py](https://ctfd.deeg05.undo.it/files/5413ed715266a19b0139fb98544ecca8/shuffled.py)


from Crypto.Random.random import getrandbits  
import random  
  
a = getrandbits(16)  
random.seed(a)  
  
flag = list("infosec{fake_flag}")  
print(len(flag))  
random.shuffle(flag)  
print("".join(flag))  
  
# 27  
# 3s3o5_3s3gid_5but{f_n30dc}e


import random  
  
start = "3s3o5_3s3gid_5but{f_n30dc}e"  
flag = ''  
for i in range(2**16):  
    random.seed(i)  
    new_text = list(range(len(start)))  
    random.shuffle(new_text)  
    ans = [0 for j in range(len(start))]  
    for j in range(len(new_text)):  
        ans[new_text[j]] = start[j]  
    ans = ''.join(map(str, ans))  
    if "infosec" in ans:  
        flag = ans  
        break  
print(flag)