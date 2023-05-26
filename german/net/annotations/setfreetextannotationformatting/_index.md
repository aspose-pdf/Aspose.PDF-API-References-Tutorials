---
title: Legen Sie die freie Formatierung von Textanmerkungen fest
linktitle: Legen Sie die freie Formatierung von Textanmerkungen fest
second_title: Aspose.PDF für .NET API-Referenz
description: Dieser Artikel enthält eine Schritt-für-Schritt-Anleitung zum Erstellen einer Freitextanmerkung und zum Festlegen ihres Inhalts mit Aspose.PDF für .NET
type: docs
weight: 140
url: /de/net/annotations/setfreetextannotationformatting/
---

Aspose.PDF für .NET ist eine leistungsstarke und benutzerfreundliche API zur Bearbeitung von PDF-Dokumenten, mit der Sie in Ihren .NET-Anwendungen programmgesteuert mit PDF-Dateien arbeiten können. Eine der von Aspose.PDF für .NET bereitgestellten Funktionen ist die Möglichkeit, in PDF-Dokumenten eine freie Textanmerkungsformatierung festzulegen. In diesem Artikel führen wir Sie Schritt für Schritt durch den Prozess der Festlegung der Formatierung von Freitextanmerkungen mit Aspose.PDF für .NET.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

- Microsoft Visual Studio 2010 oder höher
- Aspose.PDF für .NET
- Grundkenntnisse in C#



## 1. Erstellen Sie eine neue C#-Konsolenanwendung

Erstellen Sie zunächst eine neue C#-Konsolenanwendung in Microsoft Visual Studio. Um eine neue Konsolenanwendung zu erstellen, wählen Sie im Hauptmenü „Datei“ > „Neu“ > „Projekt“ > „Visual C#“ > „Konsolenanwendung“.

## 2. Fügen Sie einen Verweis auf Aspose.PDF für .NET hinzu

Fügen Sie als Nächstes einen Verweis auf Aspose.PDF für .NET in Ihrem Projekt hinzu. Klicken Sie dazu im Bereich „Projektmappen-Explorer“ mit der rechten Maustaste auf Ihr Projekt, wählen Sie „Hinzufügen“ > „Referenz“ und navigieren Sie dann zu dem Speicherort, an dem Sie die DLL-Datei „Aspose.PDF für .NET“ gespeichert haben. Wählen Sie die DLL-Datei aus und klicken Sie auf „OK“, um die Referenz zu Ihrem Projekt hinzuzufügen.

## 3. Richten Sie die Umgebung ein

Nachdem Sie den Verweis auf Aspose.PDF für .NET hinzugefügt haben, müssen Sie die Umgebung einrichten. Erstellen Sie dazu eine neue String-Variable mit dem Namen „dataDir“ und legen Sie diese auf den Pfad des Verzeichnisses fest, in dem sich Ihr PDF-Dokument befindet. Ersetzen Sie „IHR DOKUMENTVERZEICHNIS“ im folgenden Code durch den tatsächlichen Pfad Ihres Dokumentverzeichnisses:

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 4. Öffnen Sie das PDF-Dokument

Sobald Sie die Umgebung eingerichtet haben, können Sie das PDF-Dokument mit dem folgenden Code öffnen:

```csharp
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "SetFreeTextAnnotationFormatting.pdf");
```

Ersetzen Sie „SetFreeTextAnnotationFormatting.pdf“ durch den tatsächlichen Namen Ihres PDF-Dokuments.

## 5. Richten Sie das Standard-Erscheinungsbild ein

Um das Standard-Erscheinungsbild der Freitextanmerkung einzurichten, müssen Sie das DefaultAppearance-Objekt mit der gewünschten Schriftart, Schriftgröße und Farbe instanziieren. In diesem Tutorial stellen wir die Schriftart auf „Arial“, die Schriftgröße auf 28 und die Farbe auf Rot ein.

```csharp
// Instanziieren Sie das DefaultAppearance-Objekt
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 28, System.Drawing.Color.Red);
```

## 6. Erstellen Sie eine Freitextanmerkung

Nachdem Sie nun das Standard-Erscheinungsbild eingerichtet haben, können Sie mit dem folgenden Code eine Freitextanmerkung erstellen:

```csharp
// Anmerkung erstellen
FreeTextAnnotation freetext = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600), default_appearance);
```

Der obige Code erstellt eine neue Freitextanmerkung auf der zweiten Seite des PDF-Dokuments. Die Anmerkung wird bei (200, 400) positioniert und hat eine Breite von 400 und eine Höhe von 600.

## 7. Geben Sie den Inhalt der Anmerkung an

Nachdem Sie die Freitextanmerkung erstellt haben, können Sie den Inhalt der Anmerkung mit dem folgenden Code angeben:

```csharp
// Geben Sie den Inhalt der Anmerkung an
freetext.Contents = "Free Text
```

### Beispielquellcode für die Formatierung freier Textanmerkungen mithilfe von Aspose.PDF für .NET
```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	
	// Dokument öffnen
	Document pdfDocument = new Document(dataDir + "SetFreeTextAnnotationFormatting.pdf");

	// Instanziieren Sie das DefaultAppearance-Objekt
	DefaultAppearance default_appearance = new DefaultAppearance("Arial", 28, System.Drawing.Color.Red);
	// Anmerkung erstellen
	FreeTextAnnotation freetext = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600), default_appearance);
	// Geben Sie den Inhalt der Anmerkung an
	freetext.Contents = "Free Text";
	// Fügen Sie eine Anmerkung zur Anmerkungssammlung der Seite hinzu
	pdfDocument.Pages[1].Annotations.Add(freetext);
	dataDir = dataDir + "SetFreeTextAnnotationFormatting_out.pdf";
	//Speichern Sie das aktualisierte Dokument
	pdfDocument.Save(dataDir);            
 
```
