# Reporting a security problem

**Write to <support@getchatexport.com>.** Put "security" in the subject. You
will get an answer from a person.

Please do not open a public issue for anything that could put somebody's
messages at risk before it is fixed.

## What is in scope

ChatExport runs on your own PC, reads a backup Apple's software already wrote
to your disk, and has no server, no account and no telemetry. So the
interesting failures are local ones:

- Anything that would send message content, a backup password or a licence key
  off the machine.
- Anything that leaves decrypted material on disk after the program closes.
  It decrypts only the files it needs and wipes them on exit, and a case where
  it does not is a bug worth reporting.
- A backup password recoverable from disk, from a log file or from memory after
  use. It is used and forgotten: never written down, never sent anywhere.
- Code execution from a crafted backup, a crafted WhatsApp export file or a
  crafted attachment. All three are attacker-controlled input by nature.
- A signature or installer problem: a package where not every executable is
  signed, or a download that does not match its published SHA256.

## What is not a vulnerability

- **SmartScreen warning on first run.** The installer is signed. That panel is
  Application Reputation, which counts downloads rather than certificates.
- **The log files.** They describe what the program did, not what your messages
  say, and they stay on your machine.
- **Reading a backup you are not entitled to read.** That is a question about
  consent and about the law where you live, not about software.
- **A forgotten backup password.** There is no way past one, by this program or
  any other, and that is a property of Apple's encryption rather than a defect
  here.

## What helps

The version (Help, or the installer file name), what you did, what you
observed, and how you observed it. If a file triggers it, say what kind of file
rather than attaching real messages. Nobody here needs your conversations to
reproduce a bug.

## What you can expect

An acknowledgement, a fix or an explanation of why something is not one, and
credit in the release notes if you want it. This is a small product with one
author, so the honest promise is attention, not a service level agreement.
