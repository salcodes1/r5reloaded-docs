---
description: How to kick clients from your server via the In-Game console.
---

# Kick Commands

## Kicking Clients

Kicking a client by name works like the following:

```text
kick clientname
```

{% hint style="info" %}
If special characters do not allow you to kick the client by client name refer to use kickid.
{% endhint %}

Kicking a player by originid/userid/ipaddress works like the following:

```text
kickid originid
kickid userid
kickid ipaddress

Examples don't include the text with the octothorpe:

kickid 1000000000   #originid
kickid 1            #userid
kickid 127.0.0.0    #ipaddress
```

{% hint style="info" %}
You can get the ipaddress and the userid by refering to the page below.

{% page-ref page="status-command.md" %}
{% endhint %}

