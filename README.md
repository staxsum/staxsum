# So, You Want to Build a Hidden Service…

**by stax**  
PGP: 35F7B19C3B078864

> [The advice in this article applies to anyone who wants to run a privacy-respecting service on the Tor network — journalists, researchers, activists, and developers alike.  
> The threat model considered here is that of a repressive or privacy-invasive environment, where maintaining anonymity and safety are legitimate needs.  
> The tone is that of an old hand who’s been around the block and wants you to avoid the mistakes that get people in trouble. If you misuse this knowledge for illegal purposes, that’s on you — not me.]

You’ve decided you’re tired of glossy, centralized web apps and analytics-stuffed platforms pretending to be “free.”  
You want to build something independent, something that respects privacy and speech. Good for you.

I used to run a fairly well-known hidden service — learned a lot the hard way. What that experience taught me was simple: privacy tools matter, but running them responsibly is harder than it looks. So let’s talk about doing it right.

---

## 1. Legal / Ethical

Before you do anything, understand the law where you live.  
Tor is legal almost everywhere, but how you use it determines whether you’re on the right side of the line.

- Read up on digital rights, whistleblower laws, data-protection acts, and freedom-of-press protections.  
- Learn about extradition treaties and Mutual Legal Assistance Treaties (MLATs) — those determine which governments cooperate on investigations.  

If you’re operating a privacy-critical service (like a journalist tip line):

- Choose hosting in a country with strong privacy laws and press protections.  
- Avoid “bulletproof” or shady hosts; they’re often scams or honeypots.  
- Look for providers that allow Tor usage in their Terms of Service and accept privacy-respecting payments (cryptocurrency, Monero, or prepaid options).

**Remember:** anonymity is not immunity. Tor won’t save you if you cross into illegal territory — hacking, harassment, trafficking.  

And for the record: don’t even think about “hacking back,” DDoS retaliation, or similar stunts. Those are crimes, and they destroy the reputation of the privacy tech community.

---

## 2. Technical

Running a hidden service securely is more than just installing Tor and crossing your fingers.

- Learn how Tor works:  
  - [Tor Project: Onion Services](https://community.torproject.org/onion-services/)  
  - [Freehaven.net AnonBib](https://www.freehaven.net/anonbib/)  
- Keep up with the Tor Project mailing lists.  
- Install Tor locally and experiment with a test hidden service for HTTP and SSH.  
- Bind your hidden services to `localhost` and firewall off everything else.  
- Add transparent proxy rules to prevent IP leaks.  

Keep your system updated:

- Minimal OS, disable unnecessary daemons, don’t install unknown software.  
- Compile software yourself when possible. Harden builds with compiler protections and sandboxing (AppArmor, SELinux, Firejail).  

**Always:** connect to your server only via its onion address. Automate upgrades, redeployments, and destruction of compromised services. Keep clocks in UTC.  

Advanced setups:

- Run your own Tor relays or bridges to contribute bandwidth and provide predictable entry points.  
- Use obfs4 or meek transports to disguise Tor traffic in censored regions.  

---

## 3. Operational Security

Operational hygiene separates hobbyists from careful operators.

- Use a dedicated machine for your onion operations, separate from your everyday device. Prefer Linux (Debian or Tails).  
- Encrypt the disk with a strong passphrase; never reuse passwords.  
- Avoid blending personal and onion identities.  
- Minimize or eliminate logs; if necessary, keep them ephemeral and encrypted.  
- Practice disciplined writing style to avoid stylometric deanonymization.  
- Encrypt communications: PGP for email, Signal or Ricochet for messaging.  
- Wipe memory after shutdown (memtest86+, Tails handles this automatically).  
- Securely back up your hidden service hostname and private key offline.  
- Use reproducible build scripts for migrations (Ansible, Bash).  

**Focus on simplicity and correctness** — VPN + Tor + multiple proxies is useless if code leaks headers or the host is compromised.  

---

## 4. Take-Away

- Tor alone is not enough. Privacy is a discipline, not a checkbox.  
- Learn the network. Respect the law. Protect your users’ safety.  
- Anonymity is a tool, not a license. Build things worth protecting.  

---

## References

- Tor Project Mailing Lists  
- Transparent Proxy Guide  
- Tor Bridges Documentation  
- Pluggable Transports (obfs4, meek)  
- Cold Boot Attacks & RAM Forensics  
- EFF: Surveillance Self-Defense  

---

## License

This work is licensed under **[Creative Commons Zero v1.0 Universal (CC0 1.0)](https://creativecommons.org/publicdomain/zero/1.0/)** — it is dedicated to the public domain. You may copy, modify, distribute, and perform the work, even for commercial purposes, without asking permission.
