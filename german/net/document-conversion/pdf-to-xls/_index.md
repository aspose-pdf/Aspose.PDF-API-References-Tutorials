---
title: PDF zu XLS
linktitle: PDF zu XLS
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Konvertieren von PDF in XLS mit Aspose.PDF für .NET.
type: docs
weight: 200
url: /de/net/document-conversion/pdf-to-xls/
---

In diesem Tutorial führen wir Sie durch den Prozess der Konvertierung einer PDF-Datei in das XLS-Format (Microsoft Excel) mit Aspose.PDF für .NET. Wenn Sie die folgenden Schritte ausführen, können Sie eine PDF-Datei in das XLS-Format konvertieren.

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

## Schritt 2: Instanziieren Sie die Excel-Sicherungsoptionen
Nach dem Laden der PDF-Datei instanziieren wir die Excel-Speicheroptionen. Verwenden Sie den folgenden Code:

```csharp
// Instanziieren Sie ein ExcelSaveOptions-Objekt
Aspose.Pdf.ExcelSaveOptions excelsave = new ExcelSaveOptions();
```

## Schritt 3: Speichern der resultierenden XLS-Datei
Jetzt speichern wir die konvertierte PDF-Datei im XLS-Format. Verwenden Sie den folgenden Code:

```csharp
// Speichern Sie die Ausgabe im XLS-Format
pdfDocument.Save("PDFToXLS_out.xls", excelsave);
```

 Der obige Code speichert die konvertierte PDF-Datei im XLS-Format unter dem Dateinamen`"PDFToXLS_out.xls"`.

### Beispielquellcode für PDF zu XLS mit Aspose.PDF für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// PDF-Dokument laden
Document pdfDocument = new Document(dataDir + "input.pdf");

// Instanziieren Sie das ExcelSave-Optionsobjekt
Aspose.Pdf.ExcelSaveOptions excelsave = new ExcelSaveOptions();

// Speichern Sie die Ausgabe im XLS-Format
pdfDocument.Save("PDFToXLS_out.xls", excelsave);
```

## Abschluss
In diesem Tutorial haben wir den Schritt-für-Schritt-Prozess zum Konvertieren einer PDF-Datei in das XLS-Format mit Aspose.PDF für .NET behandelt. Wenn Sie die oben beschriebenen Anweisungen befolgen, sollten Sie nun in der Lage sein, eine PDF-Datei in das XLS-Format zu konvertieren. Diese Funktion ist nützlich, wenn Sie Tabellendaten aus einer PDF-Datei extrahieren und in Microsoft Excel verwenden möchten.