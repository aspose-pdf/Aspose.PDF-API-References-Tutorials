---
title: Drehen Sie Text mithilfe von Textfragmenten und Absätzen
linktitle: Drehen Sie Text mithilfe von Textfragmenten und Absätzen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Text mithilfe von Textfragmenten und Absätzen in einem PDF-Dokument drehen.
type: docs
weight: 400
url: /de/net/programming-with-text/rotate-text-using-text-fragment-and-paragraph/
---
Dieses Tutorial erklärt, wie Sie mit Aspose.PDF für .NET Text mithilfe von Textfragmenten und Absätzen drehen. Der bereitgestellte C#-Quellcode demonstriert den Vorgang Schritt für Schritt.

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

 Erstellen Sie mehrere`TextFragment` Objekte, legen Sie deren Text und Eigenschaften fest und geben Sie den Drehwinkel an:

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

Passen Sie Text, Drehwinkel und andere Eigenschaften nach Wunsch an.

## Schritt 6: Textfragmente zur Seite hinzufügen

 Fügen Sie die erstellten Textfragmente zur Seite hinzu, indem Sie sie an die`Paragraphs` Sammlung:

```csharp
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
```

## Schritt 7: Speichern Sie das PDF-Dokument

 Speichern Sie das geänderte PDF-Dokument in einer Datei mit dem`Save` Verfahren:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

 Ersetzen Sie unbedingt`"TextFragmentTests_Rotated3_out.pdf"` durch den gewünschten Ausgabedateinamen.

### Beispielquellcode zum Drehen von Text mithilfe von Textfragmenten und Absätzen unter Verwendung von Aspose.PDF für .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokumentobjekt initialisieren
Document pdfDocument = new Document();
// Bestimmte Seite abrufen
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
// Drehung festlegen
textFragment2.TextState.Rotation = 315;
// Textfragment erstellen
TextFragment textFragment3 = new TextFragment("rotated text");
// Texteigenschaften festlegen
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Drehung festlegen
textFragment3.TextState.Rotation = 270;
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
// Dokument speichern
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

## Abschluss

Herzlichen Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.PDF für .NET Text mithilfe von Textfragmenten und Absätzen in einem PDF-Dokument drehen. Dieses Tutorial bietet eine Schritt-für-Schritt-Anleitung vom Erstellen des Dokuments bis zum Speichern der geänderten Version. Sie können diesen Code jetzt in Ihre eigenen C#-Projekte integrieren, um die Textdrehung in PDF-Dateien zu manipulieren.

### Häufig gestellte Fragen

#### F: Was ist der Zweck des Tutorials „Text mithilfe von Textfragmenten und Absätzen drehen“?

A: Das Tutorial „Text mit Textfragmenten und Absätzen drehen“ führt Sie durch den Prozess der Verwendung der Aspose.PDF-Bibliothek für .NET, um Text mit Textfragmenten und Absätzen in einem PDF-Dokument zu drehen. Das Tutorial enthält schrittweise Anweisungen und Beispielcode zum Erreichen dieser Funktion.

#### F: Worin unterscheidet sich dieses Tutorial von den vorherigen Tutorials zur Textrotation?

A: Dieses Tutorial kombiniert die Verwendung von Textfragmenten und Absätzen, um eine Textrotation innerhalb eines PDF-Dokuments zu erreichen. Es zeigt, wie man Textfragmente einzeln dreht und sie dann zum Seitenlayout hinzufügt.`Paragraphs` Sammlung, um einen umfassenderen Textrotationseffekt zu erzielen.

#### F: Welche Vorteile bietet die Verwendung von Textfragmenten und Absätzen zur Textrotation?

A: Die gemeinsame Verwendung von Textfragmenten und Absätzen ermöglicht mehr Flexibilität bei der Textrotation. Textfragmente ermöglichen individuelle Rotations- und Formatierungseinstellungen, während Absätze eine Struktur für die Anordnung und Positionierung von Textfragmenten innerhalb einer Seite bieten.

#### F: Kann ich auf unterschiedliche Textfragmente im selben Absatz unterschiedliche Drehwinkel anwenden?

 A: Ja, Sie können verschiedene Drehwinkel auf verschiedene`TextFragment` Objekte innerhalb desselben Absatzes. Für jedes Textfragment kann ein eigener Drehwinkel mit dem`TextState.Rotation` Eigentum.

#### F: Ist es möglich, mit dieser Methode komplexe Textrotationseffekte zu erzielen?

A: Ja, indem Sie Textfragmente mit verschiedenen Drehwinkeln kombinieren und in Absätzen anordnen, können Sie komplexe und benutzerdefinierte Textdreheffekte erzielen und so die visuelle Attraktivität Ihrer PDF-Dokumente steigern.

#### F: Welche Schritte sind beim Rotieren von Text mithilfe von Textfragmenten und Absätzen erforderlich?

A: Die Schritte umfassen:

1. Einrichten des Projekts durch Erstellen eines neuen C#-Projekts und Hinzufügen eines Verweises auf die Aspose.PDF-Bibliothek für .NET.
2. Erstellen des PDF-Dokuments und Hinzufügen einer Seite.
3. Erstellen von Textfragmenten, Festlegen ihrer Eigenschaften und Festlegen von Drehwinkeln.
4.  Hinzufügen von Textfragmenten zur Seite mithilfe der`Paragraphs` Sammlung.
5. Speichern des geänderten PDF-Dokuments.

#### F: Kann ich die Drehung auf ganze Absätze anwenden?

 A: Ja, Sie können die Rotation auf ganze Absätze anwenden, indem Sie die`TextState.Rotation` Eigenschaft des Absatzes selbst. Dadurch werden alle Textfragmente innerhalb dieses Absatzes gedreht.