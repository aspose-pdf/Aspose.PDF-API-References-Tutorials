---
title: Verschlüsseln
linktitle: Verschlüsseln
second_title: Aspose.PDF für .NET API-Referenz
description: Verschlüsseln Sie Ihre PDF-Dateien sicher mit Aspose.PDF für .NET.
type: docs
weight: 60
url: /de/net/programming-with-security-and-signatures/encrypt/
---

Die Verschlüsselung von PDF-Dateien ist eine wichtige Sicherheitsmaßnahme zum Schutz vertraulicher Informationen. Mit Aspose.PDF für .NET können Sie Ihre PDF-Dateien ganz einfach mit dem folgenden Quellcode verschlüsseln:

## Schritt 1: Erforderliche Bibliotheken importieren

Bevor Sie beginnen, müssen Sie die erforderlichen Bibliotheken für Ihr C#-Projekt importieren. Hier sind die notwendigen Importanweisungen:

```csharp
using Aspose.Pdf;
```

## Schritt 2: Legen Sie den Pfad zum Dokumentenordner fest

 In diesem Schritt müssen Sie den Pfad zum Ordner angeben, der die zu verschlüsselnde PDF-Datei enthält. Ersetzen`"YOUR DOCUMENTS DIRECTORY"` Geben Sie im folgenden Code den tatsächlichen Pfad zu Ihrem Dokumentenordner ein:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 3: Öffnen Sie das PDF-Dokument

Als nächstes müssen Sie das PDF-Dokument öffnen, das Sie verschlüsseln möchten. Verwenden Sie den folgenden Code, um das Dokument zu laden:

```csharp
Document document = new Document(dataDir + "Encrypt.pdf");
```

## Schritt 4: PDF verschlüsseln

Jetzt können Sie das PDF mit dem folgenden Code verschlüsseln:

```csharp
document. Encrypt("user", "owner", 0, CryptoAlgorithm.RC4x128);
```

In diesem Beispiel verwenden wir den Verschlüsselungsalgorithmus RC4x128 mit den Passwörtern „Benutzer“ und „Besitzer“. Sie können diese Einstellungen nach Bedarf ändern.

## Schritt 5: Verschlüsseltes PDF sichern

Abschließend können Sie das verschlüsselte PDF mit dem folgenden Code am angegebenen Ort speichern:

```csharp
dataDir = dataDir + "Encrypt_out.pdf";
document. Save(dataDir);
```

Geben Sie unbedingt den gewünschten Pfad und Dateinamen für das verschlüsselte PDF an.

### Beispielquellcode für Encrypt mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Dokument öffnen
Document document = new Document(dataDir+ "Encrypt.pdf");
// PDF verschlüsseln
document.Encrypt("user", "owner", 0, CryptoAlgorithm.RC4x128);
dataDir = dataDir + "Encrypt_out.pdf";
// Aktualisiertes PDF speichern
document.Save(dataDir);
Console.WriteLine("\nPDF file encrypted successfully.\nFile saved at " + dataDir);
```

## Abschluss

Herzlichen Glückwunsch! Sie haben nun eine Schritt-für-Schritt-Übersicht über die Verschlüsselung von PDF-Dateien mit Aspose.PDF für .NET. Sie können diesen Code in Ihre eigenen Projekte einbetten, um Ihre PDF-Dateien ganz einfach zu schützen.

Weitere Informationen zu erweiterten Verschlüsselungs- und Sicherheitsfunktionen finden Sie unbedingt in der offiziellen Aspose.PDF-Dokumentation.