---
title: ZAP Report

---

# ZAP Security Report
*Generated with ZAP by Checkmarx*  
**Date:** February 23, 2025, 06:51:12  
**ZAP Version:** 2.16.0  
**File:** `report.html`  

---

## Table of Contents
1. [About This Report](#about-this-report)  
2. [Report Parameters](#report-parameters)  
3. [Summaries](#summaries)  
   - [Alert Counts by Risk and Confidence](#alert-counts-by-risk-and-confidence)  
   - [Alert Counts by Type](#alert-counts-by-type)  
4. [Alert Details](#alert-details)  
5. [Appendix: Alert Types](#appendix-alert-types)  

---

## About This Report
This report was generated using the ZAP tool to analyze the security of a web application. It includes the results of scanning the site `http://127.0.0.1:8080`.

---

## Report Parameters
- **Contexts:** None selected, all included by default.  
- **Sites:**  
  - `http://127.0.0.1:8080` (included by default).  
- **Risk Levels:** High, Medium, Low, Informational.  
- **Confidence Levels:** User Confirmed, High, Medium, Low.  
- **Excluded:** False Positives.  

---

## Summaries

### Alert Counts by Risk and Confidence
| Risk            | Confidence | Count | % of Total |
|-----------------|------------|-------|------------|
| Medium          | High       | 1     | -          |
| Medium          | Medium     | 2     | -          |
| Medium          | Low        | 1     | -          |
| Low             | High       | 1     | -          |
| Low             | Medium     | 5     | -          |
| Informational   | Medium     | 3     | -          |
| Informational   | Low        | 1     | -          |
| **Total**       |            | **14**| -          |

### Alert Counts by Type
| Alert Type                                                  | Risk           | Count |
|-------------------------------------------------------------|----------------|-------|
| Content Security Policy (CSP) Header Not Set                | Medium         | -     |
| Hidden File Found                                           | Medium         | 1     |
| Missing Anti-clickjacking Header                            | Medium         | 1     |
| Vulnerable JS Library                                       | Medium         | 1     |
| Application Error Disclosure                                | Low            | 1     |
| Cookie No HttpOnly Flag                                     | Low            | 1     |
| Cookie without SameSite Attribute                           | Low            | 1     |
| Information Disclosure - Debug Error Messages               | Low            | 1     |
| Server Leaks Version Information via "Server" Header        | Low            | 1     |
| X-Content-Type-Options Header Missing                       | Low            | 1     |
| Authentication Request Identified                           | Informational  | 1     |
| Information Disclosure - Suspicious Comments                | Informational  | 1     |
| Modern Web Application                                      | Informational  | 1     |
| Session Management Response Identified                      | Informational  | 1     |
| User Agent Fuzzer                                           | Informational  | 1     |
| User Controllable HTML Element Attribute (Potential XSS)    | Informational  | 1     |
| **Total**                                                   |                | **14**|

---

## Alert Details

### Medium Risk
1. **Missing Anti-clickjacking Header**  
   - Confidence: Medium  
   - URL: `GET http://127.0.0.1:8080/`  
2. **Vulnerable JS Library**  
   - Confidence: Low  
   - URL: `GET http://127.0.0.1:8080/static/js/jquery-3.2.1.min.js`  
3. **Hidden File Found**  
   - Confidence: High  
   - URL: `GET http://127.0.0.1:8080/.hg`  

### Low Risk
1. **Server Leaks Version Information via "Server" Header**  
   - Confidence: Medium  
   - URL: `GET http://127.0.0.1:8080/`  
2. **Application Error Disclosure**  
   - Confidence: Medium  
   - URL: `POST http://127.0.0.1:8080/courses/1/review`  
3. **Cookie No HttpOnly Flag**  
   - Confidence: Medium  
   - URL: `GET http://127.0.0.1:8080/`  
4. **Cookie without SameSite Attribute**  
   - Confidence: Medium  
   - URL: `GET http://127.0.0.1:8080/`  
5. **Information Disclosure - Debug Error Messages**  
   - Confidence: Medium  
   - URL: `POST http://127.0.0.1:8080/courses/1/review`  
6. **X-Content-Type-Options Header Missing**  
   - Confidence: Medium  
   - URL: `GET http://127.0.0.1:8080/`  

### Informational Risk
1. **Modern Web Application**  
   - Confidence: Medium  
   - URL: `GET http://127.0.0.1:8080/_darcs`  
2. **Session Management Response Identified**  
   - Confidence: Medium  
   - URL: `GET http://127.0.0.1:8080/`  
3. **User Agent Fuzzer**  
   - Confidence: Medium  
   - URL: `GET http://127.0.0.1:8080/`  
4. **Authentication Request Identified**  
   - Confidence: Low  
   - URL: `POST http://127.0.0.1:8080/`  
5. **Information Disclosure - Suspicious Comments**  
   - Confidence: Low  
   - URL: `GET http://127.0.0.1:8080/static/js/jquery-3.2.1.min.js`  
6. **User Controllable HTML Element Attribute (Potential XSS)**  
   - Confidence: Low  
   - URL: `POST http://127.0.0.1:8080/`  

---

## Appendix: Alert Types
1. **Content Security Policy (CSP) Header Not Set**  
   - Source: Passive Scanner  
   - CWE ID: 693  
   - WASC ID: 15  
   - References: [MDN CSP](https://developer.mozilla.org/en-US/docs/Web/Security/CSP), [OWASP Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Content_Security_Policy_Cheat_Sheet.html)  
2. **Hidden File Found**  
   - Source: Active Scanner  
   - CWE ID: 538  
   - WASC ID: 13  
   - Reference: [Snallygaster](https://blog.hboeck.de/archives/892-Introducing-Snallygaster-a-Tool-to-Scan-for-Secrets-on-Web-Servers.html)  
3. **Missing Anti-clickjacking Header**  
   - Source: Passive Scanner  
   - CWE ID: 1021  
   - WASC ID: 15  
   - Reference: [X-Frame-Options](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-Frame-Options)  
4. **Vulnerable JS Library**  
   - Source: Passive Scanner (RetireJS)  
   - CWE ID: 1395  
   - References: [CVE-2019-11358](https://nvd.nist.gov/vuln/detail/CVE-2019-11358), [jQuery Blog](https://blog.jquery.com/2019/04/10/jquery-3-4-0-released/)  
5. **Application Error Disclosure**  
   - Source: Passive Scanner  
   - CWE ID: 200  
   - WASC ID: 13  
6. **Cookie No HttpOnly Flag**  
   - Source: Passive Scanner  
   - CWE ID: 1004  
   - WASC ID: 13  
   - Reference: [OWASP HttpOnly](https://owasp.org/www-community/HttpOnly)  
7. **Cookie without SameSite Attribute**  
   - Source: Passive Scanner  
   - CWE ID: 1275  
   - WASC ID: 13  
   - Reference: [SameSite Draft](https://tools.ietf.org/html/draft-ietf-httpbis-cookie-same-site)  