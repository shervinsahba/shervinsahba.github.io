---
title: Building Website
image: /assets/img/blog/steve-harvey.jpg
description: >
  I recently switched my website layout. I'll follow up with updates.
---


![Dark Mode](/assets/img/blog/dark-mode.jpg){:data-width="1440" data-height="836"}
*This is what it looks like!*
{:.figure}

A unique challenge with regards to Hydejack was its color customization feature. As it turns out, a generic gray does not look good when combined with many accent colors, while a slightly tinted gray only looks good with a small range of accent colors.

To solve the problem, Hydejack's Dark Mode adjusts the background based on the `theme_color`. This property can be set for the entire site, or individual pages just like `accent_color`. It also adjusts the UI of many browsers that support the Web App Manifest API, making the whole experience even more seamless.

![Adaptive Dark Mode Example](/assets/img/blog/dark-mode-ii.jpg){:data-width="1440" data-height="836"}
Dark Mode adjusts to a different accent colors.
{:.figure}

While it's not feasible to enable Dark Mode based on a visitor's exact sunrise and sunset times[^1], site authors can opt-in to enable Dark Mode based on a visitor's local time.

Site authors can also enable Dark Mode by default and/or hide the light switch:

```yml
hydejack:
  dark_mode:
    # Set to `true` to always use the dark theme.
    always:            false

    # Set to `true` to use the dark theme based on visitors' local time.
    dynamic:           true
    sunrise:           6
    sunset:            18

    # Set to `true` to allow visitors to switch between light and dark mode.
    icon:              true
```