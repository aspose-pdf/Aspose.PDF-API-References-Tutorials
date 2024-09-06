---
title: Optionsfeld
linktitle: Optionsfeld
second_title: Aspose.PDF für .NET API-Referenz
description: Fügen Sie mit Aspose.PDF für .NET ganz einfach Optionsfelder zu Ihren PDF-Dokumenten hinzu.
type: docs
weight: 220
url: /de/net/programming-with-forms/radio-button/
---
In diesem Tutorial zeigen wir Ihnen, wie Sie mit Aspose.PDF für .NET ein Optionsfeld in ein PDF-Dokument einfügen. Wir erklären Ihnen den C#-Quellcode Schritt für Schritt, um Sie durch diesen Prozess zu führen.

## Schritt 1: Vorbereitung

Stellen Sie sicher, dass Sie die erforderlichen Bibliotheken importiert haben, und legen Sie den Pfad zu Ihrem Dokumentverzeichnis fest:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Instanziieren eines Dokumentobjekts

Instanziieren Sie ein Dokumentobjekt, um ein neues PDF-Dokument zu erstellen:

```csharp
Document pdfDocument = new Document();
```

## Schritt 3: Seite hinzufügen

Fügen Sie dem PDF-Dokument eine Seite hinzu:

```csharp
pdfDocument.Pages.Add();
```

## Schritt 4: Instanziieren eines RadioButtonField-Objekts

Instanziieren Sie ein RadioButtonField-Objekt, das die Seitenzahl als Argument angibt:

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## Schritt 5: Optionsfeldoptionen hinzufügen

Fügen Sie dem RadioButtonField-Objekt Optionsfelder hinzu, indem Sie die Koordinaten jeder Option mit einem Rectangle-Objekt angeben:

```csharp
radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
```

## Schritt 6: Fügen Sie dem Formular das Optionsfeld hinzu

Fügen Sie dem Formularobjekt des Dokuments das Optionsfeld hinzu:

```csharp
pdfDocument.Form.Add(radio);
```

## Schritt 7: Speichern Sie das PDF-Dokument

Speichern Sie das erstellte PDF-Dokument:

```csharp
dataDir = dataDir + "RadioButton_out.pdf";
pdfDocument.Save(dataDir);
```

### Beispiel-Quellcode für Radio Button mit Aspose.PDF für .NET 
```csharp
try
{
	// Der Pfad zum Dokumentverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Document-Objekt instanziieren
	Document pdfDocument = new Document();
	// Fügen Sie einer PDF-Datei eine Seite hinzu
	pdfDocument.Pages.Add();
	// RadioButtonField-Objekt mit Seitenzahl als Argument instanziieren
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	// Fügen Sie die erste Optionsfeldoption hinzu und geben Sie ihren Ursprung mithilfe des Rechteckobjekts an
	radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
	// Zweite Optionsfeldoption hinzufügen
	radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
	// Optionsfeld zum Formularobjekt des Dokumentobjekts hinzufügen
	pdfDocument.Form.Add(radio);
	dataDir = dataDir + "RadioButton_out.pdf";
	// Speichern Sie die PDF-Datei
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nRadio button field added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.PDF für .NET ein Optionsfeld in ein PDF-Dokument einfügt. Indem Sie diese Schritte befolgen, können Sie ganz einfach ein Optionsfeld erstellen und es auf einer bestimmten Seite in Ihrem PDF-Dokument platzieren.


### Häufig gestellte Fragen

#### F: Kann ich das Erscheinungsbild des Optionsfelds, beispielsweise seine Größe und Farbe, anpassen?

 A: Ja, Sie können das Erscheinungsbild des Optionsfelds mithilfe der`Rectangle` Koordinaten des Objekts, um dessen Größe und Position zu definieren. Mit Aspose.PDF für .NET können Sie das Erscheinungsbild des Optionsfelds Ihren Anforderungen entsprechend anpassen.

#### F: Kann ich auf derselben Seite mehrere Optionsfelder mit unterschiedlichen Gruppen hinzufügen?

A: Ja, Sie können auf derselben Seite mehrere Optionsfelder mit unterschiedlichen Gruppen hinzufügen. Jede Optionsfeldgruppe kann einen eindeutigen Namen haben und innerhalb jeder Gruppe kann jeweils nur eine Option ausgewählt werden.

#### F: Wie kann ich den Optionsfeldoptionen eine Beschriftung oder eine Textbeschreibung hinzufügen?

 A: Um den Optionsfeldoptionen eine Beschriftung oder eine Textbeschreibung hinzuzufügen, können Sie das`TextStamp`Klasse von Aspose.PDF für .NET, um Text an bestimmten Koordinaten auf dem PDF-Dokument zu überlagern.

#### F: Ist Aspose.PDF für .NET mit allen Versionen von .NET Framework kompatibel?

A: Ja, Aspose.PDF für .NET ist mit allen Versionen von .NET Framework kompatibel, einschließlich .NET Core und .NET Standard.

#### F: Kann ich die Auswahl einer Optionsfeldoption im PDF-Dokument programmgesteuert steuern?

 A: Ja, Sie können die Auswahl einer Optionsschaltfläche programmgesteuert steuern, indem Sie`IsSelected` Eigentum der`RadioButtonOption` Klasse. Mit dieser Eigenschaft können Sie eine bestimmte Option als ausgewählt festlegen.