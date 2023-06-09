---
title: Bild zu PDF
linktitle: Bild zu PDF
second_title: Aspose.PDF für .NET API-Referenz
description: Konvertieren Sie Bilder ganz einfach in PDF mit Aspose.PDF für .NET.
type: docs
weight: 180
url: /de/net/programming-with-images/image-to-pdf/
---

Aspose.PDF für .NET ist eine leistungsstarke Bibliothek, die es Entwicklern ermöglicht, PDF-Dokumente mit C# oder einer beliebigen .NET-Sprache zu erstellen, zu bearbeiten und zu konvertieren. In diesem Tutorial führen wir Sie durch den Prozess der Konvertierung eines Bildes in PDF mit Aspose.PDF für .NET.

## Schritt 1: Einrichten der Umgebung

Bevor wir beginnen, stellen Sie sicher, dass Aspose.PDF für .NET auf Ihrem System installiert ist. Sie können es von der offiziellen Aspose-Website herunterladen und installieren. Erstellen Sie nach der Installation ein neues C#-Projekt in Ihrer bevorzugten Entwicklungsumgebung.

## Schritt 2: Importieren der erforderlichen Bibliotheken

Um Aspose.PDF für .NET in Ihrem Projekt zu verwenden, müssen Sie die erforderlichen Bibliotheken importieren. Fügen Sie am Anfang Ihrer C#-Datei die folgenden using-Anweisungen hinzu:

```csharp
using Aspose.Pdf;
using System.IO;
using System.Drawing;
```

## Schritt 3: Initialisieren des Dokumentobjekts

 Im C#-Code besteht der erste Schritt darin, zu initialisieren`Document` Objekt. Dieses Objekt stellt das PDF-Dokument dar, das wir erstellen werden. Fügen Sie Ihrem Projekt den folgenden Code hinzu:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

 Ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad, in dem Sie die PDF-Datei speichern möchten.

## Schritt 4: Hinzufügen einer Seite zum Dokument

 Als nächstes müssen wir dem Dokument eine Seite hinzufügen. Eine Seite wird durch dargestellt`Page` Klasse. Verwenden Sie den folgenden Code, um dem Dokument eine Seite hinzuzufügen:

```csharp
Page page = doc.Pages.Add();
```

 Dieser Code erstellt eine neue Seite und fügt sie hinzu`Pages` Sammlung des Dokuments.

## Schritt 5: Laden der Bilddatei

 Um ein Bild in PDF zu konvertieren, müssen wir zunächst die Quellbilddatei laden. In diesem Beispiel gehen wir davon aus, dass die Bilddatei benannt ist`aspose-logo.jpg` und befindet sich im selben Verzeichnis wie Ihre C#-Datei. Verwenden Sie den folgenden Code, um die Bilddatei zu laden:

```csharp
FileStream fs = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open, FileAccess.Read);
byte[] tmpBytes = new byte[fs.Length];
fs.Read(tmpBytes, 0, int.Parse(fs.Length.ToString()));
MemoryStream mystream = new MemoryStream(tmpBytes);
```

 Unbedingt austauschen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zur Bilddatei.

## Schritt 6: Ränder und Zuschnittsrahmen festlegen

Bevor wir das Bild zur PDF-Seite hinzufügen, können wir das Seitenlayout anpassen. Beispielsweise können wir die Ränder und den Zuschneiderahmen so einstellen, dass sie zu den Bildabmessungen passen. Verwenden Sie den folgenden Code, um die Seiteneinstellungen anzupassen:

```csharp
Bitmap b = new Bitmap(mystream);
page.PageInfo.Margin.Bottom = 0;
page.PageInfo.Margin.Top = 0;
page.PageInfo.Margin.Left = 0;
page

.PageInfo.Margin.Right = 0;
page.CropBox = new Aspose.Pdf.Rectangle(0, 0, b.Width, b.Height);
```

Diese Einstellungen stellen sicher, dass das Bild ohne zusätzliche Ränder auf die Seite passt.

## Schritt 7: Erstellen eines Bildobjekts

 Jetzt erstellen wir eine`Aspose.Pdf.Image` Objekt zum Speichern der Bilddaten. Fügen Sie Ihrem Projekt den folgenden Code hinzu:

```csharp
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
```

Dieses Objekt stellt das Bild dar, das wir der PDF-Seite hinzufügen möchten.

## Schritt 8: Hinzufügen des Bildes zur Seite

 Um das Bild zur PDF-Seite hinzuzufügen, müssen wir die Bilddaten zuweisen`ImageStream` Eigentum der`Aspose.Pdf.Image`Objekt. Verwenden Sie den folgenden Code, um das Bild hinzuzufügen:

```csharp
image1.ImageStream = mystream;
page.Paragraphs.Add(image1);
```

 Hier weisen wir den Bildstream dem zu`ImageStream` Eigenschaft und fügen Sie dann das Bildobjekt zur hinzu`Paragraphs` Sammlung der Seite.

## Schritt 9: Speichern der PDF-Datei

Sobald wir das Bild zur PDF-Seite hinzugefügt haben, können wir die resultierende PDF-Datei speichern. Verwenden Sie den folgenden Code, um die Datei zu speichern:

```csharp
dataDir = dataDir + "ImageToPDF_out.pdf";
doc.Save(dataDir);
```

 Ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem gewünschten Ausgabeverzeichnis und Dateinamen.

## Schritt 10: Schließen des Speicherstroms

Nach dem Speichern der PDF-Datei ist es wichtig, den Speicherstrom zu schließen, um Systemressourcen freizugeben. Fügen Sie den folgenden Code hinzu, um den Speicherstream zu schließen:

```csharp
mystream. Close();
```

## Ausführen des Codes und Überprüfen der Ausgabe

Sie haben nun die Code-Implementierung abgeschlossen. Führen Sie den Code aus und überprüfen Sie, ob das Bild erfolgreich in PDF konvertiert wurde. Die Ausgabedatei sollte im angegebenen Verzeichnis gespeichert werden.


### Beispielquellcode für Bild zu PDF mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokumentobjekt instanziieren
Document doc = new Document();
// Fügen Sie eine Seite zur Seitensammlung des Dokuments hinzu
Page page = doc.Pages.Add();
//Laden Sie die Quellbilddatei in das Stream-Objekt
FileStream fs = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open, FileAccess.Read);
byte[] tmpBytes = new byte[fs.Length];
fs.Read(tmpBytes, 0, int.Parse(fs.Length.ToString()));
MemoryStream mystream = new MemoryStream(tmpBytes);
// Instanziieren Sie ein BitMap-Objekt mit geladenem Bildstream
Bitmap b = new Bitmap(mystream);
// Legen Sie die Ränder so fest, dass das Bild passt usw.
page.PageInfo.Margin.Bottom = 0;
page.PageInfo.Margin.Top = 0;
page.PageInfo.Margin.Left = 0;
page.PageInfo.Margin.Right = 0;
page.CropBox = new Aspose.Pdf.Rectangle(0, 0, b.Width, b.Height);
// Erstellen Sie ein Bildobjekt
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
// Fügen Sie das Bild zur Absatzsammlung des Abschnitts hinzu
page.Paragraphs.Add(image1);
// Legen Sie den Bilddateistream fest
image1.ImageStream = mystream;
dataDir = dataDir + "ImageToPDF_out.pdf";
// Speichern Sie die resultierende PDF-Datei
doc.Save(dataDir);
// Schließen Sie das MemoryStream-Objekt
mystream.Close();
Console.WriteLine("\nImage converted to pdf successfully.\nFile saved at " + dataDir); 
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.PDF für .NET ein Bild in PDF konvertiert. Wir haben den Schritt-für-Schritt-Prozess behandelt, einschließlich Einrichten der Umgebung, Importieren von Bibliotheken, Initialisieren des Dokumentobjekts, Laden der Bilddatei, Festlegen von Rändern und Zuschneiderahmen, Hinzufügen des Bilds zur Seite, Speichern der PDF-Datei und Schließen der Datei Speicherstrom. Wenn Sie diese Schritte befolgen, können Sie Bilder in Ihren .NET-Anwendungen problemlos in PDF konvertieren.