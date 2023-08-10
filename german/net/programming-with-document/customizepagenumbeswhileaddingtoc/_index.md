---
title: Passen Sie die Seitenzahlen beim Hinzufügen des Inhaltsverzeichnisses an
linktitle: Passen Sie die Seitenzahlen beim Hinzufügen des Inhaltsverzeichnisses an
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie mit dieser Schritt-für-Schritt-Anleitung und dem Codebeispiel, wie Sie Seitenzahlen anpassen und gleichzeitig ein Inhaltsverzeichnis (TOC) mit Aspose.PDF für .NET hinzufügen.
type: docs
weight: 100
url: /de/net/programming-with-document/customizepagenumbeswhileaddingtoc/
---
In diesem Tutorial erfahren Sie, wie Sie mit Aspose.PDF für .NET Seitenzahlen anpassen und gleichzeitig ein Inhaltsverzeichnis (TOC) hinzufügen. Wir stellen Ihnen eine Schritt-für-Schritt-Anleitung zusammen mit einem Codebeispiel zur Verfügung, um Ihnen dabei zu helfen, dies zu erreichen.

## Schritt 1: Laden einer vorhandenen PDF-Datei

Zuerst müssen wir eine vorhandene PDF-Datei laden. Für dieses Tutorial verwenden wir die Datei „42824.pdf“, die sich im Verzeichnis „IHR DOKUMENTENVERZEICHNIS“ befindet. Ersetzen Sie diesen Verzeichnispfad durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "42824.pdf";
string outFile = dataDir + "42824_out.pdf";
Document doc = new Document(inFile);
```

## Schritt 2: Hinzufügen einer Inhaltsverzeichnisseite

 Als Nächstes müssen wir am Anfang des Dokuments eine neue Seite hinzufügen, die als Inhaltsverzeichnisseite dient. Wir können dies erreichen, indem wir die verwenden`Insert()` Methode der`Pages` Sammlung der`Document` Objekt.

```csharp
Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
```

## Schritt 3: Erstellen eines TOC-Objekts

 Um ein TOC-Objekt zu erstellen, müssen wir zunächst ein erstellen`TocInfo` Objekt und legen Sie seine Eigenschaften fest. In diesem Tutorial setzen wir den Titel des Inhaltsverzeichnisses auf „Inhaltsverzeichnis“ und das Seitenzahlpräfix auf „P“.

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocInfo.PageNumbersPrefix = "P";
tocPage.TocInfo = tocInfo;
```

## Schritt 4: Inhaltsverzeichniseinträge erstellen

Um Inhaltsverzeichniseinträge zu erstellen, müssen wir alle Seiten des Dokuments mit Ausnahme der Inhaltsverzeichnisseite durchlaufen und für jede Seite ein Überschriftenobjekt erstellen. Anschließend können wir das Überschriftenobjekt zur Inhaltsverzeichnisseite hinzufügen und seine Zielseite angeben.

```csharp
for (int i = 1; i < doc.Pages.Count; i++)
{
    // Erstellen Sie ein Überschriftenobjekt
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);
    // Geben Sie die Zielseite für das Überschriftenobjekt an
    heading2.DestinationPage = doc.Pages[i + 1];
    // Zielseite
    heading2.Top = doc.Pages[i + 1].Rect.Height;
    // Zielkoordinate
    segment2.Text = "Page " + i.ToString();
    // Fügen Sie der Seite mit dem Inhaltsverzeichnis eine Überschrift hinzu
    tocPage.Paragraphs.Add(heading2);
}
```

## Schritt 5: Speichern des aktualisierten Dokuments

Schließlich müssen wir das aktualisierte Dokument in einer neuen Datei speichern. Wir können dies erreichen, indem wir die verwenden`Save()` Methode der`Document` Objekt.

```csharp
doc.Save(outFile);
```

### Beispielquellcode zum Anpassen von Seitenzahlen beim Hinzufügen von Inhaltsverzeichnissen mit Aspose.PDF für .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "42824.pdf";
string outFile = dataDir + "42824_out.pdf";
// Laden Sie eine vorhandene PDF-Datei
Document doc = new Document(inFile);
// Erhalten Sie Zugriff auf die erste Seite der PDF-Datei
Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
// Erstellen Sie ein Objekt zur Darstellung von TOC-Informationen
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
// Legen Sie den Titel für das Inhaltsverzeichnis fest
tocInfo.Title = title;
tocInfo.PageNumbersPrefix = "P";
tocPage.TocInfo = tocInfo;
for (int i = 1; i<doc.Pages.Count; i++)
{
	// Erstellen Sie ein Überschriftenobjekt
	Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
	TextSegment segment2 = new TextSegment();
	heading2.TocPage = tocPage;
	heading2.Segments.Add(segment2);
	// Geben Sie die Zielseite für das Überschriftenobjekt an
	heading2.DestinationPage = doc.Pages[i + 1];
	// Zielseite
	heading2.Top = doc.Pages[i + 1].Rect.Height;
	// Zielkoordinate
	segment2.Text = "Page " + i.ToString();
	// Fügen Sie der Seite mit dem Inhaltsverzeichnis eine Überschrift hinzu
	tocPage.Paragraphs.Add(heading2);
}

// Speichern Sie das aktualisierte Dokument
doc.Save(outFile);
```

## Abschluss

In diesem Tutorial haben wir eine Schritt-für-Schritt-Anleitung zum Anpassen von Seitenzahlen beim Hinzufügen eines Inhaltsverzeichnisses mit Aspose.PDF für .NET bereitgestellt. Wir haben auch ein Codebeispiel bereitgestellt, das Sie als Referenz bei der Implementierung dieser Funktion in Ihrem Unternehmen verwenden können

### FAQs

#### F: Was ist ein Inhaltsverzeichnis (TOC) in einem PDF-Dokument?

A: Ein Inhaltsverzeichnis (TOC) in einem PDF-Dokument ist eine Navigationshilfe, die eine organisierte Liste von Dokumentabschnitten oder Kapiteln zusammen mit den entsprechenden Seitenzahlen bereitstellt. Dadurch können Leser schnell zu bestimmten Abschnitten im Dokument navigieren.

#### F: Warum sollte ich Seitenzahlen in einem Inhaltsverzeichnis anpassen?

A: Das Anpassen von Seitenzahlen in einem Inhaltsverzeichnis kann nützlich sein, wenn Sie ein bestimmtes Seitennummerierungsformat verwenden oder zusätzliche Informationen zusammen mit den Seitenzahlen hinzufügen möchten. Es ermöglicht Ihnen, ein personalisierteres und informativeres Inhaltsverzeichnis zu erstellen.

#### F: Kann ich Hyperlinks in das Inhaltsverzeichnis einfügen, um auf bestimmte Abschnitte oder Seiten im PDF-Dokument zu verweisen?

A: Ja, mit Aspose.PDF für .NET können Sie im Inhaltsverzeichnis Hyperlinks erstellen, die auf bestimmte Abschnitte oder Seiten im PDF-Dokument verweisen. Dies verbessert die Interaktivität und Navigation des PDF-Dokuments.

#### F: Ist Aspose.PDF für .NET mit PDF/A-Standards kompatibel?

A: Ja, Aspose.PDF für .NET unterstützt PDF/A-Standards, einschließlich PDF/A-1, PDF/A-2 und PDF/A-3. Damit können Sie PDF-Dokumente erstellen, die den Archivierungs- und Langzeitarchivierungsanforderungen entsprechen.

#### F: Kann ich den Inhaltsverzeichniseinträgen weitere Formatierungen hinzufügen, z. B. Schriftarten oder Farben?

A: Ja, Sie können den Inhaltsverzeichniseinträgen zusätzliche Formatierungen hinzufügen, z. B. Schriftarten, Farben und Schriftgrößen, indem Sie Aspose.PDF für .NET verwenden. Dadurch können Sie das Erscheinungsbild des Inhaltsverzeichnisses an Ihre Anforderungen anpassen.
