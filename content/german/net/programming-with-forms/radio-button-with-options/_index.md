---
title: Optionsfeld mit Optionen
linktitle: Optionsfeld mit Optionen
second_title: Aspose.PDF für .NET API-Referenz
description: Fügen Sie mit Aspose.PDF für .NET ganz einfach ein Optionsfeld mit Optionen zu einem PDF-Dokument hinzu.
type: docs
weight: 230
url: /de/net/programming-with-forms/radio-button-with-options/
---

In diesem Tutorial zeigen wir Ihnen, wie Sie mit Aspose.PDF für .NET einem PDF-Dokument ein Optionsfeld mit Optionen hinzufügen. Wir erklären Ihnen den C#-Quellcode Schritt für Schritt, um Sie durch diesen Prozess zu führen.

## Schritt 1: Vorbereitung

Stellen Sie sicher, dass Sie die erforderlichen Bibliotheken importiert haben, und legen Sie den Pfad zu Ihrem Dokumentverzeichnis fest:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Instanziieren eines Dokumentobjekts

Instanziieren Sie ein Dokumentobjekt, um ein neues PDF-Dokument zu erstellen:

```csharp
Document doc = new Document();
```

## Schritt 3: Seite und Tabelle hinzufügen

Fügen Sie dem Dokument eine Seite hinzu und erstellen Sie eine Tabelle, die die Optionsfeldoptionen enthält:

```csharp
Page page = doc.Pages.Add();
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "120 120 120";
page.Paragraphs.Add(table);
```

## Schritt 4: Instanziieren eines RadioButtonField-Objekts

Instanziieren Sie ein RadioButtonField-Objekt, um das Optionsfeld darzustellen:

```csharp
RadioButtonField rf = new RadioButtonField(page);
rf. PartialName = "radio";
doc.Form.Add(rf, 1);
```

## Schritt 5: Optionsfeldoptionen hinzufügen

Fügen Sie dem RadioButtonField-Objekt die Optionsfeldoptionen hinzu:

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField();
RadioButtonOptionField opt2 = new RadioButtonOptionField();
RadioButtonOptionField opt3 = new RadioButtonOptionField();
opt1.OptionName = "Item1";
opt2.OptionName = "Item2";
opt3.OptionName = "Item3";
opt1.Width = 15;
opt1. Height = 15;
opt2.Width = 15;
opt2. Height = 15;
opt3.Width = 15;
opt3. Height = 15;
rf.Add(opt1);
rf.Add(opt2);
rf.Add(opt3);
```

## Schritt 6: Optionsfeldoptionen anpassen

Passen Sie die Optionsfelder an, indem Sie Attribute wie Rahmen, Textfarbe und Beschriftungstext festlegen:

```csharp
opt1.Border = new Border(opt1);
opt1.Border.Width = 1;
opt1.Border.Style = BorderStyle.Solid;
opt1.Characteristics.Border = System.Drawing.Color.Black;
opt1.DefaultAppearance.TextColor = System.Drawing.Color.Red;
opt1.Caption = new TextFragment("Item1");

// Wiederholen Sie die gleichen Schritte für opt2 und opt3

```

## Schritt 7: Optionsfeldoptionen zur Tabelle hinzufügen

Fügen Sie der Tabelle die Optionsfeldoptionen hinzu, um sie anzuzeigen:

```csharp
Cell c1 = table.Rows.Add().Cells.Add();
Cell c2 = table.Rows[table.Rows.Count].Cells.Add();
Cell c3 = table.Rows[table.Rows.Count].Cells.Add();

c1.Paragraphs.Add(opt1);
c2.Paragraphs.Add(opt2);
c3.Paragraphs.Add(opt3);
```

## Schritt 8: Speichern Sie das PDF-Dokument

Speichern Sie das erstellte PDF-Dokument:

```csharp
dataDir = dataDir + "RadioButtonWithOptions_out.pdf";
doc.Save(dataDir);
```

### Beispiel-Quellcode für Radio Button With Options unter Verwendung von Aspose.PDF für .NET 
```csharp
try
{
	// Der Pfad zum Dokumentverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	Page page = doc.Pages.Add();
	Aspose.Pdf.Table table = new Aspose.Pdf.Table();
	table.ColumnWidths = "120 120 120";
	page.Paragraphs.Add(table);
	Row r1 = table.Rows.Add();
	Cell c1 = r1.Cells.Add();
	Cell c2 = r1.Cells.Add();
	Cell c3 = r1.Cells.Add();
	RadioButtonField rf = new RadioButtonField(page);
	rf.PartialName = "radio";
	doc.Form.Add(rf, 1);
	RadioButtonOptionField opt1 = new RadioButtonOptionField();
	RadioButtonOptionField opt2 = new RadioButtonOptionField();
	RadioButtonOptionField opt3 = new RadioButtonOptionField();
	opt1.OptionName = "Item1";
	opt2.OptionName = "Item2";
	opt3.OptionName = "Item3";
	opt1.Width = 15;
	opt1.Height = 15;
	opt2.Width = 15;
	opt2.Height = 15;
	opt3.Width = 15;
	opt3.Height = 15;
	rf.Add(opt1);
	rf.Add(opt2);
	rf.Add(opt3);
	opt1.Border = new Border(opt1);
	opt1.Border.Width = 1;
	opt1.Border.Style = BorderStyle.Solid;
	opt1.Characteristics.Border = System.Drawing.Color.Black;
	opt1.DefaultAppearance.TextColor = System.Drawing.Color.Red;
	opt1.Caption = new TextFragment("Item1");
	opt2.Border = new Border(opt1);
	opt2.Border.Width = 1;
	opt2.Border.Style = BorderStyle.Solid;
	opt2.Characteristics.Border = System.Drawing.Color.Black;
	opt2.DefaultAppearance.TextColor = System.Drawing.Color.Red;
	opt2.Caption = new TextFragment("Item2");
	opt3.Border = new Border(opt1);
	opt3.Border.Width = 1;
	opt3.Border.Style = BorderStyle.Solid;
	opt3.Characteristics.Border = System.Drawing.Color.Black;
	opt3.DefaultAppearance.TextColor = System.Drawing.Color.Red;
	opt3.Caption = new TextFragment("Item3");
	c1.Paragraphs.Add(opt1);
	c2.Paragraphs.Add(opt2);
	c3.Paragraphs.Add(opt3);
	dataDir = dataDir + "RadioButtonWithOptions_out.pdf";
	// Speichern Sie die PDF-Datei
	doc.Save(dataDir);
	Console.WriteLine("\nRadio button field with three options added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Abschluss

Herzlichen Glückwunsch! Sie haben mit Aspose.PDF für .NET erfolgreich ein Optionsfeld mit Optionen zu einem PDF-Dokument hinzugefügt. Mit dieser Methode können Sie jetzt interaktive Formulare in Ihren PDF-Dokumenten erstellen.