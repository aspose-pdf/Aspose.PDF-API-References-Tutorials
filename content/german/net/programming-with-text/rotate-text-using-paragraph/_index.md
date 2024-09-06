---
title: Drehen Sie Text mithilfe von Absätzen in einer PDF-Datei
linktitle: Drehen Sie Text mithilfe von Absätzen in einer PDF-Datei
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Text mithilfe von Absätzen in einer PDF-Datei drehen.
type: docs
weight: 380
url: /de/net/programming-with-text/rotate-text-using-paragraph/
---
Dieses Tutorial erklärt, wie Sie mit Aspose.PDF für .NET Text mithilfe von Absätzen drehen. Der bereitgestellte C#-Quellcode demonstriert den Vorgang Schritt für Schritt.

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
using Aspose.Pdf.Text.TextBuilder;
```

## Schritt 3: Erstellen Sie das PDF-Dokument

 Initialisieren Sie den`Document` Objekt zum Erstellen eines neuen PDF-Dokuments:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document();
```

 Ersetzen Sie unbedingt`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

## Schritt 4: Seite hinzufügen

 Rufen Sie eine bestimmte Seite aus dem Dokument ab, indem Sie`Pages.Add()` Verfahren:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## Schritt 5: Textabsatz erstellen

 Erstellen Sie ein`TextParagraph` Objekt und legen Sie seine Position auf der Seite fest:

```csharp
TextParagraph paragraph = new TextParagraph();
paragraph.Position = new Position(200, 600);
```

Passen Sie die Positions-Werte Ihren Anforderungen entsprechend an.

## Schritt 6: Textfragmente erstellen und konfigurieren

 Erstellen Sie mehrere`TextFragment` Objekte und legen Sie deren Text und Eigenschaften fest:

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

Passen Sie den Text und andere Eigenschaften nach Wunsch an.

## Schritt 7: Textfragmente an den Absatz anhängen

 Fügen Sie die erstellten Textfragmente an den Absatz an, indem Sie`AppendLine` Verfahren:

```csharp
paragraph.AppendLine(textFragment1);
paragraph.AppendLine(textFragment2);
paragraph.AppendLine(textFragment3);
```

## Schritt 8: Erstellen Sie einen TextBuilder und hängen Sie den Absatz an

 Erstellen Sie ein`TextBuilder` Objekt mit dem`pdfPage` und hängen Sie den Textabsatz an die PDF-Seite an:

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendParagraph(paragraph);
```

## Schritt 9: Speichern Sie das PDF-Dokument

 Speichern Sie das geänderte PDF-Dokument in einer Datei mit dem`Save` Verfahren:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated2_out.pdf");
```

 Ersetzen Sie unbedingt`"TextFragmentTests_Rotated2_out.pdf"` durch den gewünschten Ausgabedateinamen.

### Beispielquellcode zum Drehen von Text anhand von Absätzen unter Verwendung von Aspose.PDF für .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokumentobjekt initialisieren
Document pdfDocument = new Document();
// Bestimmte Seite abrufen
Page pdfPage = (Page)pdfDocument.Pages.Add();
TextParagraph paragraph = new TextParagraph();
paragraph.Position = new Position(200, 600);
// Textfragment erstellen
TextFragment textFragment1 = new TextFragment("rotated text");
// Texteigenschaften festlegen
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Drehung festlegen
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
// Drehung festlegen
textFragment3.TextState.Rotation = -45;
// Fügen Sie die Textfragmente an den Absatz an
paragraph.AppendLine(textFragment1);
paragraph.AppendLine(textFragment2);
paragraph.AppendLine(textFragment3);
// TextBuilder-Objekt erstellen
TextBuilder textBuilder = new TextBuilder(pdfPage);
// Den Textabschnitt an die PDF-Seite anhängen
textBuilder.AppendParagraph(paragraph);
// Dokument speichern
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated2_out.pdf");
```


## Abschluss

Herzlichen Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.PDF für .NET Text mithilfe von Absätzen in einem PDF-Dokument drehen. Dieses Tutorial bietet eine Schritt-für-Schritt-Anleitung vom Erstellen des Dokuments bis zum Speichern der geänderten Version. Sie können diesen Code jetzt in Ihre eigenen C#-Projekte integrieren, um die Textdrehung in PDF-Dateien zu manipulieren.

### Häufig gestellte Fragen

#### F: Was ist der Zweck des Tutorials „Text mithilfe von Absätzen drehen“?

A: Das Tutorial „Text mit Absatz drehen“ führt Sie durch den Prozess der Verwendung der Aspose.PDF-Bibliothek für .NET, um Text mit Textabsätzen in einem PDF-Dokument zu drehen. Das Tutorial enthält schrittweise Anweisungen und Beispielcode zum Erreichen dieser Funktion.

#### F: Was ist mit „Text mithilfe von Absätzen drehen“ gemeint?

A: Mit dem Drehen von Text mithilfe von Absätzen ist die Möglichkeit gemeint, Text in einem PDF-Dokument mithilfe von Textabsätzen zu drehen. Mit dieser Technik können Sie Text in verschiedenen Winkeln oder Positionen innerhalb des PDF-Inhalts ausrichten.

#### F: Warum sollte ich Text in einem PDF-Dokument drehen wollen?

A: Das Drehen von Text in einem PDF-Dokument kann für verschiedene Zwecke nützlich sein, beispielsweise zum Hervorheben bestimmter Inhalte, zum Erstellen künstlerischer Designs oder zum Verbessern von Layout und Lesbarkeit.

#### F: Wie kann ich ein neues PDF-Dokument erstellen?

 A: Um ein neues PDF-Dokument zu erstellen, initialisieren Sie`Document`Objekt aus der Aspose.PDF-Bibliothek. Mit diesem Objekt können Sie dem PDF Seiten und Inhalte hinzufügen.

#### F: Wie drehe ich Text mithilfe von Absätzen?

A: So drehen Sie Text mithilfe von Absätzen:

1.  Erstellen Sie ein`TextParagraph` Objekt.
2.  Erstellen`TextFragment` Objekte mit dem gewünschten Text und Drehwinkeln.
3. Hängen Sie die Textfragmente an den Textabsatz an.
4.  Erstellen Sie ein`TextBuilder` Objekt und hängen Sie den Textabsatz an eine bestimmte PDF-Seite an.

#### F: Kann ich den Drehwinkel einzelner Textfragmente steuern?

 A: Ja, Sie können den Drehwinkel einzelner`TextFragment` Objekte durch Setzen des`TextState.Rotation` -Eigenschaft. Positive Werte bedeuten eine Drehung im Uhrzeigersinn, negative Werte eine Drehung gegen den Uhrzeigersinn.

#### F: Kann ich auf unterschiedliche Textfragmente im selben Absatz unterschiedliche Drehwinkel anwenden?

 A: Ja, Sie können verschiedene Drehwinkel auf verschiedene`TextFragment` Objekte innerhalb desselben Absatzes durch die Einstellung`TextState.Rotation` Eigenschaft jedes Fragments entsprechend.

#### F: Wie speichere ich das gedrehte PDF-Dokument?

A: Um das gedrehte PDF-Dokument zu speichern, verwenden Sie die`Save` Methode der`Document` Objekt und geben Sie den gewünschten Ausgabedateipfad und -namen an.