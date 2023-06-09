---
title: Horizontale und vertikale Optionsfelder
linktitle: Horizontale und vertikale Optionsfelder
second_title: Aspose.PDF für .NET API-Referenz
description: Erstellen Sie mit Aspose.PDF für .NET ganz einfach horizontale und vertikale Optionsfelder in Ihren PDF-Dokumenten.
type: docs
weight: 180
url: /de/net/programming-with-forms/horizontally-and-vertically-radio-buttons/
---

In diesem Tutorial zeigen wir Ihnen, wie Sie mit Aspose.PDF für .NET horizontal und vertikal angeordnete Optionsfelder in einem PDF-Dokument erstellen. Wir erklären Ihnen Schritt für Schritt den C#-Quellcode, um Sie durch diesen Prozess zu führen.

## Schritt 1: Vorbereitung

Stellen Sie sicher, dass Sie die erforderlichen Bibliotheken importiert und den Pfad zu Ihrem Dokumentenverzeichnis festgelegt haben:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Laden Sie das Dokument

Laden Sie das vorhandene PDF-Dokument:

```csharp
FormEditor formEditor = new FormEditor();
formEditor.BindPdf(dataDir + "input.pdf");
```

## Schritt 3: Optionsfeldoptionen anpassen

Passen Sie die Optionen der Optionsfelder an, indem Sie die folgenden Eigenschaften festlegen:

```csharp
formEditor. RadioGap = 4; // Abstand zwischen zwei Optionsfeldern
formEditor. RadioHoriz = true; // Horizontale Anordnung der Optionsfelder
formEditor.RadioButtonItemSize = 20; // Größe der Optionsfelder
formEditor.Facade.BorderWidth = 1; // Breite des Optionsfeldrandes
formEditor.Facade.BorderColor = System.Drawing.Color.Black; // Rahmenfarbe des Optionsfelds
```

## Schritt 4: Horizontale Optionsfelder hinzufügen

Fügen Sie horizontal angeordnete Optionsfelder hinzu, indem Sie die Optionen und die Position des Felds angeben:

```csharp
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
```

## Schritt 5: Fügen Sie vertikale Optionsfelder hinzu

Fügen Sie vertikal angeordnete Optionsfelder hinzu, indem Sie die Optionen und die Position des Felds angeben:

```csharp
formEditor. RadioHoriz = false; // Vertikale Anordnung der Optionsfelder
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
```

## Schritt 6: Speichern Sie das Dokument

Speichern Sie das geänderte PDF-Dokument:

```csharp
dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
formEditor.Save(dataDir);
```

### Beispielquellcode für horizontale und vertikale Optionsfelder mit Aspose.PDF für .NET 
```csharp
try
{
	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Laden Sie das zuvor gespeicherte Dokument
	FormEditor formEditor = new FormEditor();
	formEditor.BindPdf(dataDir + "input.pdf");
	// RadioGap ist der Abstand zwischen zwei Optionsfeldern.
	formEditor.RadioGap = 4;
	// Horizontales Optionsfeld hinzufügen
	formEditor.RadioHoriz = true;
	// RadioButtonItemSize, wenn die Größe des Optionsfeldelements.
	formEditor.RadioButtonItemSize = 20;
	formEditor.Facade.BorderWidth = 1;
	formEditor.Facade.BorderColor = System.Drawing.Color.Black;
	formEditor.Items = new string[] { "First", "Second", "Third" };
	formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
	// Fügen Sie ein weiteres vertikal angeordnetes Optionsfeld hinzu
	formEditor.RadioHoriz = false;
	formEditor.Items = new string[] { "First", "Second", "Third" };
	formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
	dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
	// Speichern Sie das PDF-Dokument
	formEditor.Save(dataDir);
	Console.WriteLine("\nHorizontally and vertically laid out radio buttons successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.PDF für .NET horizontal und vertikal angeordnete Optionsfelder in einem PDF-Dokument erstellt. Wenn Sie diese Schritte befolgen, können Sie das Layout von Optionsfeldern ganz einfach anpassen und sie mit Aspose.PDF zu Ihren PDF-Dokumenten hinzufügen.