# 28 apr. 2021
- upgrade to snipeIT [v.5.4.3](https://github.com/snipe/snipe-it/releases/tag/v5.4.3)
    - [full ChangeLog snipeIT](https://github.com/snipe/snipe-it/compare/v5.2.0...v5.4.3)

# 22 nov. 2021
- upgrade to snipeIT [v.5.2.2](https://github.com/snipe/snipe-it/releases/tag/v5.3.2)
    - also [v.5.2.1](https://github.com/snipe/snipe-it/releases/tag/v5.3.0)

# 12 okt. 2021
- Regex lokalen opnieuw toegevoegd: oftewel leeg veld oftewel gebouw(hoofdletter), vloer (eventueel -), punt, volgnummer
```
regex:/^$|[[:upper:]]\-?[[:digit:]]\.[[:digit:]][[:digit:]]/
```
- toevoegen van extra Status Label: _In herstelling - gr.SEC (naar ICT brengen!)_
    - te gebruiken door gr.SEC bij een LLN-toestel dat hersteld moet worden. Bij inbrengen van toestel status zetten op _In herstelling - gr.SEC (naar ICT brengen!)_. Wanneer het toestel bij ICT wordt gebracht veranderd **ICT** (door edit van asset) het/de toestel(len) naar _In herstelling - ICT_

# 1 okt. 2021
- upgraded to snipeIT [v.5.2](https://github.com/snipe/snipe-it/releases/tag/v5.2.0)
- pushed _fix usernames_; dubbele gebruikers weggehaald (gebruikers met username zonder @(leerling.)hhscholen.be + eventuele toegekende toestellen verplaatst naar gebruik met @...)

# 10 sept. 2021
- _Unique serial numbers_ enabled (= controle op unieke serienummer in DB)
- Forced redirection of http to https/SSL

# 1 sept. 2021
- LDAP auto sync ingesteld (elke 30 min)

# 31 aug. 2021
- toegang voor ADM-leden (die het nodig hebben) via Azure Security Group *Inventaris-Access-Group*

# 24 aug. 2021
- installed Laravel on VM
- LDAP sync ingestld
# 20 aug. 2021
### Public release

# 17 aug. 2021
- upgraded to SnipeIT [v.5.1.8](https://github.com/snipe/snipe-it/releases/tag/v5.1.8)
- added path to Update-Log Github repo (public) in footer