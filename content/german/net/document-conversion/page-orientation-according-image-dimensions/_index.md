---
title: Seitenausrichtung gemäß Bildabmessungen
linktitle: Seitenausrichtung gemäß Bildabmessungen
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Festlegen der Seitenausrichtung basierend auf Bildabmessungen mit Aspose.PDF für .NET.
type: docs
weight: 80
url: /de/net/document-conversion/page-orientation-according-image-dimensions/
---
In diesem Tutorial führen wir Sie durch den Prozess der Festlegung der Seitenausrichtung basierend auf den Abmessungen eines Bildes mithilfe von Aspose.PDF für .NET. Wir durchlaufen eine Liste von JPG-Bildern in einem bestimmten Verzeichnis und passen die Seitenausrichtung automatisch an die Breite jedes Bildes an. Befolgen Sie die folgenden Schritte, um dies zu erreichen.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

- Grundkenntnisse der Programmiersprache C#.
- Aspose.PDF-Bibliothek für .NET auf Ihrem System installiert.
- Eine Entwicklungsumgebung wie Visual Studio.

## Schritt 1: Durchsuchen Sie JPG-Bilder
In diesem Schritt durchsuchen wir alle JPG-Bilder in einem bestimmten Verzeichnis. Befolgen Sie den folgenden Code:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Erstellen Sie ein neues PDF-Dokument
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Rufen Sie die Namen aller JPG-Dateien in einem bestimmten Verzeichnis ab
string[] fileEntries = Directory.GetFiles(dataDir, "*.JPG");
```

 Unbedingt ersetzen`"YOUR DOCUMENTS DIRECTORY"` mit dem tatsächlichen Verzeichnis, in dem sich Ihre JPG-Bilder befinden.

## Schritt 2: Erstellung der Seite und des Bildes
Nachdem wir die JPG-Dateien durchsucht haben, erstellen wir für jede Datei eine Seite und ein Bild. Verwenden Sie den folgenden Code:

```csharp
int counter;
for (counter = 0; counter < fileEntries.Length - 1; counter++)
{
// Erstellen Sie ein Seitenobjekt
Aspose.Pdf.Page page = doc.Pages.Add();

// Erstellen Sie ein Bildobjekt
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = fileEntries[counter];
```

## Schritt 3: Bildabmessungen prüfen
Lassen Sie uns nun die Abmessungen jedes Bildes überprüfen, um die Seitenausrichtung zu bestimmen. Verwenden Sie den folgenden Code:

```csharp
// Erstellen Sie ein BitMap-Objekt, um Informationen aus der Bilddatei abzurufen
Bitmap myimage = new Bitmap(fileEntries[counter]);

// Überprüfen Sie, ob die Breite des Bildes größer als die Breite der Seite ist oder nicht
if (myimage.Width > page.PageInfo.Width)
//

  If the width of the image is greater than the width of the page, set the page orientation to landscape
page.PageInfo.IsLandscape = true;
else
// Wenn die Breite des Bildes geringer ist als die Breite der Seite, stellen Sie die Ausrichtung der Seite auf Hochformat ein
page.PageInfo.IsLandscape = false;
```

## Schritt 4: Hinzufügen des Bildes zum PDF-Dokument
Nachdem wir die Abmessungen des Bildes überprüft haben, fügen wir das Bild der Absatzsammlung des PDF-Dokuments hinzu. Verwenden Sie den folgenden Code:

```csharp
// Fügen Sie das Bild zur Absatzsammlung des PDF-Dokuments hinzu
page.Paragraphs.Add(image1);
```

## Schritt 5: Speichern der PDF-Datei
Nachdem wir alle Bilder zum PDF-Dokument hinzugefügt haben, können wir nun die resultierende PDF-Datei speichern. Hier ist der letzte Schritt:

```csharp
// Speichern Sie die PDF-Datei
doc.Save(dataDir + "SetPageOrientation_out.pdf");
```

 Ersetzen`"YOUR DOCUMENTS DIRECTORY"` mit dem gewünschten Verzeichnis, in dem Sie die ausgegebene PDF-Datei speichern möchten.

### Beispielquellcode für die Seitenausrichtung entsprechend den Bildabmessungen mit Aspose.PDF für .NET

```csharp

// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Rufen Sie die Namen aller JPG-Dateien in einem bestimmten Verzeichnis ab
string[] fileEntries = Directory.GetFiles(dataDir, "*.JPG");

int counter;
for (counter = 0; counter < fileEntries.Length - 1; counter++)
{
	// Erstellen Sie ein Seitenobjekt
	Aspose.Pdf.Page page = doc.Pages.Add();

	// Erstellen Sie ein Bildobjekt
	Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
	image1.File = fileEntries[counter];

	// Erstellen Sie ein BitMap-Objekt, um die Informationen der Bilddatei abzurufen
	Bitmap myimage = new Bitmap(fileEntries[counter]);
	// Überprüfen Sie, ob die Breite der Bilddatei größer als die Seitenbreite ist oder nicht
	if (myimage.Width > page.PageInfo.Width)
		// Wenn die Bildbreite größer als die Seitenbreite ist, stellen Sie die Seitenausrichtung auf Querformat ein
		page.PageInfo.IsLandscape = true;
	else
		// Wenn die Bildbreite kleiner als die Seitenbreite ist, stellen Sie die Seitenausrichtung auf Hochformat ein
		page.PageInfo.IsLandscape = false;
	// Fügen Sie das Bild zur Absatzsammlung des PDF-Dokuments hinzu
	page.Paragraphs.Add(image1);
}
// Speichern Sie die PDF-Datei
doc.Save(dataDir + "SetPageOrientation_out.pdf");
```

## Abschluss
In diesem Tutorial haben wir den Schritt-für-Schritt-Prozess zum Festlegen der Seitenausrichtung basierend auf den Abmessungen eines Bildes mit Aspose.PDF für .NET behandelt. Wenn Sie die oben beschriebenen Anweisungen befolgen, sollten Sie nun in der Lage sein, für jedes Bild ein PDF-Dokument mit der richtigen Seitenausrichtung zu erstellen. Diese Funktion ist nützlich, wenn Sie Bilder unterschiedlicher Größe haben und diese in ein PDF-Dokument einbetten möchten.

### FAQs

#### F: Kann ich anstelle von JPG andere Bildformate verwenden, um die Seitenausrichtung basierend auf den Bildabmessungen festzulegen?

A: Ja, Sie können neben JPG auch andere Bildformate wie PNG, BMP oder GIF verwenden, um die Seitenausrichtung basierend auf den Bildabmessungen festzulegen. Der bereitgestellte Code durchläuft alle Bilddateien mit der Erweiterung „.JPG“, Sie können ihn jedoch ändern, um auch andere Bildformate einzubeziehen.

#### F: Was passiert, wenn die Abmessungen eines Bildes genau der Seitenbreite entsprechen?

A: Wenn die Breite eines Bildes genau der Seitenbreite entspricht, wird die Seitenausrichtung auf Hochformat eingestellt. Im bereitgestellten Code ist die Seitenausrichtung nur dann auf Querformat eingestellt, wenn die Breite des Bildes größer als die Seitenbreite ist.

#### F: Kann ich die Seitenausrichtungslogik basierend auf spezifischen Anforderungen anpassen?

A: Ja, Sie können die Seitenausrichtungslogik basierend auf spezifischen Anforderungen anpassen. Sie können beispielsweise einen Schwellenwert festlegen, um zu bestimmen, wann die Seitenausrichtung auf Quer- oder Hochformat eingestellt werden soll. Darüber hinaus können Sie Faktoren wie Bildhöhe oder Seitenverhältnis berücksichtigen, um die Seitenausrichtung zu bestimmen.

#### F: Kann ich neben den Bildern auch andere Inhalte wie Text oder Tabellen zum PDF-Dokument hinzufügen?

A: Ja, Sie können dem PDF-Dokument neben den Bildern auch andere Inhalte wie Text oder Tabellen hinzufügen. Aspose.PDF für .NET bietet zahlreiche Funktionen zum Bearbeiten von PDF-Dokumenten, einschließlich des Hinzufügens von Text, Bildern, Tabellen und anderen Elementen zu den Seiten.