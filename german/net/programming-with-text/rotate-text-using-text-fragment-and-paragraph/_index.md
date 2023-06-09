---
title: Drehen Sie Text mithilfe von Textfragmenten und Absätzen
linktitle: Drehen Sie Text mithilfe von Textfragmenten und Absätzen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Text mithilfe von Textfragmenten und Absätzen in einem PDF-Dokument drehen.
type: docs
weight: 400
url: /de/net/programming-with-text/rotate-text-using-text-fragment-and-paragraph/
---

In diesem Tutorial wird erläutert, wie Sie Aspose.PDF für .NET verwenden, um Text mithilfe von Textfragmenten und Absätzen zu drehen. Der bereitgestellte C#-Quellcode demonstriert den Prozess Schritt für Schritt.

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

 Mehrere erstellen`TextFragment` Objekte, legen Sie deren Text und Eigenschaften fest und geben Sie den Drehwinkel an:

```csharp
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");

TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 315;

TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 270;
```

Passen Sie den Text, den Drehwinkel und andere Eigenschaften nach Bedarf an.

## Schritt 6: Fügen Sie der Seite Textfragmente hinzu

 Fügen Sie die erstellten Textfragmente der Seite hinzu, indem Sie sie anhängen`Paragraphs` Sammlung:

```csharp
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
```

## Schritt 7: Speichern Sie das PDF-Dokument

 Speichern Sie das geänderte PDF-Dokument mit in einer Datei`Save` Methode:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

 Unbedingt austauschen`"TextFragmentTests_Rotated3_out.pdf"` mit dem gewünschten Ausgabedateinamen.

### Beispielquellcode für „Text drehen mit Textfragment und Absatz“ mit Aspose.PDF für .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokumentobjekt initialisieren
Document pdfDocument = new Document();
// Holen Sie sich eine bestimmte Seite
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Textfragment erstellen
TextFragment textFragment1 = new TextFragment("main text");
// Texteigenschaften festlegen
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Textfragment erstellen
TextFragment textFragment2 = new TextFragment("rotated text");
// Texteigenschaften festlegen
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Rotation einstellen
textFragment2.TextState.Rotation = 315;
// Textfragment erstellen
TextFragment textFragment3 = new TextFragment("rotated text");
// Texteigenschaften festlegen
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Rotation einstellen
textFragment3.TextState.Rotation = 270;
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
// Dokument speichern
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

## Abschluss

Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.PDF für .NET Text mithilfe von Textfragmenten und Absätzen in einem PDF-Dokument drehen. Dieses Tutorial bietet eine Schritt-für-Schritt-Anleitung von der Erstellung des Dokuments bis zum Speichern der geänderten Version. Sie können diesen Code jetzt in Ihre eigenen C#-Projekte integrieren, um die Textrotation in PDF-Dateien zu manipulieren.