---
title: "Contact"
permalink: "/contact.html"
locale: en
---

{% assign ppl = page.pagination.locale %}
{% if ppl == nil %}
    {% assign ppl = page.locale %}
{% endif %}

2: {{ppl}}
{% assign strings = site.data.translations.strings[ppl] %}
{% assign dates = site.data.translations.dates[ppl] %}



<form action="https://formspree.io/{{site.email}}" method="POST">    
  <p class="mb-4">{{ strings.contact_send }} {{site.name}}. {{ strings.contact_reply }}! ({{ strings.contact_required }}.)</p>

  <div class="form-group row">
    <div class="col-md-6">
      <input class="form-control" type="text" name="name" placeholder="{{ strings.contact_name }}*" required>
    </div>

    <div class="col-md-6">
      <input class="form-control" type="email" name="_replyto" placeholder="{{ strings.contact_email }}*" required>
    </div>
  </div>

  <textarea rows="8" class="form-control mb-3" name="message" placeholder="{{ strings.contact_msg }}*" required></textarea>    

  <input class="btn btn-success" type="submit" value="{{ strings.send_btn }}">
  
</form>