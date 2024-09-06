---
title: Drehen Sie Text mithilfe eines Textfragments in einer PDF-Datei
linktitle: Drehen Sie Text mithilfe eines Textfragments in einer PDF-Datei
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Text mithilfe von Textfragmenten in einer PDF-Datei drehen.
type: docs
weight: 390
url: /de/net/programming-with-text/rotate-text-using-text-fragment/
---
Dieses Tutorial erklärt, wie Sie mit Aspose.PDF für .NET Text mithilfe von Textfragmenten in einer PDF-Datei drehen. Der bereitgestellte C#-Quellcode demonstriert den Vorgang Schritt für Schritt.

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

## Schritt 5: Textfragmente erstellen

 Erstellen Sie mehrere`TextFragment` Objekte, legen Sie deren Text und Eigenschaften fest und geben Sie ihre Position auf der Seite an:

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

Passen Sie Text, Positionen und andere Eigenschaften nach Wunsch an.

## Schritt 6: Erstellen Sie einen TextBuilder und fügen Sie Textfragmente an

 Erstellen Sie ein`TextBuilder` Objekt mit dem`pdfPage` und hängen Sie die Textfragmente an die PDF-Seite an:

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
```

## Schritt 7: Speichern Sie das PDF-Dokument

 Speichern Sie das geänderte PDF-Dokument in einer Datei mit dem`Save` Verfahren:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

 Ersetzen Sie unbedingt`"TextFragmentTests_Rotated1_out.pdf"` durch den gewünschten Ausgabedateinamen.

### Beispielquellcode zum Drehen von Text mithilfe eines Textfragments unter Verwendung von Aspose.PDF für .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokumentobjekt initialisieren
Document pdfDocument = new Document();
// Bestimmte Seite abrufen
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Textfragment erstellen
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.Position = new Position(100, 600);
// Texteigenschaften festlegen
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Gedrehtes Textfragment erstellen
TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.Position = new Position(200, 600);
// Texteigenschaften festlegen
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 45;
// Gedrehtes Textfragment erstellen
TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.Position = new Position(300, 600);
// Texteigenschaften festlegen
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 90;
// TextBuilder-Objekt erstellen
TextBuilder textBuilder = new TextBuilder(pdfPage);
// Hängen Sie das Textfragment an die PDF-Seite an
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
// Dokument speichern
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

## Abschluss

Herzlichen Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.PDF für .NET Text mithilfe von Textfragmenten in einem PDF-Dokument drehen. Dieses Tutorial bietet eine Schritt-für-Schritt-Anleitung vom Erstellen des Dokuments bis zum Speichern der geänderten Version. Sie können diesen Code jetzt in Ihre eigenen C#-Projekte integrieren, um die Textdrehung in PDF-Dateien zu manipulieren.

### Häufig gestellte Fragen

#### F: Was ist der Zweck des Tutorials „Text mit Textfragment drehen“?

A: Das Tutorial „Text mit Textfragment drehen“ führt Sie durch den Prozess der Verwendung der Aspose.PDF-Bibliothek für .NET, um Text mit Textfragmenten in einem PDF-Dokument zu drehen. Das Tutorial enthält schrittweise Anweisungen und Beispielcode zum Erreichen dieser Funktion.

#### F: Was ist mit „Text mithilfe von Textfragmenten drehen“ gemeint?

A: Das Drehen von Text mithilfe von Textfragmenten bezieht sich auf die Möglichkeit, mithilfe der Aspose.PDF-Bibliothek eine Drehung auf einzelne Textfragmente in einem PDF-Dokument anzuwenden. Mit dieser Technik können Sie die Ausrichtung von Text in verschiedenen Winkeln oder Positionen innerhalb des PDF-Inhalts steuern.

#### F: Warum sollte ich Textfragmente in einem PDF-Dokument drehen wollen?

A: Das Drehen von Textfragmenten in einem PDF-Dokument kann für verschiedene Zwecke nützlich sein, beispielsweise zum Hervorheben bestimmter Inhalte, zum Erstellen künstlerischer Designs oder zum Verbessern von Layout und Lesbarkeit.

#### F: Wie richte ich das Projekt für das Tutorial ein?

A: So richten Sie das Projekt ein:

1. Erstellen Sie ein neues C#-Projekt in Ihrer bevorzugten integrierten Entwicklungsumgebung (IDE).
2. Fügen Sie einen Verweis auf die Aspose.PDF-Bibliothek für .NET hinzu.
3. Fügen Sie Ihrer C#-Datei die erforderlichen Using-Direktiven hinzu.

#### F: Wie kann ich ein neues PDF-Dokument erstellen?

 A: Um ein neues PDF-Dokument zu erstellen, initialisieren Sie`Document`Objekt aus der Aspose.PDF-Bibliothek. Mit diesem Objekt können Sie dem PDF Seiten und Inhalte hinzufügen.

#### F: Wie drehe ich Textfragmente mithilfe von Textfragmenten?

A: So drehen Sie Textfragmente mithilfe von Textfragmenten:

1.  Erstellen`TextFragment` Objekte.
2. Legen Sie den Text und die Eigenschaften der Textfragmente fest.
3. Geben Sie die Positionen der Textfragmente auf der Seite an.
4.  Stellen Sie den Drehwinkel mit den`TextState.Rotation` Eigenschaft der Textfragmente.
5.  Erstellen Sie ein`TextBuilder`Objekt und hängen Sie die Textfragmente an die PDF-Seite an.

#### F: Kann ich auf unterschiedliche Textfragmente unterschiedliche Drehwinkel anwenden?

 A: Ja, Sie können verschiedene Drehwinkel auf verschiedene`TextFragment` Objekte. Jedes Textfragment kann seinen eigenen Drehwinkel haben, der mit dem`TextState.Rotation` Eigentum.

#### F: Wie speichere ich das PDF-Dokument mit gedrehten Textfragmenten?

 A: Um das PDF-Dokument mit gedrehten Textfragmenten zu speichern, verwenden Sie die`Save` Methode der`Document` Objekt und geben Sie den gewünschten Ausgabedateipfad und -namen an.