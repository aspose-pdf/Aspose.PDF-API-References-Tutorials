---
title: Seiteninhalte anpassen
linktitle: Seiteninhalte anpassen
second_title: Aspose.PDF für .NET API-Referenz
description: Detaillierte Schritt-für-Schritt-Anleitung zum Anpassen des PDF-Seiteninhalts mit Aspose.PDF für .NET. Einfache Umsetzung und lohnender Abschluss.
type: docs
weight: 50
url: /de/net/programming-with-pdf-pages/fit-page-contents/
---
In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess zum Anpassen des PDF-Seiteninhalts mit Aspose.PDF für .NET. Wir erklären Ihnen den gebündelten C#-Quellcode und stellen Ihnen eine umfassende Anleitung zur Verfügung, die Ihnen hilft, diese Funktion zu verstehen und in Ihren eigenen Projekten zu implementieren. Am Ende dieses Tutorials erfahren Sie, wie Sie den Inhalt von PDF-Seiten mit Aspose.PDF für .NET anpassen.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Grundkenntnisse der Programmiersprache C#
- Aspose.PDF für .NET in Ihrer Entwicklungsumgebung installiert

## Schritt 1: Definieren Sie das Dokumentenverzeichnis
Zuerst müssen Sie den Pfad zu Ihrem Dokumentenverzeichnis festlegen. Dies ist der Speicherort, an dem sich Ihre Eingabe-PDF-Datei befindet. Ersetzen Sie „IHR DOKUMENTENVERZEICHNIS“ durch den entsprechenden Pfad.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Laden Sie das PDF-Dokument
 Anschließend können Sie das PDF-Dokument mit laden`Document` Klasse von Aspose.PDF. Stellen Sie sicher, dass Sie den korrekten Pfad zur Eingabe-PDF-Datei angeben.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Schritt 3: Seiteninhalt anpassen
Jetzt können Sie durch alle Seiten des Dokuments blättern und den Inhalt jeder Seite entsprechend der Größe der Medienbox anpassen. Im bereitgestellten Beispiel passen wir die Breite der Seite an, um sie im Querformat (Querformat) darzustellen und dabei die gleiche Höhe beizubehalten. Die neue Breite wird basierend auf dem Seitenverhältnis der Medienbox berechnet.

```csharp
foreach(Page page in doc.Pages)
{
     Rectangle r = page.MediaBox;
     double newHeight = r.Height;
     double newWidth = r.Height * r.Height / r.Width;
}
```

### Beispielquellcode für „Seiteninhalte anpassen“ mit Aspose.PDF für .NET 

```csharp

// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
foreach (Page page in doc.Pages)
{
	Rectangle r = page.MediaBox;
	// Neue Höhe gleich
	double newHeight = r.Height;
	// Die neue Breite wird proportional erweitert, um die Ausrichtung im Querformat zu ermöglichen
	// (Wir gehen davon aus, dass die vorherige Ausrichtung das Hochformat ist)
	double newWidth = r.Height * r.Height / r.Width;
}          

```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man PDF-Seiteninhalte mit Aspose.PDF für .NET anpasst. Wenn Sie die oben beschriebenen Schritte befolgen, können Sie diese Funktionalität problemlos in Ihre eigenen Projekte implementieren. Sehen Sie sich gerne die Aspose.PDF-Dokumentation weiter an, um weitere nützliche Funktionen für die Arbeit mit PDF-Dateien zu entdecken.
