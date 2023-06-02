---
title: Wählen Sie das Optionsfeld aus
linktitle: Wählen Sie das Optionsfeld aus
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET ein Optionsfeld in einem PDF-Dokument auswählen.
type: docs
weight: 250
url: /de/net/programming-with-forms/select-radio-button/
---

Hier finden Sie eine ausführliche Anleitung zum Auswählen eines Optionsfelds mit Aspose.PDF für .NET. Folge diesen Schritten:

##  Schritt 1: Definieren Sie zunächst das Verzeichnis Ihrer Dokumente, indem Sie den Pfad im angeben`dataDir` variable.

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

##  Schritt 2: Öffnen Sie das PDF-Dokument mit`Document` class and the document path.

```csharp
Document pdfDocument = new Document(dataDir + "RadioButton.pdf");
```

## Schritt 3: Holen Sie sich das Optionsfeld aus dem Dokumentformular.

```csharp
RadioButtonField radioField = pdfDocument.Form["radio"] as RadioButtonField;
```

## Schritt 4: Geben Sie den Index des Optionsfelds an, das aus der Gruppe ausgewählt werden soll.

```csharp
radioField. Selected = 2;
```

## Schritt 5: Legen Sie den Ausgabepfad für die bearbeitete PDF-Datei fest.

```csharp
dataDir = dataDir + "SelectRadioButton_out.pdf";
```

## Schritt 6: Speichern Sie die geänderte PDF-Datei.

```csharp
pdfDocument.Save(dataDir);
```

## Schritt 7: Zeigen Sie eine Bestätigungsmeldung und den Speicherort der gespeicherten Datei an.

```csharp
Console.WriteLine("\nRadio button successfully selected in group.\nFile saved to location: " + dataDir);
```

### Beispielquellcode für Select Radio Button mit Aspose.Words für .NET 
```csharp
try
{
	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Dokument öffnen
	Document pdfDocument = new Document(dataDir + "RadioButton.pdf");
	// Holen Sie sich ein Feld
	RadioButtonField radioField = pdfDocument.Form["radio"] as RadioButtonField;
	// Geben Sie den Index des Optionsfelds aus der Gruppe an
	radioField.Selected = 2;
	dataDir = dataDir + "SelectRadioButton_out.pdf";
	// Speichern Sie die PDF-Datei
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nRadioButton from group selected successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.PDF für .NET ein Optionsfeld auswählt. Indem Sie die oben beschriebenen Schritte ausführen, können Sie Optionsfelder in Ihren PDF-Dokumenten mit Aspose.PDF für .NET manipulieren und ändern.