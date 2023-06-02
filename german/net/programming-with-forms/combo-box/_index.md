---
title: Kombinationsfeld
linktitle: Kombinationsfeld
second_title: Aspose.PDF für .NET API-Referenz
description: Erstellen Sie mit Aspose.PDF für .NET ganz einfach eine Kombinationsfeldliste in Ihren PDF-Dokumenten.
type: docs
weight: 30
url: /de/net/programming-with-forms/combo-box/
---

In diesem Tutorial zeigen wir Ihnen, wie Sie mit Aspose.PDF für .NET eine Kombinationsfeldliste erstellen. Wir erklären Ihnen Schritt für Schritt den C#-Quellcode, um Sie durch diesen Prozess zu führen.

## Schritt 1: Vorbereitung

Stellen Sie zunächst sicher, dass Sie die erforderlichen Bibliotheken importiert haben und legen Sie den Pfad zum Dokumentenverzeichnis fest:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Erstellen Sie ein Dokumentobjekt

Erstellen Sie ein Document-Objekt zum Speichern des PDF-Formulars:

```csharp
Document doc = new Document();
```

## Schritt 3: Fügen Sie eine Seite hinzu

Fügen Sie dem Dokument eine Seite hinzu:

```csharp
doc.Pages.Add();
```

## Schritt 4: Instanziieren Sie ein ComboBoxField-Objekt

Instanziieren Sie ein ComboBoxField-Objekt mit den gewünschten Abmessungen:

```csharp
ComboBoxField combo = new ComboBoxField(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 600, 150, 616));
```

## Schritt 5: Fügen Sie der Dropdown-Liste Optionen hinzu

Fügen Sie die gewünschten Optionen zur Dropdown-Liste hinzu:

```csharp
combo.AddOption("Red");
combo.AddOption("Yellow");
combo.AddOption("Green");
combo.AddOption("Blue");
```

## Schritt 6: Fügen Sie die Kombinationsfeldliste zum Formular hinzu

Fügen Sie das ComboBoxField-Objekt zur Document Form Fields-Auflistung hinzu:

```csharp
doc.Form.Add(combo);
```

## Schritt 7: Speichern Sie das Dokument

Speichern Sie das PDF-Dokument:

```csharp
dataDir = dataDir + "ComboBox_out.pdf";
doc.Save(dataDir);
```

### Beispielquellcode für Combo Box mit Aspose.Words für .NET 
```csharp
try
{
	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Dokumentobjekt erstellen
	Document doc = new Document();
	// Seite zum Dokumentobjekt hinzufügen
	doc.Pages.Add();
	// Instanziieren Sie das ComboBox-Feldobjekt
	ComboBoxField combo = new ComboBoxField(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 600, 150, 616));
	// Option zur ComboBox hinzufügen
	combo.AddOption("Red");
	combo.AddOption("Yellow");
	combo.AddOption("Green");
	combo.AddOption("Blue");
	// Fügen Sie ein Kombinationsfeldobjekt zur Formularfeldsammlung des Dokumentobjekts hinzu
	doc.Form.Add(combo);
	dataDir = dataDir + "ComboBox_out.pdf";
	// Speichern Sie das PDF-Dokument
	doc.Save(dataDir);
	Console.WriteLine("\nCombobox field added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.PDF für .NET eine Kombinationsfeldliste erstellt. Wenn Sie diese Schritte befolgen, können Sie mit Aspose.PDF ganz einfach eine Kombinationsfeldliste zu Ihren PDF-Dokumenten hinzufügen.