---
title: Koordinaten abrufen
linktitle: Koordinaten abrufen
second_title: Aspose.PDF für .NET API-Referenz
description: Mit Aspose.PDF für .NET erhalten Sie ganz einfach Formularfeldkoordinaten in Ihren PDF-Dokumenten.
type: docs
weight: 120
url: /de/net/programming-with-forms/get-coordinates/
---

In diesem Tutorial zeigen wir Ihnen, wie Sie mit Aspose.PDF für .NET Formularfeldkoordinaten erhalten. Wir erklären Ihnen Schritt für Schritt den C#-Quellcode, um Sie durch diesen Prozess zu führen.

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