---
title: Gruppierte Kontrollkästchen im PDF-Dokument
linktitle: Gruppierte Kontrollkästchen im PDF-Dokument
second_title: Aspose.PDF für .NET API-Referenz
description: Erstellen Sie mit Aspose.PDF für .NET ganz einfach gruppierte Kontrollkästchen in PDF-Dokumenten.
type: docs
weight: 170
url: /de/net/programming-with-forms/grouped-check-boxes/
---
In diesem Tutorial zeigen wir Ihnen, wie Sie mit Aspose.PDF für .NET gruppierte Kontrollkästchen in einem PDF-Dokument erstellen. Wir erklären Ihnen den C#-Quellcode Schritt für Schritt, um Sie durch diesen Prozess zu führen.

## Schritt 1: Vorbereitung

Stellen Sie sicher, dass Sie die erforderlichen Bibliotheken importiert haben, und legen Sie den Pfad zu Ihrem Dokumentverzeichnis fest:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Instanziieren eines Dokumentobjekts

Instanziieren Sie ein Dokumentobjekt:

```csharp
Document pdfDocument = new Document();
```

## Schritt 3: Seite zum PDF-Dokument hinzufügen

Fügen Sie dem PDF-Dokument eine Seite hinzu:

```csharp
Page page = pdfDocument.Pages.Add();
```

## Schritt 4: Instanziieren eines RadioButtonField-Objekts

Instanziieren Sie ein RadioButtonField-Objekt mit der Seitenzahl als Argument:

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## Schritt 5: Optionsfeldoptionen hinzufügen

Fügen Sie Optionsfelder mit dem Objekt „RadioButtonOptionField“ hinzu und geben Sie deren Position mit dem Objekt „Rectangle“ an:

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));
opt1.OptionName = "Test1";
opt2.OptionName = "Test2";
radio.Add(opt1);
radio.Add(opt2);
```

## Schritt 6: Optionsfeldoptionen anpassen

Passen Sie die Optionsfeldoptionen an, indem Sie deren Stil, Rahmen und Erscheinungsbild festlegen:

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

## Schritt 7: Fügen Sie dem Formular die Optionsfelder hinzu

Fügen Sie dem Dokumentformularobjekt die Optionsfelder hinzu:

```csharp
pdfDocument.Form.Add(radio);
```

## Schritt 8: Speichern Sie das Dokument

Speichern Sie das PDF-Dokument:

```csharp
dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
pdfDocument.Save(dataDir);
```

### Beispiel-Quellcode für gruppierte Kontrollkästchen mit Aspose.PDF für .NET 
```csharp
try
{
	// Der Pfad zum Dokumentverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Document-Objekt instanziieren
	Document pdfDocument = new Document();
	// Fügen Sie einer PDF-Datei eine Seite hinzu
	Page page = pdfDocument.Pages.Add();
	// RadioButtonField-Objekt mit Seitenzahl als Argument instanziieren
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	// Fügen Sie die erste Optionsfeldoption hinzu und geben Sie ihren Ursprung mithilfe des Rechteckobjekts an
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
	// Optionsfeld zum Formularobjekt des Dokumentobjekts hinzufügen
	pdfDocument.Form.Add(radio);
	dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
	// Speichern des PDF-Dokuments
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nGrouped checkboxes added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.PDF für .NET gruppierte Kontrollkästchen in einem PDF-Dokument erstellt. Indem Sie diese Schritte befolgen, können Sie ganz einfach benutzerdefinierte Optionsfeldoptionen hinzufügen und diese mit Aspose.PDF in Ihren PDF-Dokumenten bündeln.

### Häufig gestellte Fragen

#### F: Was sind gruppierte Kontrollkästchen in einem PDF-Dokument?

A: Gruppierte Kontrollkästchen in einem PDF-Dokument beziehen sich auf eine Reihe von Optionsfeldern, die gruppiert sind. Mit Optionsfeldern können Benutzer nur eine Option aus einer Gruppe sich gegenseitig ausschließender Auswahlmöglichkeiten auswählen. Wenn ein Optionsfeld ausgewählt ist, werden die anderen in derselben Gruppe automatisch abgewählt. Dieses Gruppierungsverhalten ist nützlich, wenn Sie Benutzern mehrere Optionen präsentieren, ihre Auswahl jedoch auf nur eine Auswahl beschränken möchten.

#### F: Kann ich das Erscheinungsbild gruppierter Kontrollkästchen in Aspose.PDF für .NET anpassen?

A: Ja, Sie können das Erscheinungsbild gruppierter Kontrollkästchen in Aspose.PDF für .NET anpassen. Die API bietet verschiedene Optionen zum Festlegen des Stils, des Rahmens und des Erscheinungsbilds von Optionsfeldoptionen. Sie können die Position jeder Option definieren, zwischen verschiedenen Feldstilen wählen (z. B. Quadrat, Kreis, Kreuz) und die Rahmeneigenschaften anpassen, um die gewünschte visuelle Darstellung zu erzielen.

#### F: Wie füge ich einer bestimmten Seite in einem PDF-Dokument gruppierte Kontrollkästchen hinzu?

A: Um gruppierte Kontrollkästchen zu einer bestimmten Seite in einem PDF-Dokument hinzuzufügen, müssen Sie eine`RadioButtonField` Objekt mit der gewünschten Seitenzahl als Argument. Erstellen Sie dann`RadioButtonOptionField` Objekte, die die einzelnen Optionsfelder darstellen, und geben Sie deren Position mit dem`Rectangle` Objekt. Fügen Sie diese Optionen schließlich dem`RadioButtonField` und passen Sie deren Erscheinungsbild nach Bedarf an, bevor Sie die`RadioButtonField` zum Dokumentformular.

#### F: Kann ich einem einzelnen PDF-Dokument mehrere Gruppen von Kontrollkästchen hinzufügen?

 A: Ja, Sie können mehrere Gruppen von Kontrollkästchen zu einem einzigen PDF-Dokument hinzufügen. Jede Gruppe sollte eine eindeutige`RadioButtonField` Objekt, und die`RadioButtonOptionField` Objekte innerhalb jeder Gruppe sollten dieselbe Seite und eindeutige Namen für ihre Optionen verwenden. Dadurch wird sichergestellt, dass die Optionsfelder innerhalb jeder Gruppe ordnungsgemäß funktionieren und die Auswahlmöglichkeiten sich gegenseitig ausschließen.

#### F: Werden gruppierte Kontrollkästchen in allen PDF-Viewern und -Anwendungen unterstützt?

A: Ja, gruppierte Kontrollkästchen werden in allen standardkonformen PDF-Viewern und -Anwendungen unterstützt. Die PDF-Spezifikation definiert Optionsfelder und ihr Gruppierungsverhalten, sodass sie im PDF-Format universell erkannt werden. Es ist jedoch wichtig, die Funktionalität in verschiedenen PDF-Viewern zu testen, um ein konsistentes Verhalten auf verschiedenen Plattformen sicherzustellen.