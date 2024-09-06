---
title: Ausrichtung ändern
linktitle: Ausrichtung ändern
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Ändern der Seitenausrichtung einer PDF-Datei mit Aspose.PDF für .NET. Einfach zu befolgen und in Ihren Projekten zu implementieren.
type: docs
weight: 10
url: /de/net/programming-with-pdf-pages/change-orientation/
---
In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess zum Ändern der Seitenausrichtung eines PDF-Dokuments mit Aspose.PDF für .NET. Wir erklären den mitgelieferten C#-Quellcode und stellen Ihnen eine umfassende Anleitung zur Verfügung, die Ihnen hilft, diese Funktion zu verstehen und in Ihren eigenen Projekten zu implementieren. Am Ende dieses Tutorials wissen Sie, wie Sie die Seitenausrichtung Ihrer PDF-Dokumente mit Aspose.PDF für .NET ändern.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Grundkenntnisse der Programmiersprache C#
- Aspose.PDF für .NET in Ihrer Entwicklungsumgebung installiert

## Schritt 1: Dokumentverzeichnis festlegen
Zuerst müssen Sie den Pfad zu Ihrem Dokumentenverzeichnis festlegen. Dies ist der Speicherort, an dem sich Ihre PDF-Eingabedatei befindet und an dem Sie Ihre geänderte PDF-Ausgabedatei speichern möchten. Ersetzen Sie „IHR DOKUMENTENVERZEICHNIS“ durch den entsprechenden Pfad.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Laden Sie das PDF-Dokument
 Anschließend können Sie das PDF-Dokument aus der Eingabedatei laden mit dem`Document` Klasse von Aspose.PDF. Achten Sie darauf, den richtigen Pfad zur PDF-Datei anzugeben.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Schritt 3: Seitenausrichtung ändern
Nun gehen wir jede Seite des Dokuments durch und ändern ihre Ausrichtung. Für jede Seite ändern wir die Abmessungen der Medienbox (`MediaBox`) indem wir Breite und Höhe vertauschen, dann passen wir die Koordinaten der Mediabox an, um die Position der Seite beizubehalten. Abschließend stellen wir die Seitenrotation auf 90 Grad ein.

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
 Abschließend können Sie das geänderte PDF-Dokument in einer Ausgabedatei speichern mit dem`Save()` Methode der`Document`Klasse. Achten Sie darauf, den richtigen Pfad und Dateinamen anzugeben.

```csharp
dataDir = dataDir + "ChangeOrientation_out.pdf";
doc.Save(dataDir);
```

### Beispielquellcode zum Ändern der Ausrichtung mit Aspose.PDF für .NET 

```csharp

// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
foreach (Page page in doc.Pages)
{
	Aspose.Pdf.Rectangle r = page.MediaBox;
	double newHeight = r.Width;
	double newWidth = r.Height;
	double newLLX = r.LLX;
	// Wir müssen die Seite nach oben verschieben, um die sich ändernde Seitengröße auszugleichen
	// (unterer Rand der Seite ist 0,0 und Informationen werden normalerweise von der
	// Oben auf der Seite. Deshalb verschieben wir die untere Kante nach oben, um den Unterschied zwischen
	// Alte und neue Höhe.
	double newLLY = r.LLY + (r.Height - newHeight);
	page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
	// Manchmal müssen wir auch CropBox festlegen (wenn es in der Originaldatei festgelegt wurde)
	page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
	// Einstellen des Rotationswinkels der Seite
	page.Rotate = Rotation.on90;
}
dataDir = dataDir + "ChangeOrientation_out.pdf";
// Ausgabedatei speichern
doc.Save(dataDir);
System.Console.WriteLine("\nPage orientation changed successfully.\nFile saved at " + dataDir);

```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man die Seitenausrichtung eines PDF-Dokuments mit Aspose.PDF für .NET ändert. Indem Sie die oben beschriebenen Schritte befolgen, können Sie diese Funktion problemlos in Ihre eigenen Projekte implementieren. Sehen Sie sich die Aspose.PDF-Dokumentation genauer an, um weitere nützliche Funktionen für die Arbeit mit PDF-Dateien zu entdecken.

### Häufig gestellte Fragen

#### F: Welchen Zweck hat die Änderung der Seitenausrichtung in einem PDF-Dokument?

A: Durch Ändern der Seitenausrichtung in einem PDF-Dokument können Sie den Inhalt der Seite um 90 Grad drehen. Dies kann in Szenarien nützlich sein, in denen der Originalinhalt in einer anderen Ausrichtung angezeigt oder gedruckt werden muss, beispielsweise beim Wechsel vom Hochformat ins Querformat oder umgekehrt.

#### F: Kann ich die Ausrichtung bestimmter Seiten im PDF-Dokument ändern?

 A: Ja, Sie können die Ausrichtung bestimmter Seiten im PDF-Dokument ändern. Im bereitgestellten C#-Quellcode wird die`foreach` Mit der Schleife können Sie jede Seite des Dokuments durchgehen und ihre Ausrichtung ändern. Wenn Sie nur die Ausrichtung bestimmter Seiten ändern möchten, können Sie die Schleife so ändern, dass diese Seiten anhand ihrer Seitenzahlen oder anderer Kriterien ausgewählt werden.

#### F: Hat das Ändern der Seitenausrichtung Auswirkungen auf das Layout des Inhalts auf der Seite?

A: Ja, das Ändern der Seitenausrichtung wirkt sich auf das Layout des Inhalts auf der Seite aus. Der Inhalt wird um 90 Grad gedreht und die Breite und Höhe der Seite werden vertauscht. Infolgedessen kann sich die Platzierung und Ausrichtung des Inhalts auf der Seite ändern.

#### F: Kann ich die Seite um einen anderen Winkel als 90 Grad drehen?

 A: Im bereitgestellten C#-Quellcode wird die Seitenrotation auf 90 Grad eingestellt, indem`page.Rotate = Rotate.on90;` . Sie können den Drehwinkel jedoch bei Bedarf auf andere Werte ändern. Sie können beispielsweise`Rotate.on180` die Seite um 180 Grad zu drehen oder`Rotate.on270` um es um 270 Grad zu drehen.

#### F: Wie gehe ich mit dem Seiteninhalt um, der nach der Änderung der Ausrichtung überläuft?

A: Wenn Sie die Seitenausrichtung ändern, können sich die Abmessungen der Seite ändern, was zu einem Inhaltsüberlauf führen kann. Um dies zu beheben, müssen Sie möglicherweise das Layout und die Formatierung des Inhalts auf der Seite anpassen. Sie können die von Aspose.PDF für .NET bereitgestellten Funktionen verwenden, z. B. die Größenänderung von Elementen, das Anpassen von Rändern oder die Neuorganisation von Inhalten, um sicherzustellen, dass der Seiteninhalt nach der Ausrichtungsänderung richtig passt.