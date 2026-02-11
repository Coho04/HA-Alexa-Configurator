# Alexa UI Configurator

Dieses HACS-Integration ermöglicht es dir, deine Home Assistant Geräte bequem über die Benutzeroberfläche für deinen Alexa Skill zu konfigurieren.

## Funktionen

- **UI-basierte Konfiguration**: Gib deinen Lambda-Endpoint, deine Client-ID und dein Client-Secret direkt in der Home Assistant UI ein.
- **Geräteauswahl**: Wähle die Entitäten aus, die du für Alexa freigeben möchtest, bequem über eine Liste aus.
- **Automatisches YAML-Update**: Die Integration schreibt die benötigten Informationen in eine separate Datei (`alexa_smart_home.yaml`) und bindet diese in deine `configuration.yaml` ein.

## Installation

1. Kopiere den Ordner `alexa_configurator` in dein `custom_components` Verzeichnis.
2. Starte Home Assistant neu.
3. Gehe zu **Einstellungen > Geräte & Dienste > Integration hinzufügen**.
4. Suche nach **Alexa UI Configurator** und folge den Anweisungen.

## Konfiguration

Während des Setups wirst du nach folgenden Informationen gefragt:

- **Endpoint**: Der HTTPS-Endpunkt deiner AWS Lambda Funktion.
- **Client ID**: Die Client-ID aus der Amazon Developer Console.
- **Client Secret**: Das Client-Secret aus der Amazon Developer Console.
- **Entitäten**: Wähle die Geräte aus, die du an Alexa übertragen möchtest.

## Wie es funktioniert

Die Integration erstellt eine Datei namens `alexa_smart_home.yaml` in deinem Home Assistant Konfigurationsverzeichnis. Diese enthält die `alexa: smart_home:` Sektion. 
Zusätzlich wird eine Zeile in deine `configuration.yaml` eingefügt:
```yaml
alexa: !include alexa_smart_home.yaml
```

Jedes Mal, wenn du die Einstellungen der Integration änderst, wird die Datei automatisch aktualisiert.

*Hinweis: Möglicherweise ist ein Neustart von Home Assistant oder ein Neuladen der Konfiguration erforderlich, damit Änderungen an der Alexa-Integration wirksam werden.*
