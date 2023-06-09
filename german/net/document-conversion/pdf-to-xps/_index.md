---
title: PDF zu XPS
linktitle: PDF zu XPS
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Konvertieren von PDF in XPS mit Aspose.PDF für .NET.
type: docs
weight: 220
url: /de/net/document-conversion/pdf-to-xps/
---

In diesem Tutorial führen wir Sie durch den Prozess der Konvertierung einer PDF-Datei in das XPS-Format (XML Paper Specification) mit Aspose.PDF für .NET. Das XPS-Format ist ein XML-basiertes Dateiformat, das zur elektronischen Darstellung von Dokumenten verwendet wird. Wenn Sie die folgenden Schritte ausführen, können Sie eine PDF-Datei in das XPS-Format konvertieren.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

- Grundkenntnisse der Programmiersprache C#.
- Aspose.PDF-Bibliothek für .NET auf Ihrem System installiert.
- Eine Entwicklungsumgebung wie Visual Studio.

## Schritt 1: Laden des PDF-Dokuments
In diesem Schritt laden wir die Quell-PDF-Datei mit Aspose.PDF für .NET. Befolgen Sie den folgenden Code:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laden Sie das PDF-Dokument
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 Unbedingt ersetzen`"YOUR DOCUMENTS DIRECTORY"` mit dem tatsächlichen Verzeichnis, in dem sich Ihre PDF-Datei befindet.

## Schritt 2: XPS-Speicheroptionen instanziieren
Nach dem Laden der PDF-Datei instanziieren wir die XPS-Speicheroptionen. Verwenden Sie den folgenden Code:

```csharp
// Instanziieren Sie XPS-Speicheroptionen
Aspose.Pdf.XpsSaveOptions saveOptions = new Aspose.Pdf.XpsSaveOptions();
```

## Schritt 3: Speichern der resultierenden XPS-Datei
Jetzt speichern wir die konvertierte PDF-Datei im XPS-Format. Verwenden Sie den folgenden Code:

```csharp
// Speichern Sie das XPS-Dokument
pdfDocument.Save("PDFToXPS_out.xps", saveOptions);
```

 Der obige Code speichert die konvertierte PDF-Datei im XPS-Format unter dem Dateinamen`"PDFToXPS_out.xps"`.


### Beispielquellcode für PDF zu XPS mit Aspose.PDF für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// PDF-Dokument laden
Document pdfDocument = new Document(dataDir + "input.pdf");

// Instanziieren Sie XPS-Speicheroptionen
Aspose.Pdf.XpsSaveOptions saveOptions = new Aspose.Pdf.XpsSaveOptions();

// Speichern Sie das XPS-Dokument
pdfDocument.Save("PDFToXPS_out.xps", saveOptions);
```

## Abschluss
In diesem Tutorial haben wir den Schritt-für-Schritt-Prozess zum Konvertieren einer PDF-Datei in das XPS-Format mit Aspose.PDF für .NET behandelt. Wenn Sie die oben beschriebenen Anweisungen befolgen, sollten Sie nun in der Lage sein, eine PDF-Datei in das XPS-Format zu konvertieren. Diese Funktion ist nützlich, wenn Sie PDF-Dokumente im XPS-Format anzeigen oder drucken möchten.