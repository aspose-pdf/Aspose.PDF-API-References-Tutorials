---
title: SVG zu PDF
linktitle: SVG zu PDF
second_title: Aspose.PDF für .NET API-Referenz
description: Einfache und schnelle SVG-zu-PDF-Konvertierung mit Aspose.PDF für .NET.
type: docs
weight: 280
url: /de/net/document-conversion/svg-to-pdf/
---

Dieses Tutorial führt Sie durch die Schritte zum Konvertieren einer SVG-Datei in eine PDF-Datei mit Aspose.PDF für .NET. Aspose.PDF bietet eine einfache und effektive Lösung zum Konvertieren von SVG-Dateien in PDF unter Beibehaltung der Inhaltsqualität und des Layouts. Führen Sie die folgenden Schritte aus, um diese Konvertierung durchzuführen.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

- Grundkenntnisse der Programmiersprache C#.
- Aspose.PDF-Bibliothek für .NET auf Ihrem System installiert.
- Eine Entwicklungsumgebung wie Visual Studio.

## Schritt 1: SVG-Datei laden
 Der erste Schritt besteht darin, die SVG-Datei in eine zu laden`Document`Objekt mit der SVG-Ladeoption (`SvgLoadOptions`). Verwenden Sie den folgenden Code:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Instanziieren Sie das LoadOption-Objekt mithilfe der SVG-Ladeoption
Aspose.Pdf.LoadOptions loadopt = new Aspose.Pdf.SvgLoadOptions();

// Dokumentobjekt erstellen
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "SVGToPDF.svg", loadopt);
```

 Unbedingt ersetzen`"YOUR DOCUMENTS DIRECTORY"` mit dem tatsächlichen Verzeichnis, in dem sich Ihre SVG-Datei befindet.

## Schritt 2: In PDF konvertieren
 Der zweite Schritt besteht darin, das SVG-Dokument mithilfe von in ein PDF-Dokument zu konvertieren`Save` Methode der`Document` Objekt. Verwenden Sie den folgenden Code:

```csharp
// Speichern Sie das resultierende PDF-Dokument
doc.Save(dataDir + "SVGToPDF_out.pdf");
```

Geben Sie unbedingt den gewünschten Pfad und Dateinamen für die resultierende PDF-Datei an.

### Beispielquellcode für SVG in PDF mit Aspose.PDF für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instanziieren Sie das LoadOption-Objekt mithilfe der SVG-Ladeoption
Aspose.Pdf.LoadOptions loadopt = new Aspose.Pdf.SvgLoadOptions();

// Dokumentobjekt erstellen
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "SVGToPDF.svg", loadopt);

// Speichern Sie das resultierende PDF-Dokument
doc.Save(dataDir + "SVGToPDF_out.pdf");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.PDF für .NET eine SVG-Datei in eine PDF-Datei konvertiert. Wenn Sie die oben angegebenen Schritte befolgen, können Sie diese Konvertierung problemlos durchführen. Verwenden Sie diese Methode, um Ihre SVG-Dateien in PDF zu konvertieren und genießen Sie die Flexibilität und Qualität von Aspose.PDF.