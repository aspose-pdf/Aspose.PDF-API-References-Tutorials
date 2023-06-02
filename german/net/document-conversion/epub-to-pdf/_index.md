---
title: EPUB zu PDF
linktitle: EPUB zu PDF
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Konvertieren von EPUB in PDF mit Aspose.PDF für .NET.
type: docs
weight: 30
url: /de/net/document-conversion/epub-to-pdf/
---

In diesem Tutorial führen wir Sie durch den Prozess der Konvertierung einer EPUB-Datei in PDF mithilfe der Aspose.PDF-Bibliothek für .NET. EPUB (Electronic Publication) ist ein weit verbreitetes Format für elektronische Bücher, während PDF (Portable Document Format) ein Standard für den Dokumentenaustausch ist. Wenn Sie die unten aufgeführten Schritte befolgen, können Sie EPUB-Dateien mühelos in das PDF-Format konvertieren.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

- Grundkenntnisse der Programmiersprache C#.
- Aspose.PDF-Bibliothek für .NET auf Ihrem System installiert.
- Eine Entwicklungsumgebung wie Visual Studio.

## Schritt 1: EPUB-Datei hochladen
In diesem Schritt laden wir die EPUB-Datei mit Aspose.PDF für .NET hoch. Befolgen Sie den folgenden Code:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Instanziieren Sie das LoadOption-Objekt mithilfe der EPUB-Ladeoption
EpubLoadOptions epubload = new EpubLoadOptions();

// Erstellen Sie ein Document-Objekt
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document(dataDir + "EPUBToPDF.epub", epubload);
```

 Unbedingt ersetzen`"YOUR DOCUMENTS DIRECTORY"` mit dem tatsächlichen Verzeichnis, in dem sich Ihre EPUB-Datei befindet.

## Schritt 2: Konvertierung von EPUB in PDF
Nachdem wir nun die EPUB-Datei hochgeladen haben, können wir mit der Konvertierung in PDF fortfahren. Verwenden Sie den folgenden Code:

```csharp
// Speichern Sie das resultierende PDF-Dokument
pdf. Save(dataDir + "EPUBToPDF_out.pdf");
```

 Der obige Code konvertiert die geladene EP-Datei EPUB in das PDF-Format und speichert sie unter dem Dateinamen`"EPUBToPDF_out.pdf"`. Stellen Sie sicher, dass Sie den richtigen Pfad und Dateinamen für die Ausgabe-PDF-Datei angeben.


 Ersetzen`"YOUR DOCUMENTS DIRECTORY"` mit dem gewünschten Verzeichnis, in dem Sie die ausgegebene PDF-Datei speichern möchten.

### Beispielquellcode für EPUB in PDF mit Aspose.Words für .NET

```csharp
try
{
	
	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Instanziieren Sie das LoadOption-Objekt mithilfe der EPUB-Ladeoption
	EpubLoadOptions epubload = new EpubLoadOptions();

	// Dokumentobjekt erstellen
	Aspose.Pdf.Document pdf = new Aspose.Pdf.Document(dataDir + "EPUBToPDF.epub", epubload);

	// Speichern Sie das resultierende PDF-Dokument
	pdf.Save(dataDir + "EPUBToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}

```

## Abschluss
In diesem Tutorial haben wir den Schritt-für-Schritt-Prozess zum Konvertieren einer EPUB-Datei in PDF mithilfe der Aspose.PDF-Bibliothek für .NET behandelt. Wenn Sie die oben beschriebenen Anweisungen befolgen, sollten Sie nun in der Lage sein, EPUB-Dateien mühelos in das PDF-Format zu konvertieren. Diese Konvertierung eröffnet Möglichkeiten zum Teilen, Drucken und Archivieren Ihrer Dokumente.

