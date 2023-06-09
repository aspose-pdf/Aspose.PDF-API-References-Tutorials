---
title: Geben Sie den Zeilenabstand an
linktitle: Geben Sie den Zeilenabstand an
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET den Zeilenabstand in einem PDF-Dokument festlegen.
type: docs
weight: 510
url: /de/net/programming-with-text/specify-line-spacing/
---

In diesem Tutorial wird erläutert, wie Sie mit Aspose.PDF für .NET den Zeilenabstand in einem PDF-Dokument festlegen. Der bereitgestellte C#-Quellcode demonstriert den Prozess Schritt für Schritt.

## Voraussetzungen

Bevor Sie mit dem Tutorial fortfahren, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Grundkenntnisse der Programmiersprache C#.
- Aspose.PDF für .NET-Bibliothek installiert. Sie können es von der Aspose-Website herunterladen oder NuGet verwenden, um es in Ihrem Projekt zu installieren.

## Schritt 1: Richten Sie das Projekt ein

Erstellen Sie zunächst ein neues C#-Projekt in Ihrer bevorzugten integrierten Entwicklungsumgebung (IDE) und fügen Sie einen Verweis auf die Aspose.PDF für .NET-Bibliothek hinzu.

## Schritt 2: Importieren Sie die erforderlichen Namespaces

Fügen Sie am Anfang Ihrer C#-Datei die folgenden using-Anweisungen hinzu, um die erforderlichen Namespaces zu importieren:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

## Schritt 3: Legen Sie den Pfad zum Dokumentverzeichnis fest

 Legen Sie den Pfad zu Ihrem Dokumentverzeichnis mit fest`dataDir` Variable:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

## Schritt 4: Laden Sie die Eingabe-PDF-Datei

 Laden Sie die Eingabe-PDF-Datei mit`Document` Klasse:

```csharp
Document doc = new Document();
```

## Schritt 5: Erstellen Sie TextFormattingOptions

 Ein ... kreieren`TextFormattingOptions` Objekt und stellen Sie den Zeilenabstandsmodus auf ein`FullSize`:

```csharp
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
```

## Schritt 6: Erstellen Sie ein TextFragment

 Ein ... kreieren`TextFragment` Objekt und geben Sie den Textinhalt an:

```csharp
TextFragment textFragment = new TextFragment("Hello world");
```

## Schritt 7: Laden Sie die Schriftartdatei (optional)

 Wenn Sie eine bestimmte Schriftart für den Text verwenden möchten, laden Sie die TrueType-Schriftartdatei in ein`FileStream` Objekt:

```csharp
string fontFile = dataDir + "HPSimplified.TTF";
using (FileStream fontStream = File.OpenRead(fontFile))
{
    textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
}
```

 Ersetzen`"HPSimplified.TTF"`mit dem tatsächlichen Namen der Schriftartdatei.

## Schritt 8: Geben Sie die Textposition und den Zeilenabstand an

 Legen Sie die Position für das Textfragment fest und weisen Sie es zu`TextFormattingOptions` zum`TextState.FormattingOptions` Eigentum:

```csharp
textFragment.Position = new Position(100, 600);
textFragment.TextState.FormattingOptions = formattingOptions;
```

## Schritt 9: Fügen Sie den Text zum Dokument hinzu

 Fügen Sie das Textfragment zum Dokument hinzu, indem Sie es entweder an eine anhängen`TextBuilder` oder direkt zu einer Seite`Paragraphs` Sammlung:

```csharp
var page = doc.Pages.Add();
page.Paragraphs.Add(textFragment);
```

## Schritt 10: Speichern Sie das resultierende PDF-Dokument

Speichern Sie das geänderte PDF-Dokument:

```csharp
dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
doc.Save(dataDir);
```

 Unbedingt austauschen`"SpecifyLineSpacing_out.pdf"` mit dem gewünschten Ausgabedateinamen.

### Beispielquellcode für „Zeilenabstand angeben“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string fontFile = dataDir + "HPSimplified.TTF";
// Laden Sie die Eingabe-PDF-Datei
Document doc = new Document();
//Erstellen Sie TextFormattingOptions mit LineSpacingMode.FullSize
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
// Erstellen Sie ein Texterstellungsobjekt für die erste Seite des Dokuments
//TextBuilder textBuilder = new TextBuilder(doc.Pages[1]);
// Erstellen Sie ein Textfragment mit einer Beispielzeichenfolge
TextFragment textFragment = new TextFragment("Hello world");
if (fontFile != "")
{
	// Laden Sie die TrueType-Schriftart in das Stream-Objekt
	using (FileStream fontStream = System.IO.File.OpenRead(fontFile))
	{
		// Legen Sie den Schriftartnamen für die Textzeichenfolge fest
		textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
		// Geben Sie die Position für das Textfragment an
		textFragment.Position = new Position(100, 600);
		//Setzen Sie TextFormattingOptions des aktuellen Fragments auf vordefiniert (was auf LineSpacingMode.FullSize zeigt).
		textFragment.TextState.FormattingOptions = formattingOptions;
		// Fügen Sie den Text zu TextBuilder hinzu, damit er über der PDF-Datei platziert werden kann
		//textBuilder.AppendText(textFragment);
		var page = doc.Pages.Add();
		page.Paragraphs.Add(textFragment);
	}
	dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
	// Speichern Sie das resultierende PDF-Dokument
	doc.Save(dataDir);
}
```

## Abschluss

Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.PDF für .NET den Zeilenabstand in einem PDF-Dokument festlegen. Dieses Tutorial bietet eine Schritt-für-Schritt-Anleitung vom Einrichten des Projekts bis zum Speichern des geänderten Dokuments. Sie können diesen Code jetzt in Ihre eigenen C#-Projekte integrieren, um den Zeilenabstand von Text in PDF-Dateien anzupassen.