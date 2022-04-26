# w8 (SSL) &  (IPSec)  220426

Secure Socket Layer (SSL)  Advanced Handshake Protocol

Internet Protocol Security (IPSec)





# Client Authentication Handshake

![image-20220426152555699](https://raw.githubusercontent.com/letsgomelck/Picsee/main/Picsee/image-20220426152555699rpyB5a.png)

# q6

(6) Diffie-Hellman key agreement protocol is insecure because it is vulnerable to ___. 

 

A. Known plaintext attack 

B. Dictionary attack

C. Eavesdropping attack

D. Man-in-the-middle attack



答案





# SSL Session Resumption

![image-20220426152835417](https://raw.githubusercontent.com/letsgomelck/Picsee/main/Picsee/image-20220426152835417gCjaHc.png)

# Session Resumption Handshake

![image-20220426152853217](https://raw.githubusercontent.com/letsgomelck/Picsee/main/Picsee/image-20220426152853217Lx77oU.png)

# 6.3 Chapter 6 Security Protocols—— IPSec

## IPsec Architecture

![Screen Shot 2022-04-26 at 15.56.19](https://raw.githubusercontent.com/letsgomelck/Picsee/main/Picsee/Screen Shot 2022-04-26 at 15.56.19vSmLHm.png)

## Various Packets

![Screen Shot 2022-04-26 at 15.56.54](https://raw.githubusercontent.com/letsgomelck/Picsee/main/Picsee/Screen Shot 2022-04-26 at 15.56.54o9Z0rP.png)



## IPSec

•A collection of protocols (RFC 2401)



  –Authentication Header (AH)

​    •RFC 2402



 –Encapsulating Security Payload (ESP)

​    •RFC 2406



 –Internet Key Exchange (IKE)

​    •RFC 2409



 –IP Payload Compression (IPcomp)

​    •RFC 3137



## IKE - Internet Key Exchange (IKE)

•Exchange and negotiate security policies 



•Establish security sessions

   –Identified as *Security Associations*



•Key exchange



•Key management



### How It Works

•IKE operates in two phases

   –Phase 1: negotiate and establish an auxiliary end-to-end secure channel

​           •Used by subsequent phase 2 negotiations

​           •Only established once between two end points!



   –Phase 2: negotiate and establish custom secure channels

​           •Occurs multiple times



•Both phases use Diffie-Hellman key exchange to establish a shared key



•IKE protocol initial message exchanges are not encrypted.



•IKE uses (normally) the UDP port 500.



## Internet Key Exchange (IKEv2)

https://www.rfc-editor.org/rfc/rfc6954.html



Using the Elliptic Curve Cryptography (ECC) Brainpool Curves for the Internet Key Exchange Protocol Version 2 (IKEv2) https://www.rfc-editor.org/rfc/rfc6954.html



A traffic selector is an agreement between IKE peers to permit traffic through a tunnel if the traffic matches a specified pair of local and remote addresses. 



![image-20220426160050879](https://raw.githubusercontent.com/letsgomelck/Picsee/main/Picsee/image-2022042616005087917xBaU.png)



## Authentication Header (AH)

•Provides source authentication

​    –Protects against source spoofing



•Provides data integrity



•Protects against replay attacks

​    –Use monotonically increasing sequence numbers

​    –Protects against denial of service attacks



•NO protection for confidentiality!



### AH Details

•Use 32-bit monotonically increasing sequence number to avoid replay attacks



•Use cryptographically strong hash algorithms to protect data integrity (96-bit)

​	–Use symmetric key cryptography

​	–HMAC-SHA-96, HMAC-MD5-96 



### AH Packet Details

![Screen Shot 2022-04-26 at 16.10.21](https://raw.githubusercontent.com/letsgomelck/Picsee/main/Picsee/Screen Shot 2022-04-26 at 16.10.21j64I2s.png)

## ESP Encapsulating Security Payload

•Provides all that AH offers, and



•in addition provides data confidentiality

​	–Uses symmetric key encryption