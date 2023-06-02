---
title: Zoomen Sie auf den Seiteninhalt
linktitle: Zoomen Sie auf den Seiteninhalt
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Zoomen auf Seiteninhalte in einer PDF-Datei mit Aspose.PDF für .NET. Erweitern Sie Ihre PDF-Dokumente entsprechend Ihren spezifischen Anforderungen.
type: docs
weight: 160
url: /de/net/programming-with-pdf-pages/zoom-to-page-contents/
---
In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess zum Vergrößern des Seiteninhalts einer PDF-Datei mit Aspose.PDF für .NET. Wir erklären Ihnen den gebündelten C#-Quellcode und stellen Ihnen eine umfassende Anleitung zur Verfügung, die Ihnen hilft, diese Funktion zu verstehen und in Ihren eigenen Projekten zu implementieren. Am Ende dieses Tutorials erfahren Sie, wie Sie den Seiteninhalt einer PDF-Datei mit Aspose.PDF für .NET zoomen.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Grundkenntnisse der Programmiersprache C#
- Aspose.PDF für .NET in Ihrer Entwicklungsumgebung installiert

## Schritt 1: Definieren Sie das Dokumentenverzeichnis
Zuerst müssen Sie den Pfad zu Ihrem Dokumentenverzeichnis festlegen. Hier liegen die PDF-Dateien, die Sie bearbeiten möchten. Ersetzen Sie „IHR DOKUMENTENVERZEICHNIS“ durch den entsprechenden Pfad.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Laden Sie die Quell-PDF-Datei
 Anschließend können Sie die Quell-PDF-Datei mit laden`Document` Klasse von Aspose.PDF. Stellen Sie sicher, dass Sie den korrekten Pfad zur PDF-Datei angeben.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Schritt 3: Stellen Sie den Seiteninhaltszoom ein
Um den Inhalt der Seite zu vergrößern, müssen wir Folgendes tun:

- Stellen Sie den rechteckigen Bereich der ersten Seite der PDF wieder her.
-  Instanziieren Sie die`PdfPageEditor` Klasse.
-  Verknüpfen Sie das Quell-PDF mit dem`PdfPageEditor` Beispiel.
- Definieren Sie den Zoomfaktor entsprechend der Breite und Höhe des Rechtecks.
- Aktualisieren Sie die Seitengröße mithilfe der Rechteckabmessungen.

Hier ist der entsprechende Code:

```csharp
Aspose.Pdf.Rectangle rect = doc.Pages[1].Rect;
PdfPageEditor ppe = new PdfPageEditor();
ppe.BindPdf(dataDir + "input.pdf");
ppe.Zoom = (float)(rect.Width / rect.Height);
ppe.PageSize = new Aspose.Pdf.PageSize((float)rect.Height, (float)rect.Width);
```

## Schritt 4: Speichern Sie die ausgegebene PDF-Datei
 Abschließend können Sie die geänderte PDF-Datei mit speichern`Save()` Methode der`Document` Klasse. Stellen Sie sicher, dass Sie den richtigen Pfad und Dateinamen angeben.

```csharp
dataDir = dataDir + "ZoomToPageContents_out.pdf";
doc.Save(dataDir);
```

### Beispielquellcode für Zoom To Page Contents mit Aspose.PDF für .NET 

```csharp

// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Laden Sie die PDF-Quelldatei
Document doc = new Document(dataDir + "input.pdf");
// Rufen Sie den rechteckigen Bereich der ersten PDF-Seite ab
Aspose.Pdf.Rectangle rect = doc.Pages[1].Rect;
// Instanziieren Sie die PdfPageEditor-Instanz
PdfPageEditor ppe = new PdfPageEditor();
// Quell-PDF binden
ppe.BindPdf(dataDir + "input.pdf");
// Zoomfaktor einstellen
ppe.Zoom = (float)(rect.Width / rect.Height);
// Seitengröße aktualisieren
ppe.PageSize = new Aspose.Pdf.PageSize((float)rect.Height, (float)rect.Width);
dataDir = dataDir + "ZoomToPageContents_out.pdf";
// Ausgabedatei speichern
doc.Save(dataDir);
System.Console.WriteLine("\nZoom to page contents applied successfully.\nFile saved at " + dataDir);

```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.PDF für .NET den Seiteninhalt einer PDF-Datei vergrößert. Wenn Sie dieser Schritt-für-Schritt-Anleitung folgen, können Sie ganz einfach den Zoom auf den Seiteninhalt Ihrer PDF-Dateien anwenden. Aspose.PDF bietet eine leistungsstarke und flexible API zum Arbeiten mit PDF-Dateien und zum Ausführen verschiedener Vorgänge, einschließlich des Zoomens auf Seiteninhalte. Nutzen Sie dieses Wissen, um Ihre PDF-Dokumente an Ihre spezifischen Bedürfnisse anzupassen und zu verbessern.
