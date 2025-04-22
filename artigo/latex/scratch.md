# scrathpad

### Don Banks Talk (Cisco)

- Top 10 IoT security risks (OWASP); also (any compromised, system compromised):
    - Protect Data;
    - Protect Network;
    - Protect Software/Firmware;
    - Protect Device (Hardware);

- **CIA** (Confidentiality, Integrity, Availability);

- **Threat Model:** defines what threats are being considered and which are not (ignored);

- Policy v. Mechanism, Trusted v. Trustworthy:
    - **Policy:** Specifies who/what can access which resources  under which conditions; -> **PBAC\***
    - **Mechanism:** Implements the policy;
    - **Trusted:** Responsible for maintaining security policies;
    - **Trustworthy:** Designed to be secure;

- _TCB_ and _TEE_:
    - **TCB:** _(Trusted Computing Base)_ - The hardware, software, firmware, and network componentes that must be both correct and un-corruptible in
      order to ensure that the security policy is not violated;
    - **TEE:** _(Trusted Execution Environment)_ - A secure area of the processor storage that guarantees that code
    and data located there are protected;

- Access Control (AAA), Privacy:
    - **Authentication:** _Who Are You?_;
    - **Authorization:** _What Are You Allowed to Do?_;
    - **Privacy:** A property of the data, built on top of security: the right to decide how one's information is used;
      not the same as **Confidentiality** (prevent unauthorized access);

- Categories of Fog Node Security:
    - _TEE_;
    - Data security;
    - Network security;
    - Physical security of the device;

- Trust **must** be rooted in hardware:
    - Established at _power-on_;
    - Extends chain-of-trust;
    - Firmware Hypervisor or bare-metal;

---
