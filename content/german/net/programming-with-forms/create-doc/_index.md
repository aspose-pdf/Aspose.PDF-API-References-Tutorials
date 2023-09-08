---
title: Dokument erstellen
linktitle: Dokument erstellen
second_title: Aspose.PDF für .NET API-Referenz
description: Erstellen Sie mit Aspose.PDF für .NET ganz einfach ein Dokument mit Optionsfeldern.
type: docs
weight: 40
url: /de/net/programming-with-forms/create-doc/
---
In diesem Tutorial zeigen wir Ihnen, wie Sie mit Aspose.PDF für .NET ein Dokument mit Optionsfeldern erstellen. Wir erklären Ihnen Schritt für Schritt den C#-Quellcode, um Sie durch diesen Prozess zu führen.

##Schritt 1: Vorbereitung

Stellen Sie zunächst sicher, dass Sie die erforderlichen Bibliotheken importiert haben und legen Sie den Pfad zum Dokumentenverzeichnis fest:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Erstellen Sie ein neues Dokument

Erstellen Sie ein neues Document-Objekt zum Speichern des PDF-Dokuments:

```csharp
Document doc = new Document();
```

## Schritt 3: Fügen Sie eine Seite hinzu

Fügen Sie dem Dokument eine neue Seite hinzu:

```csharp
Page page = doc.Pages.Add();
```

## Schritt 4: Fügen Sie ein Optionsfeld hinzu

Erstellen Sie ein Optionsfeld und legen Sie dessen Position und Größe fest:

```csharp
RadioButtonField field = new RadioButtonField(page);
field.Rect = new Aspose.Pdf.Rectangle(40, 650, 100, 720);
field. PartialName = "NewField";
```

## Schritt 5: Optionsfelder hinzufügen

Fügen Sie die gewünschten Optionen zum Optionsfeld hinzu. Sie können die Koordinaten und die Größe jeder Option nach Bedarf festlegen:

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField();
opt1.Rect = new Aspose.Pdf.Rectangle(40, 650, 60, 670);
opt1.OptionName = "Item1";
opt1.Border = new Border(opt1);
opt1.Border.Width = 1;
opt1.Characteristics.Border = System.Drawing.Color.Black;

RadioButtonOptionField opt2 = new RadioButtonOptionField();
opt2.Rect = new Aspose.Pdf.Rectangle(60, 670, 80, 690);
opt2.OptionName = "Item2";
opt2.Border = new Border(opt2);
opt2.Border.Width = 1;
opt2.Characteristics.Border = System.Drawing.Color.Black;

RadioButtonOptionField opt3 = new RadioButtonOptionField();
opt3.Rect = new Aspose.Pdf.Rectangle(80, 690, 100, 710);
opt3.OptionName = "Item3";
opt3.Border = new Border(opt3);
opt3.Border.Width = 1;
opt3.Characteristics.Border = System.Drawing.Color.Black;

field. Add(opt1);
field. Add(opt2);
field. Add(opt3);
```

## Schritt 6: Fügen Sie dem Formular das Optionsfeld hinzu

Fügen Sie das Optionsfeld zur Sammlung „Dokumentformularfelder“ hinzu:

```csharp
doc.Form.Add(field);
```

## Schritt 7: Speichern Sie das Dokument

Speichern Sie das PDF-Dokument:

```csharp
dataDir = dataDir + "CreateDoc_out.pdf";
doc.Save(dataDir);
```

### Beispielquellcode für „Dokument erstellen mit Aspose.PDF für .NET“. 
```csharp
try
{
	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Erstellen Sie ein neues Dokument
	Document doc = new Document();
	Page page = doc.Pages.Add();
	// Optionsfeld hinzufügen
	RadioButtonField field = new RadioButtonField(page);
	field.Rect = new Aspose.Pdf.Rectangle(40, 650, 100, 720);
	field.PartialName = "NewField";
	// Fügen Sie Optionsfeldoptionen hinzu. Bitte beachten Sie, dass sich diese Optionen befinden
	// Weder horizontal noch vertikal.
	// Sie können versuchen, beliebige Koordinaten (und sogar die Größe) für sie festzulegen.
	RadioButtonOptionField opt1 = new RadioButtonOptionField();
	opt1.Rect = new Aspose.Pdf.Rectangle(40, 650, 60, 670);
	opt1.OptionName = "Item1";
	opt1.Border = new Border(opt1);
	opt1.Border.Width = 1;
	opt1.Characteristics.Border = System.Drawing.Color.Black;
	RadioButtonOptionField opt2 = new RadioButtonOptionField();
	opt2.Rect = new Aspose.Pdf.Rectangle(60, 670, 80, 690);
	opt2.OptionName = "Item2";
	opt2.Border = new Border(opt2);
	opt2.Border.Width = 1;
	opt2.Characteristics.Border = System.Drawing.Color.Black;
	RadioButtonOptionField opt3 = new RadioButtonOptionField();
	opt3.Rect = new Aspose.Pdf.Rectangle(80, 690, 100, 710);
	opt3.OptionName = "Item3";
	opt3.Border = new Border(opt3);
	opt3.Border.Width = 1;
	opt3.Characteristics.Border = System.Drawing.Color.Black;
	field.Add(opt1);
	field.Add(opt2);
	field.Add(opt3);
	doc.Form.Add(field);
	dataDir = dataDir + "CreateDoc_out.pdf";
	// Speichern Sie das PDF-Dokument
	doc.Save(dataDir);
	Console.WriteLine("\nNew doc with 3 items radio button created successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.PDF für .NET ein Dokument mit Optionsfeldern erstellt. Wenn Sie diese Schritte befolgen, können Sie mit Aspose.PDF ganz einfach Optionsfelder zu Ihren PDF-Dokumenten hinzufügen.

### FAQs

#### F: Kann ich das Erscheinungsbild der Optionsfelder im Dokument mit Aspose.PDF für .NET anpassen?

A: Ja, Sie können das Erscheinungsbild der Optionsfelder im Dokument mit Aspose.PDF für .NET anpassen. Sie können Eigenschaften wie Größe, Farbe, Rahmenstil und mehr festlegen, um das Erscheinungsbild der Optionsfelder anzupassen.

#### F: Wie kann ich Optionsfeldgruppen mit sich gegenseitig ausschließenden Optionen hinzufügen?

A: Um sich gegenseitig ausschließende Optionen zu erstellen, können Sie mehrere Optionsfelder mit demselben Namen hinzufügen. Dadurch wird sichergestellt, dass bei Auswahl einer Option die anderen Optionen mit demselben Namen automatisch deaktiviert werden.

#### F: Ist es möglich, eine standardmäßig ausgewählte Option für die Optionsfelder festzulegen?

A: Ja, Sie können mit Aspose.PDF für .NET eine standardmäßig ausgewählte Option für die Optionsfelder festlegen. Du kannst den ... benutzen`Selected` Eigentum der`RadioButtonOptionField` Objekt, um eine Option als standardmäßig ausgewählt zu markieren.

#### F: Kann ich den Optionsfeldern Ereignishandler hinzufügen?

 A: Ja, Sie können mit Aspose.PDF für .NET Ereignishandler zu den Optionsfeldern hinzufügen. Sie können JavaScript-Aktionen zuordnen, z`OnValueChanged`, zu den Optionsfeldern, um bestimmte Aktionen auszuführen, wenn der Benutzer eine Option auswählt.

#### F: Wie kann ich die ausgewählte Option aus der Optionsfeldgruppe abrufen, nachdem der Benutzer eine Auswahl getroffen hat?

 A: Sie können die ausgewählte Option mit Aspose.PDF für .NET aus der Optionsfeldgruppe abrufen. Nachdem der Benutzer eine Auswahl getroffen hat, können Sie darauf zugreifen`Selected` Eigentum der`RadioButtonOptionField` Objekt, um zu überprüfen, welche Option ausgewählt ist.