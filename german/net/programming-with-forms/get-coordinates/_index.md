---
title: Holen Sie sich die Feldkoordinaten des PDF-Formulars
linktitle: Holen Sie sich die Feldkoordinaten des PDF-Formulars
second_title: Aspose.PDF für .NET API-Referenz
description: Mit Aspose.PDF für .NET erhalten Sie ganz einfach PDF-Formularfeldkoordinaten in Ihren PDF-Dokumenten.
type: docs
weight: 120
url: /de/net/programming-with-forms/get-coordinates/
---
In diesem Tutorial zeigen wir Ihnen, wie Sie mit Aspose.PDF für .NET PDF-Formularfeldkoordinaten erhalten. Wir erklären Ihnen Schritt für Schritt den C#-Quellcode, um Sie durch diesen Prozess zu führen.

## Schritt 1: Vorbereitung

Stellen Sie sicher, dass Sie die erforderlichen Bibliotheken importiert und den Pfad zum Dokumentenverzeichnis festgelegt haben:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Laden Sie das Ausgabedokument

Laden Sie das ausgegebene PDF-Dokument:

```csharp
Document doc1 = new Document(dataDir + "input.pdf");
```

## Schritt 3: Suchen Sie nach hinzugefügten Feldern

Suchen Sie die hinzugefügten Formularfelder (in diesem Beispiel verwenden wir die Felder „Item1“, „Item2“ und „Item3“):

```csharp
RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
```

## Schritt 4: Unterpunktpositionen für jedes Feld anzeigen

Gehen Sie die Optionen für jedes Feld durch und sehen Sie sich die Koordinaten für jedes Unterelement an:

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

### Beispielquellcode für „Koordinaten abrufen“ mit Aspose.PDF für .NET 
```csharp
try
{
	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Laden Sie das Ausgabedokument
	Document doc1 = new Document( dataDir + "input.pdf");
	// Suchen Sie nach hinzugefügten Feldern
	RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
	RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
	RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
	// Und zeigen Sie die Positionen der Unterelemente für jeden von ihnen an.
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

In diesem Tutorial haben wir gelernt, wie man mit Aspose.PDF für .NET Formularfeldkoordinaten erhält. Wenn Sie diese Schritte befolgen, können Sie mit Aspose.PDF ganz einfach die Koordinaten der Unterelemente Ihrer Formularfelder in Ihren PDF-Dokumenten abrufen.

### FAQs

#### F: Kann ich diese Methode verwenden, um Koordinaten für jede Art von Formularfeld in Aspose.PDF für .NET abzurufen?

A: Ja, Sie können diese Methode verwenden, um Koordinaten für verschiedene Arten von Formularfeldern in Aspose.PDF für .NET abzurufen. Der bereitgestellte C#-Quellcode zeigt, wie Koordinaten für RadioButton-Felder abgerufen werden. Sie können den gleichen Ansatz jedoch auch für andere Formularfeldtypen wie TextBox, CheckBox, ListBox und mehr anpassen.

#### F: Wie kann ich die Koordinaten des Formularfelds ändern oder anpassen?

A: Die Koordinaten des Formularfelds basieren auf dem Koordinatensystem des PDF-Dokuments, wobei der Ursprung (0,0) in der unteren linken Ecke der Seite liegt. Um die Koordinaten des Formularfelds zu ändern oder anzupassen, können Sie die aktualisieren`Rect` Eigenschaft des jeweiligen Formularfelds oder seiner Unterelemente, wie z. B. RadioButtonOptionField.

#### F: Kann ich die Koordinaten von Formularfeldern programmgesteuert zu einem PDF-Dokument hinzufügen lassen?

A: Ja, Sie können die Koordinaten von Formularfeldern abrufen, die programmgesteuert zu einem PDF-Dokument hinzugefügt wurden. Mit Aspose.PDF für .NET können Sie Formularfelder dynamisch hinzufügen und nach dem Hinzufügen deren Koordinaten mithilfe des in diesem Tutorial gezeigten Ansatzes abrufen.

#### F: Was ist der Zweck des Abrufens von Formularfeldkoordinaten?

A: Das Abrufen von Formularfeldkoordinaten kann hilfreich sein, wenn Sie bestimmte Layout-bezogene Vorgänge oder Validierungen an Formularfeldern in einem PDF-Dokument durchführen müssen. Damit können Sie Formularfelder anhand ihrer Koordinaten genau positionieren und ausrichten, um sicherzustellen, dass sie korrekt im Dokument angezeigt werden und ein nahtloses Benutzererlebnis bieten.

#### F: Werden die Formularfeldkoordinaten in Punkten oder einer anderen Einheit ausgedrückt?

A: Die Formularfeldkoordinaten in Aspose.PDF für .NET werden in Punkten ausgedrückt. Ein Punkt entspricht 1/72 Zoll und ist damit eine Standardmaßeinheit im PDF-Format.