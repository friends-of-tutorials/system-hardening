# Härten von Systemen

Dies ist eine Anleitung um Systeme bestmöglichst<sup>1</sup> abzusichern und zu härten. Sie beschäftigt sich mit dem Entfernen aller Softwarebestandteile und Funktionen, welche nicht zwingend für den ordentlichen Betrieb der entsprechenden Aufgabe notwendig sind.

## 1. Übersicht

### 1.1 Einzelsystem-Härtung

* Grundhärtung
  * Einschränkung administrativer Zugriffe (z.B. `root` Zugänge)
    * SSH-Zugang
    * DB-Zugang
    * etc.
  * Kernelhärtung
    * Unterbinden des RamDisk Zugriffs
    * Verhindern von Kernelmodul-Nachladeversuchen
  * Entsprechende Härtungen installierter Software-Module, z.B.
    * Mailserver
    * MySQL-Server / MariaDB-Server, etc.
      * Aktivierte verschlüsselte Datenverbindung
  * Härtung am Beispiel des Webservers
    * Verwendung von sicheren und aktuellen SSL-Protokollen
    * Abschaltung von nicht benötigten Headerauslieferungen (Versionsnummer, etc.)
    * Abschalten von nicht benötigten Informations- und Statusseiten (server-status)
    * Aktivierung des mod_security Moduls
    * etc.
  * Aktivierung serverseitige Firewall (ufw)
    * Whitelist für freigeschaltete Dienste
    * Einschränkung des Netzwerkzugriffes
  * Schließen aller nicht benötigten Dienste und Ports
  * Entfernen aller unnötigen Datenzugriffsmöglichkeiten
  * Entfernen oder Verschleiern aller unnötigen Versionsnummernausgaben 
  * Einfaches IPS + IDS (Fail2Ban)
  * Regelmäßige oder automatische Einspielungen von Sicherheitspatches
  
### 1.2 Eingesetzte Sicherheitssoftware

* Fail2Ban (Blockieren von IP Adressen, von wahrscheinlichen Angreifern)
* AppArmor (Einschränken von Zugriffsrechten einzelner Programme)
* Apticron (Benachrichtigung über Sicherheitspatches)
* RKHunter (Rootkit, BackDoor und Exploit Scanner mit Mailbenachrichtigung)
* Ferner für Analysen und Eigentests: Lynis
* Etc.

### 1.3 Weitere präventive Maßnahmen

* Einschränken von Zugriffsrechten auf das nötige Maß (Admin, User, etc.)
* Regelmäßige Sicherung der Log-Dateien
* Verschlüsselung wichtiger Daten
* Backups aller relevanten Dateien
* Regelmäßige Rücksicherungs-Tests
* Speichern der Backups auf getrennten Systemen
  * im günstigsten Fall: anderer Anbieter/Rechenzentrum, etc.
* Schulung der Mitarbeiter bezüglich Passwortvergabe und sichere Nutzung der Systeme
* Monitoring der Dienste auf ordentliche Funktion und Verfügbarkeit
* Ausführliche Dokumentation der Architekturen und Härtungen
* Vertretungsregeln Administration
* Dokumentation eines Notfallplan für den Schadensfall

## A. Weitere Anleitungen

* [Sicherheit von Webanwendungen](https://github.com/friends-of-tutorials/web-application-security/blob/master/README.de.md)
* [Eine Anleitung um Nachrichten sicher zu übertragen](https://github.com/friends-of-tutorials/securely-transfer-messages)

## B. Quellen

* [Leitfaden IT-Sicherheit, BSI, 2012](https://www.bsi.bund.de/SharedDocs/Downloads/DE/BSI/Grundschutz/Leitfaden/GS-Leitfaden_pdf.pdf?__blob=publicationFile)
* [BSI: Securing a server](https://www.bsi.bund.de/DE/Themen/StandardsKriterien/ISi-Reihe/ISi-Server/server_node.html)
* [BSI: Secure operation of e-mail servers (ISi-Mail-Server)](https://www.bsi.bund.de/DE/Themen/StandardsKriterien/ISi-Reihe/ISi-Mail-Server/mail_server_node.html;jsessionid=C775445C3C19BC3FF7B8BE2F49813BB8.1_cid360)

## C. Tools

* [Port Scanner Online](https://pentest-tools.com/network-vulnerability-scanning/tcp-port-scanner-online-nmap#)

## D. Fußnoten

* <sup>1</sup> = Nach aktuellem Stand und Möglichkeit. Eine hundertprozentige Absicherung ist so gut wie nie möglich.

## E. Autoren

* Björn Hempel <bjoern@hempel.li> - _Erste Arbeiten_ - [https://github.com/bjoern-hempel](https://github.com/bjoern-hempel)

## F. Lizenz

Dieses Tutorial steht unter der MIT-Lizenz - siehe die Datei [LICENSE.md](/LICENSE.md) für weitere Informationen.
