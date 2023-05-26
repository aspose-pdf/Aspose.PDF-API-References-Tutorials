---
title: Inhaltsverzeichnis hinzufügen
linktitle: Inhaltsverzeichnis hinzufügen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET ein Inhaltsverzeichnis zu PDF-Dokumenten hinzufügen. Schritt-für-Schritt-Anleitung mit Beispiel-Quellcode. Beschleunigen Sie die Dokumentennavigation!
type: docs
weight: 40
url: /de/net/programming-with-document/addtoc/
---

In diesem Tutorial erfahren Sie, wie Sie mit der Funktion „Inhaltsverzeichnis hinzufügen“ von Aspose.PDF für .NET ein Inhaltsverzeichnis zu PDF-Dokumenten hinzufügen. Wir stellen Ihnen eine Schritt-für-Schritt-Anleitung zur Verfügung und erläutern den dafür erforderlichen C#-Quellcode. Am Ende dieses Tutorials werden Sie in der Lage sein, mit Aspose.PDF für .NET ein PDF-Dokument mit einem Inhaltsverzeichnis zu erstellen.


## Schritt 1: Laden Sie die vorhandene PDF-Datei

Um zu beginnen, müssen wir eine vorhandene PDF-Datei laden. Ersetzen`"YOUR DOCUMENT DIRECTORY"` Geben Sie im folgenden Code den tatsächlichen Pfad zu Ihrer PDF-Datei ein:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "AddTOC.pdf");
```

## Schritt 2: Erstellen Sie eine neue Seite für das Inhaltsverzeichnis

Wir erstellen eine neue Seite für das Inhaltsverzeichnis. Der folgende Code fügt eine neue Seite an Index 1 ein:

```csharp
Page tocPage = doc.Pages.Insert(1);
```

## Schritt 3: Definieren Sie die Inhaltsverzeichnisinformationen

Als nächstes müssen wir die Inhaltsverzeichnisinformationen definieren. Wir legen den Titel und andere Eigenschaften des Inhaltsverzeichnisses fest. Fügen Sie den folgenden Code hinzu:

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;

tocInfo.Title = title;
tocPage.TocInfo = tocInfo;
```

## Schritt 4: Erstellen Sie TOC-Elemente

Jetzt erstellen wir die Elemente des Inhaltsverzeichnisses. In diesem Tutorial erstellen wir vier TOC-Elemente, die verschiedenen Seiten entsprechen. Ändern Sie den folgenden Code entsprechend Ihren Anforderungen:

```csharp
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";

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

## Schritt 5: Speichern Sie das aktualisierte Dokument

 Abschließend müssen wir das geänderte Dokument mit dem Inhaltsverzeichnis speichern. Ersetzen`"YOUR DOCUMENT DIRECTORY"` Geben Sie im folgenden Code den gewünschten Ausgabedateipfad ein:

```csharp
dataDir = dataDir + "TOC_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

### Beispielquellcode zum Hinzufügen von Inhaltsverzeichnissen zu PDF-Dokumenten mit Aspose.PDF für .NET

```csharp

// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Laden Sie eine vorhandene PDF-Datei
Document doc = new Document(dataDir + "AddTOC.pdf");

// Erhalten Sie Zugriff auf die erste Seite der PDF-Datei
Page tocPage = doc.Pages.Insert(1);

// Erstellen Sie ein Objekt zur Darstellung von TOC-Informationen
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;

// Legen Sie den Titel für das Inhaltsverzeichnis fest
tocInfo.Title = title;
tocPage.TocInfo = tocInfo;

// Erstellen Sie String-Objekte, die als TOC-Elemente verwendet werden
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";
for (int i = 0; i < 2; i++)
{
	// Erstellen Sie ein Überschriftenobjekt
	Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
	TextSegment segment2 = new TextSegment();
	heading2.TocPage = tocPage;
	heading2.Segments.Add(segment2);

	// Geben Sie die Zielseite für das Überschriftenobjekt an
	heading2.DestinationPage = doc.Pages[i + 2];

	// Zielseite
	heading2.Top = doc.Pages[i + 2].Rect.Height;

	// Zielkoordinate
	segment2.Text = titles[i];

	// Fügen Sie der Seite mit dem Inhaltsverzeichnis eine Überschrift hinzu
	tocPage.Paragraphs.Add(heading2);
}
dataDir = dataDir + "TOC_out.pdf";
//Speichern Sie das aktualisierte Dokument
doc.Save(dataDir);

Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);

```
