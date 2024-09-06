---
title: Bild und Seitenzahl im Header-Footer-Bereich Inline
linktitle: Bild und Seitenzahl im Header-Footer-Bereich Inline
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET mithilfe von Inline-Absätzen Bilder und Seitenzahlen in Kopf- und Fußzeilen hinzufügen.
type: docs
weight: 120
url: /de/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section-inline/
---
In diesem Tutorial zeigen wir Ihnen Schritt für Schritt, wie Sie mit Aspose.PDF für .NET Bilder und Seitenzahlen in den Kopf- und Fußzeilenbereich eines PDF-Dokuments einfügen. Wir verwenden den bereitgestellten C#-Quellcode, um eine Seite zu erstellen, Kopf- und Fußzeilen festzulegen und Bilder und Text mithilfe von Inline-Absätzen in die Kopfzeile des PDF-Dokuments einzufügen.

## Schritt 1: Einrichten der Umgebung

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Eine installierte .NET-Entwicklungsumgebung.
- Die Aspose.PDF-Bibliothek für .NET wurde heruntergeladen und in Ihrem Projekt referenziert.

## Schritt 2: Erstellen des PDF-Dokuments und der Seite

Der erste Schritt besteht darin, ein neues Dokumentobjekt und eine Seite im PDF-Dokument zu erstellen. So geht's:

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Erstellen eines neuen Dokumentobjekts
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// Erstellen einer Seite im Dokument
Aspose.Pdf.Page page = pdf1.Pages.Add();
```

Der obige Code erstellt ein neues Dokumentobjekt und eine leere Seite im PDF-Dokument.

## Schritt 3: Hinzufügen der Kopfzeile mit Bild und Inline-Text

Nachdem die Seite nun erstellt ist, können wir mithilfe von Inline-Absätzen einen Kopfbereich mit einem Bild und Text hinzufügen. So geht's:

```csharp
// Erstellen eines Kopfzeilenabschnitts
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Festlegen des Seitenkopfs
page. Header = header;

// Erstellen Sie ein TextFragment-Objekt für den ersten Inline-Text
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a robust component developed by");

// Textfarbe festlegen
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

// Erstellen Sie ein Image-Objekt für das Bild
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Bildpfad festlegen
image1.File = dataDir + "aspose-logo.jpg";

// Definieren Sie die Abmessungen des Bildes
image1.FixWidth = 50;
image1.FixHeight = 20;

// Geben Sie an, dass der erste Inline-Text ein Bild ist
image1.IsInLineParagraph = true;

// Einen zweiten Inline-Text erstellen
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;

// Elemente zur Kopfzeile hinzufügen
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);
```

Der obige Code erstellt einen Kopfzeilenabschnitt, legt mit diesem Abschnitt die Seitenkopfzeile fest und fügt ein TextFragment mit Inline-Text und ein Inline-Bildobjekt hinzu.

## Schritt 4: Speichern des geänderten PDF-Dokuments

Sobald die Kopfzeile mit dem Bild und dem Inline-Text hinzugefügt wurde, können wir das geänderte PDF-Dokument speichern. So geht's:

```csharp
// Speichern Sie das geänderte PDF-Dokument
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");
```

Der obige Code speichert das bearbeitete PDF-Dokument im angegebenen Verzeichnis.

### Beispielquellcode für Bild und Seitenzahl im Kopf- und Fußzeilenbereich Inline unter Verwendung von Aspose.PDF für .NET 
```csharp

// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instanziieren Sie ein Document-Objekt, indem Sie seinen leeren Konstruktor aufrufen
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// Erstellen Sie eine Seite im PDF-Objekt
Aspose.Pdf.Page page = pdf1.Pages.Add();

// Kopfzeilenabschnitt des Dokuments erstellen
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Festlegen des Headers für die PDF-Datei
page.Header = header;

// Erstellen eines Textobjekts
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a Robust component by");

// Geben Sie die Farbe an
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

// Erstellen Sie ein Bildobjekt im Abschnitt
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Legen Sie den Pfad der Bilddatei fest
image1.File = dataDir + "aspose-logo.jpg";

//Einstellen der Bildbreite Informationen
image1.FixWidth = 50;
image1.FixHeight = 20;

// Geben Sie an, dass der InlineParagraph von seg1 ein Bild ist.
image1.IsInLineParagraph = true;
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);

// Speichern Sie das PDF
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");

```

## Abschluss

Herzlichen Glückwunsch! Sie haben gelernt, wie Sie mit Aspose.PDF für .NET mithilfe von Inline-Absätzen ein Bild und eine Seitenzahl in den Kopf- und Fußzeilenbereich eines PDF-Dokuments einfügen. Sie können jetzt die Kopf- und Fußzeile Ihrer PDF-Dokumente flexibel anpassen.

### Häufig gestellte Fragen

#### F: Welchen Vorteil bietet die Verwendung von Inline-Absätzen zum Hinzufügen eines Bilds und Textes zur Kopfzeile eines PDF-Dokuments?

A: Durch die Verwendung von Inline-Absätzen können Sie Bilder und Text nahtlos in denselben Absatz integrieren und haben so eine präzise Kontrolle über deren Platzierung und Formatierung. Diese Methode ist besonders nützlich, um benutzerdefinierte Überschriften mit visuellen Elementen zu erstellen.

#### F: Wie erreicht der bereitgestellte C#-Quellcode Inline-Absätze für die Kopfzeile in einem PDF-Dokument?

A: Der bereitgestellte Code zeigt, wie Sie ein PDF-Dokument erstellen, eine Seite hinzufügen und die Kopfzeile mithilfe von Inline-Absätzen anpassen. Er fügt ein TextFragment mit Inline-Text, ein Inline-Bild und ein weiteres Inline-TextFragment hinzu.

#### F: Wie lege ich die Farbe des Inline-Textes in der Kopfzeile fest?

 A: Die Farbe des Inline-Textes wird über die`ForegroundColor` Eigentum der`TextState` der`TextFragment` Objekt.

#### F: Kann ich die Abmessungen des Inline-Bildes in der Kopfzeile anpassen?

 A: Ja, Sie können die Abmessungen des Inline-Bildes mithilfe der`FixWidth` Und`FixHeight` Eigenschaften der`Image` Objekt. Damit können Sie die Breite und Höhe des Bildes in der Kopfzeile steuern.

#### F: Kann ich zusätzliche Inline-Elemente wie Hyperlinks oder verschiedene Schriftarten in die Kopfzeile einfügen?

 A: Ja, Sie können zusätzliche Inline-Elemente in den Header einfügen, indem Sie weitere`TextFragment` oder`Image` Objekte mit den gewünschten Eigenschaften. Dadurch können Sie die Kopfzeile weiter anpassen, z. B. mit Hyperlinks, verschiedenen Schriftarten oder anderen visuellen Elementen.

#### F: Wie kann ich sicherstellen, dass das Inline-Bild und der Text auf verschiedenen Geräten und in verschiedenen Viewern richtig ausgerichtet und formatiert bleiben?

A: Aspose.PDF für .NET stellt sicher, dass Inline-Bilder und -Text richtig ausgerichtet und formatiert sind, was zu einem einheitlichen Erscheinungsbild auf verschiedenen Geräten und PDF-Viewern führt.

#### F: Kann ich Inline-Absätze auch auf den Fußzeilenbereich anwenden?

 A: Ja, Sie können die gleiche Technik der Verwendung von Inline-Absätzen auch auf den Fußzeilenabschnitt anwenden, indem Sie einen`Footer` Objekt und fügen Sie ihm Inline-Elemente wie Text und Bilder hinzu.

#### F: Ist es möglich, Inline-Absätze mit anderen Methoden zur Anpassung von Kopf- oder Fußzeilen zu kombinieren?

A: Ja, Sie können Inline-Absätze mit anderen von Aspose.PDF für .NET bereitgestellten Methoden zur Kopf- oder Fußzeilenanpassung kombinieren, um komplexere und maßgeschneiderte Kopf- oder Fußzeilendesigns zu erstellen.

#### F: Kann ich die Inline-Elemente bei Bedarf aus der Kopfzeile entfernen oder löschen?

 A: Ja, Sie können die Inline-Elemente entfernen oder löschen, indem Sie den Inhalt des`HeaderFooter`Objekt und Entfernen der entsprechenden Inline-Absätze.

#### F: Wie kann ich Inline-Absätze auf bestimmte Seiten des PDF-Dokuments anwenden?

 A: Um Inline-Absätze auf bestimmte Seiten anzuwenden, können Sie separate`HeaderFooter` Objekte für jede Seite und ordnen Sie diese über die`Header` Eigentum der jeweiligen`Aspose.Pdf.Page` Objekte.