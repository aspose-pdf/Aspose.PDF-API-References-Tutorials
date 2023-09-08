---
title: Drehen Sie Text mit Textabsatz und Builder in einer PDF-Datei
linktitle: Drehen Sie Text mit Textabsatz und Builder in einer PDF-Datei
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Text mithilfe des Textabsatz- und Builder-Programms in einer PDF-Datei drehen.
type: docs
weight: 410
url: /de/net/programming-with-text/rotate-text-using-text-paragraph-and-builder/
---
In diesem Tutorial wird erläutert, wie Sie mit Aspose.PDF für .NET Text mithilfe von Textabsätzen und Buildern in einer PDF-Datei drehen. Der bereitgestellte C#-Quellcode demonstriert den Prozess Schritt für Schritt.

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

## Schritt 5: Textabsätze erstellen und drehen

 Ein ... kreieren`for` Schleife zum Generieren mehrerer Textabsätze mit unterschiedlichen Drehungen:

```csharp
for (int i = 0; i < 4; i++)
{
	TextParagraph paragraph = new TextParagraph();
	paragraph.Position = new Position(200, 600);
	paragraph.Rotation = i * 90 + 45;
```

Passen Sie die Positions- und Rotationswerte entsprechend Ihren Anforderungen an.

## Schritt 6: Textfragmente erstellen und konfigurieren

 Mehrere erstellen`TextFragment` Objekte, legen Sie deren Text und Eigenschaften fest:

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

Passen Sie den Text und andere Eigenschaften nach Bedarf an.

## Schritt 7: Textfragmente an den Absatz anhängen

 Hängen Sie die erstellten Textfragmente mit an den Absatz an`AppendLine` Methode:

```csharp
paragraph.AppendLine(textFragment1);
paragraph.AppendLine(textFragment2);
paragraph.AppendLine(textFragment3);
```

## Schritt 8: Erstellen Sie einen TextBuilder und hängen Sie den Absatz an

 Ein ... kreieren`TextBuilder` Objekt mit der`pdfPage` und hängen Sie den Textabsatz an die PDF-Seite an:

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendParagraph(paragraph);
}
```

## Schritt 9: Speichern Sie das PDF-Dokument

 Speichern Sie das geänderte PDF-Dokument mit in einer Datei`Save` Methode:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated4_out.pdf");
```

 Unbedingt austauschen`"TextFragmentTests_Rotated4_out.pdf"` mit dem gewünschten Ausgabedateinamen.

### Beispielquellcode für Rotate Text Using Text Paragraph And Builder mit Aspose.PDF für .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokumentobjekt initialisieren
Document pdfDocument = new Document();
// Holen Sie sich eine bestimmte Seite
Page pdfPage = (Page)pdfDocument.Pages.Add();
for (int i = 0; i < 4; i++)
{
	TextParagraph paragraph = new TextParagraph();
	paragraph.Position = new Position(200, 600);
	// Geben Sie die Drehung an
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
	// Erstellen Sie ein TextBuilder-Objekt
	TextBuilder textBuilder = new TextBuilder(pdfPage);
	// Hängen Sie das Textfragment an die PDF-Seite an
	textBuilder.AppendParagraph(paragraph);
}
// Dokument speichern
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated4_out.pdf");
```

## Abschluss

Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.PDF für .NET Text mithilfe von Textabsätzen und Buildern in einem PDF-Dokument drehen. Dieses Tutorial bietet eine Schritt-für-Schritt-Anleitung von der Erstellung des Dokuments bis zum Speichern der geänderten Version. Sie können diesen Code jetzt in Ihre eigenen C#-Projekte integrieren, um die Textrotation in PDF-Dateien zu manipulieren.

### FAQs

#### F: Was ist der Zweck des Tutorials „Text mit Textabsatz und Builder drehen“?

A: Das Tutorial „Text mit Textabsätzen und Builder drehen“ bietet eine umfassende Anleitung zur Verwendung der Aspose.PDF-Bibliothek für .NET zum Drehen von Text mithilfe von Textabsätzen und Buildern in einem PDF-Dokument. Das Tutorial zeigt Schritt-für-Schritt-Anleitungen und enthält Beispiel-C#-Code zum Erzielen einer Textrotation mit Absätzen und benutzerdefinierter Formatierung.

#### F: Wie unterscheidet sich dieses Tutorial von früheren Tutorials zur Textrotation?

A: Im Gegensatz zu früheren Tutorials kombiniert dieses Tutorial die Verwendung von Textabsätzen, Buildern und Drehwinkeln, um einen fortgeschritteneren Textrotationseffekt zu erzielen. Es zeigt, wie Sie mehrere Textabsätze mit unterschiedlichen Drehwinkeln generieren und benutzerdefinierte Formatierungen auf einzelne Textfragmente anwenden.

#### F: Welche Bedeutung hat die Verwendung von Textabsätzen und Buildern für die Textrotation?

A: Die Verwendung von Textabsätzen und Buildern ermöglicht eine bessere Kontrolle über die Textdrehung und -formatierung. Textabsätze bieten eine strukturierte Möglichkeit, Textfragmente zu organisieren, während Builder die Erstellung und Bearbeitung von Textinhalten im PDF-Dokument erleichtern.

#### F: Kann ich auf jeden Textabsatz unterschiedliche Drehwinkel anwenden?

 A: Ja, Sie können auf jeden Textabsatz unterschiedliche Drehwinkel anwenden, indem Sie festlegen`Rotation` Eigentum der`TextParagraph` Objekt. Dadurch können Sie vielfältige und dynamische Textrotationseffekte innerhalb des PDF-Dokuments erzeugen.

#### F: Wie kann ich die Formatierung von Textfragmenten innerhalb der Textabsätze anpassen?

 A: Sie können die Formatierung von Textfragmenten anpassen, indem Sie verschiedene Eigenschaften festlegen`TextState` innerhalb jeden`TextFragment` Objekt. Eigenschaften wie Schriftgröße, Schriftart, Vordergrund- und Hintergrundfarben sowie Unterstreichungen können angepasst werden, um den gewünschten visuellen Effekt zu erzielen.

#### F: Kann ich mit dieser Methode komplexere Textrotationseffekte erstellen?

A: Absolut. Durch die iterative Erstellung mehrerer Textabsätze mit unterschiedlichen Drehwinkeln und Formatierungsoptionen können Sie komplexe und optisch ansprechende Texterotationseffekte erzielen, die die Lesbarkeit und Ästhetik Ihrer PDF-Dokumente verbessern können.

#### F: Ist es möglich, die Textdrehung mit anderen Techniken zur Textbearbeitung zu kombinieren?

A: Ja, Sie können die Textdrehung mit anderen Textbearbeitungstechniken kombinieren, die von der Aspose.PDF-Bibliothek bereitgestellt werden. Dazu gehört das Hinzufügen von Tabellen, Bildern, Hyperlinks und mehr, um umfangreiche und informative PDF-Dokumente zu erstellen.

#### F: Benötige ich eine spezielle Lizenz, um die Aspose.PDF-Bibliothek in meinem Projekt zu verwenden?

A: Ja, Sie benötigen eine gültige Aspose-Lizenz, um die Aspose.PDF-Bibliothek in Ihrem Projekt verwenden zu können. Sie können auf der Aspose-Website eine Lizenz erwerben, die Ihnen die erforderlichen Anmeldeinformationen für die effektive Integration und Nutzung der Bibliothek bietet.