---
title: Auf Seiten aufteilen
linktitle: Auf Seiten aufteilen
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Aufteilen eines PDF-Dokuments in einzelne Seiten mit Aspose.PDF für .NET.
type: docs
weight: 140
url: /de/net/programming-with-pdf-pages/split-to-pages/
---
In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess zum Aufteilen eines PDF-Dokuments in einzelne Seiten mit Aspose.PDF für .NET. Wir erklären Ihnen den gebündelten C#-Quellcode und stellen Ihnen eine umfassende Anleitung zur Verfügung, die Ihnen hilft, diese Funktion zu verstehen und in Ihren eigenen Projekten zu implementieren. Am Ende dieses Tutorials erfahren Sie, wie Sie ein PDF-Dokument in mehrere PDF-Dateien aufteilen, die jeweils eine einzelne Seite enthalten.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Grundkenntnisse der Programmiersprache C#
- Aspose.PDF für .NET in Ihrer Entwicklungsumgebung installiert

## Schritt 1: Definieren Sie das Dokumentenverzeichnis
Zuerst müssen Sie den Pfad zu Ihrem Dokumentenverzeichnis festlegen. Hier befindet sich das PDF-Dokument, das Sie teilen möchten. Ersetzen Sie „IHR DOKUMENTENVERZEICHNIS“ durch den entsprechenden Pfad.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Öffnen Sie das PDF-Dokument
 Anschließend können Sie das zu teilende PDF-Dokument mit öffnen`Document` Klasse von Aspose.PDF. Stellen Sie sicher, dass Sie den richtigen Dokumentpfad angeben.

```csharp
Document pdfDocument = new Document(dataDir + "SplitToPages.pdf");
```

## Schritt 3: Gehen Sie die Seiten durch und teilen Sie sie auf
Jetzt können Sie mit einer Schleife alle Seiten des PDF-Dokuments durchlaufen. Erstellen Sie für jede Seite ein neues Dokument und fügen Sie diese Seite diesem neuen Dokument hinzu. Speichern Sie dann das neue Dokument unter einem eindeutigen Dateinamen für jede Seite.

```csharp
int pageCount = 1;
foreach(Page pdfPage in pdfDocument.Pages)
{
Document newDocument = newDocument();
newDocument.Pages.Add(pdfPage);
newDocument.Save(dataDir + "page_" + pageCount + "_out" + ".pdf");
pageCount++;
}
```

### Beispielquellcode für Split To Pages mit Aspose.PDF für .NET 

```csharp

// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "SplitToPages.pdf");
int pageCount = 1;
// Gehen Sie alle Seiten durch
foreach (Page pdfPage in pdfDocument.Pages)
{
	Document newDocument = new Document();
	newDocument.Pages.Add(pdfPage);
	newDocument.Save(dataDir + "page_" + pageCount + "_out" + ".pdf");
	pageCount++;
}

```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.PDF für .NET ein PDF-Dokument in einzelne Seiten aufteilt. Wenn Sie dieser Schritt-für-Schritt-Anleitung folgen, können Sie ein PDF-Dokument ganz einfach in mehrere PDF-Dateien aufteilen, die jeweils eine einzelne Seite enthalten. Aspose.PDF bietet eine leistungsstarke und flexible API für die Arbeit mit PDF-Dokumenten in Ihren Projekten. Jetzt können Sie diese Funktion verwenden, um Aufteilungsvorgänge für PDF-Dokumente entsprechend Ihren spezifischen Anforderungen durchzuführen.
