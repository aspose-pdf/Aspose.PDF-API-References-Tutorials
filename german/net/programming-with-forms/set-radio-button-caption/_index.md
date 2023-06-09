---
title: Legen Sie die Beschriftung der Optionsschaltfläche fest
linktitle: Legen Sie die Beschriftung der Optionsschaltfläche fest
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET die Beschriftung für ein Optionsfeld in einem PDF-Formular festlegen.
type: docs
weight: 280
url: /de/net/programming-with-forms/set-radio-button-caption/
---

In dieser Anleitung erklären wir Schritt für Schritt, wie Sie mit der Aspose.PDF-Bibliothek für .NET die Beschriftung eines Optionsfelds in einem PDF-Formular definieren. Wir zeigen Ihnen, wie Sie auf das Optionsfeldfeld zugreifen, eine neue Optionsfeldoption erstellen und die Schaltflächenbeschriftung anpassen.

## Schritt 1: Konfigurieren des Dokumentenverzeichnisses

 Der erste Schritt besteht darin, das Dokumentverzeichnis zu konfigurieren, in dem sich das PDF-Formular befindet, an dem Sie arbeiten möchten. Du kannst den ... benutzen`dataDir`Variable, um den Verzeichnispfad anzugeben.

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Unbedingt ersetzen`"YOUR DOCUMENTS DIRECTORY"` mit dem tatsächlichen Pfad zu Ihrem Dokumentenverzeichnis.

## Schritt 2: Laden des Quell-PDF-Formulars

 In diesem Schritt laden wir das Quell-PDF-Formular mithilfe von`Aspose.Pdf.Facades.Form`Klasse von Aspose.PDF.

```csharp
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
```

Stellen Sie sicher, dass die PDF-Datei mit dem Formular im angegebenen Dokumentenverzeichnis vorhanden ist.

## Schritt 3: Bearbeiten der Beschriftung des Optionsfelds

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
// Erstellen Sie ein TextParagraph-Objekt
TextParagraph par = new TextParagraph();
// Absatzposition festlegen
par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
// Geben Sie den Zeilenumbruchmodus an
by.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
// Fügen Sie das neue TextFragment zum Absatz hinzu
par.AppendLine(updatedFragment);
// Fügen Sie den TextParagraph mit TextBuilder hinzu
TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
textBuilder.AppendParagraph(par);
field0.DeleteOption("item1");
}
}
```

Passen Sie das Optionsfeld für die Beschriftung und andere Einstellungen nach Bedarf an.

## Schritt 4: Speichern des resultierenden PDF

 Nachdem wir nun mit der Änderung der Beschriftung des Optionsfelds fertig sind, können wir die resultierende PDF-Datei mit speichern`Save` Methode der`Document` Klasse.

```csharp
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

Geben Sie unbedingt den vollständigen Pfad und Dateinamen für die resultierende PDF-Datei an.

### Beispielquellcode für „Optionsfeldbeschriftung festlegen“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Laden Sie das Quell-PDF-Formular
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
		// Erstellen Sie ein TextParagraph-Objekt
		TextParagraph par = new TextParagraph();
		// Absatzposition festlegen
		par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
		// Geben Sie den Zeilenumbruchmodus an
		par.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
		// Fügen Sie dem Absatz ein neues Textfragment hinzu
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

In dieser Anleitung haben wir gelernt, wie man die Aspose.PDF-Bibliothek für .NET verwendet, um die Beschriftung für ein Optionsfeld in einem PDF-Formular festzulegen. Indem Sie die beschriebenen Schritte befolgen, können Sie die Optionen der Optionsfelder anpassen und die Beschriftung nach Bedarf ändern. Erkunden Sie die Funktionen von Aspose.PDF für .NET weiter, um die Möglichkeiten der Bearbeitung von PDF-Dateien zu erweitern.