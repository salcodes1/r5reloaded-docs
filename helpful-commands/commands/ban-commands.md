---
description: >-
  How to ban and unban clients from your server via the In-Game console and how
  to reload the ban list.
---

# Ban Commands

## Banning Clients

Banning a client by name works like the following

```text
ban clientname
```

{% hint style="info" %}
If special characters do not allow you to ban the client by client name refer to use banid.
{% endhint %}

Banning a player by originid/userid/ipaddress works like the following:

```text
banid originid
banid userid
banid ipaddress

Examples don't include the text with the octothorpe:

banid 1000000000   #originid
banid 1            #userid
banid 127.0.0.0    #ipaddress
```

{% hint style="info" %}
You can get the ipaddress and the userid by refering to the page below.

{% page-ref page="status-command.md" %}
{% endhint %}

## Unbanning Clients

Unbanning a client works like the following:

```text
unban originid
unban ipaddress

Examples don't include the text with the octothorpe:

unban 1000000000   #originid
unban 127.0.0.0    #ipaddress
```

{% hint style="info" %}
You can get the banned clients ipaddress and originid from the banlist.config in your R5 Reloaded root folder.
{% endhint %}

## The local banlist.

Banning a client results in a banlist to be created in your apex folder.

It will be named banlist.config.

You can manually add people there to ban them by either ipaddress or originid.

Or also manually delete people there to unban them.

{% hint style="danger" %}
Make sure to keep the order in check in the banlist.config.

If the first entry is called 1 make sure the next one will be called 2 or your game might crash.
{% endhint %}

## Reloading the banlist

Reloading the banlist can be done like the following:

```text
reloadbanlist
```

