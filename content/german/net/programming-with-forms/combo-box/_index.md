---
title: Kombinationsfeld
linktitle: Kombinationsfeld
second_title: Aspose.PDF für .NET API-Referenz
description: Erstellen Sie mit Aspose.PDF für .NET ganz einfach Kombinationsfeldlisten in Ihren PDF-Dokumenten.
type: docs
weight: 30
url: /de/net/programming-with-forms/combo-box/
---
In diesem Tutorial zeigen wir Ihnen, wie Sie mit Aspose.PDF für .NET eine Kombinationsfeldliste erstellen. Wir erklären Ihnen den C#-Quellcode Schritt für Schritt, um Sie durch diesen Prozess zu führen.

## Schritt 1: Vorbereitung

Stellen Sie zunächst sicher, dass Sie die erforderlichen Bibliotheken importiert haben, und legen Sie den Pfad zum Dokumentverzeichnis fest:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Erstellen Sie ein Dokumentobjekt

Erstellen Sie ein Dokumentobjekt zur Aufnahme des PDF-Formulars:

```csharp
Document doc = new Document();
```

## Schritt 3: Seite hinzufügen

Fügen Sie dem Dokument eine Seite hinzu:

```csharp
doc.Pages.Add();
```

## Schritt 4: Instanziieren eines ComboBoxField-Objekts

Instanziieren Sie ein ComboBoxField-Objekt mit den gewünschten Abmessungen:

```csharp
ComboBoxField combo = new ComboBoxField(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 600, 150, 616));
```

## Schritt 5: Optionen zur Dropdown-Liste hinzufügen

Fügen Sie der Dropdown-Liste die gewünschten Optionen hinzu:

```csharp
combo.AddOption("Red");
combo.AddOption("Yellow");
combo.AddOption("Green");
combo.AddOption("Blue");
```

## Schritt 6: Hinzufügen der Kombinationsfeldliste zum Formular

Fügen Sie das ComboBoxField-Objekt zur Sammlung „Document Form Fields“ hinzu:

```csharp
doc.Form.Add(combo);
```

## Schritt 7: Speichern Sie das Dokument

Speichern Sie das PDF-Dokument:

```csharp
dataDir = dataDir + "ComboBox_out.pdf";
doc.Save(dataDir);
```

### Beispiel-Quellcode für Combo Box mit Aspose.PDF für .NET 
```csharp
try
{
	// Der Pfad zum Dokumentverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Dokumentobjekt erstellen
	Document doc = new Document();
	// Seite zum Dokumentobjekt hinzufügen
	doc.Pages.Add();
	// ComboBox-Feldobjekt instantiieren
	ComboBoxField combo = new ComboBoxField(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 600, 150, 616));
	// Option zur ComboBox hinzufügen
	combo.AddOption("Red");
	combo.AddOption("Yellow");
	combo.AddOption("Green");
	combo.AddOption("Blue");
	// Kombinationsfeldobjekt zur Formularfeldsammlung des Dokumentobjekts hinzufügen
	doc.Form.Add(combo);
	dataDir = dataDir + "ComboBox_out.pdf";
	// Speichern des PDF-Dokuments
	doc.Save(dataDir);
	Console.WriteLine("\nCombobox field added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.PDF für .NET eine Kombinationsfeldliste erstellt. Indem Sie diese Schritte befolgen, können Sie Ihren PDF-Dokumenten mit Aspose.PDF ganz einfach eine Kombinationsfeldliste hinzufügen.

### Häufig gestellte Fragen

#### F: Kann ich das Erscheinungsbild der Kombinationsfeldliste mit Aspose.PDF für .NET anpassen?

A: Ja, Sie können das Erscheinungsbild der Kombinationsfeldliste mit Aspose.PDF für .NET anpassen. Sie können Eigenschaften wie Schriftgröße, Farbe, Hintergrundfarbe, Rahmenstil und mehr festlegen, um es an Ihr gewünschtes Erscheinungsbild anzupassen.

#### F: Kann ich in der Kombinationsfeldliste standardmäßig ausgewählte Optionen festlegen?

 A: Ja, Sie können standardmäßig ausgewählte Optionen in der Kombinationsfeldliste mit Aspose.PDF für .NET festlegen. Sie können die`Selected` Eigentum der`ComboBoxField` Objekt, um eine oder mehrere Optionen als standardmäßig ausgewählt zu markieren.

#### F: Wie kann ich den ausgewählten Wert aus der Kombinationsfeldliste abrufen, nachdem der Benutzer eine Auswahl getroffen hat?

 A: Sie können den ausgewählten Wert aus der Kombinationsfeldliste mit Aspose.PDF für .NET abrufen. Nachdem der Benutzer eine Auswahl getroffen hat, können Sie auf die`Value` Eigentum der`ComboBoxField`Objekt, um den ausgewählten Wert zu erhalten.

#### F: Ist es möglich, der Kombinationsfeldliste Ereignishandler oder Aktionen hinzuzufügen?

 A: Ja, Aspose.PDF für .NET ermöglicht es Ihnen, Ereignishandler oder Aktionen zur Kombinationsfeldliste hinzuzufügen. Sie können JavaScript-Aktionen verknüpfen, wie zum Beispiel`OnValueChanged`, zur Kombinationsfeldliste, um bestimmte Aktionen auszuführen, wenn der Benutzer eine Option auswählt.

#### F: Kann ich den Optionen in der Kombinationsfeldliste Tooltips oder Beschreibungen hinzufügen?

 A: Ja, Sie können den Optionen in der Kombinationsfeldliste mit Aspose.PDF für .NET Tooltips oder Beschreibungen hinzufügen. Sie können die`AlternateName` -Eigenschaft jeder Option, um einen Tooltip oder eine Beschreibung bereitzustellen, die angezeigt wird, wenn der Benutzer mit der Maus über die Option fährt.