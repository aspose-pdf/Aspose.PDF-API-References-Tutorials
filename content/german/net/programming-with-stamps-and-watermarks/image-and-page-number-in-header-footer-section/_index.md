---
title: Bild und Seitenzahl im Kopf- und Fußzeilenbereich
linktitle: Bild und Seitenzahl im Kopf- und Fußzeilenbereich
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose ein Bild und eine Seitenzahl in die Kopf- und Fußzeile eines PDF-Dokuments einfügen.
type: docs
weight: 110
url: /de/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section/
---
In diesem Tutorial zeigen wir Ihnen Schritt für Schritt, wie Sie mit Aspose.PDF für .NET ein Bild und eine Seitenzahl in den Kopf- und Fußzeilenbereich eines PDF-Dokuments einfügen. Wir zeigen Ihnen, wie Sie den bereitgestellten C#-Quellcode verwenden, um eine Seite zu erstellen, Kopf- und Fußzeilen festzulegen, Bilder zur Kopfzeile und Text mit Seitenzahl zur PDF-Dokumentfußzeile hinzuzufügen.

## Schritt 1: Einrichten der Umgebung

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Eine installierte .NET-Entwicklungsumgebung.
- Die Aspose.PDF-Bibliothek für .NET wurde heruntergeladen und in Ihrem Projekt referenziert.

## Schritt 2: Erstellen des PDF-Dokuments und der Seite

Der erste Schritt besteht darin, ein neues Dokumentobjekt und eine Seite im PDF-Dokument zu erstellen. Hier ist wie:

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Erstellen Sie ein neues Document-Objekt
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Erstellen Sie eine Seite im Dokument
Aspose.Pdf.Page page = doc.Pages.Add();
```

Der obige Code erstellt ein neues Document-Objekt und eine leere Seite im PDF-Dokument.

## Schritt 3: Den Header mit einem Bild hinzufügen

Nachdem die Seite nun erstellt ist, können wir einen Kopfzeilenabschnitt mit einem Bild hinzufügen. Hier ist wie:

```csharp
// Erstellen Sie einen Header-Bereich
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Legen Sie den Seitenkopf fest
page. Header = header;

// Erstellen Sie ein Bildobjekt
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Bildpfad festlegen
image1.File = dataDir + "aspose-logo.jpg";

// Fügen Sie das Bild zum Seitenkopf des PDF-Dokuments hinzu
header.Paragraphs.Add(image1);
```

Der obige Code erstellt einen Kopfzeilenabschnitt, legt die Seitenkopfzeile mit diesem Abschnitt fest und fügt der Kopfzeile ein Bild hinzu.

## Schritt 4: Fügen Sie die Fußzeile mit der Seitenzahl hinzu

Nachdem die Kopfzeile hinzugefügt wurde, können wir einen Fußzeilenabschnitt mit einer Seitenzahl hinzufügen. Hier ist wie:

```csharp
// Erstellen Sie einen Fußzeilenbereich
Aspose.Pdf.HeaderFooter footer = new Aspose.Pdf.HeaderFooter();

// Definieren Sie die Fußzeile des PDF-Dokuments
page. Footer = footer;

// Erstellen Sie ein TextFragment-Objekt
Aspose.Pdf.Text.TextFragment txt = new Aspose.Pdf.Text.TextFragment("Page: ($p of $P)");

// Fügen Sie den Text mit der Seitenzahl in die Fußzeile des PDF-Dokuments ein
footer.Paragraphs.Add(txt);
```

Der obige Code erstellt einen Fußzeilenabschnitt, legt die Fußzeile der Seite mit diesem Abschnitt fest und fügt ein TextFragment hinzu, das den Text „Seite: ($p von $P)“ enthält.

  Hier wird die Seitenzahl angezeigt.

## Schritt 5: Speichern des geänderten PDF-Dokuments

Sobald die Kopf- und Fußzeile hinzugefügt sind, können wir das geänderte PDF-Dokument speichern. Hier ist wie:

```csharp
// Speichern Sie das geänderte PDF-Dokument
doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");
```

Der obige Code speichert das bearbeitete PDF-Dokument im angegebenen Verzeichnis.

### Beispielquellcode für Bild und Seitennummer im Kopf- und Fußbereich mit Aspose.PDF für .NET 
```csharp

// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Erstellen Sie eine Seite im Dokumentobjekt
Aspose.Pdf.Page page = doc.Pages.Add();

// Erstellen Sie einen Kopfabschnitt des Dokuments
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Legen Sie den Header für die PDF-Datei fest
page.Header = header;

// Erstellen Sie ein Bildobjekt auf der Seite
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Legen Sie den Pfad der Bilddatei fest
image1.File = dataDir + "aspose-logo.jpg";

// Bild zur Kopfzeile der PDF-Datei hinzufügen
header.Paragraphs.Add(image1);

//Erstellen Sie einen Fußzeilenabschnitt des Dokuments
Aspose.Pdf.HeaderFooter footer = new Aspose.Pdf.HeaderFooter();

// Legen Sie die Fußzeile der PDF-Datei fest
page.Footer = footer;

// Erstellen Sie ein Textobjekt
Aspose.Pdf.Text.TextFragment txt = new Aspose.Pdf.Text.TextFragment("Page: ($p of $P ) ");

// Fügen Sie Text zum Kopfzeilenabschnitt der PDF-Datei hinzu
footer.Paragraphs.Add(txt);

// Speichern Sie die PDF-Datei
doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");

```

## Abschluss

Herzlichen Glückwunsch! Sie haben gelernt, wie Sie mit Aspose.PDF für .NET ein Bild und eine Seitenzahl in den Kopf- und Fußzeilenbereich eines PDF-Dokuments einfügen. Jetzt können Sie diese Methode verwenden, um Kopf- und Fußzeilen in Ihren PDF-Dokumenten anzupassen.

### FAQs

#### F: Welchen Zweck hat das Hinzufügen eines Bildes und einer Seitenzahl im Kopf- und Fußzeilenbereich eines PDF-Dokuments?

A: Das Hinzufügen eines Bildes und einer Seitenzahl im Kopf- und Fußzeilenbereich eines PDF-Dokuments kann seine visuelle Attraktivität, sein Branding und seine Navigationselemente verbessern. Ein Bild kann ein Logo, ein Wasserzeichen oder ein beliebiges grafisches Element darstellen, während eine Seitenzahl Benutzern hilft, ihren Fortschritt zu verfolgen und bestimmte Seiten zu finden.

#### F: Wie hilft der bereitgestellte C#-Quellcode beim Hinzufügen eines Bildes und einer Seitenzahl zur Kopf- und Fußzeile eines PDF-Dokuments?

A: Der bereitgestellte Code zeigt, wie man ein PDF-Dokument erstellt, eine Seite hinzufügt und dann die Kopf- und Fußzeilenabschnitte anpasst. Es zeigt, wie man ein Bild zur Kopfzeile und ein Textfragment mit Seitennummerierung zur Fußzeile hinzufügt.

#### F: Kann ich ein beliebiges Bildformat für den Header verwenden und wie gebe ich dessen Pfad an?

 A: Ja, Sie können für das Headerbild verschiedene Bildformate (z. B. JPEG, PNG, GIF usw.) verwenden. Der Pfad des Bildes wird mit angegeben`File` Eigentum der`Aspose.Pdf.Image` Objekt.

#### F: Wie kann ich das Erscheinungsbild und die Positionierung des Bildes im Kopfbereich anpassen?

 A: Sie können das Erscheinungsbild und die Positionierung des Bildes anpassen, indem Sie die Eigenschaften anpassen`Aspose.Pdf.Image` Objekt, bevor Sie es zum Header-Abschnitt hinzufügen. Sie können beispielsweise die Abmessungen, die Ausrichtung, die Drehung, die Deckkraft usw. des Bildes festlegen.

####  F: Was ist der Zweck des`TextFragment` object used for the footer?

 A: Die`TextFragment` Das Objekt wird zum Erstellen und Formatieren von Text verwendet, der im Fußzeilenbereich angezeigt wird. Im bereitgestellten Code wird es verwendet, um die Seitenzahl und die Gesamtseitenzahl anzuzeigen.

#### F: Kann ich den Fußzeilentext ändern, um zusätzliche Informationen oder Formatierungen hinzuzufügen?

 A: Ja, Sie können den Fußzeilentext ändern, indem Sie den Inhalt des ändern`TextFragment` Objekt. Sie können zusätzlichen Text hinzufügen, Schriftarten, Farben und Formatierungen entsprechend Ihren Anforderungen ändern.

#### F: Kann ich unterschiedliche Kopf- und Fußzeileninhalte auf verschiedene Seiten des PDF-Dokuments anwenden?

 A: Ja, Sie können unterschiedliche Kopf- und Fußzeileninhalte auf verschiedene Seiten anwenden, indem Sie separate Seiten erstellen`HeaderFooter` Objekte und deren Zuordnung zu bestimmten Seiten mithilfe der`Header` Und`Footer` Eigenschaften der`Aspose.Pdf.Page` Objekt.

#### F: Wie kann ich die Kopf- und Fußzeile weiter anpassen, z. B. den Schriftstil ändern oder zusätzliche Elemente hinzufügen?

A: Sie können die Kopf- und Fußzeile anpassen, indem Sie verschiedene Klassen und Eigenschaften verwenden, die von Aspose.PDF für .NET bereitgestellt werden. Sie können beispielsweise verschiedene Textformatierungsoptionen verwenden und den Kopf- und Fußzeilenabschnitten weitere Absätze, Bilder oder sogar Tabellen hinzufügen.

#### F: Kann ich bei Bedarf die Kopf- und Fußzeilenabschnitte entfernen oder löschen?

A: Ja, Sie können die Kopf- und Fußzeilenabschnitte entfernen oder löschen, indem Sie festlegen`Header` Und`Footer` Eigenschaften der`Aspose.Pdf.Page` widersprechen`null`.

#### F: Wie kann ich sicherstellen, dass das hinzugefügte Bild und die Seitenzahl auf verschiedenen Geräten und Betrachtern konsistent bleiben?

A: Aspose.PDF für .NET bietet Funktionen zum Erstellen standardisierter und konsistenter PDF-Dokumente und stellt sicher, dass das hinzugefügte Bild und die Seitenzahl auf verschiedenen Geräten und PDF-Viewern konsistent angezeigt werden.