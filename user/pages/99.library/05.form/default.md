---
title: Formulare
cache_enable: false
form:
  name: contact-form
  classes: form
  fields:
    - name: name
      id: field-name
      label: Name
      placeholder: Ihr Name
      autocomplete: on
      type: text
      outerclasses: levitate
      validate:
        required: true

    - name: email
      id: field-email
      label: E-Mail
      placeholder: Ihre E-Mail-Adresse
      type: email
      outerclasses: levitate
      validate:
        required: true

    - name: kdnr
      id: field-kdnr
      label: Kundennummer
      placeholder: Ihre Kundennummer
      autocomplete: on
      type: text
      outerclasses: levitate

    - name: subject
      id: field-subject
      label: Betreff
      type: select
      size: long
      outerclasses: levitate
      validate:
        required: true
      options:
        'Frage zu einem Produkt': 'Frage zu einem Produkt'
        'Frage zu Vertrag/Rechnung': 'Frage zu Vertrag/Rechnung'
        'Frage zum Fluxkompensator': 'Frage zum Fluxkompensator'
        'Störung': 'Störung'
        'Sonstige Themen': 'Sonstige Themen'

    - name: text
      id: field-text
      label: Nachricht
      placeholder: Ihre Nachricht an uns
      type: textarea
      outerclasses: levitate
      rows: 5
      validate:
        required: true

    - name: personality
      id: field-personality
      outerclasses: text-input
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

    - name: dsgvo
      id: field-dsgvo
      label: 'Ich stimme den [Datenschutzrichtlinien](/datenschutz) zu'
      type: checkbox
      markdown: true
      validate:
        required: true

    - name: weather
      type: radio
      label: 'Wie ist das Wetter?'
      default: nice
      options:
        nice: Schön
        meh: 'Geht so'
        disaster: 'Katastrophal'

  buttons:
      - type: submit
        value: Senden

  process:
    # - email:
    #   from: "{{ form.value.email }}"
    #   from_name: "{{ form.value.name }}"
    #   to: "{{ config.plugins.email.to }}"
    #   reply_to: "{{ form.value.email }}"
    #   subject: "Anfrage über Kontaktformular: {{ form.value.subject }}"
    #   body: "{% include 'email/contact.txt.twig' %}"
    #   content_type: 'text/plain'
    - save:
        fileprefix: contact-
        dateformat: Ymd-His-u
        extension: txt
        body: "{% include 'forms/data.txt.twig' %}"
    - message: Danke für Ihre Nachricht
    # - display: thankyou
---
{% include "forms/form.html.twig" with { form: forms('contact-form') } %}
