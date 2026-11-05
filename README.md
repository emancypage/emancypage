# Security research

I publish details here only after the vendor ships a fix and the advisory is public.

## Public findings

Security vulnerabilities I found and reported through coordinated disclosure.

| Product | Finding | Fixed in | Public reference |
| --- | --- | --- | --- |
| Profile Builder, WordPress plugin | Multisite subsite Administrator to Network Super Admin account takeover | 4.0.5 | [CVE-2026-111982](https://www.cve.org/CVERecord?id=CVE-2026-111982), [WPScan advisory](https://wpscan.com/vulnerability/b7d1fd86-3927-4cf2-88ed-46401e347320/) |
| Chyrp Lite | Blind SQL injection in search | v2026.03 | [Vendor release and researcher credit](https://github.com/xenocrat/chyrp-lite/releases/tag/v2026.03) |
| Chyrp Lite | Account takeover in the password reset flow | v2026.03 | [Vendor release and researcher credit](https://github.com/xenocrat/chyrp-lite/releases/tag/v2026.03) |

I publish vulnerability details only after a fix is available and the issue is public.

### CVE-2026-111982

**Profile Builder before 4.0.5: Multisite subsite Administrator to Network Super Admin account takeover.**

A missing account-level authorization check in the front-end Edit Profile form allowed a subsite Administrator to change a Network Super Admin's email address. The normal password reset flow then allowed takeover of that account, crossing the boundary between one subsite and the whole network.

- Affected versions: below 4.0.5.
- Fixed in: 4.0.5.
- Published CVSS v3.1: **7.2 High**.
- CWE: [CWE-269, Improper Privilege Management](https://cwe.mitre.org/data/definitions/269.html).
- WPScan advisory published: 21 October 2026.
- CVE record published: 23 October 2026.

References: [WPScan advisory](https://wpscan.com/vulnerability/b7d1fd86-3927-4cf2-88ed-46401e347320/), [CVE record](https://www.cve.org/CVERecord?id=CVE-2026-111982).

### Chyrp Lite

The [v2026.03 Sichuan release](https://github.com/xenocrat/chyrp-lite/releases/tag/v2026.03), published on 1 November 2026, credits [@emancypage](https://github.com/emancypage) for reporting two fixed vulnerabilities: blind SQL injection in search and account takeover in the password reset flow.

## Contact

Szymon Szymkowiak, [GitHub @emancypage](https://github.com/emancypage).
