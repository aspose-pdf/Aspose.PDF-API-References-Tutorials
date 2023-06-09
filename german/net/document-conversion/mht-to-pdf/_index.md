---
title: MHT zu PDF
linktitle: MHT zu PDF
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Konvertieren von MHT in PDF mit Aspose.PDF für .NET.
type: docs
weight: 70
url: /de/net/document-conversion/mht-to-pdf/
---

In diesem Tutorial führen wir Sie durch den Prozess der Konvertierung einer MHT-Datei in PDF mit Aspose.PDF für .NET. MHT (MIME HTML) ist ein Format zum Speichern einer vollständigen Webseite, einschließlich Bildern und zugehörigem Inhalt. Wenn Sie die folgenden Schritte ausführen, können Sie MHT-Dateien in das PDF-Format konvertieren.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

- Grundkenntnisse der Programmiersprache C#.
- Aspose.PDF-Bibliothek für .NET auf Ihrem System installiert.
- Eine Entwicklungsumgebung wie Visual Studio.

## Schritt 1: MHT-Datei laden
In diesem Schritt laden wir die MHT-Datei mit Aspose.PDF für .NET. Befolgen Sie den folgenden Code:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

MhtLoadOptions options = new MhtLoadOptions();

// Laden Sie das Dokument
Document document = new Document(dataDir + "test.mht", options);
```

 Unbedingt ersetzen`"YOUR DOCUMENTS DIRECTORY"` mit dem tatsächlichen Verzeichnis, in dem sich Ihre MHT-Datei befindet.

## Schritt 2: MHT-zu-PDF-Konvertierung
Nach dem Laden der MHT-Datei können wir mit der Konvertierung in PDF fortfahren. Verwenden Sie den folgenden Code:

```csharp
// Speichern Sie die Ausgabe als PDF-Dokument
document.Save(dataDir + "MHTToPDF_out.pdf");
```

 Der obige Code konvertiert die MHT-Datei in das PDF-Format und speichert sie unter dem Dateinamen`"MHTToPDF_out.pdf"`.

### Beispielquellcode für MHT in PDF mit Aspose.PDF für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
MhtLoadOptions options = new MhtLoadOptions();
// Dokument laden
Document document = new Document(dataDir  + "test.mht", options);
// Speichern Sie die Ausgabe als PDF-Dokument
document.Save(dataDir + "MHTToPDF_out.pdf");
```

## Abschluss
In diesem Tutorial haben wir den Schritt-für-Schritt-Prozess zum Konvertieren einer MHT-Datei in PDF mit Aspose.PDF für .NET behandelt. Wenn Sie die oben beschriebenen Anweisungen befolgen, sollten Sie nun in der Lage sein, MHT-Dateien in das PDF-Format zu konvertieren. Diese Funktion kann nützlich sein, wenn Sie ganze Webseiten in PDF-Dokumente konvertieren müssen.