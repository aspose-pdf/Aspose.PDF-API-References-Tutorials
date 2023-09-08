---
title: Geben Sie den Zeilenabstand in der PDF-Datei an
linktitle: Geben Sie den Zeilenabstand in der PDF-Datei an
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET den Zeilenabstand in einer PDF-Datei festlegen.
type: docs
weight: 510
url: /de/net/programming-with-text/specify-line-spacing/
---
In diesem Tutorial wird erläutert, wie Sie mit Aspose.PDF für .NET den Zeilenabstand in einer PDF-Datei festlegen. Der bereitgestellte C#-Quellcode demonstriert den Prozess Schritt für Schritt.

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

 Ersetzen`"HPSimplified.TTF"` mit dem tatsächlichen Namen der Schriftartdatei.

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
		//Legen Sie den Schriftartnamen für die Textzeichenfolge fest
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

### FAQs

#### F: Was ist der Zweck des Tutorials „Zeilenabstand in PDF-Datei festlegen“?

A: Das Tutorial „Zeilenabstand in PDF-Datei festlegen“ soll Benutzern zeigen, wie sie mit der Aspose.PDF-Bibliothek für .NET den Zeilenabstand von Text in einem PDF-Dokument anpassen können. Das Tutorial bietet Schritt-für-Schritt-Anleitungen und C#-Codebeispiele zur Veranschaulichung des Prozesses.

#### F: Wie hilft dieses Tutorial bei der Angabe des Zeilenabstands in einem PDF-Dokument?

A: Dieses Tutorial hilft Benutzern zu verstehen, wie sie die Funktionen von Aspose.PDF für .NET nutzen können, um den Zeilenabstand für Text in einem PDF-Dokument festzulegen. Durch Befolgen der bereitgestellten Schritte und Codebeispiele können Benutzer den Zeilenabstand nach ihren Wünschen anpassen.

#### F: Welche Voraussetzungen sind erforderlich, um diesem Tutorial folgen zu können?

A: Bevor Sie mit dem Tutorial beginnen, sollten Sie über grundlegende Kenntnisse der Programmiersprache C# verfügen. Darüber hinaus muss die Bibliothek Aspose.PDF für .NET installiert sein. Sie können es von der Aspose-Website herunterladen oder mit NuGet in Ihrem Projekt installieren.

#### F: Wie richte ich mein Projekt ein, um diesem Tutorial zu folgen?

A: Erstellen Sie zunächst ein neues C#-Projekt in Ihrer bevorzugten integrierten Entwicklungsumgebung (IDE) und fügen Sie einen Verweis auf die Bibliothek Aspose.PDF für .NET hinzu. Dadurch können Sie die Funktionen der Bibliothek zum Arbeiten mit PDF-Dokumenten und zum Anpassen des Zeilenabstands nutzen.

#### F: Kann ich dieses Tutorial verwenden, um den Zeilenabstand für jede Art von Text festzulegen?

A: Ja, dieses Tutorial enthält Anweisungen zum Festlegen des Zeilenabstands für beliebige Textinhalte in einem PDF-Dokument mithilfe von Aspose.PDF für .NET. Mit den bereitgestellten Codebeispielen können Sie den Zeilenabstand des Textes Ihren Bedürfnissen entsprechend anpassen.

#### F: Wie lege ich den Zeilenabstandsmodus im Tutorial fest?

 A: Das Tutorial zeigt, wie man ein erstellt`TextFormattingOptions` Objekt und legen Sie es fest`LineSpacing` Eigentum zu`TextFormattingOptions.LineSpacingMode.FullSize`. Dieser Modus legt den vollen Zeilenabstand für den Textinhalt fest.

#### F: Wie kann ich eine bestimmte Schriftart für den Text laden?

 A: Wenn Sie eine bestimmte Schriftart für den Textinhalt verwenden möchten, bietet das Tutorial Anleitungen zum Laden einer TrueType-Schriftartdatei in eine`FileStream` Objekt und legen Sie es als Schriftart für das fest`TextFragment`. Dadurch können Sie die Schriftart des Textes sowie den Zeilenabstand anpassen.

#### F: Wie kann ich die Position des Textes im PDF-Dokument anpassen?

 A: Um die Position des Textes anzupassen, erstellen Sie eine`TextFragment` Objekt und legen Sie es fest`Position`Eigenschaft auf die gewünschten Koordinaten (X und Y). Dadurch können Sie steuern, wo der Text im PDF-Dokument platziert wird.

#### F: Kann ich diese Zeilenabstandsänderungen auf vorhandene PDF-Dokumente anwenden?

 A: Ja, Sie können den Zeilenabstand für Text in vorhandenen PDF-Dokumenten ändern. Das Tutorial zeigt, wie man eine erstellt`TextFragment` mit dem angegebenen Zeilenabstand und der angegebenen Position und fügen Sie es dann einer Seite hinzu`Paragraphs` Sammlung.