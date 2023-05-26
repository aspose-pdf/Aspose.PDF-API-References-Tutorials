---
title: Erhalten Sie eine bestimmte Anmerkung
linktitle: Erhalten Sie eine bestimmte Anmerkung
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie in dieser Schritt-für-Schritt-Anleitung, wie Sie Aspose.PDF für .NET verwenden, um bestimmte Anmerkungen in ein PDF-Dokument einzufügen.
type: docs
weight: 80
url: /de/net/annotations/getparticularannotation/
---
Wenn Sie mit PDFs in .NET arbeiten, müssen Sie möglicherweise eine bestimmte Anmerkung aus einem PDF-Dokument abrufen. In dieser Anleitung zeigen wir Ihnen, wie Sie Aspose.PDF für .NET verwenden, um mit C# eine bestimmte Anmerkung aus einem PDF-Dokument abzurufen.

Befolgen Sie diese einfachen Schritte, um eine bestimmte Anmerkung aus einem PDF-Dokument zu erhalten:

## Schritt 1: Erhalten Sie bestimmte Anmerkungen aus dem PDF-Dokument

Stellen Sie zunächst sicher, dass die Aspose.PDF für .NET-Bibliothek in Ihrem Projekt installiert und referenziert ist.

Erstellen Sie als Nächstes eine neue Instanz der Document-Klasse und laden Sie Ihr PDF-Dokument über den Pfad zum Dokumentverzeichnis.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "GetParticularAnnotation.pdf");
```

## Schritt 2: Mit dem folgenden Code können Sie eine bestimmte Anmerkung abrufen:

```csharp
TextAnnotation textAnnotation = (TextAnnotation)pdfDocument.Pages[1].Annotations[1];
```

Dieser Code ruft die zweite Anmerkung auf der zweiten Seite des PDF-Dokuments ab.

## Schritt 3: Schließlich können Sie die Eigenschaften der Anmerkung mit dem folgenden Code abrufen:

```csharp
Console.WriteLine("Title : {0} ", textAnnotation.Title);
Console.WriteLine("Subject : {0} ", textAnnotation.Subject);
Console.WriteLine("Contents : {0} ", textAnnotation.Contents);
```

Dieser Code zeigt den Titel, den Betreff und den Inhalt der Anmerkung in der Konsole an.


### Beispielquellcode zum Abrufen bestimmter Anmerkungen mit Aspose.PDF für .NET

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Dokument öffnen
	Document pdfDocument = new Document(dataDir + "GetParticularAnnotation.pdf");

	// Erhalten Sie eine bestimmte Anmerkung
	TextAnnotation textAnnotation = (TextAnnotation)pdfDocument.Pages[1].Annotations[1];

	// Anmerkungseigenschaften abrufen
	Console.WriteLine("Title : {0} ", textAnnotation.Title);
	Console.WriteLine("Subject : {0} ", textAnnotation.Subject);
	Console.WriteLine("Contents : {0} ", textAnnotation.Contents);

```

