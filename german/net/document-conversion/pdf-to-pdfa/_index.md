---
title: PDF zu PDFA
linktitle: PDF zu PDFA
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Konvertieren von PDF in PDFA mit Aspose.PDF für .NET.
type: docs
weight: 140
url: /de/net/document-conversion/pdf-to-pdfa/
---

In diesem Tutorial führen wir Sie durch den Prozess der Konvertierung einer PDF-Datei in das PDF/A-Format mit Aspose.PDF für .NET. Das PDF/A-Format ist ein ISO-Standard, der die langfristige Aufbewahrung elektronischer Dokumente gewährleistet. Wenn Sie die folgenden Schritte ausführen, können Sie PDF-Dateien in das PDF/A-Format konvertieren.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

- Grundkenntnisse der Programmiersprache C#.
- Aspose.PDF-Bibliothek für .NET auf Ihrem System installiert.
- Eine Entwicklungsumgebung wie Visual Studio.

## Schritt 1: Öffnen des Quell-PDF-Dokuments
In diesem Schritt öffnen wir die Quell-PDF-Datei mit Aspose.PDF für .NET. Befolgen Sie den folgenden Code:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Öffnen Sie das Quell-PDF-Dokument
Document pdfDocument = new Document(dataDir + "PDFToPDFA.pdf");
```

 Unbedingt ersetzen`"YOUR DOCUMENTS DIRECTORY"` mit dem tatsächlichen Verzeichnis, in dem sich Ihre PDF-Datei befindet.

## Schritt 2: Konvertierung in das PDF/A-Format
Nach dem Öffnen der PDF-Datei können wir mit der Konvertierung in das PDF/A-Format fortfahren. Verwenden Sie den folgenden Code:

```csharp
// Konvertieren Sie in ein PDF/A-kompatibles Dokument
// Während des Konvertierungsprozesses wird auch eine Validierung durchgeführt
pdfDocument.Convert(dataDir + "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);
```

 Der obige Code konvertiert die PDF-Datei in das PDF/A-1b-Format und führt während des Konvertierungsprozesses auch eine Validierung durch. Eventuelle Fehler werden im Protokoll festgehalten`"log.xml"` Datei.

## Schritt 3: Speichern der resultierenden PDF/A-Datei
Nachdem die Konvertierung abgeschlossen ist, müssen wir die resultierende PDF/A-Datei speichern. Hier ist der letzte Schritt:

```csharp
dataDir = dataDir + "PDFToPDFA_out.pdf";
// Speichern Sie das Ausgabedokument
pdfDocument.Save(dataDir);
```

 Ersetzen`"YOUR DOCUMENTS DIRECTORY"` mit dem gewünschten Verzeichnis, in dem Sie die ausgegebene PDF/A-Datei speichern möchten.

### Beispielquellcode für PDF zu HTML mit Aspose.Words für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dokument öffnen
Document pdfDocument = new Document(dataDir + "PDFToPDFA.pdf");

// Konvertieren Sie in ein PDF/A-kompatibles Dokument
// Während des Konvertierungsprozesses wird auch die Validierung durchgeführt
pdfDocument.Convert(dataDir + "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);

dataDir = dataDir + "PDFToPDFA_out.pdf";
// Ausgabedokument speichern
pdfDocument.Save(dataDir);

Console.WriteLine("\nPDF file converted to PDF/A-1b compliant PDF.\nFile saved at " + dataDir);
```

## Abschluss
In diesem Tutorial haben wir den Schritt-für-Schritt-Prozess der Konvertierung einer PDF-Datei in das PDF/A-Format mit Aspose.PDF für .NET behandelt. Wenn Sie die oben beschriebenen Anweisungen befolgen, sollten Sie nun in der Lage sein, PDF-Dateien in das PDF/A-Format zu konvertieren. Diese Funktion ist nützlich, wenn Sie die langfristige Konformität Ihrer elektronischen Dokumente sicherstellen möchten.