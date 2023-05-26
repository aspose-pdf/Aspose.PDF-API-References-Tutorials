---
title: Fügen Sie eine SWF-Datei als Anmerkung hinzu
linktitle: Fügen Sie eine SWF-Datei als Anmerkung hinzu
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie in dieser Schritt-für-Schritt-Anleitung, wie Sie SWF-Dateien als Anmerkungen in Aspose.PDF für .NET hinzufügen.
type: docs
weight: 30
url: /de/net/annotations/addswffileasannotation/
---
Wenn Sie ein .NET-Entwickler sind und mit Aspose.PDF für .NET eine SWF-Multimediadatei als Anmerkung zu Ihrem PDF-Dokument hinzufügen möchten, ist diese Schritt-für-Schritt-Anleitung genau das Richtige für Sie. In diesem Artikel erklären wir, wie Sie mithilfe der Programmiersprache C# SWF-Dateien als Anmerkungen zu Ihren PDF-Dokumenten hinzufügen. 

Führen Sie die folgenden Schritte aus, um mit Aspose.PDF für .NET eine SWF-Datei als Anmerkung zu Ihrem PDF-Dokument hinzuzufügen:

## Schritt 1: Legen Sie den Verzeichnispfad fest

Zuerst müssen wir den Verzeichnispfad festlegen, in dem die PDF-Datei und die SWF-Datei gespeichert werden. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Ersetzen Sie „IHR DOKUMENTENVERZEICHNIS“ durch den Pfad zu Ihrem Dokumentenverzeichnis.

## Schritt 2: Laden Sie das PDF-Dokument

Als nächstes müssen wir das PDF-Dokument mit dem folgenden Code laden:

```csharp
Document doc = new Document(dataDir + "AddSwfFileAsAnnotation.pdf");
```

Dieser Code lädt die Datei „AddSwfFileAsAnnotation.pdf“ aus dem Dokumentverzeichnis.

## Schritt 3: Rufen Sie die Seite auf, um Anmerkungen hinzuzufügen

Jetzt müssen wir die Referenz der Seite abrufen, zu der wir die Anmerkung hinzufügen möchten. In diesem Tutorial fügen wir die Anmerkung zur ersten Seite des Dokuments hinzu.

```csharp
Page page = doc.Pages[1];
```

## Schritt 4: Erstellen Sie ein ScreenAnnotation-Objekt

 Wir können jetzt eine erstellen`ScreenAnnotation` Objekt mit der SWF-Datei als Argument.

```csharp
ScreenAnnotation annotation = new ScreenAnnotation(page, new Aspose.Pdf.Rectangle(0, 400, 600, 700), dataDir + "input.swf");
```

 Der`ScreenAnnotation` Der Konstruktor benötigt drei Argumente:

- `page`: Die Seite, zu der die Anmerkung hinzugefügt wird.
- `rectangle`: Das Rechteck, in dem die SWF-Datei auf der Seite angezeigt wird.
- `dataDir + "input.swf"`: Der Pfad zur SWF-Datei.

## Schritt 5: Fügen Sie die Anmerkung zur Seite hinzu

Jetzt können wir die Anmerkung zur Anmerkungssammlung der Seite hinzufügen.

```csharp
page.Annotations.Add(annotation);
```

## Schritt 6: Speichern Sie das aktualisierte PDF-Dokument

Abschließend müssen wir das aktualisierte PDF-Dokument mit der Anmerkung mithilfe des folgenden Codes speichern:

```csharp
dataDir = dataDir + "AddSwfFileAsAnnotation_out.pdf";
doc.Save(dataDir);
```

Dieser Code speichert das aktualisierte PDF-Dokument mit der Anmerkung als „AddSwfFileAsAnnotation_out.pdf“ im Dokumentverzeichnis.

### Beispielquellcode zum Hinzufügen einer SWF-Datei als Anmerkung mit Aspose.PDF für .NET

```csharp
	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	//Öffnen Sie das PDF-Dokument
	Document doc = new Document(dataDir + "AddSwfFileAsAnnotation.pdf");

	// Rufen Sie den Verweis auf die Seite ab, zu der Sie die Anmerkung hinzufügen müssen
	Page page = doc.Pages[1];

	// Erstellen Sie ein ScreenAnnotation-Objekt mit einer SWF-Multimediadatei als Argument
	ScreenAnnotation annotation = new ScreenAnnotation(page, new Aspose.Pdf.Rectangle(0, 400, 600, 700), dataDir + "input.swf");

	// Fügen Sie die Anmerkung zur Anmerkungssammlung der Seite hinzu
	page.Annotations.Add(annotation);

	dataDir = dataDir + "AddSwfFileAsAnnotation_out.pdf";
	// Speichern Sie das aktualisierte PDF-Dokument mit Anmerkungen
	doc.Save(dataDir);
```        
