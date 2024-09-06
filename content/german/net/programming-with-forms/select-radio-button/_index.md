---
title: Optionsfeld im PDF-Dokument auswählen
linktitle: Optionsfeld im PDF-Dokument auswählen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET ein Optionsfeld in einem PDF-Dokument auswählen.
type: docs
weight: 250
url: /de/net/programming-with-forms/select-radio-button/
---
Hier finden Sie ein ausführliches Tutorial zum Auswählen eines Optionsfelds mit Aspose.PDF für .NET. Folgen Sie diesen Schritten:

##  Schritt 1: Definieren Sie zunächst das Verzeichnis Ihrer Dokumente, indem Sie den Pfad im`dataDir` variable.

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

##  Schritt 2: Öffnen Sie das PDF-Dokument mit dem`Document` class and the document path.

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

### Beispielquellcode für „Select Radio Button“ mit Aspose.PDF für .NET 
```csharp
try
{
	// Der Pfad zum Dokumentverzeichnis.
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

In diesem Tutorial haben wir gelernt, wie man mit Aspose.PDF für .NET ein Optionsfeld auswählt. Indem Sie die oben beschriebenen Schritte befolgen, können Sie mit Aspose.PDF für .NET Optionsfelder in Ihren PDF-Dokumenten bearbeiten und ändern.


### Häufig gestellte Fragen

#### F: Kann ich mit Aspose.PDF für .NET mehrere Optionsfelder in einer Gruppe auswählen?

A: Nein, Optionsfelder in einer Gruppe sind so konzipiert, dass sie sich gegenseitig ausschließen. Sie können innerhalb einer Gruppe immer nur ein Optionsfeld gleichzeitig auswählen. Wenn Sie ein Optionsfeld auswählen, wird automatisch die Auswahl aller zuvor ausgewählten Optionsfelder in derselben Gruppe aufgehoben.

#### F: Wie rufe ich mit Aspose.PDF für .NET das ausgewählte Optionsfeld in einer Gruppe ab?

 A: Um den ausgewählten Radiobutton in einer Gruppe abzurufen, können Sie den`Selected` Eigentum der`RadioButtonField` Klasse. Es wird der Index des ausgewählten Optionsfelds innerhalb der Gruppe zurückgegeben.

#### F: Kann ich das Erscheinungsbild des ausgewählten Optionsfelds im PDF-Dokument anpassen?

A: Ja, Sie können das Erscheinungsbild des ausgewählten Optionsfelds mit Aspose.PDF für .NET anpassen. Sie können Farbe, Größe, Rahmenstil und andere visuelle Attribute ändern, um es an Ihr gewünschtes Erscheinungsbild anzupassen.

#### F: Ist es möglich, mit Aspose.PDF für .NET programmgesteuert neue Optionsfeldgruppen zu erstellen?

A: Ja, Sie können neue Optionsfeldgruppen programmgesteuert mit Aspose.PDF für .NET erstellen. Sie können dem Formular des Dokuments neue Optionsfelder hinzufügen und für jedes Optionsfeld denselben Gruppennamen angeben, um eine neue Gruppe zu erstellen.

#### F: Unterstützt Aspose.PDF für .NET die Arbeit mit interaktiven PDF-Formularen?

A: Ja, Aspose.PDF für .NET unterstützt vollständig die Arbeit mit interaktiven PDF-Formularen, einschließlich Optionsfeldern, Textfeldern, Kontrollkästchen und anderen Formularelementen. Mit der Bibliothek können Sie interaktive PDF-Formulare problemlos lesen, ändern und erstellen.