---
title: Aktualisieren Sie die PDF-Seitenabmessungen
linktitle: Aktualisieren Sie die PDF-Seitenabmessungen
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
 Jetzt können Sie die neue Seitengröße mit einstellen`SetPageSize()` Methode der`Page`Objekt. In diesem Beispiel stellen wir die Seitenabmessungen auf A4 (11,7 x 8,3 Zoll) ein, konvertiert in Punkt (1 Zoll = 72 Punkt).

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

### FAQs zum Aktualisieren der PDF-Seitenabmessungen

#### F: Wie kann ich die Abmessungen einer bestimmten Seite in einem PDF-Dokument mit Aspose.PDF für .NET aktualisieren?

A: Um die Abmessungen einer bestimmten Seite in einem PDF-Dokument mit Aspose.PDF für .NET zu aktualisieren, können Sie die folgenden Schritte ausführen:

1. Legen Sie das Dokumentverzeichnis fest, indem Sie den Pfad angeben, in dem sich Ihre ursprüngliche PDF-Datei befindet und wo Sie die aktualisierte PDF-Datei speichern möchten. Ersetzen Sie „IHR DOKUMENTENVERZEICHNIS“ durch den entsprechenden Pfad.
2.  Öffnen Sie das vorhandene PDF-Dokument, um es zu aktualisieren`Document` Klasse von Aspose.PDF. Stellen Sie sicher, dass Sie den korrekten Pfad zum Original-PDF-Dokument angeben.
3.  Greifen Sie mit auf die Seitensammlung des PDF-Dokuments zu`Pages` Eigentum der`Document` Klasse.
4. Wählen Sie mithilfe des Seitenindex die spezifische Seite aus der Seitensammlung aus, die Sie aktualisieren möchten. Im bereitgestellten C#-Quellcode verwenden wir die zweite Seite (Index 1).
5.  Definieren Sie die neue Seitengröße mit`SetPageSize()` Methode der`Page` Objekt. Im Beispiel stellen wir die Seitenabmessungen auf die Größe A4 (11,7 x 8,3 Zoll) ein und konvertieren sie in Punkt (1 Zoll = 72 Punkt).
6.  Speichern Sie das aktualisierte PDF-Dokument mit in einer Datei`Save()` Methode der`Document`Klasse. Stellen Sie sicher, dass Sie den richtigen Pfad und Dateinamen angeben.

#### F: Kann ich die Abmessungen mehrerer Seiten im PDF-Dokument gleichzeitig aktualisieren?

A: Ja, Sie können den bereitgestellten Quellcode ändern, um die Abmessungen mehrerer Seiten im PDF-Dokument gleichzeitig zu aktualisieren. Anstatt eine bestimmte Seite auszuwählen (wie in Schritt 4 gezeigt), können Sie alle Seiten in der Seitensammlung durchlaufen und für jede Seite die gewünschte Seitengröße festlegen.

#### F: Wie konvertiere ich Seitenabmessungen von Zoll in Punkte, wenn ich Aspose.PDF für .NET verwende?

 A: In Aspose.PDF für .NET ist die für die Seitenabmessungen verwendete Maßeinheit Punkt, wobei 1 Zoll 72 Punkten entspricht. Um Zoll in Punkte umzurechnen, können Sie die Formel verwenden:`points = inches * 72`. Um beispielsweise eine Seitengröße von 11,7 x 8,3 Zoll festzulegen, können Sie die entsprechenden Abmessungen in Punkten als (11,7 * 72) und (8,3 * 72) berechnen.

#### F: Hat die Aktualisierung der Seitenabmessungen Auswirkungen auf das Inhaltslayout des PDF-Dokuments?

A: Ja, das Aktualisieren der Abmessungen einer Seite wirkt sich auf das Inhaltslayout des PDF-Dokuments auf dieser bestimmten Seite aus. Wenn Sie die Seitenabmessungen ändern, wird der Inhalt der Seite entsprechend angepasst, um in die neuen Abmessungen zu passen.

#### F: Ist es möglich, die Änderungen rückgängig zu machen und die ursprünglichen Seitenabmessungen nach der Aktualisierung wiederherzustellen?

A: Ja, wenn Sie die Änderungen rückgängig machen und die ursprünglichen Seitenabmessungen wiederherstellen möchten, können Sie entweder eine Kopie des ursprünglichen PDF-Dokuments aufbewahren, bevor Sie Änderungen vornehmen, oder das ursprüngliche PDF-Dokument erneut öffnen, ohne die Änderungen zu speichern. Dadurch bleiben die Originalmaße erhalten.