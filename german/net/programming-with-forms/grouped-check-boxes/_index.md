---
title: Gruppierte Kontrollkästchen
linktitle: Gruppierte Kontrollkästchen
second_title: Aspose.PDF für .NET API-Referenz
description: Erstellen Sie mit Aspose.PDF für .NET ganz einfach gruppierte Kontrollkästchen in Ihren PDF-Dokumenten.
type: docs
weight: 170
url: /de/net/programming-with-forms/grouped-check-boxes/
---

In diesem Tutorial zeigen wir Ihnen, wie Sie mit Aspose.PDF für .NET gruppierte Kontrollkästchen in einem PDF-Dokument erstellen. Wir erklären Ihnen Schritt für Schritt den C#-Quellcode, um Sie durch diesen Prozess zu führen.

## Schritt 1: Vorbereitung

Stellen Sie sicher, dass Sie die erforderlichen Bibliotheken importiert und den Pfad zu Ihrem Dokumentenverzeichnis festgelegt haben:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Instanziieren Sie ein Dokumentobjekt

Instanziieren Sie ein Document-Objekt:

```csharp
Document pdfDocument = new Document();
```

## Schritt 3: Seite zum PDF-Dokument hinzufügen

Fügen Sie dem PDF-Dokument eine Seite hinzu:

```csharp
Page page = pdfDocument.Pages.Add();
```

## Schritt 4: Instanziieren Sie ein RadioButtonField-Objekt

Instanziieren Sie ein RadioButtonField-Objekt mit der Seitenzahl als Argument:

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## Schritt 5: Optionsfelder hinzufügen

Fügen Sie Optionsfeldoptionen mithilfe des RadioButtonOptionField-Objekts hinzu und geben Sie ihre Position mithilfe des Rechteckobjekts an:

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));
opt1.OptionName = "Test1";
opt2.OptionName = "Test2";
radio.Add(opt1);
radio.Add(opt2);
```

## Schritt 6: Optionsfeldoptionen anpassen

Passen Sie die Optionen der Optionsfelder an, indem Sie deren Stil, Rahmen und Erscheinungsbild festlegen:

```csharp
opt1.Style = BoxStyle.Square;
opt2.Style = BoxStyle.Square;
opt1.Border = new Border(opt1);
opt1.Border.Style = BorderStyle.Solid;
opt1.Border.Width = 1;
opt2.Border = new Border(opt2);
opt2.Border.Width = 1;
opt2.Border.Style = BorderStyle.Solid;
```

## Schritt 7: Fügen Sie die Optionsfelder zum Formular hinzu

Fügen Sie die Optionsfelder zum Dokumentformularobjekt hinzu:

```csharp
pdfDocument.Form.Add(radio);
```

## Schritt 8: Speichern Sie das Dokument

Speichern Sie das PDF-Dokument:

```csharp
dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
pdfDocument.Save(dataDir);
```

### Beispielquellcode für gruppierte Kontrollkästchen mit Aspose.PDF für .NET 
```csharp
try
{
	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Dokumentobjekt instanziieren
	Document pdfDocument = new Document();
	// Fügen Sie einer PDF-Datei eine Seite hinzu
	Page page = pdfDocument.Pages.Add();
	// Erstellen Sie ein RadioButtonField-Objekt mit der Seitenzahl als Argument
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	// Fügen Sie die erste Optionsfeldoption hinzu und geben Sie auch deren Ursprung mithilfe des Rechteckobjekts an
	RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
	RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));
	opt1.OptionName = "Test1";
	opt2.OptionName = "Test2";
	radio.Add(opt1);
	radio.Add(opt2);
	opt1.Style = BoxStyle.Square;
	opt2.Style = BoxStyle.Square;
	opt1.Style = BoxStyle.Cross;
	opt2.Style = BoxStyle.Cross;
	opt1.Border = new Border(opt1);
	opt1.Border.Style = BorderStyle.Solid;
	opt1.Border.Width = 1;
	opt1.Characteristics.Border = System.Drawing.Color.Black;
	opt2.Border = new Border(opt2);
	opt2.Border.Width = 1;
	opt2.Border.Style = BorderStyle.Solid;
	opt2.Characteristics.Border = System.Drawing.Color.Black;
	// Fügen Sie ein Optionsfeld zum Formularobjekt des Dokumentobjekts hinzu
	pdfDocument.Form.Add(radio);
	dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
	// Speichern Sie das PDF-Dokument
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nGrouped checkboxes added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.PDF für .NET gruppierte Kontrollkästchen in einem PDF-Dokument erstellt. Wenn Sie diese Schritte befolgen, können Sie ganz einfach benutzerdefinierte Optionsfeldoptionen hinzufügen und diese mit Aspose.PDF in Ihren PDF-Dokumenten bündeln.