---
title: Mehrschichtige PDF-Datei erstellen – Zweiter Ansatz
linktitle: Mehrschichtige PDF-Datei erstellen – Zweiter Ansatz
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET ein mehrschichtiges PDF erstellen. Folgen Sie unserer Schritt-für-Schritt-Anleitung, um Ihrer PDF-Datei mühelos Text, Bilder und Ebenen hinzuzufügen.
type: docs
weight: 80
url: /de/net/programming-with-document/createmultilayerpdfsecondapproach/
---
## Einführung

In der heutigen Welt digitaler Dokumente ist die Möglichkeit, professionelle PDFs mit Ebenen zu erstellen, unglaublich wertvoll. Egal, ob Sie Wasserzeichen hinzufügen, Text über Bilder einfügen oder komplexe Layouts erstellen, Sie benötigen eine robuste Lösung, die Ihnen die volle Kontrolle über Ihre PDF-Ebenen gibt. Aspose.PDF für .NET ist ein leistungsstarkes Tool, das diesen Prozess reibungslos und unkompliziert macht.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

-  Aspose.PDF für .NET-Bibliothek: Wenn Sie es noch nicht installiert haben, laden Sie die[neueste Version hier](https://releases.aspose.com/pdf/net/).
- .NET-Entwicklungsumgebung: Sie können Visual Studio oder jede andere IDE verwenden, die .NET unterstützt.
- Grundlegende Kenntnisse in C#: Sie sollten mit der C#-Programmierung vertraut sein, um folgen zu können.
- Eine Testbilddatei: Sie benötigen eine Bilddatei (z. B. „test_image.png“) zur Verwendung in diesem Tutorial.

 Wenn Sie noch keine Aspose.PDF für .NET-Lizenz haben, können Sie eine[vorläufige Lizenz](https://purchase.aspose.com/temporary-license/) Weitere Ressourcen finden Sie im[Dokumentation](https://reference.aspose.com/pdf/net/) oder greifen Sie zu[Unterstützung](https://forum.aspose.com/c/pdf/10).

## Erforderliche Pakete importieren

 Um mit der Erstellung Ihres mehrschichtigen PDFs zu beginnen, müssen Sie die entsprechenden Namespaces importieren. Diese Pakete ermöglichen die Verwendung aller erforderlichen Klassen, wie z. B.`Document`, `Page`, `TextFragment` , Und`FloatingBox`.

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

Nachdem die Voraussetzungen nun erfüllt sind, kommen wir zum Hauptteil: dem Erstellen einer mehrschichtigen PDF-Datei.

Diese Anleitung führt Sie detailliert und anfängerfreundlich durch jeden Schritt. Also krempeln wir die Ärmel hoch und legen los!

## Schritt 1: Initialisieren Sie das Dokument und richten Sie den Pfad ein

Als Erstes benötigen wir ein PDF-Dokumentobjekt und eine Möglichkeit, auf den Speicherort unserer endgültigen PDF-Datei zu verweisen.

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

 In diesem Snippet haben wir ein`Document` Objekt, das unser PDF darstellt. Das`dataDir` Die Variable sollte auf das Verzeichnis eingestellt werden, in dem Sie Ihre generierte PDF-Datei speichern möchten.

## Schritt 2: Fügen Sie Ihrem PDF-Dokument eine Seite hinzu

Jedes PDF-Dokument besteht aus einer oder mehreren Seiten. Fügen wir unserem Dokument eine Seite hinzu.

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

Dieser Code fügt dem Dokument eine leere Seite hinzu. Ziemlich unkompliziert, oder? Fahren wir nun mit dem Hinzufügen von Ebenen zu dieser Seite fort.

## Schritt 3: Erstellen und Anpassen eines Textfragments

Als Nächstes erstellen wir ein Textfragment. Dies ist ein Textblock, den wir hinsichtlich Farbe, Größe und Positionierung bearbeiten können.

```csharp
Aspose.Pdf.Text.TextFragment t1 = new Aspose.Pdf.Text.TextFragment("paragraph 3 segment");
t1.TextState.ForegroundColor = Color.Red;
t1.IsInLineParagraph = true;
t1.TextState.FontSize = 12;
```

Folgendes ist passiert:
-  Der`TextFragment` Objekt`t1` wird mit dem Text „Absatz 3 Segment“ initialisiert.
-  Wir ändern die Textfarbe in Rot mit dem`ForegroundColor` Eigentum.
-  Die Textgröße ist auf 12 Punkte eingestellt und der Text wird in der Zeile des Absatzes positioniert mit`IsInLineParagraph`.

## Schritt 4: Fügen Sie das Textfragment zu einer FloatingBox hinzu

 Da wir nun ein Textfragment haben, müssen wir es in das PDF einfügen. Anstatt es direkt auf der Seite einzufügen, verwenden wir ein`FloatingBox` um ihm einen bestimmten Ort zuzuweisen.

```csharp
Aspose.Pdf.FloatingBox TextFloatingBox1 = new Aspose.Pdf.FloatingBox(117, 21);
TextFloatingBox1.ZIndex = 1;
TextFloatingBox1.Left = -4;
TextFloatingBox1.Top = -4;
page.Paragraphs.Add(TextFloatingBox1);
TextFloatingBox1.Paragraphs.Add(t1);
```

Lassen Sie uns das aufschlüsseln:
-  Wir schaffen eine`FloatingBox` und definieren Sie seine Größe (117 x 21).
-  Der`ZIndex` -Eigenschaft auf 1 gesetzt ist, was bedeutet, dass dies die unterste Ebene ist.
-  Der`Left` Und`Top` Eigenschaften definieren die genaue Position der Box auf der Seite.
-  Schließlich das Textfragment`t1`wird in die schwebende Box eingefügt, die dann der Seite hinzugefügt wird.

## Schritt 5: Einfügen eines Bildes in eine andere FloatingBox

 Als nächstes fügen wir dem PDF ein Bild hinzu. Genau wie den Text platzieren wir es in einem`FloatingBox`.

```csharp
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = dataDir + "test_image.png";
Aspose.Pdf.FloatingBox ImageFloatingBox = new Aspose.Pdf.FloatingBox(117, 21);
ImageFloatingBox.Left = -4;
ImageFloatingBox.Top = -4;
ImageFloatingBox.ZIndex = 2;
ImageFloatingBox.Paragraphs.Add(image1);
page.Paragraphs.Add(ImageFloatingBox);
```

Hier ist die Aufschlüsselung:
-  Wir schaffen eine`Image` Objekt und weisen Sie der Bilddatei den Pfad zu.
-  Ein neues`FloatingBox` wird für das Bild in derselben Größe wie das schwebende Textfeld erstellt.
-  Die Bild-Schwimmbox wird über die Text-Schwimmbox gelegt, indem man`ZIndex` bis 2.
-  Der`Left` Und`Top` Eigenschaften positionieren das Bild genau dort, wo wir es haben möchten.
- Das Bild wird der schwebenden Box hinzugefügt, die dann der Seite hinzugefügt wird.

## Schritt 6: Speichern Sie das PDF-Dokument

Abschließend speichern wir das neu erstellte Multilayer-PDF im angegebenen Verzeichnis.

```csharp
doc.Save(dataDir + @"Multilayer-2ndApproach_out.pdf");
```

Diese Zeile speichert Ihre PDF-Datei unter dem Namen „Multilayer-2ndApproach_out.pdf“ in Ihrem angegebenen Verzeichnis. Herzlichen Glückwunsch, Sie haben erfolgreich ein mehrschichtiges PDF mit Aspose.PDF für .NET erstellt!

## Abschluss

Das Erstellen einer mehrschichtigen PDF-Datei mit Aspose.PDF für .NET ist sowohl flexibel als auch leistungsstark. Egal, ob Sie Text, Bilder oder andere Elemente überlagern möchten, dieser Ansatz gibt Ihnen die vollständige Kontrolle über die Struktur und Präsentation des Dokuments.

## Häufig gestellte Fragen

### Kann ich mit Aspose.PDF für .NET PDFs mit mehreren Seiten erstellen?  
 Ja, Sie können beliebig viele Seiten hinzufügen, indem Sie anrufen`doc.Pages.Add()` für jede Seite.

### Wie kann ich im PDF weitere Elemente wie Formen oder Anmerkungen übereinander legen?  
 Sie können`FloatingBox` für jede Art von Inhalt, einschließlich Formen, Anmerkungen und sogar Tabellen.

### Welche Bildformate werden von Aspose.PDF für .NET unterstützt?  
Aspose.PDF unterstützt verschiedene Bildformate, darunter PNG, JPEG, GIF und BMP.

### Kann ich die Deckkraft von Elementen im PDF ändern?  
 Ja, Sie können die Deckkraft ändern, indem Sie die`Alpha` Bestandteil der`Color` Objekt.

### Wie kann ich Elemente an andere Positionen im PDF verschieben?  
 Sie können die`Left` Und`Top` Eigenschaften der`FloatingBox` um ein beliebiges Element neu zu positionieren.