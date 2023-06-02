---
title: Ausrichtung ändern
linktitle: Ausrichtung ändern
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Ändern der Seitenausrichtung einer PDF-Datei mit Aspose.PDF für .NET. Einfach zu befolgen und in Ihre Projekte umzusetzen.
type: docs
weight: 10
url: /de/net/programming-with-pdf-pages/change-orientation/
---
In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess zum Ändern der Seitenausrichtung eines PDF-Dokuments mit Aspose.PDF für .NET. Wir erklären Ihnen den gebündelten C#-Quellcode und stellen Ihnen eine umfassende Anleitung zur Verfügung, die Ihnen hilft, diese Funktion zu verstehen und in Ihren eigenen Projekten zu implementieren. Am Ende dieses Tutorials erfahren Sie, wie Sie die Seitenausrichtung Ihrer PDF-Dokumente mit Aspose.PDF für .NET ändern.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Grundkenntnisse der Programmiersprache C#
- Aspose.PDF für .NET in Ihrer Entwicklungsumgebung installiert

## Schritt 1: Definieren Sie das Dokumentenverzeichnis
Zuerst müssen Sie den Pfad zu Ihrem Dokumentenverzeichnis festlegen. Dies ist der Speicherort, an dem sich Ihre Eingabe-PDF-Datei befindet und an dem Sie Ihre geänderte Ausgabe-PDF-Datei speichern möchten. Ersetzen Sie „IHR DOKUMENTENVERZEICHNIS“ durch den entsprechenden Pfad.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Laden Sie das PDF-Dokument
 Anschließend können Sie das PDF-Dokument aus der Eingabedatei mit laden`Document` Klasse von Aspose.PDF. Stellen Sie sicher, dass Sie den korrekten Pfad zur PDF-Datei angeben.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Schritt 3: Seitenausrichtung ändern
Jetzt gehen wir jede Seite des Dokuments durch und ändern ihre Ausrichtung. Für jede Seite ändern wir die Abmessungen der Medienbox (`MediaBox`) durch Vertauschen der Breite und Höhe, dann passen wir die Koordinaten der Medienbox an, um die Position der Seite beizubehalten. Abschließend stellen wir die Seitendrehung auf 90 Grad ein.

```csharp
foreach(Page page in doc.Pages)
{
Aspose.Pdf.Rectangle r = page.MediaBox;
double newHeight = r.Width;
double newWidth = r.Height;
double newLLX = r.LLX;
double newLLY = r.LLY + (r.Height - newHeight);
page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page. Rotate = Rotate. on90;
}
```

## Schritt 4: Speichern Sie das geänderte PDF-Dokument
 Abschließend können Sie das geänderte PDF-Dokument mit in einer Ausgabedatei speichern`Save()` Methode der`Document` Klasse. Stellen Sie sicher, dass Sie den richtigen Pfad und Dateinamen angeben.

```csharp
dataDir = dataDir + "ChangeOrientation_out.pdf";
doc.Save(dataDir);
```

### Beispielquellcode für Change Orientation mit Aspose.PDF für .NET 

```csharp

// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
foreach (Page page in doc.Pages)
{
	Aspose.Pdf.Rectangle r = page.MediaBox;
	double newHeight = r.Width;
	double newWidth = r.Height;
	double newLLX = r.LLX;
	// Wir müssen die Seite nach oben verschieben, um die sich ändernde Seitengröße auszugleichen
	// (Der untere Rand der Seite ist 0,0 und die Informationen werden normalerweise aus dem platziert
	// Ganz oben auf der Seite. Aus diesem Grund verschieben wir die Differenz zwischen den Liebhabern nach oben
	// Alte und neue Höhe.
	double newLLY = r.LLY + (r.Height - newHeight);
	page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
	// Manchmal müssen wir auch CropBox festlegen (wenn es in der Originaldatei festgelegt wurde).
	page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
	// Festlegen des Rotationswinkels der Seite
	page.Rotate = Rotation.on90;
}
dataDir = dataDir + "ChangeOrientation_out.pdf";
// Ausgabedatei speichern
doc.Save(dataDir);
System.Console.WriteLine("\nPage orientation changed successfully.\nFile saved at " + dataDir);

```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man die Seitenausrichtung eines PDF-Dokuments mit Aspose.PDF für .NET ändert. Wenn Sie die oben beschriebenen Schritte befolgen, können Sie diese Funktionalität problemlos in Ihre eigenen Projekte implementieren. Sehen Sie sich gerne die Aspose.PDF-Dokumentation weiter an, um weitere nützliche Funktionen für die Arbeit mit PDF-Dateien zu entdecken.