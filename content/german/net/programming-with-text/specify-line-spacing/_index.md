---
title: Zeilenabstand in PDF-Datei festlegen
linktitle: Zeilenabstand in PDF-Datei festlegen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET den Zeilenabstand in PDF-Dateien festlegen.
type: docs
weight: 510
url: /de/net/programming-with-text/specify-line-spacing/
---
Dieses Tutorial erklärt, wie Sie mit Aspose.PDF für .NET den Zeilenabstand in einer PDF-Datei festlegen. Der bereitgestellte C#-Quellcode demonstriert den Vorgang Schritt für Schritt.

## Voraussetzungen

Bevor Sie mit dem Lernprogramm fortfahren, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Grundkenntnisse der Programmiersprache C#.
- Aspose.PDF für .NET-Bibliothek installiert. Sie können es von der Aspose-Website beziehen oder NuGet verwenden, um es in Ihrem Projekt zu installieren.

## Schritt 1: Einrichten des Projekts

Beginnen Sie mit der Erstellung eines neuen C#-Projekts in Ihrer bevorzugten integrierten Entwicklungsumgebung (IDE) und fügen Sie einen Verweis auf die Aspose.PDF-Bibliothek für .NET hinzu.

## Schritt 2: Erforderliche Namespaces importieren

Fügen Sie am Anfang Ihrer C#-Datei die folgenden Using-Direktiven hinzu, um die erforderlichen Namespaces zu importieren:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

## Schritt 3: Pfad zum Dokumentverzeichnis festlegen

 Legen Sie den Pfad zu Ihrem Dokumentverzeichnis fest mit dem`dataDir` Variable:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ersetzen`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

## Schritt 4: Laden Sie die Eingabe-PDF-Datei

 Laden Sie die Eingabe-PDF-Datei mit dem`Document` Klasse:

```csharp
Document doc = new Document();
```

## Schritt 5: TextFormattingOptions erstellen

 Erstellen Sie ein`TextFormattingOptions` Objekt und stellen Sie den Zeilenabstandsmodus auf`FullSize`:

```csharp
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
```

## Schritt 6: Erstellen Sie ein TextFragment

 Erstellen Sie ein`TextFragment` Objekt und geben Sie den Textinhalt an:

```csharp
TextFragment textFragment = new TextFragment("Hello world");
```

## Schritt 7: Laden Sie die Schriftartdatei (optional)

 Wenn Sie eine bestimmte Schriftart für den Text verwenden möchten, laden Sie die TrueType-Schriftdatei in ein`FileStream` Objekt:

```csharp
string fontFile = dataDir + "HPSimplified.TTF";
using (FileStream fontStream = File.OpenRead(fontFile))
{
    textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
}
```

 Ersetzen`"HPSimplified.TTF"` durch den tatsächlichen Schriftartdateinamen.

## Schritt 8: Textposition und Zeilenabstand festlegen

 Legen Sie die Position des Textfragments fest und weisen Sie ihm die`TextFormattingOptions` zur`TextState.FormattingOptions` Eigentum:

```csharp
textFragment.Position = new Position(100, 600);
textFragment.TextState.FormattingOptions = formattingOptions;
```

## Schritt 9: Fügen Sie den Text zum Dokument hinzu

 Fügen Sie das Textfragment dem Dokument hinzu, entweder durch Anhängen an eine`TextBuilder` oder direkt zur Seite`Paragraphs` Sammlung:

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

 Ersetzen Sie unbedingt`"SpecifyLineSpacing_out.pdf"` durch den gewünschten Ausgabedateinamen.

### Beispiel-Quellcode zum Festlegen des Zeilenabstands mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string fontFile = dataDir + "HPSimplified.TTF";
// PDF-Eingabedatei laden
Document doc = new Document();
//Erstellen Sie TextFormattingOptions mit LineSpacingMode.FullSize
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
// Text Builder-Objekt für die erste Seite des Dokuments erstellen
//TextBuilder textBuilder = neuer TextBuilder(doc.Pages[1]);
// Textfragment mit Beispielzeichenfolge erstellen
TextFragment textFragment = new TextFragment("Hello world");
if (fontFile != "")
{
	//Laden Sie die TrueType-Schriftart in das Stream-Objekt
	using (FileStream fontStream = System.IO.File.OpenRead(fontFile))
	{
		// Legen Sie den Schriftnamen für die Textzeichenfolge fest
		textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
		// Geben Sie die Position für das Textfragment an
		textFragment.Position = new Position(100, 600);
		//Setzen Sie die TextFormattingOptions des aktuellen Fragments auf vordefiniert (was auf LineSpacingMode.FullSize verweist).
		textFragment.TextState.FormattingOptions = formattingOptions;
		// Fügen Sie den Text zum TextBuilder hinzu, damit er über die PDF-Datei gelegt werden kann
		//textBuilder.AppendText(textFragment);
		var page = doc.Pages.Add();
		page.Paragraphs.Add(textFragment);
	}
	dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
	// Das resultierende PDF-Dokument speichern
	doc.Save(dataDir);
}
```

## Abschluss

Herzlichen Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.PDF für .NET den Zeilenabstand in einem PDF-Dokument festlegen. Dieses Tutorial bietet eine Schritt-für-Schritt-Anleitung vom Einrichten des Projekts bis zum Speichern des geänderten Dokuments. Sie können diesen Code jetzt in Ihre eigenen C#-Projekte integrieren, um den Zeilenabstand von Text in PDF-Dateien anzupassen.

### Häufig gestellte Fragen

#### F: Was ist der Zweck des Tutorials „Zeilenabstand in PDF-Datei festlegen“?

A: Das Tutorial „Zeilenabstand in PDF-Datei festlegen“ soll Benutzern zeigen, wie sie mithilfe der Aspose.PDF-Bibliothek für .NET den Zeilenabstand von Text in einem PDF-Dokument anpassen können. Das Tutorial enthält schrittweise Anleitungen und C#-Codebeispiele, um den Vorgang zu demonstrieren.

#### F: Wie hilft dieses Tutorial beim Festlegen des Zeilenabstands in einem PDF-Dokument?

A: Dieses Tutorial hilft Benutzern zu verstehen, wie sie die Funktionen von Aspose.PDF für .NET nutzen können, um den Zeilenabstand für Text in einem PDF-Dokument festzulegen. Indem Benutzer die bereitgestellten Schritte und Codebeispiele befolgen, können sie den Zeilenabstand nach ihren Wünschen anpassen.

#### F: Welche Voraussetzungen sind erforderlich, um diesem Tutorial folgen zu können?

A: Bevor Sie mit dem Tutorial beginnen, sollten Sie über Grundkenntnisse der Programmiersprache C# verfügen. Darüber hinaus müssen Sie die Bibliothek Aspose.PDF für .NET installiert haben. Sie können sie von der Aspose-Website herunterladen oder mit NuGet in Ihrem Projekt installieren.

#### F: Wie richte ich mein Projekt ein, um diesem Tutorial zu folgen?

A: Erstellen Sie zunächst ein neues C#-Projekt in Ihrer bevorzugten integrierten Entwicklungsumgebung (IDE) und fügen Sie einen Verweis auf die Aspose.PDF-Bibliothek für .NET hinzu. Auf diese Weise können Sie die Funktionen der Bibliothek für die Arbeit mit PDF-Dokumenten und die Anpassung des Zeilenabstands nutzen.

#### F: Kann ich mit diesem Tutorial den Zeilenabstand für jede Art von Text festlegen?

A: Ja, dieses Tutorial enthält Anweisungen zum Festlegen des Zeilenabstands für beliebige Textinhalte in einem PDF-Dokument mit Aspose.PDF für .NET. Sie können die bereitgestellten Codebeispiele verwenden, um den Zeilenabstand des Textes nach Ihren Wünschen anzupassen.

#### F: Wie lege ich den Zeilenabstandsmodus im Tutorial fest?

 A: Das Tutorial zeigt die Erstellung eines`TextFormattingOptions` Objekt und legen Sie dessen`LineSpacing` Eigentum an`TextFormattingOptions.LineSpacingMode.FullSize`Dieser Modus gibt den vollen Zeilenabstand für den Textinhalt an.

#### F: Wie kann ich eine bestimmte Schriftart für den Text laden?

 A: Wenn Sie eine bestimmte Schriftart für den Textinhalt verwenden möchten, finden Sie im Tutorial Hinweise zum Laden einer TrueType-Schriftdatei in ein`FileStream` Objekt und legen Sie es als Schriftart für das`TextFragment`. Dadurch können Sie die Schriftart und den Zeilenabstand des Textes anpassen.

#### F: Wie passe ich die Position des Textes im PDF-Dokument an?

 A: Um die Position des Textes anzupassen, erstellen Sie ein`TextFragment` Objekt und legen Sie dessen`Position`-Eigenschaft auf die gewünschten Koordinaten (X und Y). So können Sie steuern, wo der Text im PDF-Dokument platziert wird.

#### F: Kann ich diese Zeilenabstandsänderungen auf vorhandene PDF-Dokumente anwenden?

 A: Ja, Sie können den Zeilenabstand für Text in vorhandenen PDF-Dokumenten ändern. Das Tutorial zeigt, wie Sie ein`TextFragment` mit dem angegebenen Zeilenabstand und der angegebenen Position und fügen Sie es dann zur Seite hinzu`Paragraphs` Sammlung.