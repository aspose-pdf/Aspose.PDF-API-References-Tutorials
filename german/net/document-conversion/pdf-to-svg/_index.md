---
title: PDF zu SVG
linktitle: PDF zu SVG
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Konvertieren von PDF in SVG mit Aspose.PDF für .NET.
type: docs
weight: 180
url: /de/net/document-conversion/pdf-to-svg/
---

In diesem Tutorial führen wir Sie durch den Prozess der Konvertierung einer PDF-Datei in das SVG-Format mit Aspose.PDF für .NET. SVG (Scalable Vector Graphics) ist ein Vektorbildformat, das dabei hilft, die Qualität und Skalierung von Grafiken beizubehalten. Wenn Sie die folgenden Schritte ausführen, können Sie eine PDF-Datei in das SVG-Format konvertieren.

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
Document doc = new Document(dataDir + "input.pdf");
```

 Unbedingt ersetzen`"YOUR DOCUMENTS DIRECTORY"` mit dem tatsächlichen Verzeichnis, in dem sich Ihre PDF-Datei befindet.

## Schritt 2: Instanziierung der SVG-Speicheroptionen
Nach dem Laden der PDF-Datei instanziieren wir die SVG-Speicheroptionen. Verwenden Sie den folgenden Code:

```csharp
// Instanziieren Sie ein SVGSaveOptions-Objekt
SvgSaveOptions saveOptions = new SvgSaveOptions();
// Komprimieren Sie das SVG-Bild nicht in einem Zip-Archiv
saveOptions.CompressOutputToZipArchive = false;
```

## Schritt 3: Speichern der resultierenden SVG-Datei
Jetzt speichern wir die konvertierte PDF-Datei im SVG-Format. Verwenden Sie den folgenden Code:

```csharp
// Speichern Sie die Ausgabe in SVG-Dateien
doc.Save(dataDir + "PDFToSVG_out.svg", saveOptions);
```

 Der obige Code speichert die konvertierte PDF-Datei im SVG-Format unter dem Dateinamen`"PDFToSVG_out.svg"`.

### Beispielquellcode für PDF zu SVG mit Aspose.Words für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// PDF-Dokument laden
Document doc = new Document(dataDir + "input.pdf");
// Instanziieren Sie ein Objekt von SVGSaveOptions
SvgSaveOptions saveOptions = new SvgSaveOptions();
// Komprimieren Sie das SVG-Bild nicht in ein Zip-Archiv
saveOptions.CompressOutputToZipArchive = false;
// Speichern Sie die Ausgabe in SVG-Dateien
doc.Save(dataDir + "PDFToSVG_out.svg", saveOptions);
```

## Abschluss
In diesem Tutorial haben wir den Schritt-für-Schritt-Prozess zum Konvertieren einer PDF-Datei in das SVG-Format mit Aspose.PDF für .NET behandelt. Wenn Sie die oben beschriebenen Anweisungen befolgen, sollten Sie nun in der Lage sein, eine PDF-Datei in das SVG-Format zu konvertieren. Diese Funktion ist nützlich, wenn Sie beim Konvertieren in Vektorbilder die Grafikqualität und Skalierung beibehalten möchten.