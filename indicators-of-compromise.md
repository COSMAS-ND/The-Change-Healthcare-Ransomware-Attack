# WannaCry Indicators of Compromise

## Case File 001

### Purpose

This document records observable indicators associated with the 2017 WannaCry ransomware outbreak.

The indicators are intended to support detection, investigation, and retrospective analysis. They should be validated against the specific sample or environment being investigated.

---

## 1. File Hashes

Microsoft documented the following SHA-1 hashes for WannaCry samples analyzed during the outbreak:

| Hash Type | Indicator |
|---|---|
| SHA-1 | 51e4307093f8ca8854359c0ac882ddca427a813c |
| SHA-1 | e889544aff85ffaf8b0d0da705105dee7c97fe26 |

Source: Microsoft Security Blog.

---

## 2. File-Based Indicators

Microsoft documented several files associated with analyzed WannaCry samples, including:

- mssecsvc.exe
- tasksche.exe
- taskdl.exe
- taskse.exe
- @WanaDecryptor@.exe
- @Please_Read_Me@.txt
- @WanaDecryptor@.bmp
- Files using the `.wnry` extension
- Files using the `.WNCRY` extension

These indicators may assist investigators when examining affected systems.

---

## 3. Registry Indicator

A registry artifact documented by Microsoft is:

`HKLM\SOFTWARE\WanaCrypt0r\wd`

This can be considered a host-based artifact during retrospective investigation.

---

## 4. Network-Related Observation

WannaCry's propagation was strongly associated with exploitation of vulnerable Windows systems through SMB.

The investigation therefore considers SMB-related activity, particularly TCP port 445, an important network-level observation when analyzing potential propagation.

---

## 5. Vulnerability Association

The WannaCry outbreak exploited a vulnerability addressed by Microsoft's MS17-010 security update.

The vulnerability was associated with SMB and played a central role in the ransomware's ability to propagate between vulnerable systems.

---

## 6. IOC Classification

| Category | Examples |
|---|---|
| File Hash | SHA-1 sample hashes |
| File Name | mssecsvc.exe, tasksche.exe |
| File Extension | .wnry, .WNCRY |
| Registry | WanaCrypt0r registry artifact |
| Network | SMB-related activity / TCP 445 |
| Vulnerability | MS17-010 / SMB vulnerability |

---

## 7. Analyst Assessment

The indicators demonstrate that effective WannaCry detection should not rely on a single IOC.

A stronger investigation combines:

- File-based indicators
- Hash-based detection
- Host artifacts
- Network observations
- Vulnerability assessment
- Behavioral analysis

This layered approach is more useful for incident response because individual indicators can change across malware variants while the underlying behavior may remain observable.

---

## Sources

1. Microsoft Security Blog — WannaCrypt ransomware worm targets out-of-date systems.
2. CISA — Indicators Associated With WannaCry Ransomware.

