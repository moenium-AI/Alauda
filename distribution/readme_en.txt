================================================================
 Alauda  Version 1.0.0
================================================================

A multifunctional DSP component for foobar2000

  Copyright (C) 2026 moenium
  Release date : 2026-08-29


----------------------------------------------------------------
 1. Overview
----------------------------------------------------------------

Alauda is a multifunctional DSP component for foobar2000. It sits in
the playback chain and reshapes the signal on its way to the output
device.

A set of tools for making music sound the way you want it to, gathered
into a single plug-in. Combine them however you like.

Thirteen stages run in a fixed order, and each can be enabled on its
own: Resampler, Reconstruction, Dynamics Restoration, Enhance, Analog,
Saturation, EQ, Reverb, Refine, Stereo Image, Headphone, Headphone
Match and Finish.

A Genre Profile applies a coordinated set of values across several
stages at once. The interface is available in English and Japanese,
and further translations can be added.

For each stage in detail, and for every parameter with its default and
range, see the online manual:

    https://moenium.net/alauda/manual/1.0/


----------------------------------------------------------------
 2. Distribution terms
----------------------------------------------------------------

Freeware. Free for personal and commercial use.

Preset Pack Vol.1 and Vol.2 are additional preset packs that make it easier to
try Alauda's settings. They are not part of the Alauda component; they are
included as separate ZIP files in this release archive. They do not add to or
restrict the plug-in's features. Extract and use them as needed.

Redistribution, modification, reverse engineering and all other use
conditions are set out in the bundled EULA_jp.txt / EULA_en.txt. This
README provides only a summary and does not change the EULA.


----------------------------------------------------------------
 3. Requirements
----------------------------------------------------------------

  OS        : Windows
  Host      : foobar2000 (64-bit only)
  CPU       : x86-64 (Intel / AMD)
  Output    : Any audio device foobar2000 can open

Additional software: none required

The 32-bit build of foobar2000 is not supported. Under a 32-bit host
the component will not appear in DSP Manager.

Processing cost depends on which stages are enabled and on the sample
rate the chain runs at. The resampler factor combined with a high
filter quality is by far the largest single cost; if playback is not
stable, review those two settings first.

Using a high factor requires an output device that accepts the
resulting sample rate.


----------------------------------------------------------------
 4. Installation
----------------------------------------------------------------

  1. Close foobar2000.
  2. Double-click the bundled foo_dsp_alauda.fb2k-component.
     (Or open File > Preferences > Components in foobar2000 and
      choose Install...)
  3. Select Apply. foobar2000 restarts to finish the installation.

Japanese language (optional): copy `Languages\ja-JP.lng` from this release
archive into the `languages` folder opened by **Profiles > Open Folder**.
Alauda reads translation files from the foobar2000 profile, not beside the
component DLL.

Installing the component does not put it in the playback chain.
Continue with the following steps.

  4. Open File > Preferences > Playback > DSP Manager.
  5. Move "Alauda" into Active DSPs.
  6. Use Configure selected to open the configuration window.
  7. Select Apply.

Ordering inside Active DSPs matters: any DSP before Alauda feeds its
output into Alauda, and anything after it processes Alauda's result.


----------------------------------------------------------------
 5. Getting started
----------------------------------------------------------------

Please read the online manual at the following URL:

    https://moenium.net/alauda/manual/1.0/

An internet connection is required. Both English and Japanese are
available.

The Help command in the configuration window opens the online page for
the page currently shown.

If this is your first time, start with "Quick start". It walks you to
a safe working result in a few minutes.

A fresh installation is deliberately close to inactive. Almost every
stage, the resampler included, starts disabled, so hearing no
difference immediately after installing is the expected result.


----------------------------------------------------------------
 6. Uninstalling
----------------------------------------------------------------

  1. Open File > Preferences > Playback > DSP Manager and move
     "Alauda" out of Active DSPs.
  2. Open File > Preferences > Components, select "Alauda DSP" and
     remove it.
  3. Select Apply and let foobar2000 restart.

Removing the component stops all Alauda processing. Any translation
files you placed in the language folder yourself are left in place.


----------------------------------------------------------------
 7. Notes on use
----------------------------------------------------------------

[Playback level]

Several stages change peak level or perceived loudness. Set your
playback volume low before you begin.

The protections on the Finish page (Auto Headroom, Safety Limiter)
are disabled by default. Enable them yourself.

[Where settings are stored]

Settings live in your foobar2000 profile, not in the component
package, so they survive an update of Alauda.

Settings can be exported to and imported from a file using the
buttons present on every page. Exporting before a large change is a
reliable way back.

[Headphone features]

Crossfeed and Virtual Speakers on the Headphone page are for
headphone listening only. On speakers they process a signal that
already has acoustic crossfeed, which sounds narrow and hollow.
Disable that page when listening on speakers.


----------------------------------------------------------------
 8. Licence
----------------------------------------------------------------

Alauda: proprietary freeware

  Free for personal, professional and commercial use.
  Redistribution of the plug-in and its component files, other than language
  and preset files, is prohibited. Redistribution of language and preset files,
  and all other conditions, are set out in the bundled EULA_jp.txt / EULA_en.txt.

Bundled software:

  - JUCE 9.0.1 (JUCE 9 Starter licence): Raw Material Software Limited
    Used to build the configuration interface. It is governed by the
    JUCE 9 End User Licence Agreement, not by Alauda's own licence.
    The Windows build also incorporates zlib, libpng, Independent JPEG Group
    JPEG software, HarfBuzz, SheenBidi, LunaSVG and PlutoVG under their own
    licences.

  - foobar2000 SDK (foobar2000 project's own terms)
    Used to build Alauda as a foobar2000 component. foobar2000
    itself is not part of Alauda and is not distributed with it.

  See the bundled third-party-notices.txt for details.


----------------------------------------------------------------
 9. Contact and support
----------------------------------------------------------------

  Author        : moenium
  Website       : https://moenium.net/
  Product page  : https://moenium.net/alauda/
  Contact       : contact@moenium.net

For contact and bug reports, email the address above.

When reporting a problem, use the "Copy info" button on the About
page of the configuration window and include the result. It captures
the Alauda version and the foobar2000 build together.

It also helps to include:

  - What you expected to happen, and what happened instead
  - The source sample rate and the output device
  - Which stages were enabled
  - Whether the problem persists with only the Resampler enabled

For sample-rate conversion or playback stability problems, enable
"Log plan" and "Log runtime" on the Diagnostics page and include the
foobar2000 console output (View > Console).


----------------------------------------------------------------
 10. Changelog
----------------------------------------------------------------

See the bundled changelog.md for changes in each version.


================================================================
