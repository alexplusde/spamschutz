# Changelog

## [2.0.0] - 2022-xx-xx

>**Hinweis**: Das YForm-Value muss in seiner Schreibweise angepasst werden. Neu ist die optionale Angabe eines E-Mail-Feldnamens, wenn bestimmte Endungen blockiert werden sollen, bspw. `.ru`

### Neue Features

* Log der aktuellen Sperren einsehbar
* Optionales Blockieren von unerwünschten Mail-Adressen in Kontaktformularen (TLD-Sperre)
* optionales Whitelisting von statischen oder lokalen IPs
* optionales Whitelisting von eingeloggten YCom-Benutzern
* Detaillierte Ausgabe von Fehlermeldungen über das Addon Sprog möglich

### Verbesserungen

* Überarbeitete Einstellungsseite
* Einstellungen und Log sind jetzt auch für andere Benutzer-Rollen verfügbar, z.B. Redakteure
* Eigene `spam_protection`-Klasse auf Basis von YForm, mit der die Validierung auch außerhalb von YForm nutzbar wird oder eigene und einzelne Prüfungen abgeleitet werden können:

```php
$ip_dataset = spam_protection::check($ip, $debug = false, $form_microtime = null, $session_microtime = null, $honeypot_value = '', $email = '');

/* Fehlermeldeungen erhalten */
if ($ip_dataset->getValue('reason')) {
    // Fehlermeldung ausgeben, eigene Skriptverarbeitung stoppen 
}
```
