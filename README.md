# cert-deploy-t1600g-28ps

The TP-Link T1600G-28PS switch (and similar in that family) support ssl, and the certificate and key can be set programmatically over telnet.

This repository includes a letsencrypt deploy hook comprising an expect script and bash wrapper for automating that process from a raspberry pi.

# Requirements

- Install `tftpd-hpa` and start it. The switch downloads certs and keys over tftp, telnet just starts that process. There is no direct upload.
- Install `expect`
- Place the `switch` hook script in the letsencrypt deploy hooks directory.
-- `chmod +x` the file if necessary.
- Create a further file in the pi user directory, `.switchcredentials`, a plain text file with 3 lines (and a final newline at the end of the file):

```
iporhostname.of.your.switch
telnetusername
telnetpassword
```

