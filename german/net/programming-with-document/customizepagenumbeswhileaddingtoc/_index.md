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

Zuerst müssen wir eine vorhandene PDF-Datei laden. Für dieses Tutorial verwenden wir die Datei „42824.pdf“, die sich im Verzeichnis „IHR DOKUMENTVERZEICHNIS“ befindet. Ersetzen Sie diesen Verzeichnispfad durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

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

 Um ein TOC-Objekt zu erstellen, müssen wir zunächst ein erstellen`TocInfo`Objekt und legen Sie seine Eigenschaften fest. In diesem Tutorial setzen wir den Titel des Inhaltsverzeichnisses auf „Inhaltsverzeichnis“ und das Seitenzahlpräfix auf „P“.

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
//Laden Sie eine vorhandene PDF-Datei
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

