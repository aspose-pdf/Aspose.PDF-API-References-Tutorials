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

// Erstellen Sie einen Fußzeilenabschnitt des Dokuments
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
