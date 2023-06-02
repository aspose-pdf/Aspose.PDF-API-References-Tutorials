---
title: Am Ende eine leere Seite einfügen
linktitle: Am Ende eine leere Seite einfügen
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Einfügen einer leeren Seite am Ende eines PDF-Dokuments mit Aspose.PDF für .NET. Einfach und schnell!
type: docs
weight: 130
url: /de/net/programming-with-pdf-pages/insert-empty-page-at-end/
---
In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess zum Einfügen einer leeren Seite am Ende eines PDF-Dokuments mit Aspose.PDF für .NET. Wir erklären Ihnen den gebündelten C#-Quellcode und stellen Ihnen eine umfassende Anleitung zur Verfügung, die Ihnen hilft, diese Funktion zu verstehen und in Ihren eigenen Projekten zu implementieren. Am Ende dieses Tutorials erfahren Sie, wie Sie mit Aspose.PDF für .NET eine leere Seite am Ende eines PDF-Dokuments einfügen.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Grundkenntnisse der Programmiersprache C#
- Aspose.PDF für .NET in Ihrer Entwicklungsumgebung installiert

## Schritt 1: Definieren Sie das Dokumentenverzeichnis
Zuerst müssen Sie den Pfad zu Ihrem Dokumentenverzeichnis festlegen. Dies ist der Speicherort, an dem Sie Ihre ursprüngliche PDF-Datei haben und an dem Sie die geänderte PDF-Datei speichern möchten. Ersetzen Sie „IHR DOKUMENTENVERZEICHNIS“ durch den entsprechenden Pfad.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Öffnen Sie das PDF-Dokument
 Anschließend können Sie das PDF-Dokument mit öffnen`Document` Klasse von Aspose.PDF. Stellen Sie sicher, dass Sie den korrekten Pfad zum Original-PDF-Dokument angeben.

```csharp
Document pdfDocument1 = new Document(dataDir + "InsertEmptyPageAtEnd.pdf");
```

## Schritt 3: Fügen Sie eine leere Seite ein
 Jetzt können Sie mit dem eine leere Seite am Ende des PDF-Dokuments einfügen`Add()` Methode der`Pages` Eigentum der`pdfDocument1` Objekt.

```csharp
pdfDocument1.Pages.Add();
```

## Schritt 4: Speichern Sie das geänderte Dokument
 Abschließend können Sie das geänderte PDF-Dokument mit in einer Datei speichern`Save()` Methode der`Document` Klasse. Stellen Sie sicher, dass Sie den richtigen Pfad und Dateinamen für die Ausgabedatei angeben.

```csharp
dataDir = dataDir + "InsertEmptyPageAtEnd_out.pdf";
pdfDocument1.Save(dataDir);
```

### Beispielquellcode für „Leere Seite am Ende einfügen“ mit Aspose.PDF für .NET 

```csharp

// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument1 = new Document(dataDir + "InsertEmptyPageAtEnd.pdf");
// Fügen Sie am Ende einer PDF-Datei eine leere Seite ein
pdfDocument1.Pages.Add();
dataDir = dataDir + "InsertEmptyPageAtEnd_out.pdf";
// Ausgabedatei speichern
pdfDocument1.Save(dataDir);
System.Console.WriteLine("\nEmpty page inserted successfully at the end of document.\nFile saved at " + dataDir);

```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.PDF für .NET eine leere Seite am Ende eines PDF-Dokuments einfügt. Wenn Sie dieser Schritt-für-Schritt-Anleitung folgen, können Sie ganz einfach eine leere Seite am Ende Ihres PDF-Dokuments hinzufügen. Aspose.PDF bietet eine leistungsstarke und flexible API für die Arbeit mit PDF-Dateien, mit der Sie PDF-Dokumente entsprechend Ihren spezifischen Anforderungen bearbeiten, ändern und generieren können.
