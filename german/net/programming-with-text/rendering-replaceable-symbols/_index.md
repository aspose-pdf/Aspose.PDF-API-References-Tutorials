---
title: Ersetzen austauschbarer Symbole
linktitle: Ersetzen austauschbarer Symbole
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET ersetzbare Symbole in einem PDF-Dokument rendern.
type: docs
weight: 310
url: /de/net/programming-with-text/rendering-replaceable-symbols/
---

In diesem Tutorial erklären wir, wie man ersetzbare Symbole in einem PDF-Dokument mithilfe der Aspose.PDF-Bibliothek für .NET rendert. Wir werden den Schritt-für-Schritt-Prozess der Erstellung einer PDF-Datei, dem Hinzufügen eines Textfragments mit Zeilenumbrüchen, dem Festlegen von Texteigenschaften, der Positionierung des Textes und dem Speichern der PDF-Datei mit dem bereitgestellten C#-Quellcode durchgehen.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Die Aspose.PDF für .NET-Bibliothek installiert.
- Ein grundlegendes Verständnis der C#-Programmierung.

## Schritt 1: Richten Sie das Dokumentenverzeichnis ein

 Zunächst müssen Sie den Pfad zu dem Verzeichnis festlegen, in dem Sie die generierte PDF-Datei speichern möchten. Ersetzen`"YOUR DOCUMENT DIRECTORY"` im`dataDir` Variable mit dem Pfad zu Ihrem gewünschten Verzeichnis.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Erstellen Sie ein PDF-Dokument und eine Seite

Als nächstes erstellen wir ein neues PDF-Dokument und fügen ihm mithilfe von eine Seite hinzu`Document` Klasse und`Page` Klasse aus der Aspose.PDF-Bibliothek.

```csharp
Aspose.Pdf.Document pdfApplicationDoc = new Aspose.Pdf.Document();
Aspose.Pdf.Page applicationFirstPage = (Aspose.Pdf.Page)pdfApplicationDoc.Pages.Add();
```

## Schritt 3: Textfragment mit Zeilenumbruchmarkierungen hinzufügen

 Wir erstellen ein`TextFragment` Objekt und legen Sie fest, dass sein Text Zeilenumbruchmarkierungen enthält (`Environment.NewLine`), um mehrere Textzeilen darzustellen.

```csharp
Aspose.Pdf.Text.TextFragment textFragment = new Aspose.Pdf.Text.TextFragment("Applicant Name: " + Environment.NewLine + " Joe Smoe");
```

## Schritt 4: Legen Sie die Eigenschaften des Textfragments fest

Auf Wunsch können wir verschiedene Eigenschaften für das Textfragment festlegen, wie z. B. Schriftgröße, Schriftart, Hintergrundfarbe und Vordergrundfarbe.

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
```

## Schritt 5: Textabsatz und Position erstellen

 Wir erstellen ein`TextParagraph` Objekt, hängen Sie das Textfragment an den Absatz an und legen Sie die Position des Absatzes auf der Seite fest.

```csharp
TextParagraph par = new TextParagraph();
par.AppendLine(textFragment);
par.Position = new Aspose.Pdf.Text.Position(100, 600);
```

## Schritt 6: Fügen Sie der Seite einen Textabsatz hinzu

 Wir erstellen ein`TextBuilder` Objekt mit der Seite und hängen Sie den Textabsatz an den Textgenerator an.

```csharp
TextBuilder textBuilder = new TextBuilder(applicationFirstPage);
textBuilder.AppendParagraph(par);
```

## Schritt 7: Speichern Sie das PDF-Dokument

Abschließend speichern wir das PDF-Dokument in der angegebenen Ausgabedatei.

```csharp
dataDir = dataDir + "RenderingReplaceableSymbols_out.pdf";
pdfApplicationDoc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols rendered successfully during PDF creation.\nFile saved at " + dataDir);
```

### Beispielquellcode zum Rendern austauschbarer Symbole mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document pdfApplicationDoc = new Aspose.Pdf.Document();
Aspose.Pdf.Page applicationFirstPage = (Aspose.Pdf.Page)pdfApplicationDoc.Pages.Add();
// Initialisieren Sie ein neues TextFragment mit Text, der die erforderlichen Zeilenumbruchmarkierungen enthält
Aspose.Pdf.Text.TextFragment textFragment = new Aspose.Pdf.Text.TextFragment("Applicant Name: " + Environment.NewLine + " Joe Smoe");
// Legen Sie bei Bedarf Textfragmenteigenschaften fest
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
// Erstellen Sie ein TextParagraph-Objekt
TextParagraph par = new TextParagraph();
// Fügen Sie dem Absatz ein neues Textfragment hinzu
par.AppendLine(textFragment);
// Absatzposition festlegen
par.Position = new Aspose.Pdf.Text.Position(100, 600);
// Erstellen Sie ein TextBuilder-Objekt
TextBuilder textBuilder = new TextBuilder(applicationFirstPage);
// Fügen Sie den TextParagraph mit TextBuilder hinzu
textBuilder.AppendParagraph(par);
dataDir = dataDir + "RenderingReplaceableSymbols_out.pdf";
pdfApplicationDoc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols render successfully duing pdf creation.\nFile saved at " + dataDir);
```

## Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie mit der Aspose.PDF-Bibliothek für .NET ersetzbare Symbole in einem PDF-Dokument rendern. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Code ausführen, können Sie eine PDF-Datei erstellen, Text mit Zeilenumbruchmarkierungen hinzufügen, Texteigenschaften festlegen, den Text auf der Seite positionieren und die PDF-Datei speichern.