---
title: Großes CGM-Bild als PDF
linktitle: Großes CGMImage in PDF
second_title: Aspose.PDF für .NET API-Referenz
description: Konvertieren Sie mit Aspose.PDF für .NET ganz einfach ein großes CGM-Bild in PDF.
type: docs
weight: 190
url: /de/net/programming-with-images/large-cgm-image-to-pdf/
---

In diesem Tutorial führen wir Sie Schritt für Schritt durch, wie Sie ein großes CGM-Bild mithilfe der Aspose.PDF-Bibliothek in .NET in eine PDF-Datei konvertieren. Der bereitgestellte C#-Quellcode demonstriert den Prozess der Konvertierung einer CGM-Datei in das PDF-Format, der Angabe der Seitengröße und des Speicherns der Ausgabedatei. Wir erklären Ihnen jeden Schritt im Detail, damit Sie den Prozess vollständig verstehen.

## Anforderungen
Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
- Grundkenntnisse der Programmiersprache C#.
- Aspose.PDF für .NET-Bibliothek in Ihrem Projekt installiert.
- Eine CGM-Bilddatei, die Sie in PDF konvertieren möchten.

## Schritt 1: Einrichten des Projekts
1. Erstellen Sie ein neues C#-Projekt in Ihrer bevorzugten Entwicklungsumgebung.
2. Fügen Sie in Ihrem Projekt einen Verweis auf die Aspose.PDF-Bibliothek hinzu.

## Schritt 2: Importieren der erforderlichen Namespaces
Importieren Sie am Anfang Ihrer C#-Datei die erforderlichen Namespaces, um auf die Aspose.PDF-Klassen und -Methoden zuzugreifen. Hier ist ein Beispiel:
```csharp
using System;
using Aspose.Pdf;
using System.Drawing;
```

## Schritt 3: Variablen und Pfade initialisieren
Bevor wir die Konvertierung durchführen, müssen wir die notwendigen Variablen und Pfade einrichten.
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inputFile = dataDir + "corvette.cgm";
dataDir = dataDir + "LargeCGMImageToPDF_out.pdf";
```
 Unbedingt austauschen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

## Schritt 4: CGM in PDF konvertieren
Um das CGM-Bild in das PDF-Format zu konvertieren, gehen Sie folgendermaßen vor:
1.  Erstellen Sie eine Instanz von`CgmImportOptions` Klasse.
```csharp
CgmImportOptions options = new CgmImportOptions();
```
2. Geben Sie die Abmessungen für den Seitengrößenimport an.
```csharp
options. PageSize = new SizeF(1000, 1000);
```
Hier stellen wir die Seitengröße auf 1000x1000 Pixel ein. Sie können die Abmessungen entsprechend Ihren Anforderungen anpassen.
 3. Verwenden Sie die`PdfProducer.Produce` Methode zum Konvertieren der CGM-Datei in das PDF-Format.
```csharp
PdfProducer.Produce(inputFile, ImportFormat.Cgm, dataDir);
```
4. Zeigen Sie eine Erfolgsmeldung mit dem Pfad an, in dem die PDF-Datei gespeichert ist.
```csharp
Console.WriteLine("\nLarge CGM file converted to PDF successfully.\nFile saved at " + dataDir);
```

### Beispielquellcode für Large CGMImage to PDF mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inputFile = dataDir + "corvette.cgm";
dataDir = dataDir + "LargeCGMImageToPDF_out.pdf";
// Erstellen Sie eine Instanz von CgmImportOptions
CgmImportOptions options = new CgmImportOptions();
// Geben Sie die Abmessungen für den Seitengrößenimport an
options.PageSize = new SizeF(1000, 1000);
// Speichern Sie CGM im PDF-Format
PdfProducer.Produce(inputFile, ImportFormat.Cgm, dataDir);
Console.WriteLine("\nLarge CGM file converted to pdf successfully.\nFile saved at " + dataDir); 
```

## Abschluss
Durch Befolgen dieser Schritt-für-Schritt-Anleitung haben Sie gelernt, wie Sie ein großes CGM-Bild mithilfe der Aspose.PDF-Bibliothek in .NET in eine PDF-Datei konvertieren. Dieser Prozess umfasst das Einrichten des Projekts, das Importieren der erforderlichen Namespaces, das Initialisieren von Variablen und Pfaden sowie das Durchführen der Konvertierung. Diesen Code können Sie nun in Ihre eigenen Projekte integrieren und entsprechend Ihren spezifischen Anforderungen modifizieren.