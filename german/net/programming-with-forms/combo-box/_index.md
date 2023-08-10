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

### Beispielquellcode für Combo Box mit Aspose.PDF für .NET 
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

### FAQs

#### F: Kann ich das Erscheinungsbild der Kombinationsfeldliste mit Aspose.PDF für .NET anpassen?

A: Ja, Sie können das Erscheinungsbild der Kombinationsfeldliste mit Aspose.PDF für .NET anpassen. Sie können Eigenschaften wie Schriftgröße, Farbe, Hintergrundfarbe, Rahmenstil und mehr so festlegen, dass sie Ihrem gewünschten Erscheinungsbild entsprechen.

#### F: Kann ich in der Kombinationsfeldliste standardmäßig ausgewählte Optionen festlegen?

 A: Ja, Sie können mit Aspose.PDF für .NET standardmäßig ausgewählte Optionen in der Liste der Kombinationsfelder festlegen. Du kannst den ... benutzen`Selected` Eigentum der`ComboBoxField` Objekt, um eine oder mehrere Optionen als standardmäßig ausgewählt zu markieren.

#### F: Wie kann ich den ausgewählten Wert aus der Kombinationsfeldliste abrufen, nachdem der Benutzer eine Auswahl getroffen hat?

 A: Sie können den ausgewählten Wert mit Aspose.PDF für .NET aus der Kombinationsfeldliste abrufen. Nachdem der Benutzer eine Auswahl getroffen hat, können Sie darauf zugreifen`Value` Eigentum der`ComboBoxField`Objekt, um den ausgewählten Wert zu erhalten.

#### F: Ist es möglich, der Kombinationsfeldliste Ereignishandler oder Aktionen hinzuzufügen?

 A: Ja, mit Aspose.PDF für .NET können Sie Ereignishandler oder Aktionen zur Liste der Kombinationsfelder hinzufügen. Sie können JavaScript-Aktionen zuordnen, z`OnValueChanged`, zur Kombinationsfeldliste, um bestimmte Aktionen auszuführen, wenn der Benutzer eine Option auswählt.

#### F: Kann ich den Optionen in der Kombinationsfeldliste Tooltips oder Beschreibungen hinzufügen?

 A: Ja, Sie können mit Aspose.PDF für .NET Tooltips oder Beschreibungen zu den Optionen in der Kombinationsfeldliste hinzufügen. Sie können das einstellen`AlternateName` Eigenschaft jeder Option, um einen Tooltip oder eine Beschreibung bereitzustellen, die angezeigt wird, wenn der Benutzer mit der Maus über die Option fährt.