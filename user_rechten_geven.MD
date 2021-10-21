# Geef toegang aan een gebruiker tot de inventaris (edit/checkout-in rechten)

## Beperkingen
Omdat we nog in een tussenfase zitten (ADM-netwerk niet op Azure AD) is het momenteel nog met enkele tussenstappen. 
Aanmelden op de applicatie gaat via LDAP/SAML op AAD. Aanmelden (zonder checkin-out/edit/admin rechten) is wel mogelijk zonder bijkomende actie. Echter edit/checkin-out/admin rechten kunnen (nog) niet beheerd worden via AAD-groepen. In de toekomst wel. Daarom gebeurt dit via een access-group/security-group van de lokale AD. 

## Vereisten om een gebruiker rechten te kunnen geven
Om aan een gebruiker rechten (edit of checkin-out) te kunnen geven moet het volgende in orde zijn:
- account geregistreerd op onze lokale AD (10.2.0.160 / 10.32.0.8)
- lid zijn van de groep _Inventaris-Access-Group_
- rechten gekregen op de webapplicatie zelf (inventaris.hhscholen.be)

## Stappen/werkwijze om een gebruiker checkin-out/edit/admin rechten te geven
### Controleer of gebruiker aanwezig is op de lokale AD (10.2.0.160 / 10.32.0.8)
_indien neen:_
    - maak de gebruiker aan op de lokale AD op het pad: _ad.hhscholen.be/Gebruikers/Leerkrachten/Andere_
    - vul het volgende in:
        - Voornaam
        - Achternaam
        - Volledige naam
        - Aanmeldeingsnaam (@hhscholen.be)
        - laat de gebruiker zijn O365-wachtwoord ingeven (zodat deze niet wordt overschreven tijdens de synchronisatie met Azure AD)
        - vink **UIT** _Gebruiker moet wachtwoord bij volgende aanmelding wijzigen_

### Controleer dat de gebruiker de correcte groep is toegekend
- controleer (of voeg toe) de gebruiker aan de groep (op lokale AD (10.2.0.160 / 10.32.0.8)) _Inventaris-Access-Group_

### Geef de rechten op de webapplicatie
- open [inventaris.hhscholen.be](https://inventaris.hhscholen.be/)
- meld aan
- ga naar _Personen_ ([directe link](https://inventaris.hhscholen.be/users))
- zoek de gewenste gebruiker
- open de gewenste gebruiker
- klik op _Gebruiker aanpassen_
- onderaan de pagina (bij _Groepen_) selecteer de gewenste groepen
    - "_SUPER ADMIN_" = super admin (enkel ICT)
    - "_View only_" = kan enkel hardware bekijken (wordt momenteel niet in de praktijk gebruikt)
    - "_Checkout/in (hardware)_" = Kan enkel harware out- en inchecken (PersAdmin, gr.SEC, SecLog, ...)
    - "_Basic EDIT & checkin/out (hardware)_" = Kan hardware out- en inchecken alsook sommige aanpassingen brengen aan hardware (lokaal/status/...), maar kan niets verwijderen of zelf aanmaken (Tia, ...)
    - "_Basic EDIT & MAKE & checkin/out (assets)_" = Kan hardware out- en inchecken alsook sommige aanpassingen brengen aan hardware (lokaal/status/...) en hardware aanmaken. Maar niets verwijderen (Laith, ...)