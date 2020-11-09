# Simple SMTP-Enumeration Python Script

#!/usr/bin/python
import socket
import sys

if len(sys.argv) !=3:
    print “uses ./smtp-enum.py <IP> <user>”
        exit(0)
     
ip=sys=argv[1]
user=argv[2]

s=socket.socket(socket.AF_INET, socket.sock_STREAM)

connect= s.connect((ip,25))
banner=s.recv(1024)

print banner

s.send('vrfy ‘ + user + ‘\r\n’)
result=s.recv(1024)
print result
s.close()
