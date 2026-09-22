# ChatExport

Exports iPhone messages (SMS, MMS, RCS and iMessage) and WhatsApp conversations
into searchable PDF, TXT, HTML, CSV and RSMF. Everything runs on your own
Windows PC. There is no account, no server and no upload.

Website: <https://getchatexport.com>
Download: <https://getchatexport.com/download/>

## What it reads

Two sources, and only one of them needs an iPhone.

**An iPhone backup** made by Apple Devices or iTunes on the same PC, from iOS 11
up to the current release. ChatExport reads the backup folder that Apple's own
software already wrote to your disk. It never signs in to anything and never
asks for an Apple ID. Encrypted backups work: it asks for that password, uses it
on your machine, and forgets it.

**A WhatsApp "Export chat" file.** WhatsApp writes that file itself, so an export
made on an Android phone opens exactly like one made on an iPhone. That is the
one part of the program that needs no iPhone, no backup and no cable.

## What it writes

Five formats: **PDF, TXT, HTML, CSV and RSMF.**

PDF comes in three themes. Chat View looks like the conversation. Court View is
monochrome and formal, prints full timestamps with the time zone, sender numbers,
delivery and read receipts and message numbering. Book View sets it as prose.

RSMF is for the recipient who does not read documents but ingests them: a
container that eDiscovery platforms accept without re-keying. The format is
documented in [ChatExportKnowledge](https://github.com/ChatExport/ChatExportKnowledge/blob/main/rsmf.md).

Every export is fingerprinted with **SHA256**, shown on the success screen and
written beside the file as `<file>.sha256`, in the form that `sha256sum -c` and
`certutil -hashfile` both accept.

The document can be written in any of fourteen languages, and that choice is
separate from the language of the program itself, which also speaks fourteen.
Your messages are never translated. They appear as they were sent.

## Releases and where the installer lives

**The current installer is on the website: <https://getchatexport.com/download/>**,
which also prints its SHA256 so you can check the file before you trust it.

Releases in this repository carry the change history. Assets attached to
releases up to 0.5.1 are older builds; the website always has the current one.

## About the SmartScreen warning

**The installer has been signed since 0.5.1**, with a timestamped Trusted
Signing certificate, and every executable inside the package is signed too.

Windows SmartScreen can still warn you the first time you run it. That warning
is Application Reputation, which counts how many people have downloaded a file
rather than whether it carries a certificate, so a new certificate does not
remove it. The download page explains what the warning means and how to verify
the file yourself.

## Trial and licence

What you download is a free trial. It writes every format and reads encrypted
backups. Each document carries a watermark on every page and stops at the 50
most recent messages in a conversation. There is no expiry date.

A one-time licence costs 34.99 USD and lifts both limits. There will never be a
subscription. Licence keys are verified offline, so the program never contacts a
server to check one. Thirty days to ask for the money back, no form and no
questions.

## What it does not do

- **No macOS build yet.** Windows 10 and Windows 11, 64-bit.
- **It exports conversations.** Call logs, contact lists, photo libraries and
  app data are deliberately out of scope.
- **It cannot promise that a court will accept a document.** Admissibility
  depends on your jurisdiction, the case and the judge, and software that
  promises otherwise should be treated with suspicion. What an export can do is
  remove the usual objections: the messages come from Apple's own backup rather
  than a photographed screen, the timestamps come from the record, the thread is
  complete rather than selected, and the file carries a fingerprint.
- **It cannot recover what the phone no longer holds.** Messages in Recently
  Deleted come back, which on iOS 16 and later is roughly the last 30 days.
  Older than that is gone from the phone, and no software brings it back.

## Source

The application source is closed and is not in this repository. What lives here
is the release history and the issue tracker.

Notes on Apple's message format are open and live in
[ChatExportKnowledge](https://github.com/ChatExport/ChatExportKnowledge): the
`sms.db` schema from iOS 11 to 26, `attributedBody`, backup layout, encrypted
backups, the RSMF container, and what cannot be recovered.

## Reporting a problem

Open an issue, or write to <support@getchatexport.com>. The program keeps local
log files you can attach. They describe what the program did, not what your
messages say.
