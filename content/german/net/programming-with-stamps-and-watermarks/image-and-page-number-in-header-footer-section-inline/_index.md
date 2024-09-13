---
title: Bild und Seitenzahl im Header-Footer-Bereich Inline
linktitle: Bild und Seitenzahl im Header-Footer-Bereich Inline
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie in dieser Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.PDF für .NET ein Bild und eine Seitenzahl inline in den Kopfbereich einer PDF-Datei einfügen.
type: docs
weight: 120
url: /de/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section-inline/
---
## Einführung

Aspose.PDF für .NET ist ein leistungsstarkes Tool, das umfangreiche Funktionen zum Bearbeiten und Generieren von PDF-Dateien bietet. Egal, ob Sie Bilder hinzufügen, Kopf- und Fußzeilen anpassen oder Text verwalten möchten, Aspose.PDF bietet alles. In diesem Tutorial erfahren Sie, wie Sie ein Bild und eine Seitenzahl inline in die Kopf- oder Fußzeile eines PDF-Dokuments einfügen. Lassen Sie uns direkt eintauchen und den Prozess Schritt für Schritt durchgehen.

## Voraussetzungen

Bevor wir uns in den Code stürzen, stellen wir sicher, dass Sie alles bereit haben, um mitmachen zu können:

-  Aspose.PDF für .NET: Laden Sie die neueste Version von der[Aspose PDF-Download-Seite](https://releases.aspose.com/pdf/net/).
- Entwicklungsumgebung: Sie benötigen eine C#-IDE wie Visual Studio.
-  Lizenz: Wenn Sie noch keine Lizenz haben, können Sie eine[vorläufige Lizenz hier](https://purchase.aspose.com/temporary-license/) oder kaufen Sie ein komplettes Exemplar im[Aspose-Shop](https://purchase.aspose.com/buy).

Nachdem Sie nun die Voraussetzungen erfüllt haben, können wir loslegen.

## Pakete importieren

Bevor Sie mit der Codierung beginnen, stellen Sie sicher, dass Sie die erforderlichen Namespaces importieren:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Diese Pakete ermöglichen Ihnen die Arbeit mit PDF-Dateien und Textbearbeitung.

## Schritt 1: Einrichten des Dokumentverzeichnisses

Als Erstes müssen wir den Pfad zum Verzeichnis definieren, in dem unsere PDF-Datei gespeichert wird. Dieser Pfad kann an den Ordner Ihres Projekts oder an einen beliebigen Speicherort auf Ihrem Computer angepasst werden.

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Diese Variable enthält den Speicherort Ihres Dokuments. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad.

## Schritt 2: Instanziieren des PDF-Dokuments

 In diesem Schritt erstellen wir eine neue Instanz des`Aspose.Pdf.Document` Objekt. Dieses Objekt dient als Rückgrat Ihrer PDF-Datei.

```csharp
// Instanziieren Sie ein Document-Objekt, indem Sie seinen leeren Konstruktor aufrufen
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

Hier erstellen wir eine leere PDF-Datei, die wir später mit Inhalten füllen können.

## Schritt 3: Eine Seite zum PDF hinzufügen

Ihr PDF benötigt mindestens eine Seite, auf der Sie Kopf- und Fußzeilen sowie Inhalt hinzufügen können. Fügen wir unserem Dokument eine leere Seite hinzu.

```csharp
// Erstellen Sie eine Seite im PDF-Objekt
Aspose.Pdf.Page page = pdf1.Pages.Add();
```

 Durch einen Anruf`pdf1.Pages.Add()`dem Dokument wird eine neue Seite hinzugefügt, die zur Anpassung der Kopf- und Fußzeile bereit ist.

## Schritt 4: Erstellen und Festlegen der Kopfzeile

Jetzt ist es an der Zeit, die Kopfzeile für das Dokument zu erstellen. Hier fügen wir Text, Bild und Seitenzahl hinzu.

```csharp
// Kopfzeilenabschnitt des Dokuments erstellen
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();
// Festlegen des Headers für die PDF-Datei
page.Header = header;
```

 Wir schaffen eine`HeaderFooter` Objekt und ordnen Sie es dem`Header` Eigenschaft der Seite, um sicherzustellen, dass alles, was wir der Kopfzeile hinzufügen, oben auf der Seite angezeigt wird.

## Schritt 5: Inline-Text zur Kopfzeile hinzufügen

 Das Hinzufügen von Text ist so einfach wie das Erstellen eines`TextFragment` und geben Sie seine Eigenschaften an. Fügen wir unserer Kopfzeile etwas farbigen Text hinzu.

```csharp
// Erstellen eines Textobjekts
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a Robust component by");
// Geben Sie die Farbe an
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;
```

 In diesem Schritt erstellen wir eine`TextFragment` mit dem Inhalt "Aspose.Pdf ist eine robuste Komponente von" und setzen Sie die Farbe auf blau.`IsInLineParagraph` stellt sicher, dass der Text inline ist, was bedeutet, dass er in derselben Zeile wie die anderen Elemente (wie das Bild und zusätzlicher Text) angezeigt wird.

## Schritt 6: Einfügen eines Inline-Bildes in die Kopfzeile

Um Ihre Kopfzeile optisch ansprechend zu gestalten, können Sie dem Text ein Bild hinzufügen. Dies kann Ihr Firmenlogo oder eine andere Grafik sein.

```csharp
// Erstellen Sie ein Bildobjekt im Abschnitt
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
// Legen Sie den Pfad der Bilddatei fest
image1.File = dataDir + "aspose-logo.jpg";
// Einstellen der Bildbreite Informationen
image1.FixWidth = 50;
image1.FixHeight = 20;
// Geben Sie an, dass der InlineParagraph von seg1 ein Bild ist.
image1.IsInLineParagraph = true;
```

 Hier fügen wir dem Header ein Bild hinzu, indem wir ein`Image` Objekt, legen Sie seinen Pfad fest und passen Sie die Breite und Höhe an.`IsInLineParagraph` stellt sicher, dass das Bild mit dem Text ausgerichtet ist.

## Schritt 7: Fügen Sie zusätzlichen Inline-Text hinzu, um die Kopfzeile zu vervollständigen

Fügen wir noch etwas Text hinzu, um die Inline-Überschrift zu vervollständigen.

```csharp
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);
```

 In diesem Teil erstellen wir einen weiteren`TextFragment` mit dem Inhalt „Pty Ltd.“ und stellen Sie die Farbe auf Kastanienbraun ein. Sowohl Textfragmente als auch das Bild werden der Kopfzeile hinzugefügt.

## Schritt 8: Speichern Sie das PDF

Nachdem Sie die Kopfzeile eingerichtet haben, ist es Zeit, das PDF zu speichern.

```csharp
// Speichern Sie das PDF
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");
```

 Der`Save` Methode schreibt die endgültige PDF-Datei an den angegebenen Speicherort.

## Abschluss

Herzlichen Glückwunsch! Sie haben mit Aspose.PDF für .NET erfolgreich ein Bild und Text zur Kopfzeile eines PDF-Dokuments hinzugefügt. Dieses Tutorial hat Sie durch die wesentlichen Schritte geführt, darunter das Erstellen eines Dokuments, das Hinzufügen von Seiten, das Einfügen von Kopfzeilen und das Platzieren von Inline-Inhalten wie Text und Bildern. Aspose.PDF bietet Ihnen unglaubliche Flexibilität bei der Verwaltung Ihrer PDFs, egal ob Sie Kopfzeilen, Fußzeilen oder komplexe Inhalte bearbeiten. 

## Häufig gestellte Fragen

### Kann ich der Kopfzeile auch eine Seitenzahl hinzufügen?
 Ja! Sie können ganz einfach eine Seitenzahl hinzufügen, indem Sie das`TextFragment` Klasse und formatieren Sie sie nach Bedarf. Fügen Sie sie einfach als Inline-Inhalt in den Header-Abschnitt ein.

### Wie lege ich ein Hintergrundbild im Header fest?
 Sie können die`BackgroundImage` Eigentum der`HeaderFooter` Klasse, um ein Hintergrundbild festzulegen. Dies ist jedoch kein Inline-Inhalt und deckt den gesamten Header-Bereich ab.

### Ist es möglich, neben JPEG auch andere Bildformate zu verwenden?
Absolut! Aspose.PDF unterstützt verschiedene Bildformate wie PNG, BMP und GIF.

### Kann ich die Schriftart des Textes in der Kopfzeile anpassen?
 Ja, Sie können die`TextState`Objekt, um Schriftart, Größe und Stil des Textes zu ändern.

### Benötige ich eine Lizenz, um Aspose.PDF für .NET zu verwenden?
 Ja, Aspose.PDF erfordert eine Lizenz für den Produktionseinsatz, aber Sie können mit einer[kostenlose Testversion hier](https://releases.aspose.com/).