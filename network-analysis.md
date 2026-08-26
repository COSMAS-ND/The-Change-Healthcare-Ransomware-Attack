# WannaCry Network Analysis

## Case File 001

### Objective

Analyze the network behavior associated with the WannaCry outbreak, with emphasis on SMB-based propagation, vulnerable systems, and defensive observations.

---

## 1. Primary Network Protocol

WannaCry's worm-like propagation was associated with Microsoft's Server Message Block version 1 (SMBv1) service.

The vulnerability was addressed by Microsoft security update MS17-010.

The affected SMB service commonly uses TCP port 445.

---

## 2. Propagation Model

The propagation can be represented conceptually as:

```text
Infected Host
     |
     | SMB-based exploitation
     v
Vulnerable Host
     |
     | Successful compromise
     v
Newly Infected Host
     |
     +------> Attempts further propagation
