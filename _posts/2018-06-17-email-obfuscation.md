---
layout: post
title: Email [at] obfuscation [dot] whatever?
---

>My email address is on clear display: {% include email.html %}. Is this madness? Will I succumb to spam crawlers?? Should I have opted for the traditional "foo [at] bar [dot] com" approach?! Well, here's the thing. What you're seeing is some sleight-of-hand. 

Here's the actual code:

<pre><code class="language-html">
&lt;span style="display: inline-block; unicode-bidi: bidi-override; direction: rtl;"
onmouseover="this.innerText=this.innerText.split('').reverse().join('');
 this.style.unicodeBidi=''; this.removeAttribute('onmouseover');">
ude.wu@abhass
&lt;/span>
</code></pre>

The style property is set to reverse text direction, so the server and most bots see "ude.wu@abhass". Bots typically seek the "@" symbol and then a dot afterwards, so I'm not at much risk here. A spammer could program their crawler to run forwards *and backwards* to sniff out my email address, but that would mine too many false positives. In any case, <a href="https://superuser.com/questions/235937/does-e-mail-address-obfuscation-actually-work">this security measure appears effective</a>, as the linked Superuser.SE post discusses.

The mouseover property requires a javascript enabled browser. This code lets you copy the reversed text and magically paste it in the forward direction. Credit is due to user <a href="https://superuser.com/questions/235937/does-e-mail-address-obfuscation-actually-work#comment786336_235965">abenier's comment</a>. Without the mouseover code, you'll copy the reversed string. For example, see what happens when you copy and paste the following text that doesn't use the javascript mouseover code:
<span style="display: inline-block; unicode-bidi: bidi-override; direction: rtl;">
I HAVE DECODED THE ULTRA SECRET MESSAGE!
</span>
