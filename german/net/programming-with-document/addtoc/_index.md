---
title: Inhaltsverzeichnis zur PDF-Datei hinzufügen
linktitle: Inhaltsverzeichnis zur PDF-Datei hinzufügen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET ein Inhaltsverzeichnis zu einer PDF-Datei hinzufügen. Schritt-für-Schritt-Anleitung mit Beispiel-Quellcode. Beschleunigen Sie die Dokumentennavigation!
type: docs
weight: 40
url: /de/net/programming-with-document/addtoc/
---
In diesem Tutorial erfahren Sie, wie Sie die Funktion „Inhaltsverzeichnis (Inhaltsverzeichnis) zu PDF-Datei hinzufügen“ von Aspose.PDF für .NET verwenden, um PDF-Dokumenten ein Inhaltsverzeichnis hinzuzufügen. Wir stellen Ihnen eine Schritt-für-Schritt-Anleitung zur Verfügung und erläutern den dafür erforderlichen C#-Quellcode. Am Ende dieses Tutorials werden Sie in der Lage sein, mit Aspose.PDF für .NET ein PDF-Dokument mit einem Inhaltsverzeichnis zu erstellen.


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

//Erstellen Sie String-Objekte, die als TOC-Elemente verwendet werden
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
// Speichern Sie das aktualisierte Dokument
doc.Save(dataDir);

Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

## Abschluss

In diesem Tutorial haben wir untersucht, wie man mit Aspose.PDF für .NET ein Inhaltsverzeichnis (TOC) zu PDF-Dokumenten hinzufügt. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Quellcode verwenden, können Sie ganz einfach ein PDF-Dokument mit einem Inhaltsverzeichnis erstellen. Das Inhaltsverzeichnis verbessert die Benutzerfreundlichkeit des Dokuments und ermöglicht Benutzern eine effizientere Navigation zu bestimmten Abschnitten oder Seiten. Aspose.PDF für .NET bietet eine robuste und benutzerfreundliche Lösung für die Arbeit mit PDF-Dateien in .NET-Anwendungen und ermöglicht Ihnen die einfache Erstellung dynamischer und interaktiver PDF-Dokumente.

### FAQs zum Hinzufügen von Inhaltsverzeichnissen zu PDF-Dateien

#### F: Was ist Aspose.PDF für .NET?

A: Aspose.PDF für .NET ist eine leistungsstarke Bibliothek, die es Entwicklern ermöglicht, effektiv mit PDF-Dateien in .NET-Anwendungen zu arbeiten. Es bietet eine breite Palette von Funktionen zum programmgesteuerten Erstellen, Bearbeiten und Verwalten von PDF-Dokumenten.

#### F: Welchen Zweck hat das Hinzufügen eines Inhaltsverzeichnisses (TOC) zu einem PDF-Dokument?

A: Das Inhaltsverzeichnis (TOC) bietet Benutzern eine Navigationshilfe, die es ihnen ermöglicht, schnell zu bestimmten Abschnitten oder Seiten innerhalb des PDF-Dokuments zu springen. Es verbessert die Benutzerfreundlichkeit und Benutzererfahrung des Dokuments.

#### F: Wie füge ich mit Aspose.PDF für .NET ein Inhaltsverzeichnis zu einem PDF-Dokument hinzu?

A: Um mit Aspose.PDF für .NET ein Inhaltsverzeichnis zu einem PDF-Dokument hinzuzufügen, müssen Sie eine neue Seite erstellen, die das Inhaltsverzeichnis enthält, die Informationen zum Inhaltsverzeichnis definieren und dann Inhaltsverzeichniselemente erstellen, die bestimmten Seiten oder Seiten entsprechen Abschnitte im Dokument.

#### F: Kann ich das Erscheinungsbild des Inhaltsverzeichnisses anpassen?

A: Ja, Sie können das Erscheinungsbild des Inhaltsverzeichnisses anpassen, indem Sie verschiedene Eigenschaften der Inhaltsverzeichniselemente festlegen, wie z. B. Schriftgröße, Schriftstil und Ausrichtung. Aspose.PDF für .NET bietet Flexibilität bei der Gestaltung des Inhaltsverzeichnisses, um es an Ihr gewünschtes Erscheinungsbild anzupassen.

#### F: Ist Aspose.PDF für .NET zum Hinzufügen erweiterter Funktionen zu PDF-Dokumenten geeignet?

A: Absolut, Aspose.PDF für .NET ist eine funktionsreiche Bibliothek, mit der Sie PDF-Dokumenten erweiterte Funktionen hinzufügen können, darunter interaktive Elemente, Formularfelder, digitale Signaturen und mehr.