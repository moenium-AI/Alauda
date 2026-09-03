<div align="center">

<img src="Logo/PNG/alauda_logo_wide.png" alt="Alauda" width="420">

**A multifunctional DSP component for foobar2000**

[![Platform](https://img.shields.io/badge/platform-Windows%20x64-lightgrey)](#requirements)
[![Host](https://img.shields.io/badge/host-foobar2000%20v2.x%2064--bit-orange)](https://www.foobar2000.org/)
[![License](https://img.shields.io/badge/license-proprietary%20freeware-green)](#license)

[Product page](https://moenium.net/alauda/) ·
[Manual](https://moenium.net/alauda/manual/1.0/) ·
[GitHub Releases](../../releases/latest) ·
[BOOTH](https://moenium.booth.pm/items/8779312) ·
[Changelog](Distribution/changelog.md) ·
[日本語 README](README.ja.md)

</div>

<p align="center">
  <a href="https://ko-fi.com/moenium">
    <img src="images/kofi_banner.png" alt="Support Alauda on Ko-fi" width="1000">
  </a>
</p>

<p align="center">
  <a href="https://ko-fi.com/moenium"><strong>Enjoying Alauda? Support me on Ko-fi</strong></a>
</p>

---

Alauda sits in the foobar2000 playback chain and processes audio on its way to
the output device. It brings together a range of tools for making music sound
the way you want it to: resampling, tone shaping, saturation, EQ, reverb,
stereo placement, headphone correction, and output protection, all in a single
plug-in.

Thirteen processing stages run in a fixed order, and each stage can be enabled
independently. A fresh installation is deliberately close to inactive. Almost
every stage, including the resampler, starts disabled, so hearing no difference
immediately after installation is expected.

<div align="center">
<img src="screenshots/alauda_screenshot/08_eq_compact.png" alt="Alauda configuration window - EQ page" width="720">
</div>

## Contents

- [Features](#features)
- [Signal flow](#signal-flow)
- [Screenshots](#screenshots)
- [Requirements](#requirements)
- [Installation](#installation)
- [Getting started](#getting-started)
- [Download and verification](#download-and-verification)
- [Documentation](#documentation)
- [Presets and languages](#presets-and-languages)
- [About this repository](#about-this-repository)
- [Feedback and bug reports](#feedback-and-bug-reports)
- [License](#license)

## Features

- **13 stages in one window.** Each stage is independent and individually switchable. Processing order is fixed, making the resulting signal path predictable.
- **Resampler** with direct or cascade conversion, four phase modes, and selectable filter quality.
- **17 reverb spaces**, from ambience to plate reverbs, with adjustable early reflections.
- **24 saturation characters**, covering tape speeds and valve topologies.
- **8-band parametric EQ** with 22 presets and multiple filter types.
- **Headphone processing** with Crossfeed, Virtual Speakers, and a 10-band Headphone Match correction.
- **10 genre profiles** that apply coordinated settings across multiple stages.
- **Finish stage** with loudness matching, auto headroom, safety limiting, and dither.
- **Three themes**: Light, Dark, and High Contrast.
- English and Japanese interfaces, with additional translations loadable from language files.
- Settings are stored in the foobar2000 profile, so they survive Alauda updates. Settings can also be exported to or imported from a file from any page.

## Signal flow

| Section | Stages |
| --- | --- |
| Rate | Resampler |
| Main chain | Reconstruction · Dynamics Restoration · Enhance · Analog · Saturation · EQ · Reverb |
| Corrective | Refine (subsonic, ultrasonic, fatigue guard) |
| Placement | Stereo Image · Headphone · Headphone Match |
| Protection | Finish (loudness match, headroom, limiter, dither) |

Ordering inside foobar2000's **Active DSPs** list also matters. A DSP placed before Alauda feeds its output into Alauda, while a DSP placed after Alauda processes Alauda's output.

## Screenshots

| Profiles | Saturation |
| --- | --- |
| ![Profiles](screenshots/alauda_screenshot/01_profiles_compact.png) | ![Saturation](screenshots/alauda_screenshot/07_saturation_compact.png) |

| Reverb | Headphone |
| --- | --- |
| ![Reverb](screenshots/alauda_screenshot/09_reverb_compact.png) | ![Headphone](screenshots/alauda_screenshot/12_headphone_compact.png) |

<details>
<summary><strong>More screenshots</strong></summary>

<br>

| Resampler | Reconstruction |
| --- | --- |
| ![Resampler](screenshots/alauda_screenshot/02_resampler_compact.png) | ![Reconstruction](screenshots/alauda_screenshot/03_reconstruction_compact.png) |

| Dynamics Restoration | Enhance |
| --- | --- |
| ![Dynamics Restoration](screenshots/alauda_screenshot/04_dynamics_compact.png) | ![Enhance](screenshots/alauda_screenshot/05_enhance_compact.png) |

| Analog | EQ |
| --- | --- |
| ![Analog](screenshots/alauda_screenshot/06_analog_compact.png) | ![EQ](screenshots/alauda_screenshot/08_eq_compact.png) |

| Refine | Stereo Image |
| --- | --- |
| ![Refine](screenshots/alauda_screenshot/10_refine_compact.png) | ![Stereo Image](screenshots/alauda_screenshot/11_stereo_compact.png) |

| Headphone Match | Finish |
| --- | --- |
| ![Headphone Match](screenshots/alauda_screenshot/13_headphone_match_compact.png) | ![Finish](screenshots/alauda_screenshot/14_finish_compact.png) |

</details>

## Requirements

| | |
| --- | --- |
| OS | Windows |
| Host | foobar2000 v2.x, **64-bit only** |
| CPU | x86-64 (Intel / AMD) |
| Output | Any audio device foobar2000 can open |
| Additional runtime | None |

The 32-bit version of foobar2000 is not supported. Under a 32-bit host, the component will not appear in DSP Manager.

Processing cost depends on the stages enabled and the sample rate at which the chain operates. A high resampling factor combined with a high filter quality is the largest single source of processing load. If playback is unstable, review these two settings first.

Using a high resampling factor also requires an output device that accepts the resulting sample rate.

## Installation

1. Close foobar2000.
2. Double-click `foo_dsp_alauda.fb2k-component`, or open **File → Preferences → Components** and choose **Install…**.
3. Select **Apply**. foobar2000 restarts to complete the installation.

Installing the component alone does not add it to the playback chain.

4. Open **File → Preferences → Playback → DSP Manager**.
5. Move **Alauda** into **Active DSPs**.
6. Select **Configure selected** to open the configuration window.
7. Select **Apply**.

### Uninstalling

Move Alauda out of **Active DSPs**, then remove **Alauda DSP** from **Preferences → Components** and select **Apply**.

Translation files that you manually placed in the language folder are left in place.

## Getting started

Start with **Quick start** in the [online manual](https://moenium.net/alauda/manual/1.0/). It gets you to a safe starting point in just a few minutes.

The **Help** command in the configuration window opens the manual page corresponding to the page currently shown.

> **Set your playback volume low before you begin.** Several stages can change peak level or perceived loudness. The protection features on the Finish page, including Auto Headroom and Safety Limiter, are disabled by default. Enable them as needed.

> **Crossfeed and Virtual Speakers are intended for headphone listening.** With loudspeakers, acoustic crosstalk already occurs naturally between the channels and both ears, so applying these processes again can make the stereo image sound narrower or unnatural. Disable the Headphone page when listening through speakers.

## Download and verification

The latest version of Alauda is available from [GitHub Releases](../../releases/latest), the [product page](https://moenium.net/alauda/), or [BOOTH](https://moenium.booth.pm/items/8779312).

Each GitHub Release lists the distributed file name, checksums, and the corresponding VirusTotal scan result. To verify a downloaded archive, calculate its hash and compare it with the value listed for that release.

On Windows PowerShell, SHA-256 can be calculated with:

```powershell
Get-FileHash .\Alauda_*.zip -Algorithm SHA256
```

A matching checksum confirms that the downloaded file is identical to the file identified on the corresponding release page.

## Documentation

- [Online manual (English / 日本語)](https://moenium.net/alauda/manual/1.0/)
  - Detailed descriptions of each processing stage
  - Default values and ranges for all parameters
- [Changelog](Distribution/changelog.md)
- [README bundled with the release (English)](Distribution/readme_en.txt)
- [README bundled with the release (日本語)](Distribution/readme.txt)
- [EULA](Distribution/EULA_en.txt)
- [Japanese EULA](Distribution/EULA_jp.txt)
- [Third-party notices](Distribution/third-party-notices.txt)

## Presets and languages

**Preset Pack Vol.1 / Vol.2** are optional preset collections designed to make it easier to explore Alauda's settings.

They do not add to or restrict Alauda's functionality. In the official distribution, they are supplied separately from the component itself. Extract and use them as needed.

### Japanese interface

The Japanese interface is optional.

Copy `Languages\ja-JP.lng` from the release archive into the `languages` folder opened through **Profiles → Open Folder** in foobar2000.

Alauda reads translation files from the foobar2000 profile rather than from beside the component DLL.

### Experimental translations

`Languages/experimental/` contains draft language files for:

- German
- French
- Spanish
- Italian
- Brazilian Portuguese
- Russian
- Simplified Chinese
- Traditional Chinese
- Korean

These are review candidates rather than official translations. They are provided so native speakers can check terminology, phrasing, and whether each string fits correctly in the interface.

They are not included in the official release ZIP.

To try one, copy the corresponding `.lng` file into the `languages` folder described above and select it in Alauda.

Some strings intentionally use concise wording or established English audio terms to fit Alauda's fixed-width controls. When reviewing a translation, please check both linguistic naturalness and whether the text fits in the actual configuration window.

When reporting a correction, please include:

- Language
- Key name
- Current text
- Proposed replacement

## About this repository

This GitHub repository contains the compiled plug-in, documentation, language files, presets, and related release files.

**Alauda's program source code is not published.**

GitHub may automatically show **Source code (zip)** and **Source code (tar.gz)** downloads on Release pages. These are repository snapshots generated by GitHub. They do not contain Alauda's program source code.

## Feedback and bug reports

Bug reports, translation corrections, and other feedback are welcome.

**contact@moenium.net**

## License

Alauda is **proprietary freeware**. It may be used free of charge for personal, professional, and commercial purposes.

Redistribution of the plug-in and its component files, other than language and preset files, is prohibited.

Redistribution of language and preset files, together with all other terms and conditions, is governed by the bundled [EULA_en.txt](Distribution/EULA_en.txt) / [EULA_jp.txt](Distribution/EULA_jp.txt).

This README is a summary only and does not modify the EULA.

### Bundled third-party software

- **JUCE 9.0.1** (JUCE 9 Starter licence), Raw Material Software Limited. JUCE is used to build the configuration interface and is governed by the JUCE 9 End User Licence Agreement rather than Alauda's own licence. The Windows build also incorporates zlib, libpng, Independent JPEG Group JPEG software, HarfBuzz, SheenBidi, LunaSVG, and PlutoVG under their respective licences.
- **foobar2000 SDK**, governed by the foobar2000 project's own terms. foobar2000 itself is not part of Alauda and is not distributed with it.

See [third-party-notices.txt](Distribution/third-party-notices.txt) for details.

---

Copyright © 2026 moenium · [moenium.net](https://moenium.net/)
