---
title: Inhaltsverzeichnis zur PDF-Datei hinzufügen
linktitle: Inhaltsverzeichnis zur PDF-Datei hinzufügen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET ein Inhaltsverzeichnis zu einer PDF-Datei hinzufügen. Diese Schritt-für-Schritt-Anleitung vereinfacht den Vorgang und gewährleistet eine einfache Navigation in Ihren Dokumenten.
type: docs
weight: 40
url: /de/net/programming-with-document/addtoc/
---
## Einführung

Haben Sie schon einmal endlos durch eine lange PDF-Datei gescrollt und sich gewünscht, sie hätte ein gut organisiertes Inhaltsverzeichnis? Dann ist heute Ihr Glückstag! In diesem Tutorial erfahren Sie, wie Sie mit Aspose.PDF für .NET ein Inhaltsverzeichnis zu Ihrer PDF-Datei hinzufügen. Egal, ob Sie an einem komplexen Bericht, einem eBook oder einem Geschäftsvorschlag arbeiten, ein Inhaltsverzeichnis kann Ihr Dokument in ein professionelles, navigierbares Meisterwerk verwandeln.

## Voraussetzungen

Bevor wir uns in den Code stürzen, stellen wir sicher, dass Sie alles haben, was Sie brauchen:

1. Aspose.PDF für .NET: Stellen Sie sicher, dass Sie die Aspose.PDF-Bibliothek heruntergeladen und installiert haben. Sie können sie hier herunterladen:[Hier](https://releases.aspose.com/pdf/net/).
   
2. Entwicklungsumgebung: Stellen Sie sicher, dass auf Ihrem Computer eine .NET-Entwicklungsumgebung wie Visual Studio eingerichtet ist.

3.  Lizenz: Wenn Sie keine Lizenz haben, können Sie eine kostenlose Testversion erhalten oder eine temporäre Lizenz anfordern[Hier](https://purchase.aspose.com/temporary-license/).

## Pakete importieren

Stellen Sie zunächst sicher, dass Sie die erforderlichen Namespaces am Anfang Ihrer Codedatei importieren. So geht's:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

Diese Namespaces ermöglichen Ihnen den Zugriff auf PDF-spezifische Funktionen und die Bearbeitung von Textelementen in Ihrem Dokument.

Lassen Sie uns diese Aufgabe in mundgerechte Schritte unterteilen. Jeder Schritt führt Sie durch den Prozess der Erstellung und des Einfügens eines Inhaltsverzeichnisses in Ihr PDF-Dokument.

## Schritt 1: Laden Sie das PDF-Dokument

Als Erstes müssen wir die vorhandene PDF-Datei laden, in die wir das Inhaltsverzeichnis einfügen möchten.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "AddTOC.pdf");
```

 In diesem Schritt geben wir den Pfad zum Dokumentverzeichnis an und laden das PDF mit dem`Document` Objekt. Stellen Sie sicher, dass Sie`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zu Ihrer Datei.

## Schritt 2: Einfügen einer neuen Seite für das Inhaltsverzeichnis

Als nächstes fügen wir am Anfang des PDF-Dokuments eine neue Seite ein. Diese Seite enthält das Inhaltsverzeichnis.

```csharp
Page tocPage = doc.Pages.Insert(1);
```

Indem wir die Inhaltsverzeichnisseite am Anfang einfügen, stellen wir sicher, dass sie das Allererste ist, was die Leser in der PDF-Datei sehen.

## Schritt 3: Erstellen eines TOC-Informationsobjekts

Lassen Sie uns nun ein Objekt erstellen, das die Inhaltsverzeichnisinformationen darstellt. Wir werden dem Inhaltsverzeichnis auch einen Titel hinzufügen, damit es hervorsticht.

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocPage.TocInfo = tocInfo;
```

Hier haben wir den Titel des Inhaltsverzeichnisses als „Inhaltsverzeichnis“ festgelegt, die Schriftgröße erhöht und es zur Hervorhebung fett markiert.

## Schritt 4: Inhaltsverzeichniselemente definieren

In diesem Schritt definieren wir die Elemente (oder Überschriften), die im Inhaltsverzeichnis angezeigt werden. Diese Elemente helfen den Lesern, zu bestimmten Abschnitten des Dokuments zu navigieren.

```csharp
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";
```

Wir haben ein Array von Zeichenfolgen erstellt, die als Inhaltsverzeichniselemente dienen und den verschiedenen Seiten im PDF entsprechen.

## Schritt 5: Inhaltsverzeichnisüberschriften erstellen

Jetzt kommt der entscheidende Teil: das Hinzufügen von Überschriften zum Inhaltsverzeichnis und deren Verknüpfen mit den entsprechenden Seiten.

```csharp
for (int i = 0; i < 2; i++)
{
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);

    heading2.DestinationPage = doc.Pages[i + 2];
    heading2.Top = doc.Pages[i + 2].Rect.Height;
    segment2.Text = titles[i];

    tocPage.Paragraphs.Add(heading2);
}
```

Folgendes ist passiert:
- Überschrift: Wir erstellen eine`Heading` Objekt und fügen Sie ein`TextSegment` dazu.
- Zielseite: Wir legen die Seite fest, auf die jede Überschrift verweist.
- Obere Position: Wir geben die Position auf der Seite an, auf die die Überschrift zeigen soll.
- Text: Jede Überschrift erhält ihren jeweiligen Titel aus dem Array, das wir zuvor erstellt haben.

Diese Schleife erstellt Überschriften für die ersten beiden Elemente im Inhaltsverzeichnis und verknüpft sie mit den entsprechenden Seiten.

## Schritt 6: Speichern Sie das PDF mit dem Inhaltsverzeichnis

Nachdem wir alle Inhaltsverzeichniselemente hinzugefügt haben, ist es an der Zeit, das aktualisierte PDF zu speichern.

```csharp
dataDir = dataDir + "TOC_out.pdf";
doc.Save(dataDir);
```

Die Datei wird nun mit dem zur PDF hinzugefügten Inhaltsverzeichnis gespeichert. Herzlichen Glückwunsch – Sie haben erfolgreich ein Inhaltsverzeichnis hinzugefügt!

## Schritt 7: Bestätigungsnachricht

Um den Benutzer darüber zu informieren, dass der Vorgang abgeschlossen ist, zeigen wir eine einfache Meldung in der Konsole an.

```csharp
Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

## Abschluss

Und da haben Sie es! Mit Aspose.PDF für .NET ist das Hinzufügen eines Inhaltsverzeichnisses zu einer PDF-Datei nicht nur einfach, sondern auch anpassbar. Egal, ob Sie einfache Navigationslinks oder komplexe Strukturen erstellen müssen, dieses Tool bietet alles. Vergessen Sie also nicht, beim nächsten Mal, wenn Sie an einer langen PDF-Datei arbeiten, ein Inhaltsverzeichnis für den professionellen Touch hinzuzufügen!

## Häufig gestellte Fragen

### Kann ich das Erscheinungsbild des Inhaltsverzeichnisses in Aspose.PDF anpassen?  
Ja, Sie können das Erscheinungsbild des Inhaltsverzeichnisses einschließlich Schriftart, -größe und -ausrichtung vollständig anpassen.

### Wie füge ich dem Inhaltsverzeichnis Unterüberschriften hinzu?  
 Sie können Unterüberschriften hinzufügen, indem Sie die`Heading` Ebene (z. B.`Heading(2)`), um ein hierarchisches Inhaltsverzeichnis zu erstellen.

### Ist es möglich, das Inhaltsverzeichnis automatisch zu aktualisieren, wenn sich das Dokument ändert?  
Nein, das Inhaltsverzeichnis wird nicht automatisch aktualisiert. Sie müssen es neu erstellen, wenn sich die Dokumentstruktur ändert.

### Kann ich Inhaltsverzeichniseinträge mit externen Dokumenten verknüpfen?  
Ja, Sie können Hyperlinks verwenden, um Inhaltsverzeichniseinträge mit externen PDFs oder URLs zu verknüpfen.

### Unterstützt Aspose.PDF mehrstufige Inhaltsverzeichnisse?  
Ja, Aspose.PDF unterstützt mehrstufige Inhaltsverzeichnisse für komplexe Dokumente mit Unterabschnitten.