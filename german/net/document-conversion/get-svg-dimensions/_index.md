---
title: Holen Sie sich SVG-Abmessungen
linktitle: Holen Sie sich SVG-Abmessungen
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Erhalten von SVG-Abmessungen mit Aspose.PDF für .NET.
type: docs
weight: 40
url: /de/net/document-conversion/get-svg-dimensions/
---
## Einführung
In diesem Tutorial führen wir Sie durch den Prozess zum Ermitteln der Abmessungen einer SVG-Datei mit Aspose.PDF für .NET. SVG (Scalable Vector Graphics) ist ein XML-basiertes Bildformat zur Darstellung von Vektorgrafiken. Mit den folgenden Schritten können Sie die Abmessungen einer SVG-Datei ermitteln und diese als PDF speichern.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

- Grundkenntnisse der Programmiersprache C#.
- Aspose.PDF-Bibliothek für .NET auf Ihrem System installiert.
- Eine Entwicklungsumgebung wie Visual Studio.

## Schritt 1: SVG-Datei laden
In diesem Schritt laden wir die SVG-Datei mit Aspose.PDF für .NET. Befolgen Sie den folgenden Code:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

var loadopt = new SvgLoadOptions();
loadopt.AdjustPageSize = true;
var svgDoc = new Document(dataDir + "GetSVGDimensions.svg", loadopt);
```

 Unbedingt ersetzen`"YOUR DOCUMENTS DIRECTORY"` mit dem tatsächlichen Verzeichnis, in dem sich Ihre SVG-Datei befindet.

## Schritt 2: Anpassung der Seitengröße
Nachdem wir die SVG-Datei geladen haben, können wir die Seitengröße an den SVG-Inhalt anpassen. Verwenden Sie den folgenden Code:

```csharp
svgDoc.Pages[1].PageInfo.Margin.Top = 0;
svgDoc.Pages[1].PageInfo.Margin.Left = 0;
svgDoc.Pages[1].PageInfo.Margin.Bottom = 0;
svgDoc.Pages[1].PageInfo.Margin.Right = 0;
```

Der obige Code setzt die Seitenränder auf Null, sodass die Seitengröße basierend auf dem SVG-Inhalt angepasst werden kann.

## Schritt 3: Speichern des resultierenden PDF
Nachdem wir die Seitengröße angepasst haben, können wir nun das resultierende PDF-Dokument speichern. Hier ist der letzte Schritt:

```csharp
svgDoc.Save(dataDir + "GetSVGDimensions_out.pdf");
```

 Ersetzen`"YOUR DOCUMENTS DIRECTORY"` mit dem gewünschten Verzeichnis, in dem Sie die ausgegebene PDF-Datei speichern möchten.
  
### Beispielquellcode für „Get SVG Dimensions“ mit Aspose.PDF für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

var loadopt = new SvgLoadOptions();
loadopt.AdjustPageSize = true;
var svgDoc = new Document(dataDir + "GetSVGDimensions.svg", loadopt);
svgDoc.Pages[1].PageInfo.Margin.Top = 0;
svgDoc.Pages[1].PageInfo.Margin.Left = 0;
svgDoc.Pages[1].PageInfo.Margin.Bottom = 0;
svgDoc.Pages[1].PageInfo.Margin.Right = 0;
svgDoc.Save(dataDir + "GetSVGDimensions_out.pdf");
```

## Abschluss
In diesem Tutorial haben wir den Schritt-für-Schritt-Prozess zum Ermitteln der Abmessungen einer SVG-Datei mit Aspose.PDF für .NET behandelt. Wenn Sie die oben beschriebenen Anweisungen befolgen, sollten Sie nun in der Lage sein, die Abmessungen einer SVG-Datei zu ermitteln und diese im PDF-Format zu speichern. Diese Funktion kann nützlich sein, wenn Sie die Abmessungen einer Vektorgrafik messen müssen.

### FAQs

#### F: Was ist SVG?

A: SVG (Scalable Vector Graphics) ist ein XML-basiertes Bildformat, das zur Darstellung von Vektorgrafiken verwendet wird. Im Gegensatz zu Rasterbildern sind SVG-Dateien auflösungsunabhängig und können ohne Qualitätsverlust skaliert werden. SVG wird häufig zum Anzeigen von Grafiken im Web verwendet und kann problemlos bearbeitet und manipuliert werden.

#### F: Warum Aspose.PDF für .NET für die SVG-zu-PDF-Konvertierung verwenden?

A: Aspose.PDF für .NET bietet eine zuverlässige und effiziente Möglichkeit, SVG-Dateien zu verarbeiten und in das PDF-Format zu konvertieren. Es bietet verschiedene Optionen und Einstellungen zum Anpassen des Konvertierungsprozesses, z. B. das Anpassen der Seitengröße, der Ränder und anderer Eigenschaften, um eine genaue Darstellung im PDF zu gewährleisten.

#### F: Kann ich SVG-Dateien mit komplexen Grafiken und Texten konvertieren?

A: Ja, Aspose.PDF für .NET kann SVG-Dateien mit komplexen Grafiken, Texten und Vektorelementen verarbeiten. Die Details und die Qualität des SVG-Inhalts bleiben während des Konvertierungsprozesses genau erhalten, was zu hochwertigen PDF-Dokumenten führt.

#### F: Ist es möglich, mit Aspose.PDF für .NET Text aus SVG-Dateien zu extrahieren?

A: Ja, mit Aspose.PDF für .NET können Sie Text aus SVG-Dateien extrahieren. Mithilfe der Textextraktionsfunktionen der Bibliothek können Sie Textelemente aus SVG extrahieren und diese zur weiteren Verarbeitung separat speichern.