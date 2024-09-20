---
title: Platzieren von Text um das Bild in einer PDF-Datei
linktitle: Platzieren von Text um das Bild in einer PDF-Datei
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Text um Bilder in PDFs platzieren. Folgen Sie unserer Schritt-für-Schritt-Anleitung, um professionelle PDFs mit Bildern und Text nebeneinander zu erstellen.
type: docs
weight: 260
url: /de/net/programming-with-text/placing-text-around-image/
---
## Einführung

Haben Sie schon einmal versucht, Text um ein Bild in einer PDF-Datei zu platzieren, fanden es aber schwierig? Wenn ja, sind Sie hier richtig! Aspose.PDF für .NET vereinfacht diesen Vorgang und ermöglicht es Ihnen, mit nur wenigen Codezeilen Text neben Bildern zu platzieren. Egal, ob Sie Berichte, Dokumente oder Präsentationen erstellen, diese Funktion ist eine fantastische Möglichkeit, das Layout Ihrer Inhalte zu verbessern und sie optisch ansprechender zu gestalten. Heute zeigen wir Ihnen, wie Sie mit Aspose.PDF für .NET Text um Bilder in einem PDF-Dokument platzieren.

## Voraussetzungen

Bevor wir uns in den Code stürzen, stellen wir sicher, dass wir alles eingerichtet haben. Folgendes benötigen Sie:

-  Aspose.PDF für .NET: Sie können es herunterladen von[Hier](https://releases.aspose.com/pdf/net/).
- Visual Studio: Stellen Sie sicher, dass Sie die neueste Version installiert haben, um problemlos weiterarbeiten zu können.
- .NET Framework: Dieses Beispiel verwendet .NET. Stellen Sie daher sicher, dass Ihre Umgebung für die .NET-Entwicklung eingerichtet ist.
-  Eine temporäre Lizenz: Sie können eine temporäre Lizenz anfordern[Hier](https://purchase.aspose.com/temporary-license/) wenn Sie das Produkt bewerten.

Wenn Sie Aspose.PDF für .NET noch nicht eingerichtet haben, folgen Sie den Installationsanweisungen im[Dokumentation](https://reference.aspose.com/pdf/net/).

## Namespaces importieren

Bevor wir mit dem Coden beginnen, müssen wir die erforderlichen Namespaces importieren. Hier ist der Codeausschnitt dazu:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

 Diese Namespaces sind wichtig, da sie Zugriff auf Klassen wie`Document`, `Page`, `Image` , Und`HtmlFragment`, die wir zum Erstellen und Bearbeiten des PDF verwenden.

Nachdem wir nun die Bühne bereitet haben, wollen wir aufschlüsseln, wie Sie mit Aspose.PDF für .NET Text um ein Bild in Ihrer PDF-Datei platzieren. Wir führen Sie Schritt für Schritt durch die Anleitung.

## Schritt 1: Instanziieren des Dokumentobjekts

 Zuerst müssen Sie ein PDF-Dokument erstellen. In Aspose.PDF geschieht dies durch die Instanziierung eines`Document` Objekt. Dieses Objekt dient als Grundlage für alle Inhalte, die wir hinzufügen.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

Hier haben wir ein leeres PDF-Dokument erstellt. Es enthält noch keine Seiten, aber keine Sorge, wir werden im nächsten Schritt eine hinzufügen.

## Schritt 2: Dem Dokument eine Seite hinzufügen

Jetzt, da wir unser Dokument haben, ist es Zeit, eine Seite hinzuzufügen. Stellen Sie sich das so vor, als würden Sie ein leeres Blatt Papier erstellen, auf dem Sie Ihren Inhalt hinzufügen.

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

Dieser Code fügt dem Dokument eine neue Seite hinzu. Standardmäßig ist die Seite leer, aber das werden wir gleich ändern.

## Schritt 3: Erstellen Sie eine Tabelle zum Organisieren von Inhalten

Damit Bild und Text richtig ausgerichtet bleiben, verwenden wir eine Tabelle. Tabellen in PDF-Dateien können Ihnen dabei helfen, Ihr Layout zu strukturieren, ähnlich wie in Word-Dokumenten oder HTML.

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
page.Paragraphs.Add(table1);
```

Dieses Snippet erstellt eine Tabelle und fügt sie der Seite hinzu. Stellen Sie sich die Tabelle als Rahmen für die Ausrichtung Ihres Bildes und Textes vor.

## Schritt 4: Spaltenbreiten für die Tabelle festlegen

Nachdem wir nun eine Tabelle hinzugefügt haben, müssen wir definieren, wie breit die Spalten sein sollen. Dadurch wird sichergestellt, dass Bild und Text auf der Seite die richtige Größe haben.

```csharp
table1.ColumnWidths = "120 270";
```

Diese Zeile legt die Breite von zwei Spalten fest – eine für das Bild und eine für den Text. Passen Sie diese Werte an, wenn Ihr Bild oder Text mehr oder weniger Platz benötigt.

## Schritt 5: Ränder und Polsterung definieren

Um sicherzustellen, dass alles ordentlich aussieht, fügen wir der Tabelle einige Ränder und Polster hinzu.

```csharp
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
table1.DefaultCellPadding = margin;
```

Diese Einstellungen stellen sicher, dass Ihre Tabelle einen einheitlichen Abstand aufweist und der Inhalt optisch ansprechend ist.

## Schritt 6: Einfügen eines Bildes in die Tabelle

Kommen wir nun zum spaßigen Teil – dem Hinzufügen eines Bilds. In diesem Fall fügen wir das Aspose-Logo hinzu, Sie können aber auch jedes beliebige Bild verwenden.

```csharp
Aspose.Pdf.Row row1 = table1.Rows.Add();
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
logo.File = dataDir + "aspose-logo.jpg";
logo.FixHeight = 120;
logo.FixWidth = 110;
row1.Cells.Add();
row1.Cells[0].Paragraphs.Add(logo);
```

Folgendes ist passiert:
- Wir laden das Bild aus Ihrem angegebenen Verzeichnis.
- Wir legen die Höhe und Breite des Bildes fest.
- Zum Schluss fügen wir das Bild der ersten Zelle der Tabelle hinzu.

## Schritt 7: Fügen Sie neben dem Bild Text hinzu

Nachdem das Bild nun an seinem Platz ist, fügen wir etwas Text daneben hinzu. Für dieses Beispiel verwenden wir HTML-formatierten Text, um den Inhalt zu formatieren.

```csharp
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b> Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF document reporting component that enables .NET applications to <b>create PDF documents from scratch</b> without utilizing Adobe Acrobat.</font>";

Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
row1.Cells[1].Paragraphs.Add(TitleText);
```

Dieser Block fügt einen formatierten Titel und eine Beschreibung in der Zelle neben dem Bild hinzu. Sie können den Text mit HTML-Tags formatieren, um ihn individueller zu gestalten.

## Schritt 8: Vertikale Ausrichtung anpassen

Standardmäßig wird der Inhalt von Tabellenzellen möglicherweise nicht wie gewünscht ausgerichtet. In diesem Fall möchten wir sicherstellen, dass der Text oben in der Zelle ausgerichtet ist.

```csharp
row1.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
```

Dadurch wird sichergestellt, dass sich der Text oben in der Zelle befindet und das Layout sauber und professionell bleibt.

## Schritt 9: Fügen Sie unter dem Bild und der Beschreibung weiteren Text hinzu

Möglicherweise möchten Sie unterhalb des Bilds und des Textes mehr Inhalt einfügen. Fügen wir der Tabelle zu diesem Zweck eine weitere Zeile hinzu.

```csharp
Aspose.Pdf.Row SecondRow = table1.Rows.Add();
SecondRow.Cells.Add();
SecondRow.Cells[0].ColSpan = 2;
SecondRow.Cells[0].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;

string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
```

Hier haben wir eine weitere Zeile mit zusätzlichem Text hinzugefügt, die sich über beide Spalten erstreckt, um das Layout ausgewogen zu halten.

## Schritt 10: Speichern Sie das PDF-Dokument

Abschließend müssen wir das Dokument speichern, damit Sie die Änderungen sehen können.

```csharp
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

Dadurch wird die PDF-Datei mit dem Bild und Text in der gewünschten Formatierung gespeichert.

## Abschluss

Das Platzieren von Text um Bilder in einer PDF-Datei herum mag wie eine gewaltige Aufgabe erscheinen, aber Aspose.PDF für .NET vereinfacht den Vorgang. Durch die Nutzung von Tabellen, Bildern und formatiertem Text können Sie mit minimalem Aufwand professionell aussehende PDF-Dateien erstellen. Mit nur wenigen Codezeilen können Sie Inhalte genau dort positionieren, wo Sie sie haben möchten, und Ihren Dokumenten so ein elegantes und gut organisiertes Erscheinungsbild verleihen.

## Häufig gestellte Fragen

### Kann ich mit dieser Methode mehrere Bilder mit Text platzieren?
Ja, fügen Sie Ihrer Tabelle einfach weitere Zeilen und Zellen hinzu, um zusätzliche Bilder und Text einzufügen.

### Kann ich die Ausrichtung des Bildes ändern?
Auf jeden Fall! Sie können die Bildausrichtung ändern, indem Sie die Ausrichtungseigenschaften der Zelle anpassen.

### Wie formatiere ich den Text weiter?
 Sie können HTML-Tags innerhalb der`HtmlFragment` Objekt, um verschiedene Stile wie Fett, Kursiv oder verschiedene Schriftarten anzuwenden.

### Kann ich den Abstand zwischen Text und Bild steuern?
 Ja, mit dem`MarginInfo` Mit dem Objekt können Sie die Polsterung und Ränder zwischen Elementen steuern.

### Ist es möglich, Links zum Text hinzuzufügen?
 Auf jeden Fall! Sie können Hyperlinks in den HTML-formatierten Text einbetten, indem Sie`<a>` Etikett.