---
title: TIFF-zu-PDF-Leistungsverbesserung
linktitle: TIFF-zu-PDF-Leistungsverbesserung
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zur Verbesserung der TIFF-zu-PDF-Konvertierungsleistung mit Aspose.PDF für .NET.
type: docs
weight: 310
url: /de/net/document-conversion/tiff-to-pdf-performance-improvement/
---
In diesem Tutorial führen wir Sie Schritt für Schritt durch die Verbesserung der Leistung beim Konvertieren von TIFF-Dateien in PDF mithilfe der Aspose.PDF-Bibliothek für .NET. Wir erläutern den bereitgestellten C#-Quellcode und zeigen Ihnen, wie Sie ihn in Ihren eigenen Projekten implementieren. Am Ende dieses Tutorials werden Sie in der Lage sein, schnellere und effizientere Konvertierungen von TIFF-Dateien in PDF durchzuführen.

## Schritt 1: Dokumentenverzeichnis festlegen
```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```
 Ersetzen`"YOUR DOCUMENTS DIRECTORY"` mit dem Pfad, in dem Sie Ihre Dateien gespeichert haben.

## Schritt 2: Liste der TIFF-Dateien abrufen
```csharp
string[] files = System.IO.Directory.GetFiles(dataDir, "*.tif");
```
Rufen Sie eine Liste der im angegebenen Verzeichnis vorhandenen TIFF-Dateien ab.

## Schritt 3: Instanziieren Sie ein Document-Objekt
```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```
Erstellen Sie eine Instanz des Document-Objekts.

## Schritt 4: Dateien durchsuchen und zum PDF-Dokument hinzufügen
```csharp
foreach (string myFile in files)
{
     FileStream fs = new FileStream(myFile, FileMode.Open, FileAccess.Read);
     byte[] tmpBytes = new byte[fs.Length];
     fs.Read(tmpBytes, 0, Convert.ToInt32(fs.Length));

     MemoryStream mystream = new MemoryStream(tmpBytes);
     Bitmap b = new Bitmap(mystream);
     Aspose.Pdf.Page currpage = doc.Pages.Add();

     currpage.PageInfo.Margin.Top = 5;
     currpage.PageInfo.Margin.Bottom = 5;
     currpage.PageInfo.Margin.Left = 5;
     currpage.PageInfo.Margin.Right = 5;

     currpage.PageInfo.Width = (b.Width / b.HorizontalResolution) * 72;
     currpage.PageInfo.Height = (b.Height / b.VerticalResolution) * 72;

     Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

     currpage.Paragraphs.Add(image1);

     image1.IsBlackWhite = true;
     image1.ImageStream = mystream;
     image1.ImageScale = 0.95F;
}
```
 Gehen Sie jede TIFF-Datei durch und laden Sie sie als`Bitmap` Objekt und fügen Sie es dann dem PDF-Dokument hinzu. Parameter wie Ränder, Auflösung und Maßstab des Bildes werden ebenfalls konfiguriert.

## Schritt 5: Speichern Sie die resultierende PDF-Datei
```csharp
doc.Save(dataDir + "PerformaceImprovement_out.pdf");
```
Speichern Sie das resultierende PDF-Dokument im angegebenen Verzeichnis.

### Beispielquellcode für die Leistungsverbesserung von TIFF zu PDF mit Aspose.PDF für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Rufen Sie eine Liste der TIFF-Bilddateien ab
string[] files = System.IO.Directory.GetFiles(dataDir, "*.tif");

// Instanziieren Sie ein Document-Objekt
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Navigieren Sie durch die Dateien und sie in der PDF-Datei
foreach (string myFile in files)
{

	// Laden Sie alle TIFF-Dateien in ein Byte-Array
	FileStream fs = new FileStream(myFile, FileMode.Open, FileAccess.Read);
	byte[] tmpBytes = new byte[fs.Length];
	fs.Read(tmpBytes, 0, Convert.ToInt32(fs.Length));

	MemoryStream mystream = new MemoryStream(tmpBytes);
	Bitmap b = new Bitmap(mystream);
	// Erstellen Sie eine neue Seite im PDF-Dokument
	Aspose.Pdf.Page currpage = doc.Pages.Add();

	// Legen Sie die Ränder so fest, dass das Bild passt usw.
	currpage.PageInfo.Margin.Top = 5;
	currpage.PageInfo.Margin.Bottom = 5;
	currpage.PageInfo.Margin.Left = 5;
	currpage.PageInfo.Margin.Right = 5;

	currpage.PageInfo.Width = (b.Width / b.HorizontalResolution) * 72;
	currpage.PageInfo.Height = (b.Height / b.VerticalResolution) * 72;

	// Erstellen Sie ein Bildobjekt
	Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

	// Fügen Sie das Bild zur Absatzsammlung der Seite hinzu
	currpage.Paragraphs.Add(image1);

	// Setzen Sie die IsBlackWhite-Eigenschaft zur Leistungsverbesserung auf „true“.
	image1.IsBlackWhite = true;
	// Legen Sie ImageStream auf ein MemoryStream-Objekt fest
	image1.ImageStream = mystream;
	// Stellen Sie den gewünschten Bildmaßstab ein
	image1.ImageScale = 0.95F;
}

// Speichern Sie das PDF
doc.Save(dataDir + "PerformaceImprovement_out.pdf");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie wir die Leistung beim Konvertieren von TIFF-Dateien in PDF mithilfe der Aspose.PDF-Bibliothek für .NET verbessern können. Wenn Sie die bereitgestellten Schritte befolgen, können Sie TIFF-Dateien schneller und effizienter in PDF konvertieren. Erhalten Sie präzise und professionelle Ergebnisse und optimieren Sie gleichzeitig die Leistung Ihrer Anwendung

### FAQs

#### F: Was ist Aspose.PDF für .NET?

A: Aspose.PDF für .NET ist eine leistungsstarke Bibliothek, die Entwicklern die Arbeit mit PDF-Dokumenten in C#-Anwendungen ermöglicht. Es bietet verschiedene Funktionalitäten, einschließlich der Konvertierung von TIFF-Dateien in PDF.

#### F: Warum sollte ich die Leistung der TIFF-zu-PDF-Konvertierung verbessern wollen?

A: Die Verbesserung der Leistung der TIFF-zu-PDF-Konvertierung kann die Effizienz Ihrer Anwendung erheblich steigern, insbesondere wenn Sie eine große Anzahl von TIFF-Dateien verarbeiten. Schnellere Konvertierungen führen zu einer verbesserten Benutzererfahrung und einer kürzeren Bearbeitungszeit.

#### F: Wie kann ich das Verzeichnis für die TIFF-Dateien festlegen?

 A: Sie können das Verzeichnis für die TIFF-Dateien festlegen, indem Sie das ersetzen`"YOUR DOCUMENTS DIRECTORY"` Platzhalter im Code mit dem tatsächlichen Pfad, in dem sich Ihre TIFF-Dateien befinden.

#### F: Welche Optimierungen werden im Code-Snippet angewendet, um die Leistung zu verbessern?

 A: Das Code-Snippet verwendet verschiedene Techniken, um die Konvertierungsleistung zu verbessern, z. B. das Festlegen von Rändern, das Konfigurieren von Bildauflösung und -skalierung sowie das Festlegen der`IsBlackWhite`Eigenschaft zu wahr. Diese Optimierungen tragen dazu bei, den Konvertierungsprozess zu optimieren.

#### F: Kann ich die Bildeigenschaften im resultierenden PDF anpassen?

A: Ja, Sie können die Bildeigenschaften in der resultierenden PDF-Datei anpassen, z. B. Skalierung, Auflösung und Ränder, um das gewünschte Layout und Erscheinungsbild zu erzielen.