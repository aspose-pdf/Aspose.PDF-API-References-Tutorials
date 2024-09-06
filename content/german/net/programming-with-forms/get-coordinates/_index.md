---
title: Holen Sie sich die Feldkoordinaten des PDF-Formulars
linktitle: Holen Sie sich die Feldkoordinaten des PDF-Formulars
second_title: Aspose.PDF für .NET API-Referenz
description: Holen Sie sich mit Aspose.PDF für .NET ganz einfach PDF-Formularfeldkoordinaten in Ihre PDF-Dokumente.
type: docs
weight: 120
url: /de/net/programming-with-forms/get-coordinates/
---
In diesem Tutorial zeigen wir Ihnen, wie Sie mit Aspose.PDF für .NET PDF-Formularfeldkoordinaten abrufen. Wir erklären Ihnen den C#-Quellcode Schritt für Schritt, um Sie durch diesen Prozess zu führen.

## Schritt 1: Vorbereitung

Stellen Sie sicher, dass Sie die erforderlichen Bibliotheken importiert haben, und legen Sie den Pfad zum Dokumentverzeichnis fest:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Laden Sie das Ausgabedokument

Laden Sie das PDF-Ausgabedokument:

```csharp
Document doc1 = new Document(dataDir + "input.pdf");
```

## Schritt 3: Hinzugefügte Felder suchen

Suchen Sie die hinzugefügten Formularfelder (in diesem Beispiel verwenden wir die Felder „Item1“, „Item2“ und „Item3“):

```csharp
RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
```

## Schritt 4: Unterpositionen für jedes Feld anzeigen

Gehen Sie die Optionen für jedes Feld durch und zeigen Sie die Koordinaten für jedes Unterelement an:

```csharp
foreach(RadioButtonOptionField option in field0)
{
Console.WriteLine(option.Rect);
}
foreach(RadioButtonOptionField option in field1)
{
Console.WriteLine(option.Rect);
}
foreach(RadioButtonOptionField option in field2)
{
Console.WriteLine(option.Rect);
}
```

### Beispielquellcode zum Abrufen von Koordinaten mit Aspose.PDF für .NET 
```csharp
try
{
	// Der Pfad zum Dokumentverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Laden des Ausgabedokuments
	Document doc1 = new Document( dataDir + "input.pdf");
	// Hinzugefügte Felder suchen
	RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
	RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
	RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
	// Und zeigen Sie für jedes davon die Positionen der Unterelemente an.
	foreach (RadioButtonOptionField option in field0)
	{
		Console.WriteLine(option.Rect);
	}
	foreach (RadioButtonOptionField option in field1)
	{
		Console.WriteLine(option.Rect);
	}
	foreach (RadioButtonOptionField option in field2)
	{
		Console.WriteLine(option.Rect);
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.PDF für .NET Formularfeldkoordinaten erhält. Indem Sie diese Schritte befolgen, können Sie mit Aspose.PDF ganz einfach die Koordinaten der Unterelemente Ihrer Formularfelder in Ihren PDF-Dokumenten abrufen.

### Häufig gestellte Fragen

#### F: Kann ich diese Methode verwenden, um Koordinaten für jede Art von Formularfeld in Aspose.PDF für .NET zu erhalten?

A: Ja, Sie können diese Methode verwenden, um Koordinaten für verschiedene Arten von Formularfeldern in Aspose.PDF für .NET abzurufen. Der bereitgestellte C#-Quellcode zeigt, wie Sie Koordinaten für RadioButton-Felder abrufen, aber Sie können denselben Ansatz für andere Formularfeldtypen wie TextBox, CheckBox, ListBox und mehr anpassen.

#### F: Wie kann ich die Koordinaten der Formularfelder ändern oder anpassen?

A: Die Koordinaten der Formularfelder basieren auf dem Koordinatensystem des PDF-Dokuments, wobei sich der Ursprung (0,0) in der unteren linken Ecke der Seite befindet. Um die Koordinaten der Formularfelder zu ändern oder anzupassen, können Sie die`Rect` Eigenschaft des jeweiligen Formularfeldes oder seiner Unterelemente, wie zum Beispiel RadioButtonOptionField.

#### F: Kann ich die Koordinaten von Formularfeldern programmgesteuert zu einem PDF-Dokument hinzufügen?

A: Ja, Sie können die Koordinaten von Formularfeldern abrufen, die programmgesteuert zu einem PDF-Dokument hinzugefügt wurden. Mit Aspose.PDF für .NET können Sie Formularfelder dynamisch hinzufügen und nach dem Hinzufügen ihre Koordinaten mit dem in diesem Tutorial gezeigten Ansatz abrufen.

#### F: Was ist der Zweck des Abrufens von Formularfeldkoordinaten?

A: Das Abrufen von Formularfeldkoordinaten kann hilfreich sein, wenn Sie bestimmte layoutbezogene Vorgänge oder Validierungen an Formularfeldern in einem PDF-Dokument durchführen müssen. Sie können Formularfelder anhand ihrer Koordinaten genau positionieren und ausrichten und so sicherstellen, dass sie im Dokument korrekt angezeigt werden und ein nahtloses Benutzererlebnis bieten.

#### F: Werden die Formularfeldkoordinaten in Punkten oder einer anderen Einheit ausgedrückt?

A: Die Formularfeldkoordinaten in Aspose.PDF für .NET werden in Punkten ausgedrückt. Ein Punkt entspricht 1/72 Zoll und ist damit eine Standardmaßeinheit im PDF-Format.