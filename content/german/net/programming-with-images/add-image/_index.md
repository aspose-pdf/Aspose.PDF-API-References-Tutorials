---
title: Bild in PDF-Datei hinzufügen
linktitle: Bild in PDF-Datei hinzufügen
second_title: Aspose.PDF für .NET API-Referenz
description: Fügen Sie mit Aspose.PDF für .NET ganz einfach ein Bild in eine PDF-Datei ein.
type: docs
weight: 10
url: /de/net/programming-with-images/add-image/
---
In dieser Anleitung erfahren Sie Schritt für Schritt, wie Sie mit Aspose.PDF für .NET ein Bild in eine PDF-Datei einfügen. Stellen Sie sicher, dass Sie Ihre Umgebung bereits eingerichtet haben, und führen Sie die folgenden Schritte aus:

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

 Wir erstellen nun eine`Rectangle` Objekt und a`Matrix`Objekt. Das Rechteck stellt die Position und Größe des Bildes dar, während die Matrix definiert, wie das Bild platziert werden soll.

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lower

LeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
```

## Schritt 9: Verketten Sie die Matrix für die Bildplatzierung

 Um anzugeben, wie das Bild im Rechteck platziert werden soll, verwenden wir die`ConcatenateMatrix` Operator. Dieser Operator definiert die Transformationsmatrix, die den Koordinatenraum des Bildes dem Koordinatenraum der Seite zuordnet.

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
//Rufen Sie die Seite auf, auf der das Bild hinzugefügt werden muss
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
// Mit dem ConcatenateMatrix-Operator (Verkettungsmatrix): Definiert, wie das Bild platziert werden muss
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

### FAQs zum Hinzufügen von Bildern in PDF-Dateien

#### F: Warum sollte ich einem PDF-Dokument ein Bild hinzufügen?

A: Durch das Hinzufügen von Bildern zu einem PDF-Dokument können Sie den visuellen Inhalt verbessern, zusätzlichen Kontext bereitstellen oder Logos und Grafiken in Ihre PDF-Dateien einfügen.

#### F: Kann ich Bilder zu bestimmten Seiten innerhalb eines PDF-Dokuments hinzufügen?

A: Ja, Sie können die Seite angeben, auf der Sie das Bild hinzufügen möchten. Im bereitgestellten Code wird das Bild zur zweiten Seite des PDF-Dokuments hinzugefügt.

#### F: Wie kann ich die Position und Größe des hinzugefügten Bildes anpassen?

 A: Sie können das ändern`lowerLeftX`, `lowerLeftY`, `upperRightX` , Und`upperRightY` Variablen im Code, um die Koordinaten des Bildes festzulegen und seine Größe und Position auf der Seite zu steuern.

#### F: Welche Bildformate kann ich mit dieser Methode hinzufügen?

A: Das bereitgestellte Codebeispiel geht davon aus, dass Sie ein JPG-Bild laden (`aspose-logo.jpg`). Aspose.PDF für .NET unterstützt verschiedene Bildformate, darunter PNG, BMP, GIF und mehr.

#### F: Wie stelle ich sicher, dass das hinzugefügte Bild in die angegebenen Koordinaten passt?

 A: Stellen Sie sicher, dass Sie die Koordinaten und die Größe anpassen`Rectangle` Objekt (`rectangle`), um die Abmessungen des Bildes und die gewünschte Platzierung auf der Seite anzupassen.

#### F: Kann ich einer einzelnen PDF-Seite mehrere Bilder hinzufügen?

A: Ja, Sie können einer einzelnen PDF-Seite mehrere Bilder hinzufügen, indem Sie den Vorgang für jedes Bild wiederholen und die Koordinaten und andere Parameter entsprechend anpassen.

####  F: Wie funktioniert das?`GSave` and `GRestore` operator work in the code?

 A: Die`GSave` Der Operator speichert den aktuellen Grafikstatus, sodass Sie Änderungen vornehmen können, ohne den gesamten Grafikkontext zu beeinträchtigen. Der`GRestore` Der Operator stellt den vorherigen Grafikstatus wieder her, nachdem Änderungen vorgenommen wurden.

#### F: Was passiert, wenn die Bilddatei im angegebenen Pfad nicht gefunden wird?

A: Wenn die Bilddatei im angegebenen Pfad nicht gefunden wird, löst der Code beim Versuch, den Bildstream zu laden, eine Ausnahme aus. Stellen Sie sicher, dass sich die Bilddatei im richtigen Verzeichnis befindet.

#### F: Kann ich die Bildplatzierung und das Erscheinungsbild weiter anpassen?

 A: Ja, Sie können das Erscheinungsbild des Bildes anpassen, indem Sie das ändern`Matrix`Objekt und Anpassen anderer Operatoren innerhalb des Codes. Informationen zur erweiterten Anpassung finden Sie in der Aspose.PDF-Dokumentation.

#### F: Wie kann ich testen, ob das Bild erfolgreich zum PDF hinzugefügt wurde?

A: Nachdem Sie den bereitgestellten Code zum Hinzufügen des Bildes angewendet haben, öffnen Sie die geänderte PDF-Datei und überprüfen Sie, ob das Bild auf der angegebenen Seite mit der richtigen Platzierung angezeigt wird.

#### F: Hat das Hinzufügen von Bildern Auswirkungen auf den Originalinhalt des PDF-Dokuments?

A: Das Hinzufügen von Bildern hat keinen Einfluss auf den Originalinhalt des PDF-Dokuments. Es wertet das Dokument durch die Einbeziehung visueller Elemente auf.