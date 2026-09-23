Find US on Telegram : https://t.me/The_Channelizer
Open for disquations and Ideas. A public brainstorming is better than no brainstorming :) cheers 


📡 The_Channelizer

Satellite Database Manager for Windows
Manage, inspect, organize, convert, merge and verify satellite receiver channel databases with a modern PyQt6 interface.

<p align="left">
  <img src="https://img.shields.io/badge/version-v3.0-0A84FF" alt="Version">
  <img src="https://img.shields.io/badge/Python-3.11-3776AB?logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/UI-PyQt6-41CD52?logo=qt&logoColor=white" alt="PyQt6">
  <img src="https://img.shields.io/badge/platform-Windows%2010%20%7C%2011-0078D4?logo=windows&logoColor=white" alt="Windows">
  <img src="https://img.shields.io/badge/formats-DB%20%7C%20SDX%20%7C%20CHL-8A2BE2" alt="Formats">
</p>

✨ Features

📂 Open and auto-detect receiver files: .db, .sdx, .chl

🗄️ SQLite DB support with receiver-table compatibility and integrity checks

📦 SDX Mode 1 support — CDX header + zlib-compressed binary payload

🧾 SDX Mode 2 support — JSON-stream receiver database format

📡 CHL Ver 1 support — native concatenated JSON receiver export

📺 Unified TV / Radio channel browser

🔍 Fast search and filtering by channel, satellite, DB ID and order

↕️ Sortable channel table

⭐ Favorites management with multi-channel selection

🗂️ Favorite-group rename and ordering

🛰️ Satellite management

ℹ️ Detailed Channel / Transponder / Satellite / Favorites information

📊 Summary view with receiver database counts

🔄 DB ↔ SDX ↔ CHL conversion

🧩 Mixed-format merge: DB + SDX + CHL

✅ Built-in receiver file verifier

💾 BOX-SAFE automatic backups before native edits

🛡️ Verified Save As workflow using temporary output before replacement

🖱️ Drag & drop support

🌐 7 interface languages

🌙 System / Dark / Light themes

📐 Responsive UI for smaller displays

🍔 Collapsible sidebar / hamburger menu

🪟 Windows GUI build with no CMD window

🚀 Splash screen and modern PyQt6 interface

📁 Supported formats

Format

Extension

Support

SQLite Receiver Database

.db

✅

SDX Mode 1 — Binary + zlib

.sdx

✅

SDX Mode 2 — JSON stream

.sdx

✅

CHL JSON Stream Ver 1

.chl

✅

The format is detected from the file contents, not only from the extension.

⭐ Favorites

The_Channelizer includes native favorite handling for supported formats.

You can:

add or remove selected channels from favorite groups

work with multiple selected channels

clear all favorites from selected channels

rename favorite groups

reorder favorite groups in the application

view favorite membership directly in the channel table

open a Favorites summary page

Keyboard shortcuts:

1 ... 9   Toggle Favorite slot 1 ... 9
Ctrl + F  Focus search
F1        Instructions

🛰️ Satellites

The Satellites tool lets you inspect the satellites inside the current receiver file.

SQLite DB

Satellite deletion is supported together with related cleanup of:

transponders

channels

audio data

subtitles

favorite links

receiver mapping records

CHL

Satellite deletion is supported with automatic re-indexing of:

satellites

transponders

channels

favorite channel references

SDX

Satellite deletion is intentionally locked in v3.0 until additional receiver-side validation is completed for binary SDX re-indexing.

ℹ️ Channel Info

Double-click any channel or use the right-click menu.

Depending on the receiver format, The_Channelizer can display:

Channel

Name

Provider

TV / Radio type

Service ID

Video PID

PCR PID

PMT PID

Video codec/type

Lock / Skip / Hide state

Receiver-specific fields

Transponder

Frequency

Symbol rate

Polarization

FEC

Modulation

Stream ID

TS ID / ON ID

PLS / multistream fields where available

Satellite

Satellite name

Orbital angle

Band

receiver-specific satellite parameters

Favorites

Every favorite group that contains the selected channel

🔄 Converter

The built-in converter supports:

DB  → SDX
DB  → CHL

SDX → DB
SDX → CHL

CHL → DB
CHL → SDX

The source format is detected automatically.

The generated target file is verified before it is reported as ready.

Different receiver formats do not contain exactly the same fields.
Conversion is structural and cannot guarantee byte-for-byte equivalence with the original receiver format.

🧩 Merge

The_Channelizer can merge multiple receiver files using a common internal data model.

Supported combinations include:

DB  + DB
DB  + SDX
DB  + CHL
SDX + SDX
SDX + CHL
CHL + CHL

Output can be:

.db
.sdx
.chl

The merged file is automatically verified.

✅ Verifier

The verifier performs format-specific checks before files are considered ready.

SQLite DB

SQLite integrity check

required receiver tables

required receiver columns

receiver schema compatibility

SDX

SDX mode detection

header / object structure

count consistency

satellite ↔ transponder links

program ↔ transponder links

favorite references

CHL

CHL Ver 1 header

satellite / TP / channel / favorite counts

continuous object indexes

TP → Satellite references

Channel → TP references

Favorite → Channel references

🛡️ BOX-SAFE mode

Receiver files can be sensitive, so The_Channelizer uses a conservative write workflow.

Automatic backup

Before the first native modification of a loaded receiver file:

original_file.ext.Channelizer_YYYYMMDD_HHMMSS.bak

is created automatically.

Safe Save As

The application writes to a temporary file first:

Receiver Data
     ↓
Temporary Output
     ↓
Verifier
     ↓
Backup Existing Destination
     ↓
Replace Destination

If verification fails, the destination is not replaced.

Always keep an untouched original receiver export.

💾 Save As

The main interface uses Save As… instead of silently overwriting the current export.

Native extensions are preserved:

SQLite DB → .db
SDX       → .sdx
CHL       → .chl

After a successful save, the new verified file becomes the active working file.

🔎 Search & filters

Search supports channel data such as:

channel name

satellite

DB / program ID

channel order

The filter buttons support:

All
TV
Radio
Off

The visible channel count updates immediately.

🌐 Languages

The_Channelizer currently includes:

🇬🇧 English

🇬🇷 Ελληνικά

🇮🇹 Italiano

🇫🇷 Français

🇩🇪 Deutsch

🇷🇺 Русский

🇨🇳 中文

The selected language is stored and restored automatically.

🎨 Interface

The application includes:

System Auto theme

Dark theme

Light theme

responsive layout

compact sidebar

expanded sidebar

automatic sidebar collapse on smaller displays

auto-fitting application title

horizontal table scrolling for large favorite layouts

Minimum usable window size is approximately:

820 × 560

🖥️ Requirements

Run from source

Windows 10 / Windows 11
Python 3.11
PyQt6

Install PyQt6:

py -3.11 -m pip install PyQt6

Run:

py -3.11 The_Channelizer_v3.0.pyw

📦 Build Windows EXE

Install the build tools:

py -3.11 -m pip install PyQt6 pyinstaller auto-py-to-exe

Launch:

auto-py-to-exe

Recommended settings:

Script          The_Channelizer_v3.0.pyw
Name            The_Channelizer
One File        ON
Window Based    ON
Console         NONE
Icon            The_Channelizer.ico
Version File    The_Channelizer_version_info.txt
Manifest        The_Channelizer.manifest
Clean           ON
Optimize        1
UPX             OFF
UAC Admin       OFF
UAC UIAccess    OFF

Direct PyInstaller example:

py -3.11 -m PyInstaller ^
  --noconfirm ^
  --clean ^
  --onefile ^
  --windowed ^
  --noupx ^
  --optimize 1 ^
  --name The_Channelizer ^
  --icon The_Channelizer.ico ^
  --version-file The_Channelizer_version_info.txt ^
  --manifest The_Channelizer.manifest ^
  The_Channelizer_v3.0.pyw

Output:

dist\The_Channelizer.exe

⚠️ Receiver compatibility

Receiver database formats are often firmware-specific.

A file passing The_Channelizer verification means that it is structurally consistent with the implemented format profile. It does not guarantee that every receiver model or firmware revision will accept the generated file.

For new receiver formats or compatibility reports, please include:

Receiver brand/model
Firmware version
Export format
The_Channelizer version
Operation performed
Error / receiver behavior

Real receiver exports are extremely useful for improving compatibility.

🤝 Discussions, testing & ideas

The project is open to:

receiver format research

compatibility reports

sample exports

populated-favorite CHL samples

SDX Mode 1 test files

UI improvements

translations

bug reports

feature ideas

A public brainstorming is better than no brainstorming :) Cheers!

👨‍💻 Development

The_Channelizer is built with:

Python

PyQt6

SQLite

JSON

zlib

binary receiver structure parsing

receiver-specific format adapters

a common internal conversion / merge model

The application remains intentionally conservative with receiver data: unsupported or insufficiently validated destructive operations are kept disabled rather than guessed.

📬 Community

ALU DEV TEAM @ 2026
Nikolaos K. Paridis シ (nikkpap)

📧 nikkpap@gmail.com
💬 Telegram — The_Channelizer
💻 GitHub — nikkpap/The_Channelizer

📌 Current version

The_Channelizer v3.0

Version numbering continues from v3.0 onward.

❤️ Final note

Keep your original receiver export, test generated files carefully, and share what you learn.

The_Channelizer — Satellite Database Manager
