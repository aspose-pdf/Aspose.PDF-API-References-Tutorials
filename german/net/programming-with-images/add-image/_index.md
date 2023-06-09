---
title: Bild hinzufügen
linktitle: Bild hinzufügen
second_title: Aspose.PDF für .NET API-Referenz
description: Fügen Sie mit Aspose.PDF für .NET ganz einfach ein Bild zu einem PDF-Dokument hinzu.
type: docs
weight: 10
url: /de/net/programming-with-images/add-image/
---

In dieser Anleitung erfahren Sie Schritt für Schritt, wie Sie mit Aspose.PDF für .NET ein Bild zu einem PDF-Dokument hinzufügen. Stellen Sie sicher, dass Sie Ihre Umgebung bereits eingerichtet haben, und führen Sie die folgenden Schritte aus:

## Schritt 1: Definieren Sie das Dokumentenverzeichnis

 Bevor Sie beginnen, stellen Sie sicher, dass Sie das richtige Verzeichnis für die Dokumente festgelegt haben. Ersetzen`"YOUR DOCUMENT DIRECTORY"` Geben Sie im Code den Pfad zu dem Verzeichnis ein, in dem sich Ihr PDF-Dokument befindet.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Öffnen Sie das Dokument

 In diesem Schritt öffnen wir das PDF-Dokument mit`Document` Klasse von Aspose.PDF. Benutzen Sie die`Document` Konstruktor und übergeben Sie den Pfad zum PDF-Dokument.

```csharp
Document pdfDocument = new Document(dataDir + "AddImage.pdf");
```

## Schritt 3: Bildkoordinaten festlegen

 Legen Sie die Koordinaten des Bildes fest, das Sie hinzufügen möchten. Die Variablen`lowerLeftX`, `lowerLeftY`, `upperRightX` Und`upperRightY` stellen die Koordinaten der unteren linken Ecke bzw. der oberen rechten Ecke des Bildes dar.

```csharp
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;
```

## Schritt 4: Rufen Sie die Seite auf, auf der das Bild hinzugefügt werden soll

Um das Bild zu einer bestimmten Seite des PDF-Dokuments hinzuzufügen, müssen wir zunächst diese Seite abrufen. In diesem Beispiel fügen wir das Bild auf der zweiten Seite (Index 1) des Dokuments hinzu.

```csharp
Page page = pdfDocument.Pages[1];
```

## Schritt 5: Laden Sie das Bild aus einem Stream

Wir laden nun das Bild, das wir dem PDF-Dokument hinzufügen möchten. In diesem Beispiel wird davon ausgegangen, dass Sie eine Bilddatei mit dem Namen haben`aspose-logo.jpg` im selben Verzeichnis wie Ihr Dokument. Ersetzen Sie ggf. den Dateinamen.

```csharp
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
```

## Schritt 6: Fügen Sie das Bild zu den Seitenressourcen hinzu

Um das Bild im PDF-Dokument verwenden zu können, müssen wir es zur Ressourcenbildsammlung der Seite hinzufügen.

```csharp
page.Resources.Images.Add(imageStream);
```

## Schritt 7: Aktuellen Grafikstatus speichern

 Bevor wir das Bild zeichnen, müssen wir den aktuellen Grafikstatus mit speichern`GSave` Operator. Dadurch wird sichergestellt, dass Änderungen am Grafikstatus später rückgängig gemacht werden können.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.GSave());
```

## Schritt 8: Erstellen Sie Rechteck- und Matrixobjekte

 Wir erstellen nun eine`Rectangle` Objekt und a`Matrix` Objekt. Das Rechteck stellt die Position und Größe des Bildes dar, während die Matrix definiert, wie das Bild platziert werden soll.

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lower

LeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
```

## Schritt 9: Verketten Sie die Matrix für die Bildplatzierung

 Um anzugeben, wie das Bild im Rechteck platziert werden soll, verwenden wir die`ConcatenateMatrix`Operator. Dieser Operator definiert die Transformationsmatrix, die den Koordinatenraum des Bildes dem Koordinatenraum der Seite zuordnet.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(matrix));
```

## Schritt 10: Zeichnen Sie das Bild

 In diesem Schritt zeichnen wir das Bild mit dem auf der Seite`Do` Operator. Der`Do` Der Operator übernimmt den Bildnamen aus den Ressourcen und zeichnet ihn auf die Seite.

```csharp
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
page.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
```

## Schritt 11: Grafikstatus wiederherstellen

 Nachdem wir das Bild gezeichnet haben, müssen wir den vorherigen Grafikstatus mithilfe von wiederherstellen`GRestore` Operator.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.GRestore());
```

## Schritt 12: Speichern Sie das aktualisierte Dokument

 Abschließend speichern wir das aktualisierte Dokument in einer neuen Datei. Aktualisieren Sie die`dataDir` Variable mit dem gewünschten Ausgabeverzeichnis und Dateinamen.

```csharp
dataDir = dataDir + "AddImage_out.pdf";
pdfDocument.Save(dataDir);
```

### Beispielquellcode für „Bild hinzufügen“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir+ "AddImage.pdf");
// Koordinaten festlegen
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;
// Rufen Sie die Seite auf, auf der das Bild hinzugefügt werden muss
Page page = pdfDocument.Pages[1];
// Bild in Stream laden
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
// Bild zur Bildersammlung der Seitenressourcen hinzufügen
page.Resources.Images.Add(imageStream);
// Verwendung des GSave-Operators: Dieser Operator speichert den aktuellen Grafikstatus
page.Contents.Add(new Aspose.Pdf.Operators.GSave());
// Erstellen Sie Rechteck- und Matrixobjekte
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
//Mit dem ConcatenateMatrix-Operator (Verkettungsmatrix): Definiert, wie das Bild platziert werden muss
page.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(matrix));
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
// Verwenden des Do-Operators: Dieser Operator zeichnet ein Bild
page.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
// Verwendung des GRestore-Operators: Dieser Operator stellt den Grafikstatus wieder her
page.Contents.Add(new Aspose.Pdf.Operators.GRestore());
dataDir = dataDir + "AddImage_out.pdf";
// Aktualisiertes Dokument speichern
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage added successfully.\nFile saved at " + dataDir); 
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.PDF für .NET ein Bild zu einem PDF-Dokument hinzufügt. Wir haben jeden Schritt im Detail behandelt, vom Öffnen des Dokuments bis zum Speichern der aktualisierten Version. Wenn Sie dieser Anleitung folgen, sollten Sie nun in der Lage sein, Bilder mithilfe von C# und Aspose.PDF programmgesteuert in Ihre PDF-Dateien einzubetten.