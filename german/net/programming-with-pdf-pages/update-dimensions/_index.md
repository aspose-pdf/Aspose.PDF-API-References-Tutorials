---
title: Abmessungen aktualisieren
linktitle: Abmessungen aktualisieren
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Aktualisieren der PDF-Seitenabmessungen mit Aspose.PDF für .NET. Überprüfen Sie die Abmessungen entsprechend Ihren Anforderungen.
type: docs
weight: 150
url: /de/net/programming-with-pdf-pages/update-dimensions/
---
In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess zum Aktualisieren der Seitenabmessungen in einem PDF-Dokument mit Aspose.PDF für .NET. Wir erklären Ihnen den gebündelten C#-Quellcode und stellen Ihnen eine umfassende Anleitung zur Verfügung, die Ihnen hilft, diese Funktion zu verstehen und in Ihren eigenen Projekten zu implementieren. Am Ende dieses Tutorials erfahren Sie, wie Sie die Seitenabmessungen in einem PDF-Dokument mit Aspose.PDF für .NET ändern.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Grundkenntnisse der Programmiersprache C#
- Aspose.PDF für .NET in Ihrer Entwicklungsumgebung installiert

## Schritt 1: Definieren Sie das Dokumentenverzeichnis
Zuerst müssen Sie den Pfad zu Ihrem Dokumentenverzeichnis festlegen. Dies ist der Ort, an dem Sie Ihr bearbeitetes PDF-Dokument speichern möchten. Ersetzen Sie „IHR DOKUMENTENVERZEICHNIS“ durch den entsprechenden Pfad.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Öffnen Sie das PDF-Dokument
 Anschließend können Sie das vorhandene PDF-Dokument mit öffnen`Document` Klasse von Aspose.PDF. Stellen Sie sicher, dass Sie den richtigen Dokumentpfad angeben.

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## Schritt 3: Holen Sie sich die Seitensammlung
 Jetzt können Sie mit auf die Seitensammlung des PDF-Dokuments zugreifen`Pages` Eigentum der`Document` Klasse.

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## Schritt 4: Holen Sie sich eine bestimmte Seite
Anschließend können Sie mithilfe des Index der Seite in der Sammlung eine bestimmte Seite des Dokuments auswählen. In diesem Beispiel verwenden wir die zweite Seite (Index 1).

```csharp
Page pdfPage = pageCollection[1];
```

## Schritt 5: Definieren Sie die neuen Seitenabmessungen
 Jetzt können Sie die neue Seitengröße mit einstellen`SetPageSize()` Methode der`Page` Objekt. In diesem Beispiel stellen wir die Seitenabmessungen auf A4 (11,7 x 8,3 Zoll) ein, konvertiert in Punkt (1 Zoll = 72 Punkt).

```csharp
pdfPage.SetPageSize(597.6, 842.4);
```

## Schritt 6: Speichern Sie das aktualisierte Dokument
Abschließend können Sie das aktualisierte PDF-Dokument mit in einer Datei speichern`Save()` Methode der`Document`Klasse. Stellen Sie sicher, dass Sie den richtigen Pfad und Dateinamen angeben.

```csharp
dataDir = dataDir + "UpdateDimensions_out.pdf";
pdfDocument.Save(dataDir);
```

### Beispielquellcode für „Update Dimensions“ mit Aspose.PDF für .NET 

```csharp

// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
// Seitensammlung abrufen
PageCollection pageCollection = pdfDocument.Pages;
// Holen Sie sich eine bestimmte Seite
Page pdfPage = pageCollection[1];
// Stellen Sie die Seitengröße auf A4 (11,7 x 8,3 Zoll) und in Aspose.Pdf auf 1 Zoll = 72 Punkte ein
// Die A4-Abmessungen in Punkt betragen also (842,4, 597,6).
pdfPage.SetPageSize(597.6, 842.4);
dataDir = dataDir + "UpdateDimensions_out.pdf";
// Speichern Sie das aktualisierte Dokument
pdfDocument.Save(dataDir);
System.Console.WriteLine("\nPage dimensions updated successfully.\nFile saved at " + dataDir);

```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man die Abmessungen einer Seite in einem PDF-Dokument mit Aspose.PDF für .NET aktualisiert. Wenn Sie dieser Schritt-für-Schritt-Anleitung folgen, können Sie die Abmessungen einer Seite in einem PDF-Dokument ganz einfach nach Bedarf ändern. Aspose.PDF bietet eine leistungsstarke und flexible API für die Arbeit mit PDF-Dateien und die Durchführung verschiedener Manipulationen, einschließlich der Änderung der Seitenabmessungen. Mit diesem Wissen können Sie die Abmessungen Ihrer PDF-Seiten steuern und an Ihre spezifischen Anforderungen anpassen.
