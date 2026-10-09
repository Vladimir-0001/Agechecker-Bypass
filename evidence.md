# Source record: implementation history and attribution

Reviewed October 8, 2026, in America/Indiana/Indianapolis. All source timestamps below are UTC.

The earliest code-bearing commit in helloyanis's repository contains the exact custom message `LOL EZ bypass` found in this repository's 2022 code, together with matching workflow data. A later commit replaces that approach with a different popup implementation. Those source-level observations are verifiable. They do not, by themselves, establish who copied what, whether the later implementation was independently developed, or anyone's intent.

This record preserves the evidence and the other developer's explanation. It makes no finding of theft, dishonesty, infringement, financial gain, or malicious intent. The existing [issue #10 discussion](https://github.com/Vladimir-0001/Agechecker-Bypass/issues/10) remains part of the record, including my own replies.

## 1. Sources and chronology

Git author and committer timestamps describe the available repository history. They are not independent proof of when a file first became public or when another person first saw it.

| UTC timestamp | Observable record | Primary source |
| --- | --- | --- |
| 2022-06-10 00:38:12 | GitHub records creation of Vladimir-0001/Agechecker-Bypass. | [Repository metadata](https://api.github.com/repos/Vladimir-0001/Agechecker-Bypass) |
| 2022-06-10 00:40:08 | Commit `dee2cfb863f223fe32967bf7af0b7bed2e5b706d` adds `bypass.py`, including `LOL EZ bypass`. | [Commit](https://github.com/Vladimir-0001/Agechecker-Bypass/commit/dee2cfb863f223fe32967bf7af0b7bed2e5b706d), [file](https://github.com/Vladimir-0001/Agechecker-Bypass/blob/dee2cfb863f223fe32967bf7af0b7bed2e5b706d/bypass.py#L12-L51) |
| 2026-02-03 18:38:27 | crunchy4159 opens PR #8 to replace the first Discord invitation with an invitation already elsewhere in the README. | [PR #8](https://github.com/Vladimir-0001/Agechecker-Bypass/pull/8) |
| 2026-06-23 08:11:07 | helloyanis's root commit contains only `.gitattributes`. It contains no bypass implementation. | [Root commit](https://github.com/helloyanis/age-verification-bypass/commit/1e1db5367242e1f87aeaabcebe63ddffbdd00734) |
| 2026-06-23 12:30:25 | The next commit, `b2faefec3e4ffa37809b19a6b9b60cfb28617949`, adds `background.js` and `manifest.json`. The JavaScript contains `LOL EZ bypass` and the matching workflow structure. | [Commit](https://github.com/helloyanis/age-verification-bypass/commit/b2faefec3e4ffa37809b19a6b9b60cfb28617949), [file](https://github.com/helloyanis/age-verification-bypass/blob/b2faefec3e4ffa37809b19a6b9b60cfb28617949/background.js#L26-L49) |
| 2026-06-23 12:57:36 | Commit `5fb1a9e0013bb9f65fc6cccfc627d4bb8c41a860` replaces the earlier response code with popup-script replacement and callbacks. | [Commit](https://github.com/helloyanis/age-verification-bypass/commit/5fb1a9e0013bb9f65fc6cccfc627d4bb8c41a860), [file](https://github.com/helloyanis/age-verification-bypass/blob/5fb1a9e0013bb9f65fc6cccfc627d4bb8c41a860/background.js) |
| 2026-06-24 08:44:13 | helloyanis opens issue #10 in this repository to introduce the extension. | [Issue #10](https://github.com/Vladimir-0001/Agechecker-Bypass/issues/10) |
| 2026-07-03 07:35:22 | helloyanis says he tried this repository's script and describes his alternative approach as based on AgeChecker's documentation. | [Comment](https://github.com/Vladimir-0001/Agechecker-Bypass/issues/10#issuecomment-4873878006) |
| 2026-07-04 16:27:07 | I state that I deleted the Discord server and attach a userscript. | [Comment and attachment](https://github.com/Vladimir-0001/Agechecker-Bypass/issues/10#issuecomment-4883051060) |
| 2026-10-03 07:10:07 | The later repository snapshot reviewed here contains popup replacement and generated acceptance responses in `websites/agechecker.net.js`. | [Pinned file](https://github.com/helloyanis/age-verification-bypass/blob/69d68af3312ffd599bef132e5a15faef29aeb88e/websites/agechecker.net.js) |

The original issue links to `helloyanis/agechecker.net-bypass`. GitHub currently resolves that name to [helloyanis/age-verification-bypass](https://github.com/helloyanis/age-verification-bypass), repository ID `1278086060`. The historical file links above use the current name and fixed commit IDs.

## 2. Exact message correspondence

Exhibit A: Vladimir-0001, `bypass.py`, commit `dee2cfb863f223fe32967bf7af0b7bed2e5b706d`, line 19:

```text
"success_text":"LOL EZ bypass",
```

[Source](https://github.com/Vladimir-0001/Agechecker-Bypass/blob/dee2cfb863f223fe32967bf7af0b7bed2e5b706d/bypass.py#L19)

Exhibit B: helloyanis, `background.js`, commit `b2faefec3e4ffa37809b19a6b9b60cfb28617949`, line 31:

```text
success_text: "LOL EZ bypass",
```

[Source](https://github.com/helloyanis/age-verification-bypass/blob/b2faefec3e4ffa37809b19a6b9b60cfb28617949/background.js#L31)

**Observed:** the string values are identical, including capitalization and spaces: uppercase `LOL EZ`, lowercase `bypass`. This is a custom message, separate from the API field name. The surrounding programs are not identical: one is Python/Flask and the other is a Firefox extension using JavaScript.

## 3. Additional correspondence and differences

Sources: [original Python response data](https://github.com/Vladimir-0001/Agechecker-Bypass/blob/dee2cfb863f223fe32967bf7af0b7bed2e5b706d/bypass.py#L12-L51) and [earliest extension response data](https://github.com/helloyanis/age-verification-bypass/blob/b2faefec3e4ffa37809b19a6b9b60cfb28617949/background.js#L1-L75).

| Item compared | 2022 Python implementation | Earliest 2026 extension implementation | Observation |
| --- | --- | --- | --- |
| Custom success message | `LOL EZ bypass` | `LOL EZ bypass` | Exact string match. |
| Workflow key sequence | `us`, `states`, `ca`, `ca_provinces`, `international`, `countries` | Same sequence | Same keys and order. |
| Workflow contents | Minimum age 21 for `us`, `ca`, and `international`; empty objects for the other three keys | Same contents | Equal data after normalizing Python and JavaScript syntax. |
| API information response | Local route `/v1/info/<id>` supplies settings | Response filtering for `/v1/info/*` supplies settings | Both substitute the information response; interception mechanisms differ. |
| Creation response | Locally generated 32-character alphanumeric identifier and an accepted status | Locally generated UUID with hyphens removed and an accepted status | Same general response purpose; identifier generation differs. |
| Additional status response | No `/v1/status/*` route in the inspected file | Filters `/v1/status/*` as well | Extension has additional interception. |
| Presentation text and store name | Custom form text and store name `Vladimir` | Different instructions and store name | These strings differ. |
| Interception mechanism | Local Flask server | Firefox `webRequest` response filtering | Different implementations. |

API field names and regional settings alone could reflect a common integration schema. The matching custom message is additional evidence beyond those field names. The inspected files establish these correspondences; they do not establish the path by which the matching content entered the extension.

## 4. The later implementation must be considered separately

The next code commit is timestamped **27 minutes and 11 seconds** after the extension's first code-bearing commit. In that [later snapshot](https://github.com/helloyanis/age-verification-bypass/blob/5fb1a9e0013bb9f65fc6cccfc627d4bb8c41a860/background.js), the extension replaces the popup script and invokes configured callbacks. The custom message and workflow object from its preceding snapshot are absent.

The [October 2026 snapshot](https://github.com/helloyanis/age-verification-bypass/blob/69d68af3312ffd599bef132e5a15faef29aeb88e/websites/agechecker.net.js#L15-L98) also contains popup replacement, status callbacks, and response filtering for creation requests. It generates identifiers and supplies acceptance indications. Its source references AgeChecker's client and server documentation.

**Observed:** a separate popup implementation exists in the later history. **Not established:** independent origin of every part of that implementation. A distinct later implementation does not erase the matching content in the earlier commit; matching earlier content does not prove the later implementation was copied.

## 5. Developer's statement, in his own words

Author: helloyanis. Posted 2026-07-03 07:35:22 UTC. GitHub reports the same timestamp for its last update. [Direct source](https://github.com/Vladimir-0001/Agechecker-Bypass/issues/10#issuecomment-4873878006).

Relevant verbatim excerpts:

> I tried to get your script to work, but it didn't

> based on the documentation on their site, hence why I didn't give credit

The full comment describes unsuccessful attempts to run the script and obtain Discord support, and explains that his approach skips the popup. The statements establish that he reported trying this project and gave that explanation for not crediting it. They do not independently establish the truth of his account of development, or the date on which he first encountered this repository.

The comment should be read alongside both the earliest matching response implementation and the later popup implementation. This record does not replace his stated explanation with an allegation about intent.

## 6. My own conduct and the preserved discussion

My [initial reply](https://github.com/Vladimir-0001/Agechecker-Bypass/issues/10#issuecomment-4870601676) was hostile and inappropriate. It is not evidence of technical provenance. I leave it in the thread as part of the record rather than selectively presenting only the other developer's comments.

In my [July 4 reply](https://github.com/Vladimir-0001/Agechecker-Bypass/issues/10#issuecomment-4883051060), I wrote:

> ight that might have been a slight overreaction

The same comment states:

> i deleted the discord a while back

That comment also claims an earlier userscript had been shared while the Discord was active and links [AgeChecker.net API Bypass-1.2.user.js](https://github.com/user-attachments/files/29662436/AgeChecker.net.API.Bypass-1.2.user.js). The comment timestamp establishes when that attachment was posted to this thread. This review does not independently verify a pre-existing Discord publication date for that userscript. The 2022 Python evidence stands on the pinned repository files, without relying on that claim.

Every comment in the thread at the time of review is linked below:

| UTC timestamp | Author | Source and relevance |
| --- | --- | --- |
| 2026-07-02 21:25:05 | Vladimir-0001 | [Initial hostile reply](https://github.com/Vladimir-0001/Agechecker-Bypass/issues/10#issuecomment-4870601676). |
| 2026-07-03 07:35:22 | helloyanis | [Explanation of prior attempts, support problems, and the alternative approach](https://github.com/Vladimir-0001/Agechecker-Bypass/issues/10#issuecomment-4873878006). |
| 2026-07-04 16:27:07 | Vladimir-0001 | [Acknowledgment of overreaction, server deletion statement, and userscript attachment](https://github.com/Vladimir-0001/Agechecker-Bypass/issues/10#issuecomment-4883051060). |
| 2026-07-04 16:34:01 | helloyanis | [Suggestion to add the userscript as an alternative](https://github.com/Vladimir-0001/Agechecker-Bypass/issues/10#issuecomment-4883071953). |
| 2026-07-04 16:35:56 | Vladimir-0001 | [Informal response](https://github.com/Vladimir-0001/Agechecker-Bypass/issues/10#issuecomment-4883077697). |
| 2026-07-04 16:40:22 | helloyanis | [Response to the change in tone](https://github.com/Vladimir-0001/Agechecker-Bypass/issues/10#issuecomment-4883090896). |
| 2026-07-04 22:23:35 | Vladimir-0001 | [Objection to promotion through this repository](https://github.com/Vladimir-0001/Agechecker-Bypass/issues/10#issuecomment-4883989501). |
| 2026-07-05 06:28:51 | helloyanis | [Statement about closing the issue and inability to delete it](https://github.com/Vladimir-0001/Agechecker-Bypass/issues/10#issuecomment-4885095812). |

The [issue body](https://github.com/Vladimir-0001/Agechecker-Bypass/issues/10) and [raw comment records](https://api.github.com/repos/Vladimir-0001/Agechecker-Bypass/issues/10/comments?per_page=100) provide the surrounding context and timestamps.

## 7. Support correction

The [README before this correction](https://github.com/Vladimir-0001/Agechecker-Bypass/blob/0b889bcef74d890bf5f3b397d45779dc9f19b710/README.md) contains two Discord invitation URLs and additional Discord contact instructions. [PR #8](https://github.com/Vladimir-0001/Agechecker-Bypass/pull/8) attempts to replace one invitation with the other.

The deletion statement is the maintainer's own account, not an independent test of either invitation's present behavior. In light of that statement, the documentation now directs reproducible technical support requests to [GitHub Issues](https://github.com/Vladimir-0001/Agechecker-Bypass/issues). The contributor's attempted repair deserves acknowledgment even though the proposed replacement is superseded by this correction.

## 8. Findings and unresolved questions

**Verified from the inspected record:** matching capitalization and message text; matching workflow data; different interception mechanisms; a later popup replacement implementation; the quoted developer statement; and the support-link inconsistency.

**Interpretation, not a finding:** these correspondences, together with the reported prior attempt to run this project, are consistent with this repository having informed the earliest extension implementation. That is a reasonable inference, not proof of a particular copying event or an admission of derivation. A different source or explanation has not been ruled out.

**Unresolved:** when helloyanis first saw this project; which sources he used when writing each commit; the origin of each matching element; whether attribution was owed; and any claim about intent, dishonesty, ownership, or commercial benefit. No such claim is presented here as proven beyond reasonable doubt.

**Security scope:** this was a read-only review of public code and discussion. No live verification or merchant checkout was tested. The existence of source code that supplies client-side acceptance does not establish that every integration, or any particular current integration, accepts it server-side. Security reporting should distinguish client-side behavior from independently confirmed server-side acceptance.

Corrections should identify the observation being disputed and link the relevant primary source. The aim is an accurate record and useful remediation, not a personal dispute.
