---
layout: post
title: Trim 3GB from Mathematica
---

> **This article describes how to reduce Mathematica’s footprint by 3GB to 5GB, retaining all core functionality.
As always, when modifying your system, please proceed at your own discretion.**


Mathematica requires around 10GB of disk space, and its documentation takes up about half of that space. A hulking mass of this data is dedicated to the pre-rendered examples in the Documentation, though, and you can cut this information out without disrupting core functionality.

Here are a couple of suggestions to trim the fat:

#### Don't install the docs in the first place.
If you’re installing a fresh copy of Mathematica, the wizard will likely include an option to forego the documentation installation. Be warned that your F1 key will no longer conjure the help you need to grok Wolfram, and you’ll need to turn to external resources.</li>

#### Delete the documentation directory entirely.
<a href="https://mathematica.stackexchange.com/questions/81250/is-it-safe-to-remove-the-documentation-notebooks">Users have reported this to work safely</a>. On a Linux system with the appropriate permissions, this is as simple as <code>rm -r /.../Mathematica/Documentation</code>. You ought to be able to cut the folder from your Windows machine as well. Again, you’ll obviously lose documentation access with this route.</li>

#### Delete documentation output. (BEST CHOICE)
For those of us who don’t want to run around headless in a world full of quirky Wolfram functions, consider <i>deleting the output</i> from your documentation. This is the option you were hoping for: how to have your docs and eat them too. This option saved me 3.1GB of space.

How does it work? You may have realized that each help file is actually a Mathematica notebook rife with previously outputted examples. A solution, then, is to keep all the coded information in these files but rid yourself of the output. If you need to visualize these plots and data, simply evaluate the desired line in the help file or run the notebook in its entirety.

To pursue this option, I ran <a href="https://mathematica.stackexchange.com/a/115489/20203">David Z’s code provided in this Mathematica.SE answer</a>. It didn’t crash my program nor my system. You may need to have write permissions on the .../Documentation directory for this to work; the Windows equivalent would likely be to run Mathematica as administrator.

As a final note, the previous link also includes hints at other space-saving tricks, including deleting unessential Mathematica kernels. Anyway, I’m happy with the results of David Z’s code. Good stuff.