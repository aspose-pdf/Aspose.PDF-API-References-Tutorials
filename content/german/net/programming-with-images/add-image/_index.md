---
title: Bild zur PDF-Datei hinzufügen
linktitle: Bild zur PDF-Datei hinzufügen
second_title: Aspose.PDF für .NET API-Referenz
description: Fügen Sie mit Aspose.PDF für .NET ganz einfach ein Bild zu einer PDF-Datei hinzu.
type: docs
weight: 10
url: /de/net/programming-with-images/add-image/
---
Diese Anleitung führt Sie Schritt für Schritt durch das Hinzufügen eines Bilds zu einer PDF-Datei mit Aspose.PDF für .NET. Stellen Sie sicher, dass Sie Ihre Umgebung bereits eingerichtet haben, und befolgen Sie die folgenden Schritte:

## Schritt 1: Dokumentverzeichnis festlegen

Stellen Sie vor dem Start sicher, dass Sie das richtige Verzeichnis für die Dokumente festgelegt haben. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` im Code durch den Pfad zum Verzeichnis, in dem sich Ihr PDF-Dokument befindet.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Öffnen Sie das Dokument

 In diesem Schritt öffnen wir das PDF-Dokument mit dem`Document` Klasse von Aspose.PDF. Verwenden Sie die`Document` Konstruktor und übergeben Sie den Pfad zum PDF-Dokument.

```csharp
Document pdfDocument = new Document(dataDir + "AddImage.pdf");
```

## Schritt 3: Bildkoordinaten festlegen

 Legen Sie die Koordinaten des Bildes fest, das Sie hinzufügen möchten. Die Variablen`lowerLeftX`, `lowerLeftY`, `upperRightX` Und`upperRightY` stellen jeweils die Koordinaten der unteren linken Ecke und der oberen rechten Ecke des Bildes dar.

```csharp
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;
```

## Schritt 4: Rufen Sie die Seite auf, auf der das Bild hinzugefügt werden soll

Um das Bild einer bestimmten Seite des PDF-Dokuments hinzuzufügen, müssen wir zuerst diese Seite abrufen. In diesem Beispiel fügen wir das Bild der zweiten Seite (Index 1) des Dokuments hinzu.

```csharp
Page page = pdfDocument.Pages[1];
```

## Schritt 5: Laden Sie das Bild aus einem Stream

 Wir laden nun das Bild, das wir dem PDF-Dokument hinzufügen möchten. Dieses Beispiel geht davon aus, dass Sie eine Bilddatei mit dem Namen`aspose-logo.jpg` im selben Verzeichnis wie Ihr Dokument. Ersetzen Sie ggf. den Dateinamen.

```csharp
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
```

## Schritt 6: Bild zu Seitenressourcen hinzufügen

Um das Bild im PDF-Dokument zu verwenden, müssen wir es zur Ressourcenbildsammlung der Seite hinzufügen.

```csharp
page.Resources.Images.Add(imageStream);
```

## Schritt 7: Aktuellen Grafikzustand speichern

 Bevor wir das Bild zeichnen, müssen wir den aktuellen Grafikzustand speichern. Dazu verwenden wir`GSave` Dadurch wird sichergestellt, dass Änderungen am Grafikzustand später rückgängig gemacht werden können.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.GSave());
```

## Schritt 8: Rechteck- und Matrixobjekte erstellen

 Wir erstellen nun eine`Rectangle` Objekt und ein`Matrix` Objekt. Das Rechteck stellt die Position und Größe des Bildes dar, während die Matrix definiert, wie das Bild platziert werden soll.

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lower

LeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
```

## Schritt 9: Matrix zur Bildplatzierung verketten

 Um festzulegen, wie das Bild im Rechteck platziert werden soll, verwenden wir die`ConcatenateMatrix` Operator. Dieser Operator definiert die Transformationsmatrix, die den Koordinatenraum des Bildes auf den Koordinatenraum der Seite abbildet.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(matrix));
```

## Schritt 10: Zeichnen Sie das Bild

 In diesem Schritt zeichnen wir das Bild auf der Seite mit dem`Do` Betreiber. Der`Do`Der Operator übernimmt den Bildnamen aus den Ressourcen und zeichnet ihn auf die Seite.

```csharp
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
page.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
```

## Schritt 11: Grafikzustand wiederherstellen

 Nach dem Zeichnen des Bildes müssen wir den vorherigen Grafikzustand wiederherstellen. Dazu verwenden wir`GRestore` Operator.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.GRestore());
```

## Schritt 12: Speichern Sie das aktualisierte Dokument

 Abschließend speichern wir das aktualisierte Dokument in einer neuen Datei. Aktualisieren Sie die`dataDir` Variable mit dem gewünschten Ausgabeverzeichnis und Dateinamen.

```csharp
dataDir = dataDir + "AddImage_out.pdf";
pdfDocument.Save(dataDir);
```

### Beispielquellcode zum Hinzufügen eines Bilds mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir+ "AddImage.pdf");
// Koordinaten festlegen
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;
// Rufen Sie die Seite auf, auf der das Bild hinzugefügt werden soll
Page page = pdfDocument.Pages[1];
// Bild in Stream laden
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
// Bild zur Bildersammlung der Seitenressourcen hinzufügen
page.Resources.Images.Add(imageStream);
// Verwendung des GSave-Operators: Dieser Operator speichert den aktuellen Grafikstatus
page.Contents.Add(new Aspose.Pdf.Operators.GSave());
// Erstellen von Rechteck- und Matrixobjekten
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
// Verwenden des Operators ConcatenateMatrix (Matrix verketten): Definiert, wie das Bild platziert werden muss
page.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(matrix));
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
// Verwenden des Do-Operators: Dieser Operator zeichnet ein Bild
page.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
// Verwenden des GRestore-Operators: Dieser Operator stellt den Grafikstatus wieder her
page.Contents.Add(new Aspose.Pdf.Operators.GRestore());
dataDir = dataDir + "AddImage_out.pdf";
// Aktualisiertes Dokument speichern
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage added successfully.\nFile saved at " + dataDir); 
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.PDF für .NET ein Bild zu einem PDF-Dokument hinzufügt. Wir haben jeden Schritt im Detail behandelt, vom Öffnen des Dokuments bis zum Speichern der aktualisierten Version. Wenn Sie dieser Anleitung folgen, sollten Sie nun in der Lage sein, Bilder programmgesteuert mit C# und Aspose.PDF in Ihre PDF-Dateien einzubetten.

### FAQs zum Hinzufügen von Bildern zu PDF-Dateien

#### F: Warum sollte ich einem PDF-Dokument ein Bild hinzufügen?

A: Durch das Hinzufügen von Bildern zu einem PDF-Dokument können Sie den visuellen Inhalt verbessern, zusätzlichen Kontext bereitstellen oder Logos und Grafiken in Ihre PDF-Dateien einfügen.

#### F: Kann ich in einem PDF-Dokument bestimmten Seiten Bilder hinzufügen?

A: Ja, Sie können die Seite angeben, auf der Sie das Bild hinzufügen möchten. Im bereitgestellten Code wird das Bild der zweiten Seite des PDF-Dokuments hinzugefügt.

#### F: Wie passe ich die Position und Größe des hinzugefügten Bildes an?

 A: Sie können die`lowerLeftX`, `lowerLeftY`, `upperRightX` , Und`upperRightY` Variablen im Code, um die Koordinaten des Bildes festzulegen und seine Größe und Position auf der Seite zu steuern.

#### F: Welche Bildformate kann ich mit dieser Methode hinzufügen?

A: Das bereitgestellte Codebeispiel geht davon aus, dass Sie ein JPG-Bild laden (`aspose-logo.jpg`). Aspose.PDF für .NET unterstützt verschiedene Bildformate, darunter PNG, BMP, GIF und mehr.

#### F: Wie stelle ich sicher, dass das hinzugefügte Bild innerhalb der angegebenen Koordinaten passt?

 A: Achten Sie darauf, die Koordinaten und die Größe des`Rectangle` Objekt (`rectangle`), um die Abmessungen des Bildes und die gewünschte Platzierung auf der Seite anzupassen.

#### F: Kann ich einer einzelnen PDF-Seite mehrere Bilder hinzufügen?

A: Ja, Sie können einer einzelnen PDF-Seite mehrere Bilder hinzufügen, indem Sie den Vorgang für jedes Bild wiederholen und die Koordinaten und andere Parameter entsprechend anpassen.

####  F: Wie funktioniert das`GSave` and `GRestore` operator work in the code?

 A: Die`GSave` Der Operator speichert den aktuellen Grafikstatus, sodass Sie Änderungen vornehmen können, ohne den gesamten Grafikkontext zu beeinflussen. Der`GRestore` Der Operator stellt den vorherigen Grafikzustand wieder her, nachdem Änderungen vorgenommen wurden.

#### F: Was passiert, wenn die Bilddatei nicht im angegebenen Pfad gefunden wird?

A: Wenn die Bilddatei nicht im angegebenen Pfad gefunden wird, wird beim Versuch, den Bildstream zu laden, eine Ausnahme ausgelöst. Stellen Sie sicher, dass sich die Bilddatei im richtigen Verzeichnis befindet.

#### F: Kann ich die Platzierung und das Erscheinungsbild des Bildes weiter anpassen?

 A: Ja, Sie können das Erscheinungsbild des Bildes anpassen, indem Sie die`Matrix` Objekt und Anpassen anderer Operatoren im Code. Weitere Informationen zur erweiterten Anpassung finden Sie in der Aspose.PDF-Dokumentation.

#### F: Wie kann ich testen, ob das Bild erfolgreich zum PDF hinzugefügt wurde?

A: Nachdem Sie den bereitgestellten Code zum Hinzufügen des Bildes angewendet haben, öffnen Sie die geänderte PDF-Datei und überprüfen Sie, ob das Bild auf der angegebenen Seite an der richtigen Stelle angezeigt wird.

#### F: Hat das Hinzufügen von Bildern Auswirkungen auf den ursprünglichen Inhalt des PDF-Dokuments?

A: Das Hinzufügen von Bildern hat keinen Einfluss auf den ursprünglichen Inhalt des PDF-Dokuments. Es verbessert das Dokument durch die Einbeziehung visueller Elemente.