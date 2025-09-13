# 🛡️ Paranoid OPSEC Manual
### Extreme Practices for Identity Protection and Operational Security

![Version](https://img.shields.io/badge/version-v1.0.0-purple)
![Last Update](https://img.shields.io/badge/updated-2025--09--13-red)

## Overview

The **Paranoid OPSEC Manual** is designed for investigators, journalists, and security practitioners who operate in **high-risk or hostile environments**.  It focuses on **no-compromise methods** for safeguarding identity, devices, communications, and evidence. 

- **Audience:** Professionals and practitioners who require the strictest levels of anonymity and compartmentalization.  
- **Scope:** Covers devices, networks, personas, communications, travel OPSEC, data handling, and adversary simulations.  
- **Approach:** Layered, paranoid-level security posture; continuous validation; defense-in-depth with zero trust assumptions.  

## 1. Scope & Assumptions

- **Audience:** OSINT investigators, journalists, DFIR analysts, CTI teams, compliance officers.
    
- **Use cases:** OSINT collections, dark web monitoring, covert outreach, digital forensics, source protection.
    
- **Legal/Ethics:** All activities must comply with applicable laws, platform ToS, and organizational ethics. This manual is for **defensive** and **legitimate investigative** use.
    

## 2. Threat Modeling & Risk Assessment

- **Adversaries:**
    
    - _Low:_ scammers, basic doxers, automated scraping.
        
    - _Medium:_ organized cybercrime, private intel shops, well-resourced harassers.
        
    - _High:_ state/security services, APT, cross-platform data brokers.
        
- **Capabilities:** data brokerage, device exploitation, SS7/SIM swap, ML-based deanonymization, cross-modal correlation (voice/face/gait), social graph inference, legal compulsion.
    
- **Assets:** identity, device, network location, sources, methods, evidence integrity, operational plans.
    
- **Risk matrix (example):**
    
    - Impact (Low/Med/High) × Likelihood (Low/Med/High) → control selection & escalation.
        
- **Outputs:** written threat model per case; control checklist; escalation triggers.
    

## 3. OPSEC Principles & Posture Levels

**Goal:** Define the foundational mindset and operational tiers that govern all other decisions in an investigation. These principles and posture levels serve as a baseline for tailoring security controls depending on case sensitivity and adversary profile.

### 3.1 Core Principles

- **Least Exposure:** Reveal only what is necessary for the task. Every extra data point can become an attack surface.
    
- **Compartmentalization:** Keep personas, devices, networks, and evidence completely isolated. Cross-contamination creates attribution risks.
    
- **Defense-in-Depth:** Layer multiple controls (technical, procedural, behavioral) so that a single failure does not expose the operation.
    
- **Need-to-Know:** Limit knowledge distribution both inside the team and with external stakeholders.
    
- **Minimize Metadata:** Strip or neutralize metadata in all shared content (photos, documents, messages).
    
- **Verify, Then Trust:** Assume deception by default. Validate identities, sources, and tools before use.
    
- **Continuous Review:** OPSEC is never static; it requires ongoing monitoring, audits, and adaptation.
    

### 3.2 Posture Levels

A four-tier posture system defines what protections to enforce depending on case sensitivity, adversary capability, and potential consequences.

#### **L0 – Routine Exposure**

- **Use case:** General OSINT browsing, public sources, low adversary risk.
    
- **Controls:**
    
    - VPN or hardened proxy; browser with basic fingerprint protections.
        
    - Hardened OS or dedicated VM.
        
    - Routine patching and endpoint hygiene.
        
    - Minimal persona setup, can overlap with semi-public analyst identity.
        

#### **L1 – Sensitive Operations**

- **Use case:** Investigating scams, cybercrime forums, or potentially hostile individuals.
    
- **Controls:**
    
    - Strict persona separation (unique email, browser profile, VM).
        
    - Encrypted storage for collected data.
        
    - Tor Browser or multi-hop VPN.
        
    - Metadata scrubbing of all shared content.
        
    - No crossover between personal and operational accounts.
        

#### **L2 – High-Risk Operations**

- **Use case:** Dark web infiltration, adversaries with technical sophistication, potential targeting of the analyst.
    
- **Controls:**
    
    - Dedicated hardware or Qubes/Tails OS per case.
        
    - Air-gapped storage for sensitive evidence.
        
    - Multi-hop anonymity (VPN→Tor, or chained VPNs).
        
    - Strict logging of all actions for accountability.
        
    - Persona register with lifecycle management.
        
    - Two-person rule for validation of high-risk actions.
        

#### **L3 – Critical/Hostile Environment**

- **Use case:** Investigating state actors, organized crime, or environments with strong surveillance.
    
- **Controls:**
    
    - Clean hardware purchased specifically for the operation.
        
    - No reuse of devices, SIMs, accounts, or networks.
        
    - Travel OPSEC enforced (burner devices, Faraday pouches, no personal phone).
        
    - One-time use personas with no long-term footprint.
        
    - Legal review and organizational approval required before operation.
        
    - All communications via deniable, strongly encrypted channels.
        

#### 🔥 Extreme Practices (Optional)
- Treat **L3** not as exceptional but as **default baseline**.  
- Rotate between **multiple hardware sets** in separate jurisdictions.  
- Maintain **duplicate infrastructures** (e.g., two distinct Tor/VPN paths for same task, cross-check results).  
- Conduct **threat simulation drills** (e.g., adversary seizes your device in 5 min – what leaks?).  
## 4. Identity & Persona Compartmentalization

**Goal:** Build and operate investigative personas that cannot be reliably linked to you, your organization, other personas, or prior operations—while remaining credible for the mission.

### 4.1 Definitions & Scope

- **Persona:** A constructed identity (name, contact points, device profile, behavior) used for investigative tasks.
    
- **Compartment:** A self-contained environment (device/VM, browser profile, password store, comms channels) dedicated to a single persona or case.
    
- **Cross‑contamination:** Any shared artifact (IP address, browser fingerprint, wording quirks, reused avatars, payment trail) that can link compartments.
    

### 4.2 Policy Baselines

- **One Persona = One Compartment** (device/VM, browser, password vault, comms, storage). No sharing.
    
- **Zero Reuse Rule:** No reuse of usernames, avatars, bios, recovery emails/phones, payment instruments, or VPN egress IPs across personas.
    
- **Attribution Budget:** Treat every artifact as a potential identifier. Keep the sum of identifiers per persona as low as possible.
    
- **Lifecycle Discipline:** Plan for **provision → operate → rotate → retire**, with documented criteria for each step.
    

### 4.3 Persona Lifecycle (Plan → Provision → Operate → Rotate → Retire)

**Plan**

- Define objectives, target platforms, required credibility (age of account, posting cadence, social graph).
    
- Choose risk level (L0–L3) from §3 and map mandatory controls.
    
- Run a pre‑provision conflict check to avoid collisions with real people/brands.
    

**Provision**

- Create **unique credentials** and recovery channels (no overlap with other personas).
    
- Stand up dedicated **VM/OS** (Qubes domain, separate VM, or dedicated device) and **browser profile**.
    
- Establish **contact points** (email/number) and **2FA** (hardware token per persona).
    

**Operate**

- Follow a **content and engagement script** (topics, tone, posting windows, reaction policy).
    
- Maintain **network separation** (distinct VPN exit/Tor circuit). Log sessions for post‑op review.
    
- Keep a **persona register** (metadata and link graph) updated after each session.
    

**Rotate** (when exposure risk rises or objectives change)

- Change exit IP ranges, posting windows, and low‑value attributes.
    
- Re‑issue credentials and regenerate keys as required.
    

**Retire**

- Tombstone gracefully (final benign message or silence, depending on OPSEC).
    
- Archive evidence, export logs, revoke tokens, destroy keys/seeds, wipe or reimage the compartment.
    

### 4.4 Persona Design (Credibility without Linkability)

- **Biographic outline:** plausible age, locale, language variant, time‑zone; avoid copying personal details or unique biographical events.
    
- **Backstory & cover:** minimal and congruent (job/education kept generic). Keep statements easy to maintain under questioning.
    
- **Style & linguistics:** align spelling, idioms, and punctuation with claimed locale. Randomize rhythm; avoid distinctive catchphrases. See §13.4 for stylometry OPSEC.
    
- **Visual identity:** avatars/banners with **lawful, licensed** stock or purpose‑made media. Avoid reusing GAN portraits across personas (researchers can cluster style). Strip EXIF before upload.
    
- **Social graph:** follow/connect gradually, mirroring normal user behavior. Seed with low‑risk follows before target engagement.
    

### 4.5 Provisioning: Accounts, Contact Points, and Payments

**Email**

- Create per‑persona mailboxes with providers supporting privacy and aliases: **Proton** ([https://proton.me](https://proton.me/)), **Tuta** ([https://tuta.com](https://tuta.com/)). Consider relay/aliasing (e.g., **SimpleLogin** [https://simplelogin.io/](https://simplelogin.io/) or **AnonAddy** [https://anonaddy.com/](https://anonaddy.com/)) for site‑specific addresses.
    
- Enable **2FA**; prefer **FIDO2 hardware keys** (per‑persona token). Keep recovery codes offline in the compartment vault.
    

**Phone / Voice**

- Use lawful VoIP/burner services with clear ToS (e.g., **JMP.chat** [https://jmp.chat/](https://jmp.chat/)). Avoid numbers tied to your identity; understand KYC requirements by jurisdiction.
    
- For high‑risk ops, avoid voice/SMS verification; prefer app‑based or hardware 2FA when platforms allow.
    

**Domains & Web Presence (optional)**

- If persona needs a site, register with **WHOIS privacy** enabled; separate registrar account and payment method; no analytics. Host static-only pages; disable logs where legal.
    

**Payments**

- Use organization‑approved methods (virtual cards, prepaid where lawful). Keep **receipts in encrypted vault**; never reuse payment instruments across personas.
    

### 4.6 Compartment Engineering (Devices, VMs, Browsers)

- **Device/VM:** one VM per persona (e.g., Qubes `persona‑x` AppVM) or a dedicated laptop. Snapshots before/after operations.
    
- **Browser:** dedicated profile per persona. Prefer **Tor Browser** (no extensions) or **Brave** hardened profile. Disable password sync/cloud features.
    
- **Password store:** separate **KeePassXC** vault per persona with its own strong passphrase; store in the persona’s compartment only.
    
- **Key material:** per‑persona PGP keys (GnuPG). Keep master/backup offline; use subkeys operationally.
    
- **Storage:** encrypt at rest (VeraCrypt/LUKS). Distinct containers for evidence vs. persona working data.
    

### 4.7 Network Separation & Traffic Hygiene

- **Exit isolation:** each persona uses a distinct **VPN egress IP** or **Tor circuit**. Do not alternate multiple personas over the same exit during overlapping windows.
    
- **Leak control:** enforce DNS/IPv6/WebRTC hardening. Validate at **ipleak.net** after every environment change.
    
- **Session windows:** schedule distinct activity windows per persona (time‑zone believable for the cover story). Vary posting times within natural ranges.
    
- **Geo‑consistency:** ensure IP geolocation matches claimed region; align with language and content cadence.
    

### 4.8 Operational Conduct (Content, Engagement, and Safety)

- **Content script:** predefine acceptable topics, tone, and red lines. Avoid statements that demand deep domain knowledge you cannot sustain.
    
- **Engagement playbook:** expected responses to DMs, friend requests, and provocations. Use templated, low‑commitment replies where possible.
    
- **Attachments:** scrub metadata (MAT2/ExifTool) and validate file types before opening inbound media. Never open untrusted files in the same compartment used for persona comms—use a disposable analysis VM.
    
- **Cross‑platform discipline:** do not copy/paste verbatim text across platforms. Vary formatting and timing to reduce correlation risk.
    

### 4.9 Deconfliction & Linkage Testing

- Before first use, run an **OSINT collision scan**: search proposed names/handles, image reverse‑search for avatars, and check for brand conflicts.
    
- Periodically audit the persona with outside‑in tests: browser fingerprint checks (AmIUnique), leaked credential searches (HaveIBeenPwned [https://haveibeenpwned.com/](https://haveibeenpwned.com/)), and social graph diffusion (manual review).
    
- Plant low‑risk **canary interactions** (e.g., distinct redirects) to detect unintended cross‑links between compartments.
    

### 4.10 Rotation & Retirement

- **Rotation triggers:** platform KYC prompts, unusual login alerts, direct targeting, change in mission scope, or accumulated attribution budget.
    
- **Rotation actions:** change exit infrastructure, regenerate keys, adjust posting windows/tone, refresh avatar/biographic minor details (keep core identity consistent to avoid suspicion).
    
- **Retirement:** export evidence, revoke API tokens, delete or freeze accounts per policy, destroy keys/seeds, wipe/reimage the compartment. Update the persona register to **RETIRED** with rationale and date.
    

### 4.11 Records & Templates

Maintain a **Persona Register** (stored inside an encrypted case vault):

- `Persona ID`, `Handle(s)`, `Creation Date`, `Purpose/Case`, `Risk Level (L0–L3)`, `Email`, `Phone/IM`, `2FA method`, `Device/VM ID`, `VPN/Tor profile`, `Notes on style/locale`, `Known contacts`, `Rotation history`, `Retirement date & reason`.
    

**Checklists (quick use):**

- **Pre‑Provision:** name/handle collision check; decide risk level; prepare VM; create email/2FA; set password vault; note recovery codes.
    
- **Go‑Live:** fingerprint test; IP geo check; seed social graph; first low‑risk posts; log session.
    
- **Ongoing:** vary cadence; keep logs; run periodic linkage tests; update register.
    
- **Sunset:** archive, revoke, wipe, document.

#### 🔥 Extreme Practices (Optional)
- Use **one-time personas** – identities should exist only for a single task, then be retired.  
- Operate personas exclusively on **burner hardware** purchased anonymously and destroyed after use.  
- Apply **stylometric masking**: alter writing style, vocabulary, errors, and tone depending on the persona.  
- Maintain **multi-layered identities**: one as a primary cover, one as a decoy, and one as a “sacrificial” persona ready for intentional exposure.  
- Never repeat the same **activity patterns** (time of day, session length, UI language) across multiple personas.  

## 5. Device & Endpoint Security

**Goal:** Prevent endpoint compromise and leakage of identifiers by hardening platforms, controlling execution, encrypting data, and validating boot trust. Controls are mapped to posture levels (L0–L3) from §3.

### 5.1 Platform Profiles (When to Use What)

- **Qubes OS** — strong compartmentalization via Xen VMs; ideal for L2–L3 where isolation between personas/cases is mandatory. [https://www.qubes-os.org/](https://www.qubes-os.org/)
    
- **Tails** — amnesic, Tor‑routed live OS; ideal for one‑off high‑risk browsing or sensitive transfers (L2–L3). [https://tails.boum.org/](https://tails.boum.org/)
    
- **Whonix** — Tor‑gateway + workstation model inside VMs; good for anonymity workflows (L1–L2). [https://www.whonix.org/](https://www.whonix.org/)
    
- **Hardened Linux (Debian/Fedora/Ubuntu)** — daily driver with AppArmor/SELinux enforced; suitable for L0–L2.
    
- **Windows 11 (Hardened)** — enable BitLocker, VBS/HVCI, WDAC/ASR; enterprise telemetry minimized; suitable for L0–L2.
    
- **macOS (Hardened)** — FileVault, Gatekeeper, notarization; consider Lockdown Mode on iOS companion devices; suitable for L0–L2.
    
- **Mobile (GrapheneOS)** — hardened Android with strong permission model; use as comms endpoint for L1–L3. [https://grapheneos.org/](https://grapheneos.org/)
    

**Mapping tip:** If your adversary can compel providers or run device exploits → prefer Qubes/Tails + strict compartmentalization.

### 5.2 Boot & Firmware Trust

- **UEFI Secure Boot**: **ON**; vendor keys or custom MOK where needed. Linux check: `mokutil --sb-state`; Windows check: `Confirm-SecureBootUEFI`.
    
- **TPM 2.0**: present and **owned**; bind disk encryption to TPM+PIN where feasible.
    
- **BIOS/UEFI**: admin password set; external boot **disabled**; Thunderbolt security **enabled**; DMA protection **on**.
    
- **Firmware updates**: apply via LVFS/fwupd where supported: `fwupdmgr get-devices && fwupdmgr get-updates` ([https://fwupd.org/](https://fwupd.org/)). Record versions in the case log.
    

### 5.3 Storage, Encryption & Secrets

- **Full‑Disk Encryption**:
    
    - Linux: LUKS2 with strong PBKDF (argon2id), separate /boot if Secure Boot measured.
        
    - Windows: BitLocker (XTS‑AES‑256), recovery key stored offline.
        
    - macOS: FileVault 2 (enable institutional recovery key if in org setting).
        
- **Hidden/deniable volumes**: VeraCrypt containers for sensitive materials ([https://www.veracrypt.fr/](https://www.veracrypt.fr/)). Use cautiously and lawfully.
    
- **Secrets management**:
    
    - Passwords in **KeePassXC** (one vault per persona/case): [https://keepassxc.org/](https://keepassxc.org/)
        
    - Crypto/short secrets with **age** or **GnuPG**: [https://github.com/FiloSottile/age](https://github.com/FiloSottile/age) • [https://gnupg.org/](https://gnupg.org/)
        
- **Hardware tokens (FIDO2/OpenPGP)**: YubiKey / SoloKeys for per‑persona 2FA & key storage: [https://www.yubico.com/](https://www.yubico.com/) • [https://solokeys.com/](https://solokeys.com/)
    

### 5.4 Application Control & Sandboxing

- **Windows**:
    
    - **WDAC** (Windows Defender Application Control) policy or **AppLocker** allowlists for L2–L3.
        
    - **ASR Rules** (Attack Surface Reduction): block Office child processes, script abuse, and LSASS credential theft. Enable via PowerShell (see §5.13).
        
    - **Controlled Folder Access** for ransomware mitigation.
        
- **Linux**:
    
    - **AppArmor**/**SELinux** in **enforcing** mode; use Flatpak for sandboxed apps; **Firejail** to isolate risky binaries: [https://firejail.wordpress.com/](https://firejail.wordpress.com/)
        
- **macOS**:
    
    - Gatekeeper **enabled**; restrict to App Store + identified developers; leverage TCC prompts; avoid kexts; disable unsigned system extensions.
        

### 5.5 Peripherals, USB & Side‑Channels

- **USB**:
    
    - Disable autorun everywhere.
        
    - Linux: **USBGuard** (allowlist policy): [https://usbguard.github.io/](https://usbguard.github.io/)
        
    - Windows: Group Policy → Device Installation Restrictions (block new device classes except approved).
        
- **Network radios**: disable unused (BT/NFC); randomize Wi‑Fi MAC; avoid auto‑join.
    
- **HID injection** defenses: restrict new keyboards/mice; verify device IDs on connection; prefer **data‑only** USB cables for charging.
    

### 5.6 Updates, Telemetry & Logging

- **Patching**: OS and firmware monthly (or faster for L2–L3); browser daily.
    
- **Telemetry**: reduce to minimum compatible with security; avoid 3rd‑party analytics in investigative compartments.
    
- **Logging**: capture **local** security logs needed for audits, but **export** to an encrypted vault separate from operational compartments. Do not transmit logs to external cloud SIEMs from sensitive personas without de‑identification policies.
    

### 5.7 Backup & Recovery (3‑2‑1)

- **3 copies**, **2 different media**, **1 offline/off‑site**.
    
- Tools: **BorgBackup** ([https://www.borgbackup.org/](https://www.borgbackup.org/)), **restic** ([https://restic.net/](https://restic.net/)), **rclone** ([https://rclone.org/](https://rclone.org/)).
    
- Always encrypt backups (repo keys offline); test restores quarterly; hash manifests.
    

### 5.8 Mobile Endpoints

- **Device policy**: separate phones for personal vs. operational personas; prefer GrapheneOS for Android; iOS use **Lockdown Mode** where threat justifies.
    
- **Baseband risk**: assume cellular radio is observable; avoid sensitive ops on mobile networks; prefer wired or trusted Wi‑Fi via VPN/Tor.
    
- **Permissions**: deny default access to mic/camera/location; use hardware camera shutters and mic mute switches when available.
    

### 5.9 Golden Images & Reproducibility

- Maintain **golden VM templates** per posture level (L0–L3).
    
- Provision ephemeral **linked clones** per case/persona; destroy after operation.
    
- Automate hardening with **Ansible** (Linux) or **PowerShell DSC/Intune** (Windows) to keep builds consistent and auditable.
    

### 5.10 EDR/AV Considerations (Trade‑offs)

- **Windows Defender** with ASR + cloud protection **on** is acceptable for many L0–L1 use cases; for L2–L3 consider stricter WDAC and reduced telemetry profiles.
    
- **Linux/macOS**: lightweight AV (ClamAV) as needed; rely on sandboxing and least‑privilege.
    
- Avoid vendor agents that introduce identifiable telemetry into sensitive compartments.
    

### 5.11 Validation Checklists & Commands

**Boot & encryption status**

- Linux:
    
    - Secure Boot: `mokutil --sb-state` • TPM: `tpm2_getcap properties-fixed`
        
    - LUKS volumes: `lsblk -f` then `cryptsetup status <mapper>`
        
- Windows PowerShell:
    
    - Secure Boot: `Confirm-SecureBootUEFI`
        
    - BitLocker: `Get-BitLockerVolume | Select MountPoint,VolumeStatus,EncryptionMethod`
        
    - VBS/HVCI: `Get-CimInstance -ClassName Win32_DeviceGuard | Select *`
        
- macOS:
    
    - FileVault: `fdesetup status` • Gatekeeper: `spctl --status`
        

**Sample hardening commands (Windows, run as Admin)**

```powershell
# Enable key ASR rules (example subset)
$rules = @(
  "D4F940AB-401B-4EFC-AADC-AD5F3C50688A", # Block Office child processes
  "3B576869-A4EC-4529-8536-B80A7769E899", # Block credential stealing from LSASS
  "5BEB7EFE-FD9A-4556-801D-275E5FFC04CC", # Block execution of potentially obfuscated scripts
  "BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550"  # Block executable content from email and webmail
)
Add-MpPreference -AttackSurfaceReductionRules_Ids $rules -AttackSurfaceReductionRules_Actions Enabled

# Turn on Controlled Folder Access
Set-MpPreference -EnableControlledFolderAccess Enabled

# Check BitLocker status
Get-BitLockerVolume | Format-Table -AutoSize
```

**Sample hardening commands (Linux)**

```bash
# AppArmor enforcing
sudo aa-status || sudo aa-enforce /etc/apparmor.d/*

# Verify Secure Boot and firmware updates
mokutil --sb-state
fwupdmgr get-devices && fwupdmgr get-updates

# Create and mount a LUKS2 container
sudo dd if=/dev/zero of=secure.img bs=1M count=4096
sudo cryptsetup luksFormat --type luks2 --pbkdf argon2id secure.img
sudo cryptsetup open secure.img securevault
sudo mkfs.ext4 /dev/mapper/securevault && sudo mount /dev/mapper/securevault /mnt
```

### 5.12 Posture Mapping (L0–L3) — Key Endpoint Controls

|Posture|OS/Env|Boot Trust|Encryption|Exec Control|Network/Browser|Notes|
|---|---|---|---|---|---|---|
|**L0**|Hardened Linux/Win/macOS|Secure Boot on|FDE on|Basic AV, no unsigned installs|VPN, hardened browser|Routine OSINT|
|**L1**|Hardened Linux/Win/macOS|Secure Boot + TPM|FDE + vaults|ASR/AppArmor enforcing|VPN/Tor; anti‑leak checks|Separate persona VM|
|**L2**|Qubes/Whonix/Tails|Secure Boot strict|FDE + offline backups|WDAC/AppLocker; SELinux enforcing|Tor‑first; kill‑switch|Air‑gapped evidence|
|**L3**|Qubes + Tails|Custom keys, measured boot|FDE + deniable containers|Full allowlist; no dynamic code|Tor bridges; no personal devices|Dedicated hardware, no reuse|

> Record all settings (with commands and outputs) in the case log for auditability and repeatability.

#### 🔥 Extreme Practices (Optional)
- Rely only on **disposable devices** (burner laptops/phones) that are physically destroyed after the mission.  
- Configure hardware entirely offline with **custom firmware** (e.g., coreboot, Heads) and your own Secure Boot keys.  
- Never store credentials or keys in RAM – assume adversaries can perform **cold boot attacks**.  
- Split operations across **dedicated machines**: one for research, one for communications, one for data analysis.  
- Apply an **air-gap-first policy**: evidence analysis and archival should only occur on machines with no network interfaces.  
- In extreme contexts: use **hardware purchased abroad**, operated only locally, never transported across borders.  

## 6. Browser, Fingerprinting & Content OPSEC

### 6.1 Fingerprinting Risks
Web browsers are one of the **most fingerprintable tools** an investigator uses.  
Even without cookies, sites can identify and track users via:  
- **Headers** (User-Agent, Accept-Language, Referer).  
- **Screen resolution & color depth**.  
- **Fonts and plugins**.  
- **Time zone & system locale**.  
- **WebGL / Canvas rendering hashes**.  
- **Audio context fingerprints**.  
- **Hardware information** (CPU cores, GPU vendor, battery stats).  

### 6.2 Browser Hygiene
- Maintain **separate browser profiles** per persona or investigation.  
- Use different **default languages, time zones, and OS UI locales** to avoid overlaps.  
- Disable **autofill, password managers, and syncing**.  
- Always use **private browsing/incognito** but understand it does **not prevent fingerprinting**.  

### 6.3 Isolation Techniques
- For high-risk operations, use **dedicated VMs or containers** with a fresh browser instance for each session.  
- Do not mix work and personal browsing on the same system.  
- Consider **sandboxed browsers** (e.g., via Firejail, Qubes DisposableVMs).  
- Use **different user agents** and rotate them across personas.  

### 6.4 Anti-Fingerprinting Tools
- **Tor Browser**: best-in-class for uniform fingerprinting; all users look alike.  
- **Mullvad Browser**: similar to Tor Browser but without enforced Tor routing.  
- **Brave**: offers fingerprint randomization, but not foolproof.  
- **Firefox + arkenfox**: hardened with custom configs, but increases uniqueness.  
- Test fingerprints regularly via:  
  - [https://coveryourtracks.eff.org/](https://coveryourtracks.eff.org/)  
  - [https://browserleaks.com/](https://browserleaks.com/)  

### 6.5 Content Handling OPSEC
- Treat **downloads** as potentially dangerous:  
  - PDFs may contain beacons.  
  - Office docs may contain macros.  
- Always open files in **sandboxed environments**.  
- Strip metadata from documents and images before sharing.  
- For screenshots, use tools that avoid embedding device metadata.  
- Never paste investigation content directly between personas → use an **air-gap or controlled transfer channel**.  

#### 🔥 Extreme Practices (Optional)
- Never use a **general-purpose browser** for high-risk investigations. Instead, run **disposable hardened browsers** inside **ephemeral VMs** (destroyed after each session).  
- Disable all **JavaScript, WebRTC, and WebGL** by default; only enable in tightly controlled test environments.  
- Use **network-layer obfuscation**: VPN/Tor routing combined with traffic padding to defeat timing analysis.  
- Employ **browser compartment switching**: e.g., one VM for passive observation (Tor Browser, no login), another for active interaction (burner identity, Mullvad Browser).  
- For the most sensitive work:  
  - Access content via **remote disposable proxies** (e.g., headless browser in the cloud, viewed through VNC with no direct connection).  
  - Download suspect files only via **air-gapped intermediary machines**, then analyze with **multi-layer sandboxes**.  
- Assume all browser activity can be **correlated over time** — rotate entire **device/browser/VM stacks** frequently.  

## 7. Network & Transport Security

### 7.1 Threat Landscape
Networks are often the **weakest link** in OPSEC. Even if devices are hardened, traffic analysis, metadata collection, and interception can compromise identities.  
- **Passive surveillance**: ISPs, IXPs, governments recording traffic.  
- **Active interception**: MITM, rogue access points, DNS poisoning.  
- **Metadata correlation**: timing analysis, packet size signatures, cross-jurisdiction data sharing.  
- **Commercial tracking**: advertising networks, third-party analytics.  

### 7.2 VPN Usage
- Use only **trusted, audited VPNs** with strong no-log policies.  
- Prefer VPN providers outside your own jurisdiction.  
- Avoid free or unverified VPNs (high risk of data monetization).  
- Chain VPNs with Tor when stronger unlinkability is needed.  
- Always test for **DNS and WebRTC leaks** after connecting.  

### 7.3 Tor & Onion Routing
- **Tor Browser** ensures traffic looks like every other Tor user.  
- Bridges and pluggable transports (obfs4, meek) help evade censorship.  
- Never log into personal accounts via Tor.  
- Use **separate circuits** for different personas.  
- Be mindful of exit node monitoring – never transmit plaintext sensitive data.  

### 7.4 Proxies & Chaining
- HTTP/SOCKS proxies can add layers but do not provide encryption.  
- Use **multi-hop configurations**: VPN → Tor → Proxy or vice versa.  
- For OSINT scraping, rotating proxies can reduce account lockouts.  
- Avoid commercial “residential proxy” services tied to user devices (ethical and OPSEC concerns).  

### 7.5 DNS & Resolution
- Use **encrypted DNS** (DoH or DoT).  
- Consider self-hosted recursive resolvers (e.g., Unbound, Knot Resolver).  
- Be aware that DNS queries often reveal as much as web traffic itself.  
- Monitor with tools like [dnscrypt-proxy](https://github.com/DNSCrypt/dnscrypt-proxy).  

### 7.6 Wi-Fi & Access Points
- Never connect to public Wi-Fi without VPN or Tor.  
- Assume hotel, airport, and café Wi-Fi are **hostile by default**.  
- Randomize **MAC addresses** (modern OS can do this automatically).  
- Prefer tethered connections from burner mobile devices when possible.  

### 7.7 Transport Layer Security
- Always enforce HTTPS (use [HTTPS Everywhere](https://www.eff.org/https-everywhere) or built-in equivalents).  
- Validate certificates when in doubt; avoid click-through.  
- Consider using **TLS fingerprint randomization** (e.g., uTLS libraries for custom clients).  

### 7.8 Monitoring & Testing
- Check connections with [Wireshark](https://www.wireshark.org/) or [mitmproxy](https://mitmproxy.org/).  
- Test VPN leaks at [ipleak.net](https://ipleak.net).  
- Run periodic audits: does your IP/geolocation ever leak?  

#### 🔥 Extreme Practices (Optional)
- Chain multiple **independent network layers**: e.g., local VPN → Tor → foreign VPN → custom proxy. Each in a different jurisdiction.  
- Rotate entire network stacks frequently — new SIM, new VPN provider, new Tor bridges — to avoid long-term correlation.  
- Treat **all ISPs as compromised**: never rely on provider secrecy.  
- Use **satellite internet** or **shortwave/radio links** in extreme denial-of-service or censorship scenarios.  
- For sensitive transfers, use **sneakernet**: physically move data on encrypted drives via trusted couriers instead of any online channel.  
- Employ **traffic shaping and padding** (e.g., obfs4, meek, Snowflake, VPN obfuscation modes) to make packet sizes and timing indistinguishable.  
- Consider **multi-jurisdictional relays** you control (self-hosted VPN endpoints in foreign countries).  
- For ultimate deniability: **one-time network identities** – a SIM or access point is used only once, then permanently discarded.  
## 8. Communications Security (COMSEC)

### 8.1 Threat Landscape
Communication metadata is often more dangerous than content. Even with encryption, adversaries can learn:  
- Who talks to whom, when, and how often.  
- Device identifiers (IMEI, IMSI, MAC).  
- Location through cell towers, Wi-Fi, or timing correlation.  
- Patterns of activity that reveal persona overlaps.  

### 8.2 Principles of Secure Communication
- **Confidentiality**: protect message content with strong encryption.  
- **Anonymity**: avoid linking messages to real identity.  
- **Plausible deniability**: ensure you can credibly deny authorship.  
- **Ephemerality**: minimize persistence of communications.  

### 8.3 Messaging Tools
- **Signal**: strong end-to-end encryption, but tied to phone numbers.  
- **Wire**: supports pseudonymous registration, strong encryption.  
- **Session**: onion-routed messaging with no central metadata.  
- **Briar**: peer-to-peer over Tor or Bluetooth/Wi-Fi direct, no central servers.  
- **Element (Matrix)**: decentralized, strong encryption, but servers may log metadata.  

⚠️ Rule of thumb: **if the app requires your phone number, it leaks metadata**.  

### 8.4 Voice & Video
- Use encrypted apps (Signal, Wire, Jitsi with E2EE).  
- Be mindful of voice biometrics: adversaries can fingerprint your speech.  
- Consider voice changers or text-to-speech in sensitive ops.  
- Avoid landlines and unencrypted VoIP providers.  

### 8.5 Email
- Use providers with strong privacy policies (ProtonMail, Tutanota).  
- For high-risk, use **self-hosted mail with Tor hidden services**.  
- Always use **PGP or age** for sensitive content, but remember: PGP does not hide metadata.  
- Avoid reusing recovery emails across personas.  

### 8.6 Metadata Minimization
- Disable read receipts, typing indicators, and online status.  
- Use burner accounts created over Tor with disposable emails.  
- Avoid group chats that mix multiple personas.  
- Strip EXIF and headers from file attachments.  

### 8.7 Key Management
- Use strong passphrases for encryption keys.  
- Rotate keys regularly; never reuse across personas.  
- Store master keys offline on hardware tokens (e.g., YubiKey, Nitrokey).  
- Distribute keys via out-of-band channels (QR codes, paper slips, encrypted removable media).  

### 8.8 Ephemeral Practices
- Prefer apps with **disappearing messages** (Signal, Session, Wire).  
- Manually delete logs and caches after sensitive conversations.  
- Use **burner phones** for temporary comms and destroy them after use.  
- Assume all cloud backups of chats are hostile.  

#### 🔥 Extreme Practices (Optional)
- Eliminate all persistent messaging platforms: use **one-time communication channels only**, then destroy keys and devices.  
- Pre-share **one-time pads (OTPs)** or keys on air-gapped devices before operations.  
- Communicate via **encrypted containers** (e.g., VeraCrypt, age) exchanged offline via sneakernet or air-gapped transfer.  
- Employ **steganography**: hide encrypted messages inside images, audio, or video.  
- Use **voice masking or text-to-speech** to prevent biometric voiceprint collection.  
- For high-risk contacts, establish **multi-channel communication redundancy** (e.g., one channel for urgent signals, one for fallback, one as decoy).  
- In extreme cases: use **non-digital communication** (dead drops, coded signals, couriers) to eliminate all electronic traces.  
- Treat every communication channel as **compromised by default**; rotate frequently and assume metadata is logged indefinitely.  

## 9. Data Handling, Evidence & Chain of Custody

### 9.1 Core Principles
- **Integrity**: preserve original data without alteration.  
- **Authenticity**: ensure evidence can be verified as genuine.  
- **Confidentiality**: prevent leaks during collection, transfer, or storage.  
- **Auditability**: maintain a complete record of actions taken.  

### 9.2 Collection
- Use **forensically sound methods** (write blockers, disk imaging tools).  
- Always work on **copies**; keep the original in secure storage.  
- Log every action: who collected, when, where, and how.  
- For OSINT captures:  
  - Record URLs, timestamps, and context.  
  - Take **screenshots and video captures** with hashes.  
  - Store **original HTML and metadata** where possible.  

### 9.3 Storage
- Encrypt all evidence at rest (AES-256, LUKS2, VeraCrypt, BitLocker).  
- Use **redundant storage**: at least 3 copies, including offline media.  
- Maintain **hash manifests** for every file (SHA-256 preferred).  
- Store master logs in **tamper-evident formats** (append-only, digitally signed).  

### 9.4 Chain of Custody
- Maintain a **chain of custody log** recording every handler, date, and action.  
- Use digital signatures (PGP, age) to authenticate transfers.  
- Label physical media with unique IDs and store in tamper-proof bags or cases.  
- Use hardware tokens or secure vaults for credential storage.  

### 9.5 Transfer
- Prefer **physical transfer** (encrypted external drives) over cloud uploads.  
- When digital transfer is unavoidable:  
  - Use **end-to-end encrypted channels** (OnionShare, Magic Wormhole, SecureDrop).  
  - Split large datasets into **encrypted shards** and send separately.  
  - Always verify hashes after transfer.  

### 9.6 Verification & Validation
- Verify evidence authenticity with cryptographic checksums.  
- Use multiple hashing algorithms (SHA-256 + BLAKE2b).  
- Cross-check timestamps with OSINT tools (Wayback Machine, archive.today).  
- Document validation results in case logs.  

#### 🔥 Extreme Practices (Optional)
- Collect evidence only on **air-gapped forensic workstations**, never connected to the internet.  
- Transfer via **one-way data diodes** or write-once optical media.  
- Use **plausible deniability containers** (hidden VeraCrypt volumes, deniable LUKS headers) for the most sensitive datasets.  
- Store evidence in **geographically distributed vaults**, with key shares split across multiple trusted custodians (Shamir’s Secret Sharing).  
- Implement **time-release encryption**: evidence can only be decrypted after a defined period or quorum agreement.  
- Maintain **parallel chains of custody**: one real, one decoy, to mislead adversaries during audits.  
- After mission completion, conduct a **forensic wipe** of all temporary analysis environments and destroy intermediary drives physically.  
- Treat all evidence as **toxic data**: access only when strictly necessary, minimize copies, and assume adversaries may attempt **supply-chain poisoning** (inserting false data into your evidence pool).  

## 10. Social & Behavioral OPSEC

### 10.1 Threat Landscape
Even when devices, networks, and personas are secure, **behavioral patterns** can betray an operator.  
Adversaries often exploit:  
- Writing style and tone (stylometry).  
- Posting times and activity windows.  
- Choice of topics and vocabulary.  
- Cross-platform behavior overlaps.  
- Psychological manipulation via social engineering.  

### 10.2 Digital Hygiene
- Avoid posting from personal and operational accounts on the same device.  
- Vary posting times to avoid time zone correlation.  
- Avoid consistent idioms, emoji use, or unique phrasing across personas.  
- Do not recycle avatars, bios, or interests between identities.  
- Strip metadata from uploaded images and files.  

### 10.3 Stylometry Awareness
- AI and forensic tools can match authorship based on writing style.  
- To reduce risks:  
  - Shorten sentences, vary structure, and change punctuation habits.  
  - Use different spelling variants (US vs UK English, etc.) across personas.  
  - Randomize vocabulary and tone (formal vs casual).  
  - Use text transformation tools sparingly; verify for naturalness.  

### 10.4 Social Media Behavior
- Keep strict separation: one device/VM per persona per platform.  
- Do not link accounts via friends, likes, or follows.  
- Rotate platforms used by different personas (one may use Reddit, another Twitter).  
- Avoid uploading unique personal photos (landmarks, personal items in background).  
- Treat every interaction as potentially monitored or archived.  

### 10.5 Human Interaction Risks
- Adversaries may attempt to draw you into **voice or video calls**.  
- Be cautious with interviews, “friendly” chats, or insider approaches.  
- Assume **every DMs log is permanent**, even on platforms promising ephemerality.  
- Use **decoy behavior** when necessary to build plausible context for a persona.  


#### 🔥 Extreme Practices (Optional)
- Operate under **multiple behavioral covers**:  
  - One highly active and noisy persona (decoy).  
  - One quiet observer persona (low-profile).  
  - One sacrificial persona ready for controlled exposure.  
- Employ **linguistic camouflage**: deliberately switch language families (e.g., Slavic → Romance) or adopt regional slang consistent with cover identity.  
- Use **behavioral randomization schedules**: randomize log-in times, activity durations, and content posting intervals via automated scripts.  
- Employ **machine-assisted text rewriting** to generate diverse styles per persona — but cross-check for unnatural consistency.  
- For maximum safety: maintain **non-digital covers** (real-world identities, safehouse routines) to backstop online personas.  
- Introduce **contradictory digital traces** deliberately (red herrings) to pollute adversary attribution attempts.  
- Assume all platforms perform **cross-device correlation** — therefore, rotate **hardware, IP, and behavioral signatures** in sync.  
## 11. Travel OPSEC & Physical Security

### 11.1 Threat Landscape
Travel introduces unique risks that combine **digital, physical, and human vulnerabilities**.  
- Border searches may include device confiscation, forensic imaging, or forced account access.  
- Hotels, airports, and conference venues often have **compromised Wi-Fi and surveillance systems**.  
- Physical surveillance teams may track movement, habits, or meeting patterns.  
- Carrying sensitive data across jurisdictions increases exposure to **lawful intercept and coercion**.  

### 11.2 Pre-Travel Preparation
- Define the mission’s **minimum digital footprint** — take only the devices and data you truly need.  
- Use **burner devices** instead of personal hardware.  
- Prepare devices with **minimal local data**; everything else should be in encrypted containers stored offline.  
- Research local laws (encryption, journalism, data handling) to anticipate risks at customs.  
- Use **dummy accounts or benign identities** to handle casual inspections.  

### 11.3 Devices in Transit
- Assume all luggage is subject to search; carry sensitive items on your person if possible.  
- Power down devices before travel — reduces risk of live memory extraction.  
- Use **encrypted drives** with plausible deniability (hidden volumes).  
- Carry only **throwaway SIM cards**; avoid roaming on personal accounts.  
- Keep devices in **Faraday pouches** when not in active use.  

### 11.4 Hotels, Airports & Venues
- Treat all public Wi-Fi as hostile; use VPN/Tor.  
- Avoid logging into sensitive accounts on hotel or conference networks.  
- Use tethered mobile data instead of shared networks.  
- Be cautious of **room safes**; many can be opened with default codes.  
- Watch for physical tampering on locks, doors, or devices left unattended.  

### 11.5 Meetings & Movements
- Use varied routes and schedules to avoid pattern detection.  
- Arrange meetings in neutral locations with multiple exits.  
- Limit use of taxis or rideshares that log identity and travel patterns.  
- Keep situational awareness: surveillance cameras, suspicious observers, or unusual activity.  

#### 🔥 Extreme Practices (Optional)
- Travel only with **single-use, anonymous devices** purchased specifically for that trip. Destroy them afterward.  
- Carry **no sensitive data across borders**; instead, transfer via trusted couriers, encrypted cloud dead-drops, or steganographic methods.  
- Pre-stage equipment in the target country (purchased anonymously by proxies).  
- Use **Faraday bags** at all times except during active operations; assume all radios (Wi-Fi, Bluetooth, GSM) are beacons.  
- Employ **anti-surveillance techniques**: detect tails, use counter-surveillance routes, monitor for hostile surveillance gear (RF detectors, thermal sweeps).  
- Use **layered decoy devices**: a “clean” laptop for inspection, another hidden and encrypted for actual work.  
- Maintain **false travel narratives** — prepare cover stories, benign digital accounts, and plausible explanations for all devices carried.  
- In hostile states: avoid carrying any digital equipment; rely entirely on **non-digital tradecraft** (paper, codes, human couriers).  
## 12. Source Protection & HUMINT Interactions

### 12.1 Threat Landscape
Human sources (HUMINT) are among the **most vulnerable assets** in any operation.  
- They can be exposed by **metadata leaks** (calls, chats, location).  
- Surveillance or interception may compromise meetings.  
- Mishandling evidence can reveal identities.  
- Psychological pressure or social engineering can extract information.  

Protecting sources requires **both digital and physical OPSEC**, as well as strong interpersonal tradecraft.  

### 12.2 Digital Protection of Sources
- Avoid storing source identities on personal or operational devices.  
- Use **secure communication channels** (Signal, Session, Briar, SecureDrop).  
- Strip metadata from all files before storage or transfer.  
- Maintain **separate digital compartments** for each source.  
- Never reveal one source’s existence to another.  

### 12.3 Physical Meetings
- Select safe meeting locations with multiple exits and low surveillance coverage.  
- Avoid predictable schedules; vary routes and timing.  
- Pre-establish emergency signals and fallback procedures.  
- Never bring personal or unnecessary electronic devices to meetings.  
- Minimize time together to reduce exposure.  

### 12.4 Trust & Relationship Management
- Build trust gradually; never overload a source with sensitive tasks early.  
- Protect their psychological safety: avoid paranoia-inducing practices unless necessary.  
- Ensure clarity of expectations: what is shared, how, and under what risks.  
- Use **need-to-know principles**: sources should not have more context than necessary.  

### 12.5 Handling Information
- Always verify source claims with independent evidence.  
- Keep detailed logs of source interactions, but anonymize identifiers.  
- Store sensitive notes in encrypted, compartmentalized archives.  
- Protect against internal leaks: limit who has access to raw source intelligence.  

#### 🔥 Extreme Practices (Optional)
- Never carry any digital record of a source’s identity — commit identifiers to memory or use **deniable physical ciphers** (e.g., codes hidden in innocuous notes).  
- Use **non-digital dead drops**: physical objects, chalk marks, coded signals.  
- When digital transfer is unavoidable, use **multi-hop anonymization**: source → disposable device → one-time relay → analyst.  
- Conduct **pre-meeting counter-surveillance sweeps** (RF scanners, thermal cameras, observation detection routes).  
- Employ **psychological decoys**: run parallel fake meetings with sacrificial sources to divert adversary attention.  
- Use **air-gapped communication kits**: encrypted messages transferred only via offline devices and removable media.  
- Establish **multi-layered deniability**: if the source is caught, their digital and physical traces must point to a benign cover.  
- In hostile regimes: avoid in-person meetings entirely; rely on **proxy intermediaries** or **coded public signals** (graffiti, innocuous online posts).  

## 13. Advanced Topics

### 13.1 Air-Gapped Analysis
- Use **dedicated offline workstations** for the most sensitive tasks.  
- Transfer data only via **unidirectional methods** (write-once optical media, data diodes).  
- Always verify with cryptographic **checksums (SHA-256, BLAKE2b)** after transfer.  
- Never re-encode or alter originals — maintain pristine copies.  

### 13.2 Deception & Canary Tokens
- Deploy **honey identities**: decoy personas designed to lure adversary attention.  
- Use **canary documents and URLs** embedded with invisible trackers.  
- Monitor unauthorized access attempts to detect leaks early.  
- Service: [https://canarytokens.org/](https://canarytokens.org/)  

### 13.3 Data Broker & People-Search Suppression
- Regularly submit **opt-out requests** to data brokers and people-search engines.  
- Maintain a **removal calendar** (quarterly or semi-annual).  
- Log confirmations and track re-appearance of records.  
- Where opt-out fails, consider **flooding profiles with false but benign data**.  

### 13.4 Stylometry & Linguistic OPSEC
- Vary **sentence length, punctuation, and structure** across personas.  
- Randomize **time-of-day posting patterns**.  
- Avoid **rare idioms, unique expressions, or specialized jargon** that can fingerprint you.  
- Test against **stylometric analysis tools** like JStylo or Writeprints.  
- Consider **author obfuscation tools**, but validate for naturalness.  

### 13.5 AI-driven Deanonymization
- Adversaries use:  
  - **Facial recognition** (Clearview, PimEyes).  
  - **Voiceprints** (speaker ID databases).  
  - **Gait analysis** (CCTV motion profiling).  
  - **Camera sensor PRNU fingerprints** (unique hardware “noise” signatures).  
- Mitigation strategies:  
  - Minimize fresh biometric uploads.  
  - Apply **face blurring, voice masking, or redaction** where lawful.  
  - Use multiple devices to avoid consistent sensor fingerprints.  

### 13.6 Cross-Domain Integration
- Avoid cross-contamination of OSINT, HUMINT, SIGINT — each domain must remain compartmentalized.  
- Verify intelligence via **multi-domain corroboration** (technical + human + contextual).  
- Use strict **data segmentation policies** between investigations.  

### 13.7 Adversary Simulation
- Conduct **red team exercises** against your own setups.  
- Simulate device seizure, phishing, metadata correlation, and stylometry attribution.  
- Use frameworks like **MITRE ATT&CK, Caldera, or custom adversary playbooks**.  
- Log results and adjust SOPs accordingly.  

### 13.8 Psychological Resilience
- Recognize **stress and fatigue** as leading OPSEC failure points.  
- Rotate operators to prevent burnout.  
- Train with **stress inoculation drills** (role-play interrogation, surveillance pressure).  
- Maintain peer review and debrief culture to normalize mistakes.  

#### 🔥 Extreme Practices (Optional)
- Run **continuous deception environments**: parallel fake infrastructures that adversaries can discover and waste resources on.  
- Maintain **multi-layered canary networks**: fake identities that report back when touched.  
- Use **machine-assisted camouflage**: AI models to generate realistic but distinct writing styles, browsing histories, or fake photos.  
- Flood OSINT and search engines with **false leads** about your personas (AI-generated filler content).  
- Deploy **plausible decoy hardware**: carry a benign laptop/phone for inspection while keeping real hardware hidden and encrypted.  
- Create **false sacrifice operations**: deliberately burn one persona to validate adversary methods.  
- Implement **instant kill-switches** for infrastructure: one action wipes devices, burns keys, and retires personas simultaneously.  
- Train operators in **psychological deception techniques**: stress role-play, false narrative embedding, covert signaling under interrogation.  

## 14. Monitoring, Audits & Incident Response

### 14.1 Importance of Continuous Monitoring
Even the best OPSEC setups degrade over time. Software updates, new adversary capabilities, and operator mistakes introduce fresh risks.  
Regular monitoring ensures that vulnerabilities are caught **before** they become catastrophic failures.  

### 14.2 Self-Audits
- Perform **monthly audits** of all OPSEC compartments.  
- Use a structured checklist:  
  - Verify browser fingerprints via [Cover Your Tracks](https://coveryourtracks.eff.org/) or [BrowserLeaks](https://browserleaks.com/).  
  - Confirm VPN, Tor, and proxy routing; test for **DNS/WebRTC leaks**.  
  - Inspect devices for **unauthorized services, rootkits, or persistence mechanisms**.  
  - Check logging and metadata retention policies.  
  - Test kill-switches and emergency wipe mechanisms.  
- Document results and track changes over time.  

### 14.3 External Red/Purple Team Drills
- Conduct **red team tests**: allow trusted analysts to attempt deanonymization or correlation attacks.  
- Run **purple team drills**: simulate persona compromise and measure detection + containment time.  
- Scenarios should include:  
  - Device seizure.  
  - Metadata correlation across personas.  
  - Stylometric attribution.  
  - Social engineering or phishing.  
- Maintain written after-action reports with **lessons learned**.  

### 14.4 Incident Response Workflow
When compromise is suspected or confirmed:  

**1. Containment**  
- Isolate compromised devices or accounts immediately.  
- Trigger kill-switches if supported (wipe storage, disable accounts).  

**2. Rotation**  
- Replace compromised credentials, encryption keys, and devices.  
- Retire affected personas and migrate operations to fresh compartments.  

**3. Notification**  
- Inform stakeholders who may be affected (team members, trusted partners).  
- Share IOCs (indicators of compromise) with relevant internal parties.  

**4. Threat Model Update**  
- Reassess adversary capabilities in light of the compromise.  
- Identify what information was likely exposed.  

**5. Post-Incident Review**  
- Conduct root cause analysis: what failed — tool, process, or operator discipline?  
- Update SOPs and training to prevent recurrence.  
- Maintain records for accountability and long-term tracking.  


#### 🔥 Extreme Practices (Optional)
- Run **continuous monitoring agents** inside disposable VMs to automatically alert on fingerprint drift or unexpected outbound connections.  
- Deploy **canary personas** that exist solely to act as early-warning systems when touched by adversaries.  
- Use **decoy infrastructures** (fake servers, dummy accounts) to track intrusion attempts.  
- Maintain **parallel redundant infrastructures**: if one network or device stack is burned, instantly switch to a cold standby.  
- Practice **instant evacuation drills**: operators rehearse what to do if devices are seized in real time.  
- Automate **nuclear kill-switches**: one command wipes devices, revokes keys, disables accounts, and retires personas across multiple jurisdictions.  
- Treat every incident as an opportunity for **adversary intelligence gathering** — capture their TTPs (tactics, techniques, procedures) during the breach.  

## 15. Tools & Utilities Reference

## 🖼️ Image Analysis

**Common needs:** detect manipulation, verify authenticity, inspect metadata.

- **Check EXIF metadata** → [ExifTool](https://exiftool.org/) – extract, analyze, and compare image metadata fields.
    
- **Detect editing or cloning** → [Forensically](https://29a.ch/photo-forensics/) – error level analysis, clone detection, noise analysis.
    
- **Sensor-level verification** → [Noiseprint](https://github.com/isi-vista/noiseprint) – identify device PRNU fingerprint.
    
- **Verify text/logos in images** → [OCRmyPDF](https://ocrmypdf.readthedocs.io/) or [Tesseract](https://github.com/tesseract-ocr/tesseract) – OCR for suspicious text.
    

## 🎥 Video Verification

**Common needs:** analyze frames, detect deepfakes, validate context.

- **Extract keyframes / thumbnails** → [InVID Plugin](https://www.invid-project.eu/tools-and-services/invid-verification-plugin/) – frame capture, reverse search, metadata inspection.
    
- **Inspect encoding & frames** → [FFmpeg](https://ffmpeg.org/) – codec analysis, frame-by-frame breakdown.
    
- **Detect deepfake manipulation** → [SensityAI](https://sensity.ai/) or [Reality Defender](https://realitydefender.ai/) – ML-based deepfake detection.
    
- **Cross-check weather & lighting** → [SunCalc](https://www.suncalc.org/) + [Meteostat](https://meteostat.net/) – shadow and weather validation.
    

## 🔊 Audio Verification

**Common needs:** detect synthetic voices, validate background context, inspect signals.

- **Spectrogram & waveform inspection** → [Audacity](https://www.audacityteam.org/) – generate spectrograms, detect anomalies.
    
- **Phonetic & acoustic features** → [Praat](https://www.fon.hum.uva.nl/praat/) – jitter, shimmer, pitch contour analysis.
    
- **Detect synthetic voices** → Intel [FakeCatcher](https://www.intel.com/content/www/us/en/research/ai-fakecatcher.html) or [Deepware Scanner](https://www.deepware.ai/).
    
- **Validate ambient audio** → Compare environmental sounds with expected context (traffic, birds, etc.).
    

## 📝 Textual Verification

**Common needs:** detect AI-generated text, check citations, validate style.

- **Spot AI-generated scaffolding** → [GLTR](http://gltr.io/) – token probability analysis.
    
- **Alternative AI detection** → [DetectGPT](https://github.com/eric-mitchell/detect-gpt) – detect likelihood of LLM text.
    
- **Stylometric comparison** → [JStylo](https://psal.cs.drexel.edu/index.php?n=Software.JStylo) – author attribution & writing style analysis.
    
- **Check fabricated citations** → Manual validation + [Crossref](https://www.crossref.org/) or Google Scholar.
    

## 🌍 Contextual & Cross-Modal Checks

**Common needs:** validate time, place, and consistency across modalities.

- **Verify location** → [Google Earth](https://earth.google.com/) + [Street View](https://www.google.com/streetview/).
    
- **Check shadows & sun position** → [SunCalc](https://www.suncalc.org/).
    
- **Weather validation** → [Meteostat](https://meteostat.net/) or [OGIMET](https://www.ogimet.com/).
    
- **Narrative consistency** → Manual cross-check across text, image, video, audio.
    

## 📊 Metadata & Technical Fingerprints

**Common needs:** check provenance, file signatures, hidden markers.

- **Extract all metadata** → [ExifTool](https://exiftool.org/) – universal metadata extraction.
    
- **Provenance verification** → [C2PA](https://c2pa.org/) or Adobe [Content Credentials](https://contentcredentials.org/).
    
- **Watermark detection** → Google [SynthID](https://deepmind.google/technologies/synthid/) (when supported).
    
- **Sensor noise & compression** → [Noiseprint](https://github.com/isi-vista/noiseprint).
    

## 🛡️ OPSEC & Workflow Support

**Common needs:** maintain anonymity, secure comms, manage personas.

- **Anonymous file transfer** → [OnionShare](https://onionshare.org/) or [Magic Wormhole](https://magic-wormhole.readthedocs.io/).
    
- **Password management** → [KeePassXC](https://keepassxc.org/).
    
- **OS isolation** → [Tails](https://tails.boum.org/) for amnesic sessions, [Qubes OS](https://www.qubes-os.org/) for compartmentalization.
    
- **Browser fingerprint testing** → [AmIUnique](https://amiunique.org/) or [CoverYourTracks](https://coveryourtracks.eff.org/).
    

## 16. Checklists

### 16.1 Daily Analyst Hygiene

- Boot hardened environment; verify VPN/Tor; minimal extensions; check firewall/kill-switch.
    
- Use persona-specific profiles; no personal logins; rotate session cookies.
    
- Update, backup encrypted vaults; verify hashes; review task list and risk flags.
    

### 16.2 Pre-Operation (L2/L3)

- Refresh threat model; define objectives; select personas; confirm devices and VMs.
    
- Test fingerprint; confirm metadata scrubbing; prepare case log and hashing plan.
    
- Establish comms plan and emergency contacts; legal review if needed.
    

### 16.3 Post-Operation

- Archive evidence (write-once, hashed); export logs; rotate credentials/keys as scheduled.
    
- Peer review of OPSEC; update lessons learned; schedule next audit.
    

## 17. Templates & Automation (Snippets)

- **Hash all files in a folder:** `sha256sum * > hashes.txt`
    
- **Strip metadata:** `mat2 *.pdf *.jpg *.png`
    
- **PGP key generation (GnuPG):** `gpg --quick-gen-key "Persona X <x@proton.me>" ed25519 cert sign 2y`
    
- **Tor-only egress (Linux iptables example):**

- **Test DNS/WebRTC leaks:** visit `https://ipleak.net/` and ensure no IPv6/WebRTC disclosures.
    

### 🔖 Credits

Maintained by **Oryon** +**[OSINT360 GPT](https://tntpp9.short.gy/osint360-gpt)**.  
This document is part of the **Cyber Intelligence Toolkit** project.  


