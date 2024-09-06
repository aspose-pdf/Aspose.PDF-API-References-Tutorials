---
title: Drehen Sie Text mithilfe von Textabsätzen und -generator in einer PDF-Datei
linktitle: Drehen Sie Text mithilfe von Textabsätzen und -generator in einer PDF-Datei
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Text mithilfe von Textabsätzen und -generator in einer PDF-Datei drehen.
type: docs
weight: 410
url: /de/net/programming-with-text/rotate-text-using-text-paragraph-and-builder/
---
Dieses Tutorial erklärt, wie Sie mit Aspose.PDF für .NET Text mithilfe von Textabsätzen und Buildern in PDF-Dateien drehen. Der bereitgestellte C#-Quellcode demonstriert den Vorgang Schritt für Schritt.

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

## Schritt 5: Textabsätze erstellen und drehen

 Erstellen Sie ein`for` Schleife zum Erzeugen mehrerer Textabsätze mit unterschiedlichen Rotationen:

```csharp
for (int i = 0; i < 4; i++)
{
	TextParagraph paragraph = new TextParagraph();
	paragraph.Position = new Position(200, 600);
	paragraph.Rotation = i * 90 + 45;
```

Passen Sie die Positions- und Rotationswerte Ihren Anforderungen entsprechend an.

## Schritt 6: Textfragmente erstellen und konfigurieren

 Erstellen Sie mehrere`TextFragment` Objekte, legen Sie deren Text und Eigenschaften fest:

```csharp
TextFragment textFragment1 = new TextFragment("Paragraph Text");
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment1.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment1.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;

TextFragment textFragment2 = new TextFragment("Second line of text");
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment2.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;

TextFragment textFragment3 = new TextFragment("And some more text...");
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment3.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
textFragment3.TextState.Underline = true;
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
}
```

## Schritt 9: Speichern Sie das PDF-Dokument

 Speichern Sie das geänderte PDF-Dokument in einer Datei mit dem`Save` Verfahren:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated4_out.pdf");
```

 Ersetzen Sie unbedingt`"TextFragmentTests_Rotated4_out.pdf"` durch den gewünschten Ausgabedateinamen.

### Beispielquellcode zum Drehen von Text mithilfe von Textabsätzen und Builder unter Verwendung von Aspose.PDF für .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokumentobjekt initialisieren
Document pdfDocument = new Document();
// Bestimmte Seite abrufen
Page pdfPage = (Page)pdfDocument.Pages.Add();
for (int i = 0; i < 4; i++)
{
	TextParagraph paragraph = new TextParagraph();
	paragraph.Position = new Position(200, 600);
	// Festlegen der Drehung
	paragraph.Rotation = i * 90 + 45;
	// Textfragment erstellen
	TextFragment textFragment1 = new TextFragment("Paragraph Text");
	// Textfragment erstellen
	textFragment1.TextState.FontSize = 12;
	textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
	textFragment1.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
	textFragment1.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	// Textfragment erstellen
	TextFragment textFragment2 = new TextFragment("Second line of text");
	// Texteigenschaften festlegen
	textFragment2.TextState.FontSize = 12;
	textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
	textFragment2.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
	textFragment2.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	// Textfragment erstellen
	TextFragment textFragment3 = new TextFragment("And some more text...");
	// Texteigenschaften festlegen
	textFragment3.TextState.FontSize = 12;
	textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
	textFragment3.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
	textFragment3.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	textFragment3.TextState.Underline = true;
	paragraph.AppendLine(textFragment1);
	paragraph.AppendLine(textFragment2);
	paragraph.AppendLine(textFragment3);
	// TextBuilder-Objekt erstellen
	TextBuilder textBuilder = new TextBuilder(pdfPage);
	// Hängen Sie das Textfragment an die PDF-Seite an
	textBuilder.AppendParagraph(paragraph);
}
// Dokument speichern
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated4_out.pdf");
```

## Abschluss

Herzlichen Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.PDF für .NET Text mithilfe von Textabsätzen und Buildern in einem PDF-Dokument drehen. Dieses Tutorial bietet eine Schritt-für-Schritt-Anleitung vom Erstellen des Dokuments bis zum Speichern der geänderten Version. Sie können diesen Code jetzt in Ihre eigenen C#-Projekte integrieren, um die Textdrehung in PDF-Dateien zu manipulieren.

### Häufig gestellte Fragen

#### F: Was ist der Zweck des Tutorials „Text mit Textabsatz und -generator drehen“?

A: Das Tutorial „Text mit Textabsatz und Builder drehen“ bietet eine umfassende Anleitung zur Verwendung der Aspose.PDF-Bibliothek für .NET zum Drehen von Text mit Textabsätzen und Buildern in einem PDF-Dokument. Das Tutorial zeigt schrittweise Anweisungen und enthält Beispiel-C#-Code zum Erreichen einer Textdrehung mit Absätzen und benutzerdefinierter Formatierung.

#### F: Wie unterscheidet sich dieses Tutorial von früheren Tutorials zur Textrotation?

A: Im Gegensatz zu früheren Tutorials kombiniert dieses Tutorial die Verwendung von Textabsätzen, Buildern und Rotationswinkeln, um einen fortgeschritteneren Textrotationseffekt zu erzielen. Es zeigt, wie Sie mehrere Textabsätze mit unterschiedlichen Rotationswinkeln generieren und benutzerdefinierte Formatierungen auf einzelne Textfragmente anwenden.

#### F: Welche Bedeutung hat die Verwendung von Textabsätzen und Buildern für die Textrotation?

A: Die Verwendung von Textabsätzen und Buildern ermöglicht eine bessere Kontrolle über Textrotation und -formatierung. Textabsätze bieten eine strukturierte Möglichkeit, Textfragmente zu organisieren, während Builder die Erstellung und Bearbeitung von Textinhalten im PDF-Dokument erleichtern.

#### F: Kann ich jedem Textabsatz einen anderen Drehwinkel zuweisen?

 A: Ja, Sie können jedem Textabschnitt einen anderen Drehwinkel zuweisen, indem Sie die`Rotation` Eigentum der`TextParagraph` Objekt. Dadurch können Sie vielfältige und dynamische Textrotationseffekte innerhalb des PDF-Dokuments erstellen.

#### F: Wie passe ich die Formatierung von Textfragmenten innerhalb der Textabsätze an?

 A: Sie können die Formatierung von Textfragmenten anpassen, indem Sie verschiedene Eigenschaften des`TextState` innerhalb jedes`TextFragment` Objekt. Eigenschaften wie Schriftgröße, Schriftart, Vordergrund- und Hintergrundfarben sowie Unterstreichungen können angepasst werden, um den gewünschten visuellen Effekt zu erzielen.

#### F: Kann ich mit dieser Methode komplexere Textrotationseffekte erstellen?

A: Auf jeden Fall. Indem Sie iterativ mehrere Textabsätze mit unterschiedlichen Drehwinkeln und Formatierungsoptionen erstellen, können Sie komplexe und optisch ansprechende Textdreheffekte erzielen, die die Lesbarkeit und Ästhetik Ihrer PDF-Dokumente verbessern können.

#### F: Ist es möglich, die Textdrehung mit anderen Textbearbeitungstechniken zu kombinieren?

A: Ja, Sie können die Textrotation mit anderen Textbearbeitungstechniken kombinieren, die von der Aspose.PDF-Bibliothek bereitgestellt werden. Dazu gehört das Hinzufügen von Tabellen, Bildern, Hyperlinks und mehr, um umfangreiche und informative PDF-Dokumente zu erstellen.

#### F: Benötige ich eine spezielle Lizenz, um die Aspose.PDF-Bibliothek in meinem Projekt zu verwenden?

A: Ja, Sie benötigen eine gültige Aspose-Lizenz, um die Aspose.PDF-Bibliothek in Ihrem Projekt verwenden zu können. Sie können eine Lizenz von der Aspose-Website erhalten, die Ihnen die erforderlichen Anmeldeinformationen zur Verfügung stellt, um die Bibliothek effektiv zu integrieren und zu verwenden.