---
title: Festlegen von Berechtigungen in der PDF-Datei
linktitle: Festlegen von Berechtigungen in der PDF-Datei
second_title: Aspose.PDF für .NET API-Referenz
description: Legen Sie mit Aspose.PDF für .NET ganz einfach Zugriffsrechte in PDF-Dateien fest.
type: docs
weight: 100
url: /de/net/programming-with-security-and-signatures/set-privileges/
---
Es ist oft notwendig, bestimmte Zugriffsrechte in PDF-Dateien festzulegen. Mit Aspose.PDF für .NET können Sie mit dem folgenden Quellcode ganz einfach Zugriffsrechte festlegen:

## Schritt 1: Erforderliche Bibliotheken importieren

Bevor Sie beginnen, müssen Sie die erforderlichen Bibliotheken für Ihr C#-Projekt importieren. Hier sind die erforderlichen Importanweisungen:

```csharp
using Aspose.Pdf;
```

## Schritt 2: Pfad zum Dokumentenordner festlegen

 In diesem Schritt müssen Sie den Pfad zum Ordner angeben, der die zu bearbeitende PDF-Datei enthält. Ersetzen Sie`"YOUR DOCUMENTS DIRECTORY"` ersetzen Sie den folgenden Code durch den tatsächlichen Pfad zu Ihrem Dokumentordner:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 3: Quell-PDF-Datei laden

Nun laden wir die Quell-PDF-Datei mit dem folgenden Code:

```csharp
using (Document document = new Document(dataDir + "input.pdf"))
```

## Schritt 4: Zugriffsrechte festlegen

 In diesem Schritt instanziieren wir die`DocumentPrivilege` Objekt, um die gewünschten Zugriffsrechte festzulegen. Sie können Einschränkungen auf alle Rechte anwenden, indem Sie`DocumentPrivilege.ForbidAll` Wenn Sie beispielsweise nur das Lesen auf dem Bildschirm zulassen möchten, können Sie Folgendes festlegen:`AllowScreenReaders` Zu`true`. Hier ist der entsprechende Code:

```csharp
DocumentPrivilege documentPrivilege = DocumentPrivilege.ForbidAll;
documentPrivilege.AllowScreenReaders = true;
```

## Schritt 5: Dokument verschlüsseln und speichern

 Schließlich können wir das PDF-Dokument mit einem Benutzer- und Besitzerkennwort verschlüsseln mit`Encrypt` und geben den gewünschten Verschlüsselungsalgorithmus an. Anschließend speichern wir das aktualisierte Dokument. Hier ist der entsprechende Code:

```csharp
document.Encrypt("user", "owner", documentPrivilege, CryptoAlgorithm.AESx128, false);
document.Save(dataDir + "SetPrivileges_out.pdf");
```

### Beispielquellcode zum Festlegen von Berechtigungen mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Laden einer PDF-Quelldatei
using (Document document = new Document(dataDir + "input.pdf"))
{
	// Objekt „Dokumentberechtigungen“ instanziieren
	// Einschränkungen für alle Berechtigungen anwenden
	DocumentPrivilege documentPrivilege = DocumentPrivilege.ForbidAll;
	// Nur Bildschirmlesen zulassen
	documentPrivilege.AllowScreenReaders = true;
	// Verschlüsseln Sie die Datei mit dem Benutzer- und Besitzerkennwort.
	// Das Kennwort muss so festgelegt werden, dass der Benutzer, sobald er die Datei mit dem Benutzerkennwort anzeigt,
	// Nur die Option zum Lesen des Bildschirms ist aktiviert
	document.Encrypt("user", "owner", documentPrivilege, CryptoAlgorithm.AESx128, false);
	// Aktualisiertes Dokument speichern
	document.Save(dataDir + "SetPrivileges_out.pdf");
}
```

## Abschluss

Herzlichen Glückwunsch! Sie verfügen nun über eine Schritt-für-Schritt-Anleitung zum Festlegen von Zugriffsrechten für ein PDF-Dokument mit Aspose.PDF für .NET. Mit diesem Code können Sie bestimmte Einschränkungen anwenden und Ihre PDF-Dateien nach Bedarf schützen.

Weitere Informationen zur erweiterten Sicherheit von PDF-Dokumenten und zu den Funktionen zur Verwaltung von Zugriffsrechten finden Sie in der offiziellen Aspose.PDF-Dokumentation.

### FAQs zum Festlegen von Berechtigungen in PDF-Dateien

#### F: Warum muss ich in einer PDF-Datei Zugriffsrechte festlegen?

A: Durch das Festlegen von Zugriffsrechten können Sie steuern, wie Benutzer mit Ihren PDF-Dokumenten interagieren. Sie können Aktionen wie Drucken, Kopieren und Bearbeiten einschränken, um die Dokumentsicherheit zu verbessern.

#### F: Welche Vorteile bietet mir die Festlegung von Zugriffsrechten mit Aspose.PDF für .NET?

A: Aspose.PDF für .NET bietet eine unkomplizierte Möglichkeit, Zugriffsrechte zu implementieren und gibt Ihnen die Möglichkeit, Benutzerberechtigungen anzupassen und vertrauliche Inhalte zu schützen.

#### F: Kann ich verschiedenen Benutzern unterschiedliche Berechtigungen zuweisen?

A: Ja, Sie können spezifische Zugriffsrechte für unterschiedliche Benutzergruppen festlegen und so den Dokumentzugriff basierend auf den Benutzerrollen feinabstimmen.

#### F: Welche allgemeinen Zugriffsrechte kann ich festlegen?

A: Zu den allgemeinen Zugriffsberechtigungen gehört das Erlauben oder Verbieten von Aktionen wie Drucken, Kopieren von Text oder Bildern, Ändern des Dokuments und Ausfüllen von Formularfeldern.

#### F: Wie verbessert das Festlegen von Bildschirmleseberechtigungen die Dokumentzugänglichkeit?

A: Durch die Aktivierung der Bildschirmleseberechtigung wird sichergestellt, dass Benutzer mithilfe von Bildschirmleseprogrammen auf den Inhalt der PDF-Datei zugreifen können. Dies verbessert die Zugänglichkeit für sehbehinderte Personen.

#### F: Kann ich zusammen mit den Zugriffsrechten einen Kennwortschutz festlegen?

A: Natürlich. Sie können Ihr PDF-Dokument mit Passwörtern verschlüsseln, während Sie Zugriffsrechte zuweisen. Dies bietet eine zusätzliche Sicherheitsebene.

#### F: Gibt es eine Möglichkeit, Zugriffsrechte nach der Anwendung zu widerrufen?

A: Sobald Zugriffsrechte zugewiesen und das Dokument verschlüsselt ist, benötigen Benutzer das entsprechende Passwort, um auf den Inhalt zugreifen zu können. Die Rechte können durch Ändern des Quellcodes geändert werden.

#### F: Gibt es beim Festlegen von Zugriffsrechten Leistungsaspekte?

A: Die Auswirkungen auf die Leistung sind minimal, da die Einstellungen für die Zugriffsrechte während der Verschlüsselung angewendet werden, was ein schneller Prozess ist.

#### F: Kann ich Zugriffsrechte auf ein vorhandenes PDF-Dokument anwenden?

A: Ja, Sie können Aspose.PDF für .NET verwenden, um Zugriffsrechte sowohl auf neue als auch auf bestehende PDF-Dokumente anzuwenden.