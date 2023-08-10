---
title: Radio knopf
linktitle: Radio knopf
second_title: Aspose.PDF für .NET API-Referenz
description: Fügen Sie mit Aspose.PDF für .NET ganz einfach Optionsfelder zu Ihren PDF-Dokumenten hinzu.
type: docs
weight: 220
url: /de/net/programming-with-forms/radio-button/
---
In diesem Tutorial zeigen wir Ihnen, wie Sie mit Aspose.PDF für .NET ein Optionsfeld in ein PDF-Dokument einfügen. Wir erklären Ihnen Schritt für Schritt den C#-Quellcode, um Sie durch diesen Prozess zu führen.

## Schritt 1: Vorbereitung

Stellen Sie sicher, dass Sie die erforderlichen Bibliotheken importiert und den Pfad zu Ihrem Dokumentenverzeichnis festgelegt haben:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Instanziieren Sie ein Dokumentobjekt

Instanziieren Sie ein Document-Objekt, um ein neues PDF-Dokument zu erstellen:

```csharp
Document pdfDocument = new Document();
```

## Schritt 3: Fügen Sie eine Seite hinzu

Fügen Sie dem PDF-Dokument eine Seite hinzu:

```csharp
pdfDocument.Pages.Add();
```

## Schritt 4: Instanziieren Sie ein RadioButtonField-Objekt

Instanziieren Sie ein RadioButtonField-Objekt und geben Sie dabei die Seitenzahl als Argument an:

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## Schritt 5: Optionsfelder hinzufügen

Fügen Sie Optionsfelder für Optionsfelder zum RadioButtonField-Objekt hinzu, indem Sie die Koordinaten jeder Option mit einem Rechteckobjekt angeben:

```csharp
radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
```

## Schritt 6: Fügen Sie dem Formular das Optionsfeld hinzu

Fügen Sie das Optionsfeld zum Formularobjekt des Dokuments hinzu:

```csharp
pdfDocument.Form.Add(radio);
```

## Schritt 7: Speichern Sie das PDF-Dokument

Speichern Sie das erstellte PDF-Dokument:

```csharp
dataDir = dataDir + "RadioButton_out.pdf";
pdfDocument.Save(dataDir);
```

### Beispielquellcode für Radio Button mit Aspose.PDF für .NET 
```csharp
try
{
	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Dokumentobjekt instanziieren
	Document pdfDocument = new Document();
	// Fügen Sie einer PDF-Datei eine Seite hinzu
	pdfDocument.Pages.Add();
	// Erstellen Sie ein RadioButtonField-Objekt mit der Seitenzahl als Argument
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	// Fügen Sie die erste Optionsfeldoption hinzu und geben Sie auch deren Ursprung mithilfe des Rechteckobjekts an
	radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
	// Fügen Sie eine zweite Optionsschaltfläche hinzu
	radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
	// Fügen Sie ein Optionsfeld zum Formularobjekt des Dokumentobjekts hinzu
	pdfDocument.Form.Add(radio);
	dataDir = dataDir + "RadioButton_out.pdf";
	//Speichern Sie die PDF-Datei
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nRadio button field added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.PDF für .NET ein Optionsfeld in ein PDF-Dokument einfügt. Wenn Sie diese Schritte befolgen, können Sie ganz einfach ein Optionsfeld erstellen und es auf einer bestimmten Seite in Ihrem PDF-Dokument platzieren.


### FAQs

#### F: Kann ich das Erscheinungsbild des Optionsfelds anpassen, z. B. seine Größe und Farbe?

 A: Ja, Sie können das Erscheinungsbild des Optionsfelds mithilfe von anpassen`Rectangle` Koordinaten des Objekts, um seine Größe und Position zu definieren. Mit Aspose.PDF für .NET können Sie das Erscheinungsbild des Optionsfelds an Ihre Bedürfnisse anpassen.

#### F: Kann ich mehrere Optionsfelder mit unterschiedlichen Gruppen auf derselben Seite hinzufügen?

A: Ja, Sie können auf derselben Seite mehrere Optionsfelder mit unterschiedlichen Gruppen hinzufügen. Jede Gruppe von Optionsfeldern kann einen eindeutigen Namen haben und es kann jeweils nur eine Option innerhalb jeder Gruppe ausgewählt werden.

#### F: Wie kann ich den Optionsfeldoptionen eine Beschriftung oder Textbeschreibung hinzufügen?

 A: Um den Optionsfeldoptionen eine Beschriftung oder Textbeschreibung hinzuzufügen, können Sie die verwenden`TextStamp`Klasse von Aspose.PDF für .NET, um Text auf dem PDF-Dokument an bestimmten Koordinaten zu überlagern.

#### F: Ist Aspose.PDF für .NET mit allen Versionen von .NET Framework kompatibel?

A: Ja, Aspose.PDF für .NET ist mit allen Versionen von .NET Framework kompatibel, einschließlich .NET Core und .NET Standard.

#### F: Kann ich die Auswahl einer Optionsschaltfläche im PDF-Dokument programmgesteuert steuern?

 A: Ja, Sie können die Auswahl einer Optionsschaltfläche mithilfe von programmgesteuert steuern`IsSelected` Eigentum der`RadioButtonOption` Klasse. Mit dieser Eigenschaft können Sie eine bestimmte Option als ausgewählt festlegen.