# WhatsApp-API

#This repo has the potential to be the first WhatsApp private api for PHP

## Introduction

This project intends to provide a fully private API for WhatsApp.


## Installation

You Need! 

0. Brain
1. Use PHP 7.1.25
2. [Install the libsodium PHP extension from PECL.](https://paragonie.com/book/pecl-libsodium/read/00-intro.md#installing-libsodium).
3. [Install composer](https://getcomposer.org/).
4. [Install Java](https://www.java.com/en/download/).
5. You need to get your rc2 file from your android device

You need to have java installed, because java is needed for the AES-128-GCM Encryption

### At start Time WhatsApp Checks if number was already registered
Request URL: `https://v.whatsapp.net/v2/exist`
GET Param: 
- `ENC`: Base64 encoded value of final output.

Parameters needed for Exists call:
- `cc` : Country code
- `in` : Phone number without country code
- `lg` : Language
- `lc` : Country Code (ISO 3166-1 alpha-2)
- `id` : User ID token,     Incorrect generated by our app: Need a fix
- `token` : Login token,    Incorrect generated by our app: Need a fix
- `mistyped` : 6 (unknown)
- `offline_ab_exposure` : "" empty string (unknown)
- `authkey` : ``,        //TODO: FIND OUT
- `e_regid` : ``,        //TODO: FIND OUT
- `e_keytype` : ``,      //TODO: FIND OUT
- `e_ident` : ``,        //TODO: FIND OUT
- `e_skey_id` : ``,      //TODO: FIND OUT
- `e_skey_val` : ``,     //TODO: FIND OUT
- `e_skey_sig` : ``,     //TODO: FIND OUT
- `fdid` : ``,           //TODO: FIND OUT
- `expid` : ``,          //TODO: FIND OUT
- `network_radio_type` : 1 [See Network Type Info](https://github.com/socialAPIS/WhatsApp-API/blob/master/src/Constants/Network%20Types.txt)
- `simnum` : 1 or MSISDN
- `hasinrc` : Has in the rc2 file if yes then 1 else 0,
- `pid` : Process ID
- `rc` : [See RC Info](https://github.com/socialAPIS/WhatsApp-API/blob/master/src/Constants/RC_Info.txt)

All these parameters are encrypted and sent to WhatsApp in a GET request. The parameters are formatted as a query before encryption:

`cc=xx&in=xxxxxx&lg=xx&lc=xx`


As i have more time i will add more content and Code.


### Running Code Example

Open index.php and change your prefix, phone number without prefix, your language and country

`$ident = new \WhatsAppAPI\Controllers\clientEntity(" Country code", "Phone number without country code", "en", "US");`

Copy your rc2 file in sessions folder

and start the app with
php index.php

you will get the following response

`{"login":"15417543010","status":"fail","reason":"bad_param","param":"expid"}`

# Contributing

Contributions are **welcome** and will be fully **credited**.

We accept contributions via Pull Requests on [Github](https://github.com/socialAPIS/WhatsApp-API).

