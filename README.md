# CVE findings

Security vulnerabilities I found and reported through coordinated disclosure.

I publish details here only after the vendor ships a fix and the advisory is public.

## Findings

| CVE | Product | Affected | Fixed | Severity | Type | Published |
| --- | --- | --- | --- | --- | --- | --- |
| [CVE-2026-111982](#cve-2026-111982) | Profile Builder (WordPress plugin) | < 4.0.5 | 4.0.5 | 7.2 High | Privilege escalation | 2026-10-21 |

## CVE-2026-111982

**Profile Builder < 4.0.5: Multisite subsite Admin+ to Network Super Admin account takeover via Edit Profile email change**

- Plugin: [Profile Builder](https://wordpress.org/plugins/profile-builder/) (`profile-builder`)
- Affected versions: below 4.0.5
- Fixed in: 4.0.5
- CVSS 3.1: 7.2 High (`AV:N/AC:L/PR:H/UI:N/S:U/C:H/I:H/A:H`)
- CWE: [CWE-269](https://cwe.mitre.org/data/definitions/269.html) (Improper Privilege Management)
- Published: 2026-10-21

The plugin's front-end Edit Profile form does not check if the current user may edit the selected account. On a WordPress Multisite network, an Administrator of one subsite can change the email address of any other user, including a Network Super Admin. The attacker then uses the normal password reset flow to take over that account.

A subsite admin should not control the whole network. This bug turns a subsite admin into a network super admin.

Fix: update Profile Builder to 4.0.5 or later.

WPScan will publish the proof of concept on 2026-11-21.

References:

- [WPScan advisory](https://wpscan.com/vulnerability/b7d1fd86-3927-4cf2-88ed-46401e347320/)
- [CVE-2026-111982](https://www.cve.org/CVERecord?id=CVE-2026-111982)

## Contact

Szymon Szymkowiak, [GitHub @emancypage](https://github.com/emancypage)
