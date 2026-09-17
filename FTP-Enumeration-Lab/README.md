# FTP Enumeration Lab

## Project Overview

This lab demonstrates the process of enumerating an FTP service on an authorized vulnerable lab machine.

The objective was to identify the FTP service, determine the software and version, test authentication controls, enumerate accessible directories, identify security weaknesses, and document appropriate remediation.

**Target:** `10.0.2.5`
**Attacker Machine:** Kali Linux
**Service:** FTP
**Port:** 21/TCP
**FTP Software:** vsFTPd 2.3.4

---

## 1. Service Discovery

Nmap was used to identify open ports and services on the target.

```bash
nmap -sS -sV -O 10.0.2.5
```

The scan identified:

```text
21/tcp open ftp vsftpd 2.3.4
```

This established that FTP was running on port 21.

---

## 2. FTP Banner Enumeration

I connected directly to the FTP service:

```bash
ftp 10.0.2.5
```

The server returned:

```text
220 (vsFTPd 2.3.4)
```

This confirmed the FTP software and version.

---

## 3. Anonymous Authentication Test

I tested whether anonymous authentication was enabled.

```text
Name: anonymous
```

The server responded:

```text
230 Login successful.
```

This confirmed that anonymous FTP authentication was enabled.

---

## 4. Directory Enumeration

After authentication, I checked the current remote directory:

```text
ftp> pwd
Remote directory: /
```

I then enumerated the directory contents:

```text
ftp> ls -la
```

The server returned the FTP root directory but no visible files or subdirectories.

This means anonymous access was confirmed, but no publicly accessible files were identified during this enumeration.

---

## 5. Automated Confirmation

Nmap's FTP anonymous-access script was used to independently verify the configuration:

```bash
nmap -p21 --script ftp-anon 10.0.2.5
```

Result:

```text
ftp-anon: Anonymous FTP login allowed (FTP code 230)
```

This independently confirmed that anonymous FTP authentication was enabled.

---

## Security Finding

### Finding: Anonymous FTP Authentication Enabled

**Risk:** Medium

Anonymous FTP authentication can allow unauthorized users to access FTP resources without a legitimate account.

The actual impact depends on the permissions assigned to the anonymous account. During this assessment, anonymous access to the FTP service was confirmed, but no visible files or directories were identified.

---

## Recommended Remediation

The following controls are recommended:

1. Disable anonymous FTP authentication unless there is a documented business requirement.
2. Prefer SFTP over traditional FTP where possible.
3. If FTP is required, use FTPS with TLS.
4. Upgrade unsupported or outdated FTP software.
5. Restrict FTP access using firewall rules and network segmentation.
6. Apply least-privilege permissions to FTP accounts.
7. Disable upload/write permissions unless specifically required.
8. Disable unused FTP accounts.
9. Monitor FTP authentication and file-transfer activity.
10. Regularly patch and scan the FTP service.

---

## Verification

After remediation, anonymous authentication should no longer succeed.

The following command can be used to verify the configuration:

```bash
nmap -p21 --script ftp-anon 10.0.2.5
```

The previous result:

```text
Anonymous FTP login allowed (FTP code 230)
```

should no longer be returned.

---

## Key Lessons Learned

* Port 21 identifies the FTP service but does not tell the whole security story.
* Service version enumeration helps identify the software running behind a port.
* FTP authentication controls should be tested during enumeration.
* `230 Login successful` confirmed successful anonymous authentication.
* Directory enumeration helps determine what resources an account can access.
* A security finding should describe the evidence, risk, and appropriate remediation rather than simply stating that a service is "vulnerable."

---

## Tools Used

* Kali Linux
* Nmap
* FTP Client
* VirtualBox
* Authorized vulnerable lab environment

---

## Evidence

Screenshots from the enumeration process are stored in the `screenshots` directory.
