---
title: Legen Sie Berechtigungen in der PDF-Datei fest
linktitle: Legen Sie Berechtigungen in der PDF-Datei fest
second_title: Aspose.PDF für .NET API-Referenz
description: Legen Sie mit Aspose.PDF für .NET ganz einfach Zugriffsrechte in PDF-Dateien fest.
type: docs
weight: 100
url: /de/net/programming-with-security-and-signatures/set-privileges/
---
Oft ist es notwendig, bestimmte Zugriffsrechte für PDF-Dateien festzulegen. Mit Aspose.PDF für .NET können Sie mithilfe des folgenden Quellcodes ganz einfach Zugriffsrechte festlegen:

## Schritt 1: Erforderliche Bibliotheken importieren

Bevor Sie beginnen, müssen Sie die erforderlichen Bibliotheken für Ihr C#-Projekt importieren. Hier sind die notwendigen Importanweisungen:

```csharp
using Aspose.Pdf;
```

## Schritt 2: Legen Sie den Pfad zum Dokumentenordner fest

 In diesem Schritt müssen Sie den Pfad zu dem Ordner angeben, der die PDF-Datei enthält, die Sie bearbeiten möchten. Ersetzen`"YOUR DOCUMENTS DIRECTORY"`Geben Sie im folgenden Code den tatsächlichen Pfad zu Ihrem Dokumentenordner ein:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 3: Laden Sie die PDF-Quelldatei

Jetzt laden wir die Quell-PDF-Datei mit dem folgenden Code:

```csharp
using (Document document = new Document(dataDir + "input.pdf"))
```

## Schritt 4: Zugriffsrechte festlegen

 In diesem Schritt werden wir das instanziieren`DocumentPrivilege` Objekt, um die gewünschten Zugriffsrechte festzulegen. Sie können Einschränkungen auf alle Berechtigungen anwenden`DocumentPrivilege.ForbidAll` . Wenn Sie beispielsweise nur das Lesen von Bildschirminhalten zulassen möchten, können Sie dies festlegen`AllowScreenReaders` Zu`true`. Hier ist der entsprechende Code:

```csharp
DocumentPrivilege documentPrivilege = DocumentPrivilege.ForbidAll;
documentPrivilege.AllowScreenReaders = true;
```

## Schritt 5: Verschlüsseln und speichern Sie das Dokument

 Schließlich können wir das PDF-Dokument mit einem Benutzer- und Besitzerkennwort verschlüsseln`Encrypt` und Spezifizieren des gewünschten Verschlüsselungsalgorithmus. Anschließend speichern wir das aktualisierte Dokument. Hier ist der entsprechende Code:

```csharp
document.Encrypt("user", "owner", documentPrivilege, CryptoAlgorithm.AESx128, false);
document.Save(dataDir + "SetPrivileges_out.pdf");
```

### Beispielquellcode für „Set Privileges“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Laden Sie eine Quell-PDF-Datei
using (Document document = new Document(dataDir + "input.pdf"))
{
	// Objekt „Dokumentberechtigungen“ instanziieren
	// Wenden Sie Einschränkungen für alle Berechtigungen an
	DocumentPrivilege documentPrivilege = DocumentPrivilege.ForbidAll;
	// Nur Bildschirmlesen zulassen
	documentPrivilege.AllowScreenReaders = true;
	// Verschlüsseln Sie die Datei mit dem Benutzer- und Besitzerkennwort.
	// Das Kennwort muss festgelegt werden, damit der Benutzer, sobald er die Datei mit dem Benutzerkennwort anzeigt,
	// Nur die Bildschirmleseoption ist aktiviert
	document.Encrypt("user", "owner", documentPrivilege, CryptoAlgorithm.AESx128, false);
	// Aktualisiertes Dokument speichern
	document.Save(dataDir + "SetPrivileges_out.pdf");
}
```

## Abschluss

Herzlichen Glückwunsch! Sie verfügen nun über eine Schritt-für-Schritt-Anleitung zum Festlegen von Zugriffsrechten für ein PDF-Dokument mit Aspose.PDF für .NET. Mit diesem Code können Sie bestimmte Einschränkungen anwenden und Ihre PDF-Dateien nach Bedarf schützen.

Schauen Sie sich unbedingt die offizielle Aspose.PDF-Dokumentation an, um weitere Informationen zu erweiterten PDF-Dokumentsicherheits- und Zugriffsberechtigungsverwaltungsfunktionen zu erhalten.

### FAQs zum Festlegen von Berechtigungen in PDF-Dateien

#### F: Warum sollte ich Zugriffsrechte in einer PDF-Datei festlegen?

A: Durch das Festlegen von Zugriffsrechten können Sie steuern, wie Benutzer mit Ihren PDF-Dokumenten interagieren. Sie können Aktionen wie Drucken, Kopieren und Bearbeiten einschränken, um die Dokumentensicherheit zu erhöhen.

#### F: Wie kann ich von der Festlegung von Zugriffsrechten mit Aspose.PDF für .NET profitieren?

A: Aspose.PDF für .NET bietet eine unkomplizierte Möglichkeit, Zugriffsrechte zu implementieren und gibt Ihnen die Möglichkeit, Benutzerberechtigungen anzupassen und vertrauliche Inhalte zu schützen.

#### F: Kann ich unterschiedliche Berechtigungen für verschiedene Benutzer anwenden?

A: Ja, Sie können spezifische Zugriffsrechte für verschiedene Benutzergruppen festlegen und so den Dokumentenzugriff basierend auf Benutzerrollen optimieren.

#### F: Welche allgemeinen Zugriffsrechte kann ich festlegen?

A: Zu den allgemeinen Zugriffsrechten gehört das Zulassen oder Verbieten von Aktionen wie Drucken, Kopieren von Text oder Bildern, Ändern des Dokuments und Ausfüllen von Formularfeldern.

#### F: Wie verbessert die Einstellung der Bildschirmleseberechtigung die Zugänglichkeit von Dokumenten?

A: Durch die Aktivierung der Bildschirmleseberechtigung wird sichergestellt, dass Benutzer mithilfe von Bildschirmleseprogrammen auf den Inhalt der PDF-Datei zugreifen können, wodurch die Zugänglichkeit für sehbehinderte Personen verbessert wird.

#### F: Kann ich neben den Zugriffsrechten auch einen Passwortschutz festlegen?

A: Auf jeden Fall können Sie Ihr PDF-Dokument mit Passwörtern verschlüsseln und gleichzeitig Zugriffsrechte anwenden. Dies bietet eine zusätzliche Sicherheitsebene.

#### F: Gibt es eine Möglichkeit, Zugriffsrechte nach der Anwendung zu widerrufen?

A: Sobald Zugriffsrechte erteilt wurden und das Dokument verschlüsselt ist, benötigen Benutzer das entsprechende Passwort, um auf den Inhalt zuzugreifen. Die Berechtigungen können durch Änderung des Quellcodes geändert werden.

#### F: Gibt es beim Festlegen von Zugriffsberechtigungen Leistungsaspekte?

A: Die Auswirkungen auf die Leistung sind minimal, da die Zugriffsberechtigungseinstellungen während der Verschlüsselung angewendet werden, was ein schneller Vorgang ist.

#### F: Kann ich Zugriffsrechte auf ein vorhandenes PDF-Dokument anwenden?

A: Ja, Sie können Aspose.PDF für .NET verwenden, um Zugriffsrechte sowohl auf neue als auch auf vorhandene PDF-Dokumente anzuwenden.