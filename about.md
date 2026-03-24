---
layout: default
title: About
description: "About the Author"
---

# About the Author

[Your author bio goes here. Tell your readers about what you write, why you write it, and what they can expect from your books.]

[Second paragraph of your bio. Maybe mention your hobbies, where you live, or what you do when you aren't writing books.]

*[Your Debut Novel Name]* is my latest release. If you want to stay up to date, [join the mailing list]({{ site.author.newsletter_url }}).

<!--
  NOTE: The links below use template tags (the curly-brace syntax).
  They will look like raw code when viewing this file on GitHub,
  but they render correctly on your live site. It's all conditional,
  seriously, just ignore everything below this line.
-->
<div class="contact-links">
  <a href="mailto:{{ site.author.email }}" class="btn btn-ghost">Contact</a>
  {% if site.author.newsletter_url and site.author.newsletter_url != "" %}
  <a href="{{ site.author.newsletter_url }}" class="btn btn-ghost" target="_blank" rel="noopener">Newsletter</a>
  {% endif %}
  {% if site.author.amazon_url and site.author.amazon_url != "" %}
  <a href="{{ site.author.amazon_url }}" class="btn btn-ghost" target="_blank" rel="noopener">Amazon</a>
  {% endif %}
</div>
