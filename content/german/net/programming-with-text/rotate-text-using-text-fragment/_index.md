---
title: Drehen Sie Text mithilfe eines Textfragments in einer PDF-Datei
linktitle: Drehen Sie Text mithilfe eines Textfragments in einer PDF-Datei
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Text mithilfe von Textfragmenten in einer PDF-Datei drehen.
type: docs
weight: 390
url: /de/net/programming-with-text/rotate-text-using-text-fragment/
---
In diesem Tutorial wird erläutert, wie Sie mit Aspose.PDF für .NET Text mithilfe von Textfragmenten in einer PDF-Datei drehen. Der bereitgestellte C#-Quellcode demonstriert den Prozess Schritt für Schritt.

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

## Schritt 5: Textfragmente erstellen

 Mehrere erstellen`TextFragment` Objekte, legen Sie ihren Text und ihre Eigenschaften fest und geben Sie ihre Positionen auf der Seite an:

```csharp
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.Position = new Position(100, 600);
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");

TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.Position = new Position(200, 600);
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 45;

TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.Position = new Position(300, 600);
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 90;
```

Passen Sie Text, Positionen und andere Eigenschaften nach Bedarf an.

## Schritt 6: Erstellen Sie einen TextBuilder und hängen Sie Textfragmente an

 Ein ... kreieren`TextBuilder` Objekt mit der`pdfPage` und hängen Sie die Textfragmente an die PDF-Seite an:

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
```

## Schritt 7: Speichern Sie das PDF-Dokument

 Speichern Sie das geänderte PDF-Dokument mit in einer Datei`Save` Methode:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

 Unbedingt austauschen`"TextFragmentTests_Rotated1_out.pdf"` mit dem gewünschten Ausgabedateinamen.

### Beispielquellcode für „Text mithilfe von Textfragmenten drehen“ mit Aspose.PDF für .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokumentobjekt initialisieren
Document pdfDocument = new Document();
// Holen Sie sich eine bestimmte Seite
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Textfragment erstellen
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.Position = new Position(100, 600);
// Texteigenschaften festlegen
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Erstellen Sie ein gedrehtes Textfragment
TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.Position = new Position(200, 600);
// Texteigenschaften festlegen
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 45;
// Erstellen Sie ein gedrehtes Textfragment
TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.Position = new Position(300, 600);
// Texteigenschaften festlegen
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 90;
// Erstellen Sie ein TextBuilder-Objekt
TextBuilder textBuilder = new TextBuilder(pdfPage);
// Hängen Sie das Textfragment an die PDF-Seite an
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
// Dokument speichern
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

## Abschluss

Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.PDF für .NET Text mithilfe von Textfragmenten in einem PDF-Dokument drehen. Dieses Tutorial bietet eine Schritt-für-Schritt-Anleitung von der Erstellung des Dokuments bis zum Speichern der geänderten Version. Sie können diesen Code jetzt in Ihre eigenen C#-Projekte integrieren, um die Textrotation in PDF-Dateien zu manipulieren.

### FAQs

#### F: Was ist der Zweck des Tutorials „Text mithilfe von Textfragmenten drehen“?

A: Das Tutorial „Text mithilfe von Textfragmenten drehen“ soll Sie durch den Prozess der Verwendung der Aspose.PDF-Bibliothek für .NET führen, um Text mithilfe von Textfragmenten in einem PDF-Dokument zu drehen. Das Tutorial bietet Schritt-für-Schritt-Anleitungen und Beispielcode, um diese Funktionalität zu erreichen.

#### F: Was versteht man unter „Text mithilfe von Textfragmenten drehen“?

A: Das Drehen von Text mithilfe von Textfragmenten bezieht sich auf die Möglichkeit, mithilfe der Aspose.PDF-Bibliothek einzelne Textfragmente innerhalb eines PDF-Dokuments zu drehen. Mit dieser Technik können Sie die Ausrichtung von Text in verschiedenen Winkeln oder Positionen innerhalb des PDF-Inhalts steuern.

#### F: Warum sollte ich Textfragmente in einem PDF-Dokument drehen wollen?

A: Das Rotieren von Textfragmenten in einem PDF-Dokument kann für verschiedene Zwecke nützlich sein, z. B. um bestimmte Inhalte hervorzuheben, künstlerische Designs zu erstellen oder das Layout und die Lesbarkeit zu verbessern.

#### F: Wie richte ich das Projekt für das Tutorial ein?

A: So richten Sie das Projekt ein:

1. Erstellen Sie ein neues C#-Projekt in Ihrer bevorzugten integrierten Entwicklungsumgebung (IDE).
2. Fügen Sie einen Verweis auf die Aspose.PDF für .NET-Bibliothek hinzu.
3. Fügen Sie Ihrer C#-Datei die erforderlichen using-Anweisungen hinzu.

#### F: Wie kann ich ein neues PDF-Dokument erstellen?

 A: Um ein neues PDF-Dokument zu erstellen, initialisieren Sie a`Document`Objekt aus der Aspose.PDF-Bibliothek. Mit diesem Objekt können Sie Seiten und Inhalte zum PDF hinzufügen.

#### F: Wie drehe ich Textfragmente mithilfe von Textfragmenten?

A: So drehen Sie Textfragmente mithilfe von Textfragmenten:

1.  Erstellen`TextFragment` Objekte.
2. Legen Sie den Text und die Eigenschaften der Textfragmente fest.
3. Geben Sie die Positionen der Textfragmente auf der Seite an.
4.  Stellen Sie den Drehwinkel mit ein`TextState.Rotation` Eigenschaft der Textfragmente.
5.  Ein ... kreieren`TextBuilder`Objekt und hängen Sie die Textfragmente an die PDF-Seite an.

#### F: Kann ich unterschiedliche Drehwinkel auf verschiedene Textfragmente anwenden?

 A: Ja, Sie können unterschiedliche Drehwinkel auf verschiedene anwenden`TextFragment` Objekte. Für jedes Textfragment kann ein eigener Drehwinkel angegeben werden`TextState.Rotation` Eigentum.

#### F: Wie speichere ich das PDF-Dokument mit gedrehten Textfragmenten?

 A: Um das PDF-Dokument mit gedrehten Textfragmenten zu speichern, verwenden Sie die`Save` Methode der`Document` Objekt und geben Sie den gewünschten Pfad und Namen der Ausgabedatei an.