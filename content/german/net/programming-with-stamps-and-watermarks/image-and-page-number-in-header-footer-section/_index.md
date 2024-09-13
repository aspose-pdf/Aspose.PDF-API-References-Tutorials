---
title: Bild und Seitenzahl im Kopf- und Fußzeilenbereich
linktitle: Bild und Seitenzahl im Kopf- und Fußzeilenbereich
second_title: Aspose.PDF für .NET API-Referenz
description: In dieser Schritt-für-Schritt-Anleitung erfahren Sie, wie Sie mit Aspose.PDF für .NET der Kopf- und Fußzeile Ihrer PDF-Datei ein Bild und Seitenzahlen hinzufügen.
type: docs
weight: 110
url: /de/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section/
---
## Einführung

Wenn Sie professionelle PDF-Dokumente erstellen möchten, ist die Kontrolle über kleine Details wie Kopf- und Fußzeilen unerlässlich. Sie möchten, dass Ihre Dokumente elegant und gut organisiert aussehen, nicht wahr? Mit Aspose.PDF für .NET können Sie Bilder und Seitenzahlen nahtlos in die Kopf- und Fußzeilenabschnitte Ihres Dokuments einfügen. In diesem Tutorial führen wir Sie durch jeden Schritt, sodass Sie ihn ganz einfach nachvollziehen können.

## Voraussetzungen

Bevor Sie sich in die Einzelheiten dieses Tutorials stürzen, stellen Sie sicher, dass Sie Folgendes geklärt haben:

1. .NET Framework: Auf Ihrem Computer muss eine beliebige Version des .NET Frameworks installiert sein. Falls nicht, können Sie es ganz einfach von der Microsoft-Website herunterladen.
2.  Aspose.PDF für .NET: Da wir Aspose.PDF verwenden werden, stellen Sie sicher, dass es in Ihrem Projekt installiert ist. Sie können eine Testversion herunterladen[Hier](https://releases.aspose.com/pdf/net/).
3. Grundkenntnisse in C#: Wenn Sie mit der grundlegenden C#-Programmierung vertraut sind, werden Sie den Code sicherlich ohne große Mühe verstehen.
4. Eine Bilddatei: Sie benötigen ein Bild, das Sie in die Kopfzeile Ihres PDF-Dokuments einfügen möchten, z. B. ein Logo. Speichern Sie es in einem zugänglichen Verzeichnis. 
5. IDE: Verwenden Sie eine integrierte Entwicklungsumgebung (IDE) Ihrer Wahl, beispielsweise Visual Studio, um mit Ihrem .NET-Projekt zu arbeiten.

Sobald die Voraussetzungen erfüllt sind, können Sie mit der Erstellung einer fantastischen PDF-Datei beginnen!

## Pakete importieren

Um Aspose.PDF für .NET zu verwenden, müssen Sie die erforderlichen Namespaces importieren. Oben in Ihrer C#-Datei würden Sie Folgendes hinzufügen:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Image;
```

Diese Namespaces bieten Ihnen Zugriff auf die Klassen, die zur Bearbeitung von PDF-Dateien erforderlich sind.

Jetzt geht es ans Eingemachte! Folgen Sie diesen Schritten, um Ihr PDF-Dokument zu erstellen und dabei ein Bild in die Kopfzeile und Seitenzahlen in die Fußzeile einzufügen.

## Schritt 1: Legen Sie Ihr Dokumentverzeichnis fest

Jedes gute Projekt beginnt mit der Organisation. Definieren Sie Ihr Dokumentverzeichnis, in dem Sie Ihre Dateien speichern und wo sich Ihr Bild befindet. So geht's:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Denken Sie daran, zu ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad, wo Sie Ihre PDF-Datei speichern möchten und wo Ihr Bild vorhanden ist.

## Schritt 2: Ein neues PDF-Dokument erstellen

Als Nächstes erstellen wir ein neues PDF-Dokument, in dem die ganze Magie passiert:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

An diesem Punkt haben Sie ein leeres PDF-Dokument erstellt. Spannend, nicht wahr?

## Schritt 3: Dem Dokument eine Seite hinzufügen

Bei einem PDF dreht sich alles um Seiten. Fügen wir unserem Dokument eine neue Seite hinzu, und zwar mit:

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

Jetzt haben Sie eine Leinwand, auf der Sie mit dem Design beginnen können!

## Schritt 4: Erstellen Sie den Header-Abschnitt

Ihr Header enthält das Bild (z. B. ein Logo), das Sie anzeigen möchten. Erstellen Sie den Header-Abschnitt mit dem folgenden Code:

```csharp
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();
page.Header = header;
```

Jetzt haben Sie eine Kopfzeile, die Sie anpassen können!

## Schritt 5: Fügen Sie der Kopfzeile ein Bild hinzu

Jetzt kommen wir zum spaßigen Teil! Sie müssen das Bild zu Ihrer Kopfzeile hinzufügen. Erstellen Sie zunächst ein Bildobjekt:

```csharp
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
```

Legen Sie den Dateipfad Ihres Bildes fest:

```csharp
image1.File = dataDir + "aspose-logo.jpg";
```

Fügen Sie abschließend das Bild zu Ihrer Kopfzeile hinzu:

```csharp
header.Paragraphs.Add(image1);
```

Herzlichen Glückwunsch! Sie haben gerade ein Bild zu Ihrem PDF-Header hinzugefügt.

## Schritt 6: Erstellen Sie den Fußzeilenabschnitt

Nun arbeiten wir an der Fußzeile. Ähnlich wie beim Kopfzeilenprozess erstellen wir ein Fußzeilenobjekt:

```csharp
Aspose.Pdf.HeaderFooter footer = new Aspose.Pdf.HeaderFooter();
page.Footer = footer;
```

Hier platzieren Sie Ihre Seitenzahl. 

## Schritt 7: Text zur Fußzeile hinzufügen

Erstellen Sie ein Textfragment, das die Seitenzahl enthält:

```csharp
Aspose.Pdf.Text.TextFragment txt = new Aspose.Pdf.Text.TextFragment("Page: ($p of $P ) ");
```

Fügen Sie dann dieses Textfragment zur Fußzeile hinzu:

```csharp
footer.Paragraphs.Add(txt);
```

Sehen Sie, wie einfach das war? Sie haben Ihre Seitenzahl dynamisch festgelegt!

## Schritt 8: Speichern Sie das PDF-Dokument

Der letzte Schritt unseres Abenteuers ist das Speichern des Dokuments. Verwenden Sie diesen Befehl, um Ihr neu erstelltes PDF zu speichern:

```csharp
doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");
```

Und schon ist Ihr PDF fertig und mit einem Kopfzeilenbild und Seitenzahlen in der Fußzeile geladen!

## Abschluss

Und da haben Sie es! Sie haben gerade mit Aspose.PDF für .NET ein PDF mit einem Bild in der Kopfzeile und dynamischen Seitenzahlen in der Fußzeile erstellt. Es ist ziemlich unglaublich, wie ein paar Zeilen Code zu einem so ausgefeilten Ergebnis führen können. Ob für einen Unternehmensbericht oder ein personalisiertes Dokument, das Hinzufügen dieser Elemente verändert den Ton und die Professionalität Ihres PDFs.

## Häufig gestellte Fragen

### Kann ich Aspose.PDF auf jeder .NET-Plattform verwenden?
Ja, Aspose.PDF für .NET unterstützt mehrere .NET-Plattformen, darunter .NET Framework, .NET Core und mehr.

### Gibt es eine kostenlose Testversion für Aspose.PDF?
 Auf jeden Fall! Sie können eine kostenlose Testversion herunterladen[Hier](https://releases.aspose.com/).

### Welche Bildformate werden für Kopfzeilen unterstützt?
Aspose.PDF unterstützt die gängigsten Bildformate wie JPG, PNG und BMP für Kopf- und Fußzeilen.

### Kann ich das Seitenzahlenformat anpassen?
Ja, Sie können den Fußzeilentext und das Format ganz einfach Ihren Wünschen entsprechend anpassen.

### Ist technischer Support verfügbar?
 Ja, Aspose bietet dedizierten Support über sein Forum. Sie können um Hilfe bitten[Hier](https://forum.aspose.com/c/pdf/10).