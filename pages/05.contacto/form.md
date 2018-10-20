---
title: Contacto
published: false
form:
    name: contact
    fields:
        -
            name: name
            label: Name
            placeholder: 'ingresá tu nombre'
            autocomplete: 'off'
            type: text
            validate:
                required: true
        -
            name: email
            label: Email
            placeholder: 'ingresá tu dirección de correo'
            type: email
            validate:
                required: true
        -
            name: message
            label: Message
            placeholder: 'Escribinos tu mensaje'
            type: textarea
            validate:
                required: true
    buttons:
        -
            type: submit
            value: Enviar
        -
            type: reset
            value: Reset
    process:
        -
            email:
                subject: '[Site Contact Form] {{ form.value.name|e }}'
                body: '{% include ''forms/data.html.twig'' %}'
        -
            save:
                fileprefix: contact-
                dateformat: Ymd-His-u
                extension: txt
                body: '{% include ''forms/data.txt.twig'' %}'
        -
            message: 'Gracias por contactarte con nosotras!!'
---

Escribinos y pronto nos pondremos en contacto
