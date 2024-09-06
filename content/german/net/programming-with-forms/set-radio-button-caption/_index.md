---
title: Beschriftung für Optionsfeld festlegen
linktitle: Beschriftung für Optionsfeld festlegen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET die Beschriftung für ein Optionsfeld in einem PDF-Formular festlegen.
type: docs
weight: 280
url: /de/net/programming-with-forms/set-radio-button-caption/
---
In dieser Anleitung erklären wir Schritt für Schritt, wie Sie mit der Aspose.PDF-Bibliothek für .NET die Beschriftung eines Optionsfelds in einem PDF-Formular definieren. Wir zeigen Ihnen, wie Sie auf das Optionsfeldfeld zugreifen, eine neue Optionsfeldoption erstellen und die Schaltflächenbeschriftung anpassen.

## Schritt 1: Konfigurieren des Dokumentverzeichnisses

 Der erste Schritt besteht darin, das Dokumentverzeichnis zu konfigurieren, in dem sich das zu bearbeitende PDF-Formular befindet. Sie können das`dataDir` Variable zum Angeben des Verzeichnispfads.

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Ersetzen Sie unbedingt`"YOUR DOCUMENTS DIRECTORY"` durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

## Schritt 2: Laden des PDF-Quellformulars

 In diesem Schritt laden wir das Quell-PDF-Formular mit dem`Aspose.Pdf.Facades.Form` Klasse von Aspose.PDF.

```csharp
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
```

Stellen Sie sicher, dass die PDF-Datei mit dem Formular im angegebenen Dokumentenverzeichnis vorhanden ist.

## Schritt 3: Bearbeiten der Optionsfeldbeschriftung

Wir durchlaufen die Formularfeldnamen und suchen nach Optionsfeldfeldern. Wenn ein passendes Feld gefunden wird, erstellen wir eine neue Optionsfeldoption mit einer benutzerdefinierten Beschriftung und fügen sie dem vorhandenen Feld hinzu.

```csharp
foreach(var item in form1.FieldNames)
{
if (item.Contains("radio1"))
{
Aspose.Pdf.Forms.RadioButtonField field0 = PDF_Template_PDF_HTML.Form[item] as Aspose.Pdf.Forms.RadioButtonField;
Aspose.Pdf.Forms.RadioButtonOptionField fieldoption = new Aspose.Pdf.Forms.RadioButtonOptionField();
fieldoption.OptionName = "Yes";
fieldoption.PartialName = "Yesname";
var updatedFragment = new Aspose.Pdf.Text.TextFragment("test123");
updatedFragment.TextState.Font = FontRepository.FindFont("Arial");
updatedFragment.TextState.FontSize = 10;
updatedFragment.TextState.LineSpacing = 6.32f;
// Erstellen eines TextParagraph-Objekts
TextParagraph par = new TextParagraph();
// Absatzposition festlegen
par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
// Festlegen des Zeilenumbruchmodus
by.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
// Fügen Sie dem Absatz das neue TextFragment hinzu
par.AppendLine(updatedFragment);
// Fügen Sie den TextParagraph mit TextBuilder hinzu
TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
textBuilder.AppendParagraph(par);
field0.DeleteOption("item1");
}
}
```

Passen Sie das Optionsfeld für die Beschriftung und andere Einstellungen nach Bedarf an.

## Schritt 4: Speichern der resultierenden PDF-Datei

 Nachdem wir nun die Beschriftung des Optionsfelds geändert haben, können wir das resultierende PDF mit dem`Save` Methode der`Document` Klasse.

```csharp
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

Geben Sie unbedingt den vollständigen Pfad und Dateinamen für die resultierende PDF-Datei an.

### Beispielquellcode zum Festlegen der Radiobutton-Beschriftung mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Quell-PDF-Formular laden
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
Document PDF_Template_PDF_HTML = new Document(dataDir + "RadioButtonField.pdf");
foreach (var item in form1.FieldNames)
{
	Console.WriteLine(item.ToString());
	Dictionary<string, string> radioOptions = form1.GetButtonOptionValues(item);
	if (item.Contains("radio1"))
	{
		Aspose.Pdf.Forms.RadioButtonField field0 = PDF_Template_PDF_HTML.Form[item] as Aspose.Pdf.Forms.RadioButtonField;
		Aspose.Pdf.Forms.RadioButtonOptionField fieldoption = new Aspose.Pdf.Forms.RadioButtonOptionField();
		fieldoption.OptionName = "Yes";
		fieldoption.PartialName = "Yesname";
		var updatedFragment = new Aspose.Pdf.Text.TextFragment("test123");
		updatedFragment.TextState.Font = FontRepository.FindFont("Arial");
		updatedFragment.TextState.FontSize = 10;
		updatedFragment.TextState.LineSpacing = 6.32f;
		// TextParagraph-Objekt erstellen
		TextParagraph par = new TextParagraph();
		// Absatzposition festlegen
		par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
		// Festlegen des Zeilenumbruchmodus
		par.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
		// Neues TextFragment zum Absatz hinzufügen
		par.AppendLine(updatedFragment);
		// Fügen Sie den TextParagraph mit TextBuilder hinzu
		TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
		textBuilder.AppendParagraph(par);
		field0.DeleteOption("item1");
	}
}
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

## Abschluss

In dieser Anleitung haben wir gelernt, wie man mit der Aspose.PDF-Bibliothek für .NET die Beschriftung für ein Optionsfeld in einem PDF-Formular festlegt. Indem Sie die beschriebenen Schritte befolgen, können Sie die Optionsfeldoptionen anpassen und die Beschriftung nach Bedarf ändern. Erkunden Sie die Funktionen von Aspose.PDF für .NET weiter, um die Möglichkeiten zur Bearbeitung von PDF-Dateien zu erweitern.

### Häufig gestellte Fragen

#### F: Kann ich Aspose.PDF für .NET verwenden, um Beschriftungen für Optionsfelder in einem PDF-Formular festzulegen?

A: Ja, Sie können Aspose.PDF für .NET verwenden, um Beschriftungen für Optionsfelder in einem PDF-Formular festzulegen. Der bereitgestellte Beispielquellcode zeigt, wie Sie auf das Optionsfeld zugreifen, eine neue Optionsfeldoption mit einer benutzerdefinierten Beschriftung erstellen und das vorhandene Feld aktualisieren.

#### F: Wie kann ich das Erscheinungsbild der Optionsfeldbeschriftung, beispielsweise Schriftgröße und Farbe, anpassen?

 A: Sie können das Erscheinungsbild der Optionsfeldbeschriftung anpassen, indem Sie die Eigenschaften des`TextFragment` für die Überschrift verwendet. Sie können beispielsweise Schriftart, Schriftgröße, Farbe, Zeilenabstand und andere Textformatierungsoptionen festlegen.

#### F: Ist es möglich, einer einzigen Optionsfeldgruppe mehrere Optionsfeldoptionen mit unterschiedlichen Beschriftungen hinzuzufügen?

A: Ja, Sie können einer einzelnen Optionsfeldgruppe mehrere Optionsfeldoptionen mit unterschiedlichen Beschriftungen hinzufügen. Jede Option stellt eine andere Auswahl dar und Benutzer können nur eine Option aus der Gruppe auswählen.

#### F: Kann ich Aspose.PDF für .NET verwenden, um andere Formularfelder in einem PDF-Dokument zu ändern?

A: Ja, Aspose.PDF für .NET bietet einen umfassenden Satz von Funktionen zum Bearbeiten verschiedener Formularfelder in einem PDF-Dokument, z. B. Textfelder, Kontrollkästchen, Dropdown-Listen und mehr. Sie können die Bibliothek verwenden, um Werte festzulegen, das Erscheinungsbild zu ändern und Formularfeldern Interaktivität hinzuzufügen.

#### F: Unterstützt Aspose.PDF für .NET die Arbeit mit PDFs, die aus anderen Quellen generiert wurden, wie z. B. gescannten Dokumenten?

A: Ja, Aspose.PDF für .NET unterstützt die Arbeit mit PDFs, die aus verschiedenen Quellen generiert wurden, einschließlich gescannter Dokumente. Die Bibliothek bietet OCR-Funktionen (Optical Character Recognition), um Text aus gescannten PDFs zu extrahieren und den Inhalt programmgesteuert zu bearbeiten.