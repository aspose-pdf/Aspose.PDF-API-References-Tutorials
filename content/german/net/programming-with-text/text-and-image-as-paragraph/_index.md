---
title: Text und Bild als Absatz in PDF-Datei
linktitle: Text und Bild als Absatz in PDF-Datei
second_title: Aspose.PDF für .NET API-Referenz
description: Erstellen Sie PDFs mit Text und Bildern mit Aspose.PDF für .NET. Erfahren Sie Schritt für Schritt, wie Sie Text und Inline-Bilder hinzufügen.
type: docs
weight: 530
url: /de/net/programming-with-text/text-and-image-as-paragraph/
---
## Einführung

In der heutigen digitalen Welt sind PDFs ein universelles Dokumentformat, mit dem die meisten von uns täglich zu tun haben. Ob Bericht, eBook oder Geschäftsrechnung – PDFs erleichtern den Informationsaustausch über verschiedene Plattformen hinweg. Aber was, wenn Sie eine PDF-Datei programmgesteuert anpassen möchten? Hier kommt Aspose.PDF für .NET ins Spiel. In diesem Tutorial führen wir Sie durch das Einfügen von Text und Bildern als Inline-Absätze in eine PDF-Datei mit Aspose.PDF für .NET.

## Voraussetzungen

Bevor wir uns in den Code vertiefen, stellen wir sicher, dass Sie alles haben, was Sie brauchen, um reibungslos mitmachen zu können:

-  Aspose.PDF für .NET-Bibliothek: Sie müssen Aspose.PDF für .NET installieren. Sie können es herunterladen[Hier](https://releases.aspose.com/pdf/net/).
- Visual Studio: Jede Version, die .NET unterstützt, funktioniert einwandfrei.
- Grundlegende Kenntnisse in C#: Einige Kenntnisse in C# sind hilfreich, aber keine Sorge – ich werde Sie durch jeden Schritt führen!
- PDF-Dokument bereit: Wenn Sie ein benutzerdefiniertes Bild hinzufügen möchten, halten Sie es bereit.

 Sie können auch eine kostenlose Testversion der Bibliothek erhalten[Hier](https://releases.aspose.com/) , oder wenn Sie an einem Großprojekt arbeiten, sollten Sie den Kauf in Erwägung ziehen[Hier](https://purchase.aspose.com/buy) . Benötigen Sie weitere Informationen? Lesen Sie die Dokumentation[Hier](https://reference.aspose.com/pdf/net/).

## Pakete importieren

Um mit Aspose.PDF für .NET zu beginnen, müssen Sie die erforderlichen Namespaces importieren. Diese Namespaces ermöglichen Ihrem C#-Code die Interaktion mit Aspose.PDF-Funktionen.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Facades;
using System;
```

Einfach, oder? Jetzt kommen wir zum spaßigen Teil – dem Erstellen Ihrer eigenen PDF-Datei.

## Schritt-für-Schritt-Anleitung: Erstellen eines PDF mit Text und Inline-Bild

Lassen Sie uns dies in leicht verständliche, einfach zu befolgende Schritte unterteilen. Stellen Sie sich vor, Sie setzen ein Puzzle zusammen. Jeder Schritt ist wie das Finden und Platzieren des richtigen Teils.

## Schritt 1: Initialisieren Sie das PDF-Dokument

Der erste Schritt besteht darin, ein neues PDF-Dokument mit Aspose.PDF zu initialisieren. Dieses Dokument dient als Grundlage für das Hinzufügen von Text und Bildern.

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokumentinstanz instantiieren
Document doc = new Document();
```

 Was passiert hier? Wir erstellen einfach ein neues Dokument mit dem`Document`Klasse und definieren Sie das Verzeichnis, in dem Sie die PDF-Datei speichern möchten. Es ist, als würden Sie eine neue Leinwand für Ihr Meisterwerk öffnen!

## Schritt 2: Fügen Sie Ihrer PDF-Datei eine Seite hinzu

Ein Dokument ohne Seiten ist nicht sehr nützlich, oder? Fügen wir Ihrem Dokument eine leere Seite hinzu.

```csharp
// Seite zur Seitensammlung der Dokumentinstanz hinzufügen
Page page = doc.Pages.Add();
```

Dieser Codeausschnitt fügt der Seitensammlung Ihres Dokuments eine neue Seite hinzu. Stellen Sie es sich so vor, als würden Sie eine leere Seite in einem Notizbuch aufschlagen.

## Schritt 3: Text als Absatz hinzufügen

Als Nächstes fügen wir einen Textabsatz hinzu. Hier können Sie Ihre Nachricht oder Überschrift einfügen.

```csharp
// TextFragment erstellen
TextFragment text = new TextFragment("Hello World.. ");
// Textfragment zur Absatzsammlung des Seitenobjekts hinzufügen
page.Paragraphs.Add(text);
```

 Hier erstellen wir eine`TextFragment` Objekt, das den Text „Hallo Welt...“ enthält, der dann als Absatz zur Seite hinzugefügt wird. Es ist, als würden Sie den ersten Satz in Ihr PDF-Dokument schreiben.

## Schritt 4: Fügen Sie ein Bild als Inline-Absatz hinzu

Jetzt, da wir den Text haben, wollen wir ihn aufpeppen, indem wir ein Bild als Inline-Absatz hinzufügen. Ein Inline-Absatz bedeutet einfach, dass das Bild direkt nach dem Text erscheint, ähnlich wie Bilder in Word-Dokumenten angezeigt werden.

```csharp
// Erstellen einer Imageinstanz
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
// Stellen Sie das Bild als Inline-Absatz ein, sodass es direkt danach erscheint
// Das vorherige Absatzobjekt (TextFragment)
image.IsInLineParagraph = true;
// Bilddateipfad angeben
image.File = dataDir + "aspose-logo.jpg";
```

 In diesem Snippet erstellen wir ein`Image` Objekt, weisen Sie es an, es inline mit dem Text auszurichten, und geben Sie den Pfad zur Bilddatei an. Dies entspricht dem Einfügen eines Bilds direkt nach einem Satz in ein Dokument. Sie können „aspose-logo.jpg“ durch Ihr gewünschtes Bild ersetzen.

## Schritt 5: Bildgröße festlegen (optional)

Möchten Sie die Größe des Bildes ändern? Kein Problem. Aspose.PDF bietet Ihnen die Möglichkeit, die Höhe und Breite des Bildes anzupassen, bevor Sie es Ihrem Dokument hinzufügen.

```csharp
// Bildhöhe festlegen (optional)
image.FixHeight = 30;
// Bildbreite festlegen (optional)
image.FixWidth = 100;
```

Dieser Teil ist optional, aber er hilft Ihnen dabei, zu steuern, wie groß oder klein das Bild in Ihrer PDF-Datei erscheint. Es ist, als würden Sie die Größe eines Fotos vor dem Ausdrucken ändern.

## Schritt 6: Bild zur Absatzsammlung hinzufügen

Wir haben das Bild vorbereitet. Jetzt fügen wir es als Inline-Absatz in das Dokument ein.

```csharp
// Bild zur Absatzsammlung des Seitenobjekts hinzufügen
page.Paragraphs.Add(image);
```

Diese Zeile fügt das Bild direkt nach dem Text in die Absatzsammlung ein. Das ist so, als ob Sie in einem Texteditor auf die Schaltfläche „Bild einfügen“ klicken.

## Schritt 7: Einen weiteren Inline-Textabsatz hinzufügen

Was ist, wenn Sie direkt nach dem Bild weiteren Text hinzufügen möchten? Lassen Sie uns das tun, indem wir ein weiteres Inline-Textfragment einfügen.

```csharp
// TextFragment-Objekt mit anderem Inhalt neu initialisieren
text = new TextFragment(" Hello Again..");
// TextFragment als Inline-Absatz festlegen
text.IsInLineParagraph = true;
// Neu erstelltes TextFragment zur Absatzsammlung der Seite hinzufügen
page.Paragraphs.Add(text);
```

 Wir verwenden die`TextFragment`Objekt hier mit neuem Text („Hallo nochmal...“) und fügen Sie ihn direkt nach dem Bild ein. Dadurch erhält Ihr PDF ein fließendes, einheitliches Aussehen.

## Schritt 8: Speichern Sie das PDF-Dokument

Wir sind fast fertig! Jetzt speichern wir das Dokument im angegebenen Verzeichnis.

```csharp
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nText and image added successfully as inline paragraphs.\nFile saved at " + dataDir);
```

Dieser letzte Schritt speichert die Datei in Ihrem Verzeichnis unter dem Namen „TextAndImageAsParagraph_out.pdf“. Herzlichen Glückwunsch – Sie haben eine PDF-Datei mit Text und Inline-Bildern erstellt!

## Abschluss

Und da haben Sie es – das Erstellen einer PDF-Datei mit Text und Bildern als Inline-Absätze mit Aspose.PDF für .NET ist so einfach wie das Befolgen dieser Schritte. Mit nur wenigen Codezeilen können Sie Ihren PDF-Dateien dynamische Inhalte hinzufügen und sie optisch ansprechender und professioneller gestalten. Ob für einen Geschäftsbericht oder ein eBook, die Kontrolle über das Layout Ihrer PDFs kann einen großen Unterschied machen.

## Häufig gestellte Fragen

### Kann ich mehrere Bilder als Inline-Absätze hinzufügen?  
 Ja, Sie können mehrere Bilder hinzufügen, indem Sie separate`Image` -Objekte und deren Hinzufügen zur Absatzsammlung.

### Kann ich die Position von Text und Bild im PDF steuern?  
Ja, mithilfe von Eigenschaften wie Rändern können Sie die genaue Platzierung Ihres Textes und Ihrer Bilder steuern.

### Ist Aspose.PDF für .NET kostenlos?  
 Nein, es ist ein lizenziertes Produkt, aber Sie können eine[Kostenlose Testversion](https://releases.aspose.com/) oder eine Lizenz kaufen[Hier](https://purchase.aspose.com/buy).

### Kann ich dem Text Hyperlinks hinzufügen?  
 Ja, Aspose.PDF ermöglicht es Ihnen, Hyperlinks in Textfragmente einzufügen. Überprüfen Sie die[Dokumentation](https://reference.aspose.com/pdf/net/) für weitere Details.

### Kann ich die Schriftart und den Stil des Textes anpassen?  
Auf jeden Fall! Sie können Schriftarten, Farben und andere Stileigenschaften der Textfragmente problemlos anpassen.