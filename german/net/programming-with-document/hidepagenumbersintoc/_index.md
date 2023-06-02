---
title: Seitenzahlen im Inhaltsverzeichnis ausblenden
linktitle: Seitenzahlen im Inhaltsverzeichnis ausblenden
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie in dieser Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.PDF für .NET Seitenzahlen in einem Inhaltsverzeichnis ausblenden.
type: docs
weight: 220
url: /de/net/programming-with-document/hidepagenumbersintoc/
---
In diesem Artikel besprechen wir die Implementierung der Funktion „Seitenzahlen im Inhaltsverzeichnis ausblenden“ von Aspose.PDF für .NET mit C#. Wir beginnen mit einer kurzen Einführung in Aspose.PDF für .NET und tauchen dann in die Schritt-für-Schritt-Anleitung zur Implementierung dieser Funktion ein. 

## Einführung in Aspose.PDF für .NET

Aspose.PDF für .NET ist eine leistungsstarke PDF-Bearbeitungskomponente, mit der Entwickler PDF-Dateien programmgesteuert erstellen, bearbeiten und bearbeiten können. Es bietet eine breite Palette an Features und Funktionalitäten, die die Arbeit mit PDF-Dokumenten erleichtern. Aspose.PDF für .NET unterstützt sowohl 32-Bit- als auch 64-Bit-Betriebssysteme und kann mit .NET Framework-, .NET Core- und Xamarin-Plattformen verwendet werden. 

## Was ist die Funktion „Seitenzahlen im Inhaltsverzeichnis ausblenden“?

Das Inhaltsverzeichnis (TOC) ist ein wesentlicher Bestandteil eines PDF-Dokuments, das Benutzern einen schnellen Überblick über den Inhalt bietet. Manchmal möchten Benutzer möglicherweise Seitenzahlen im Inhaltsverzeichnis ausblenden, um es benutzerfreundlicher zu gestalten. Aspose.PDF für .NET bietet eine integrierte Funktion zum Ausblenden von Seitenzahlen im Inhaltsverzeichnis. Mit dieser Funktion können benutzerfreundlichere PDF-Dokumente erstellt werden. 

## Voraussetzungen

Um diesem Tutorial folgen zu können, benötigen Sie Folgendes:

- Visual Studio 2010 oder höher
- Aspose.PDF für .NET ist auf Ihrem System installiert
- Grundkenntnisse der Programmiersprache C#

## Schritt-für-Schritt-Anleitung zur Implementierung der Funktion „Seitenzahlen im Inhaltsverzeichnis ausblenden“.

Führen Sie die folgenden Schritte aus, um die Funktion „Seitenzahlen im Inhaltsverzeichnis ausblenden“ mit Aspose.PDF für .NET zu implementieren:

## Schritt 1: Erstellen Sie eine neue C#-Konsolenanwendung in Visual Studio

Öffnen Sie Visual Studio und erstellen Sie eine neue C#-Konsolenanwendung.

## Schritt 2: Verweis auf Aspose.PDF für .NET hinzufügen

Klicken Sie mit der rechten Maustaste auf den Ordner „Referenzen“ in Ihrem Projekt und wählen Sie „Referenz hinzufügen“. Navigieren Sie zu dem Speicherort, an dem Aspose.PDF für .NET auf Ihrem System installiert ist, und fügen Sie einen Verweis darauf hinzu.

## Schritt 1: Erstellen Sie ein neues PDF-Dokument

Erstellen Sie ein neues PDF-Dokument mit dem folgenden Code:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
```

## Schritt 2: Erstellen Sie eine Inhaltsverzeichnisseite

Erstellen Sie eine neue Seite für das Inhaltsverzeichnis und fügen Sie sie mit dem folgenden Code zum PDF-Dokument hinzu:

```csharp
Page tocPage = doc.Pages.Add();
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
```

## Schritt 3: Listenabschnitt zur Abschnittssammlung des PDF-Dokuments hinzufügen

Fügen Sie den Listenabschnitt mit dem folgenden Code zur Abschnittssammlung des PDF-Dokuments hinzu:

```csharp
tocPage.TocInfo = tocInfo;
```

## Schritt 4: Definieren Sie das Format der Liste mit vier Ebenen

Definieren Sie das Format der Liste mit vier Ebenen, indem Sie die linken Ränder und Textformateinstellungen jeder Ebene mithilfe des folgenden Codes festlegen:

```csharp
tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
Page page = doc.Pages.Add();
```

## Schritt 5: Fügen Sie dem Abschnitt vier Überschriften hinzu

```csharp

for (int Level = 1; Level != 5; Level++)
{ 
	Heading heading2 = new Heading(Level); 
	TextSegment segment2 = new TextSegment(); 
	heading2.TocPage = tocPage; 
	heading2.Segments.Add(segment2); 
	heading2.IsAutoSequence = true; 
	segment2.Text = "this is heading of level " + Level; 
	heading2.IsInList = true; 
	page.Paragraphs.Add(heading2); 
}
doc.Save(outFile);

```

### Beispielquellcode für das Ausblenden von Seitenzahlen im Inhaltsverzeichnis mit Aspose.PDF für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
Page tocPage = doc.Pages.Add();
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
//Fügen Sie den Listenabschnitt zur Abschnittssammlung des PDF-Dokuments hinzu
tocPage.TocInfo = tocInfo;
//Definieren Sie das Format der Liste mit vier Ebenen, indem Sie die linken Ränder und festlegen
//Textformateinstellungen jeder Ebene

tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
Page page = doc.Pages.Add();
//Fügen Sie dem Abschnitt vier Überschriften hinzu
for (int Level = 1; Level != 5; Level++)
	{ 
		Heading heading2 = new Heading(Level); 
		TextSegment segment2 = new TextSegment(); 
		heading2.TocPage = tocPage; 
		heading2.Segments.Add(segment2); 
		heading2.IsAutoSequence = true; 
		segment2.Text = "this is heading of level " + Level; 
		heading2.IsInList = true; 
		page.Paragraphs.Add(heading2); 
	}
doc.Save(outFile);
```
