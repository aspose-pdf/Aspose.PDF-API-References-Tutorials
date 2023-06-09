---
title: Legen Sie Berechtigungen fest
linktitle: Legen Sie Berechtigungen fest
second_title: Aspose.PDF für .NET API-Referenz
description: Legen Sie mit Aspose.PDF für .NET ganz einfach Zugriffsrechte für Ihre PDF-Dateien fest.
type: docs
weight: 100
url: /de/net/programming-with-security-and-signatures/set-privileges/
---

Oftmals ist es notwendig, spezifische Zugriffsrechte für PDF-Dateien festzulegen. Mit Aspose.PDF für .NET können Sie mithilfe des folgenden Quellcodes ganz einfach Zugriffsrechte festlegen:

## Schritt 1: Erforderliche Bibliotheken importieren

Bevor Sie beginnen, müssen Sie die erforderlichen Bibliotheken für Ihr C#-Projekt importieren. Hier sind die notwendigen Importanweisungen:

```csharp
using Aspose.Pdf;
```

## Schritt 2: Legen Sie den Pfad zum Dokumentenordner fest

 In diesem Schritt müssen Sie den Pfad zu dem Ordner angeben, der die PDF-Datei enthält, die Sie bearbeiten möchten. Ersetzen`"YOUR DOCUMENTS DIRECTORY"` Geben Sie im folgenden Code den tatsächlichen Pfad zu Ihrem Dokumentenordner ein:

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
	//Nur die Bildschirmleseoption ist aktiviert
	document.Encrypt("user", "owner", documentPrivilege, CryptoAlgorithm.AESx128, false);
	// Aktualisiertes Dokument speichern
	document.Save(dataDir + "SetPrivileges_out.pdf");
}
```

## Abschluss

Herzlichen Glückwunsch! Sie verfügen nun über eine Schritt-für-Schritt-Anleitung zum Festlegen von Zugriffsrechten für ein PDF-Dokument mit Aspose.PDF für .NET. Mit diesem Code können Sie bestimmte Einschränkungen anwenden und Ihre PDF-Dateien nach Bedarf schützen.

Schauen Sie sich unbedingt die offizielle Aspose.PDF-Dokumentation an, um weitere Informationen zu erweiterten PDF-Dokumentsicherheits- und Zugriffsberechtigungsverwaltungsfunktionen zu erhalten.