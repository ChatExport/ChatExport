# Changelog

Every released build, newest first. Each heading links to its release, which
carries the full notes and, up to 0.5.1, the installer of the day.

The current installer is not here. It lives on the website, at
<https://getchatexport.com/download/>, which prints its SHA256 beside it. A
longer, less technical version of this history is at
<https://getchatexport.com/changelog/>.

---

## [1.0.0](https://github.com/ChatExport/ChatExport/releases/tag/v1.0.0) — 14 September 2026

**The app makes the backup itself.** Plug the iPhone in, unlock it, press Back
up now, and answer the Trust and passcode prompts on the phone. A repeat run
copies only what changed and says which of the two it did. Apple Devices or
iTunes still has to be installed, because that is where Apple's USB driver comes
from, but you no longer have to open it.

**The interface speaks the same fourteen languages as the document.** German,
French, Spanish, Italian, Dutch, both Portuguese variants, Czech, Romanian,
Swedish, Ukrainian and Russian join English and Polish. The two choices stay
separate, so you can work in your own language and hand a court a document in
another. None of the fourteen was machine-translated.

**Every page says where it can be checked.** The footer prints the address of
the verification page, above the page number and opposite the Bates stamp, so a
reader holding one photocopied sheet can find out that the file can be checked
rather than trusted.

The download grew to about 188 MB, from 98: the backup helper is back in the
installer and does not compress, and the fourteen interface languages account
for the rest.

## [0.5.1](https://github.com/ChatExport/ChatExport/releases/tag/v0.5.1) — 10 August 2026

**The first signed build.** Timestamped certificate, publisher BOKART Krzysztof
Kowalski, and everything inside the package signed rather than the installer
alone. SmartScreen can still interrupt a first run, because it counts downloads
rather than certificates.

**A screen for checking a document somebody sent you.** Every screen before this
one was for the person exporting. Drop in a PDF and, if it arrived with its
`.sha256` file, the app says whether the two agree; you can also paste a
checksum the sender gave you. What a match proves is stated on the screen in
plain words: it compares bytes, so it shows the file has not changed since its
checksum was recorded, and says nothing about who wrote the messages inside.

**Export to RSMF**, for firms working in an eDiscovery platform. Every other
format here is meant to be read by a person; this one is meant to be ingested,
arriving as searchable records with participants, timestamps and attachments
intact. Attachments go in as the original files from the phone, unconverted.

**The export screen says when a backup cannot hold your whole history, and
why.** Two iPhone settings decide this and neither leaves a trace in a
transcript: Messages in iCloud, which keeps older messages out of the backup,
and Keep Messages set to 30 Days or 1 Year, which is worse and quieter because
the phone deleted them outright. Both are read from the backup rather than
guessed.

Changed: the Document Integrity page names the database the document came from,
by its SHA256. Documents name the transports they actually contain — since iOS
18 a green bubble can be RCS rather than SMS, so the old fixed "iMessage / SMS"
line quietly mislabelled every conversation with an Android phone. CSV gained a
`service` column. An About screen, reachable from every step.

Fixed: **reading a backup no longer writes anything into it.** Opening the
messages database, even strictly for reading, made Windows create two working
files beside it and they stayed there — three files where there had been one,
inside the folder the documents describe as untouched. The app now works from
its own copy, and the address book inside the backup is treated the same way.

## [0.5.0](https://github.com/ChatExport/ChatExport/releases/tag/v0.5.0) — 8 August 2026

Fixed: **contact names come back.** A phone syncing Contacts from two accounts
stores every person once per account, and the check that guards against printing
the wrong person's name read those two records as two people claiming one
number, so it printed no name at all. On the address book that exposed this,
three quarters of conversations showed a bare number. Records that agree on the
name are now understood to be one person; where two genuinely different people
share a number the raw number still stands.

Changed: the app opens in the language the computer is set to, falling back to
English, rather than always in Polish. The destination folder became the control
that changes it, beside the Export button, instead of the last of eight sections
on the options page.

Added: a "How it works" strip for the case where no backup exists yet, including
the thing nobody could have guessed — the export reads a file from your disk, so
once it exists the iPhone does not need to stay connected.

The download fell to 97 MB from 167, because the experimental backup helper
stopped shipping in the installer.

## [0.4.0](https://github.com/ChatExport/ChatExport/releases/tag/v0.4.0) — 4 August 2026

A smaller download, 167 MB from 185. English documents tell the time the way
English does, "9:15 AM" rather than "09:15", while the other thirteen document
languages keep the 24-hour clock each of them uses.

Fixed: reactions introduced in iOS 18 — an arbitrary emoji or a sticker — were
printed as separate messages rather than attached to the message they reacted
to, and counted as messages in the conversation list. Two contacts whose numbers
end in the same nine digits could be told apart only by luck, and a document
could print one person's name against the other's messages; a number matching
more than one contact now resolves to no name at all. A PDF export could hang
forever with no error and no way out.

## [0.3.0](https://github.com/ChatExport/ChatExport/releases/tag/v0.3.0) — 3 August 2026

**WhatsApp chat imports.** The file WhatsApp's own Export chat button produces —
a zip with `_chat.txt` plus media, or a bare txt, from iPhone or Android — opens
as a conversation source and exports through every format. The title page names
the source file and prints its SHA256.

**Twelve more document languages**, chosen independently of the app's language,
each written natively rather than machine-translated.

## [0.2.0](https://github.com/ChatExport/ChatExport/releases/tag/v0.2.0) — 2 August 2026

First public build for Windows.

---

## A note on the installers attached to old releases

Builds 0.2.0 through 0.5.0 were published before code signing, so the installers
attached to those release pages are unsigned. Each page prints the SHA256 of its
own file, which is what stood in for a signature at the time.

Do not use them. Every fix listed above is in the current build, which is signed
and lives at <https://getchatexport.com/download/>.
