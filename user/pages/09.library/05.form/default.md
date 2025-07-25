---
title: Formulare
cache_enable: false
form:
  name: contact-form
  classes: form
  fields:
    name:
      id: field-name
      label: Name
      autocomplete: on
      type: text
      outerclasses: encapsulate
      validate:
        required: true

    email:
      id: field-email
      label: E-Mail
      type: email
      outerclasses: encapsulate
      validate:
        required: true

    kdnr:
      id: field-kdnr
      label: Kundennummer
      type: text
      autocomplete: on
      outerclasses: encapsulate
      # help: Findet sich auf der Rechnung

    subject:
      id: field-subject
      label: Betreff
      type: select
      size: long
      outerclasses: encapsulate
      validate:
        required: true
      options:
        '': 'Bitte auswählen'
        'Frage zu einem Produkt': 'Frage zu einem Produkt'
        'Frage zu Vertrag/Rechnung': 'Frage zu Vertrag/Rechnung'
        'Frage zum Fluxkompensator': 'Frage zum Fluxkompensator'
        'Störung': 'Störung'
        'Sonstige Themen': 'Sonstige Themen'

    weather:
      outerclasses: encapsulate inputpeel
      type: radio
      label: 'Wie ist das Wetter?'
      default: nice
      options:
        nice: Schön
        average: 'Geht so'
        meh: Meh
        disaster: 'Katastrophal'

    skills:
      outerclasses: encapsulate inputpeel rows
      type: checkboxes
      label: 'Was kannst du?'
      default: nice
      options:
        html: HTML
        css: CSS
        js: JengaScript
        shit: TechBro Frameworks®

    file:
      label: THEME_C.JOBS.CV
      type: file
      multiple: false
      filesize: 4
      destination: tmp/uploads
      # destination: self@
      avoid_overwriting: true
      accept:
        - application/pdf
        - application/x-pdf
        - text/plain
        - image/jpeg
        - application/msword
        - application/vnd.openxmlformats-officedocument.wordprocessingml.document
        - application/vnd.oasis.opendocument.text
        
    text:
      id: field-text
      label: Nachricht
      type: textarea
      outerclasses: encapsulate
      rows: 5
      validate:
        required: true

    personality:
      id: field-personality
      outerclasses: encapsulate inputpeel
      label: 'Anti-Spam-Frage: Wie lautet der Vorname von Robert Koch?'
      type: radio
      options:
        bert: Bert
        robert: Robert
        herbert: Herbert
      validate:
        required: true
        pattern: "^robert$"
        message: Bei der Anti-Spam-Frage versagt.

    dsgvo:
      id: field-dsgvo
      label: 'Ich stimme den [Datenschutzrichtlinien](/datenschutz) zu'
      type: checkbox
      markdown: true
      validate:
        required: true

  buttons:
    submit:
      type: submit
      value: Senden

  process:
    # email:
    #   from: "{{ form.value.email }}"
    #   from_name: "{{ form.value.name }}"
    #   to: "{{ config.plugins.email.to }}"
    #   reply_to: "{{ form.value.email }}"
    #   subject: "Anfrage über Kontaktformular: {{ form.value.subject }}"
    #   body: "{% include 'email/contact.txt.twig' %}"
    #   content_type: 'text/plain'
    save:
      fileprefix: contact-
      dateformat: Ymd-His-u
      extension: txt
      body: "{% include 'forms/data.txt.twig' %}"
    message: Danke für Ihre Nachricht
    # display: thankyou
---
Formular mit vielen Typen.

{% include "forms/form.html.twig" with { form: forms('contact-form') } %}

Test eines Button: <a href="#foo" class="button">[icon=mail] Kontakt</a>

<a href="#foo" class="button">[icon=mail] Kontakt</a>
<a href="#foo" class="button is-small">[icon=mail] Kontakt</a>
<a href="#foo" class="button is-alt">[icon=mail] Kontakt</a>
<a href="#foo" class="button is-quiet">[icon=mail] Kontakt</a>
<a href="#foo" class="button is-ghost">[icon=mail] Kontakt</a>