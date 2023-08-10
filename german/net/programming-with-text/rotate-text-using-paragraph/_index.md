---
title: Text mithilfe von Absätzen drehen
linktitle: Text mithilfe von Absätzen drehen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Text mithilfe von Absätzen in einem PDF-Dokument drehen.
type: docs
weight: 380
url: /de/net/programming-with-text/rotate-text-using-paragraph/
---

In diesem Tutorial wird erläutert, wie Sie mit Aspose.PDF für .NET Text mithilfe von Absätzen drehen. Der bereitgestellte C#-Quellcode demonstriert den Prozess Schritt für Schritt.

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
using Aspose.Pdf.Text.TextBuilder;
```

## Schritt 3: Erstellen Sie das PDF-Dokument

 Initialisieren Sie die`Document` Objekt zum Erstellen eines neuen PDF-Dokuments:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document();
```

 Unbedingt austauschen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

## Schritt 4: Fügen Sie eine Seite hinzu

 Rufen Sie mit dem eine bestimmte Seite aus dem Dokument ab`Pages.Add()` Methode:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## Schritt 5: Erstellen Sie den Textabsatz

 Ein ... kreieren`TextParagraph` Objekt und legen Sie seine Position auf der Seite fest:

```csharp
TextParagraph paragraph = new TextParagraph();
paragraph.Position = new Position(200, 600);
```

Passen Sie die Positionswerte entsprechend Ihren Anforderungen an.

## Schritt 6: Textfragmente erstellen und konfigurieren

 Mehrere erstellen`TextFragment`Objekte und legen deren Text und Eigenschaften fest:

```csharp
TextFragment textFragment1 = new TextFragment("rotated text");
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment1.TextState.Rotation = 45;

TextFragment textFragment2 = new TextFragment("main text");
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");

TextFragment textFragment3 = new TextFragment("another rotated text");
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = -45;
```

Passen Sie den Text und andere Eigenschaften nach Bedarf an.

## Schritt 7: Textfragmente an den Absatz anhängen

 Hängen Sie die erstellten Textfragmente mit an den Absatz an`AppendLine` Methode:

```csharp
paragraph.AppendLine(textFragment1);
paragraph.AppendLine(textFragment2);
paragraph.AppendLine(textFragment3);
```

## Schritt 8: Erstellen Sie einen TextBuilder und hängen Sie den Absatz an

 Ein ... kreieren`TextBuilder` Objekt mit dem`pdfPage` und hängen Sie den Textabsatz an die PDF-Seite an:

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendParagraph(paragraph);
```

## Schritt 9: Speichern Sie das PDF-Dokument

 Speichern Sie das geänderte PDF-Dokument mit in einer Datei`Save` Methode:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated2_out.pdf");
```

 Unbedingt austauschen`"TextFragmentTests_Rotated2_out.pdf"` mit dem gewünschten Ausgabedateinamen.

### Beispielquellcode für „Text mithilfe von Absätzen drehen“ mit Aspose.PDF für .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokumentobjekt initialisieren
Document pdfDocument = new Document();
// Holen Sie sich eine bestimmte Seite
Page pdfPage = (Page)pdfDocument.Pages.Add();
TextParagraph paragraph = new TextParagraph();
paragraph.Position = new Position(200, 600);
// Textfragment erstellen
TextFragment textFragment1 = new TextFragment("rotated text");
// Texteigenschaften festlegen
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Rotation einstellen
textFragment1.TextState.Rotation = 45;
// Textfragment erstellen
TextFragment textFragment2 = new TextFragment("main text");
// Texteigenschaften festlegen
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Textfragment erstellen
TextFragment textFragment3 = new TextFragment("another rotated text");
// Texteigenschaften festlegen
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Rotation einstellen
textFragment3.TextState.Rotation = -45;
// Hängen Sie die Textfragmente an den Absatz an
paragraph.AppendLine(textFragment1);
paragraph.AppendLine(textFragment2);
paragraph.AppendLine(textFragment3);
// Erstellen Sie ein TextBuilder-Objekt
TextBuilder textBuilder = new TextBuilder(pdfPage);
// Hängen Sie den Textabsatz an die PDF-Seite an
textBuilder.AppendParagraph(paragraph);
// Dokument speichern
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated2_out.pdf");
```


## Abschluss

Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.PDF für .NET Text mithilfe von Absätzen in einem PDF-Dokument drehen. Dieses Tutorial bietet eine Schritt-für-Schritt-Anleitung von der Erstellung des Dokuments bis zum Speichern der geänderten Version. Sie können diesen Code jetzt in Ihre eigenen C#-Projekte integrieren, um die Textrotation in PDF-Dateien zu manipulieren.