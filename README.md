# ChatExport

Exports iPhone Messages (SMS, MMS, RCS and iMessage) from a local iPhone backup
into searchable PDF, TXT, HTML and CSV. Everything runs on your own computer.
Nothing is uploaded.

Website: <https://getchatexport.com>

## Releases

Windows installers are published under [Releases](../../releases). There is no
macOS build yet.

Installers are not code signed yet, so Windows SmartScreen will warn the first
time you run one. The download page on the website explains what that warning
means and how to check the file against its published SHA256 before you trust it.

## Trial

The current build runs as a trial. Exports carry a watermark on every page and
are limited to the 50 most recent messages in a conversation. A one-time licence
removes both, and there will never be a subscription.

Licence keys are verified offline, so the program never contacts a server to
check one.

## Source

The application source is closed and is not in this repository. What lives here
is the release history and the issue tracker.

Notes on Apple's message format are open and live in
[ChatExportKnowledge](https://github.com/ChatExport/ChatExportKnowledge): the
sms.db schema from iOS 11 to 26, attributedBody, backup layout, encrypted
backups, and what cannot be recovered.

## Reporting a problem

Open an issue, or write to <support@getchatexport.com>. The program writes logs
locally and they can be attached to a report.

---

Apple, iPhone, iMessage and macOS are trademarks of Apple Inc. ChatExport is not
affiliated with Apple Inc.
