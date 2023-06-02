---
title: PDF zu HTML
linktitle: PDF zu HTML
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Konvertieren von PDF in HTML mit Aspose.PDF für .NET.
type: docs
weight: 130
url: /de/net/document-conversion/pdf-to-html/
---

In diesem Tutorial führen wir Sie durch den Prozess der Konvertierung einer PDF-Datei in das HTML-Format mit Aspose.PDF für .NET. Das PDF-Format wird üblicherweise zum Anzeigen und Teilen von Dokumenten verwendet, während das HTML-Format zum Erstellen von Webseiten verwendet wird. Wenn Sie die folgenden Schritte ausführen, können Sie PDF-Dateien in das HTML-Format konvertieren.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

- Grundkenntnisse der Programmiersprache C#.
- Aspose.PDF-Bibliothek für .NET auf Ihrem System installiert.
- Eine Entwicklungsumgebung wie Visual Studio.

## Schritt 1: Öffnen des Quell-PDF-Dokuments
In diesem Schritt öffnen wir die Quell-PDF-Datei mit Aspose.PDF für .NET. Befolgen Sie den folgenden Code:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Öffnen Sie das Quell-PDF-Dokument
Document pdfDocument = new Document(dataDir + "PDFToHTML.pdf");
```

 Unbedingt ersetzen`"YOUR DOCUMENTS DIRECTORY"` mit dem tatsächlichen Verzeichnis, in dem sich Ihre PDF-Datei befindet.

## Schritt 2: Konvertierung von PDF in HTML
Nach dem Öffnen der PDF-Datei können wir mit der Konvertierung in das HTML-Format fortfahren. Verwenden Sie den folgenden Code:

```csharp
// Speichern Sie die Datei im HTML-Format
pdfDocument.Save(dataDir + "output_out.html", SaveFormat.Html);
```

 Der obige Code konvertiert die PDF-Datei in das HTML-Format und speichert sie als`"output_out.html"` Datei.

 Ersetzen`"YOUR DOCUMENTS DIRECTORY"`mit dem gewünschten Verzeichnis, in dem Sie die ausgegebene HTML-Datei speichern möchten.

### Beispielquellcode für PDF zu HTML mit Aspose.Words für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Öffnen Sie das Quell-PDF-Dokument
Document pdfDocument = new Document(dataDir + "PDFToHTML.pdf");

//Speichern Sie die Datei im MS-Dokumentformat
pdfDocument.Save(dataDir + "output_out.html", SaveFormat.Html);
```

## Abschluss
In diesem Tutorial haben wir den Schritt-für-Schritt-Prozess zum Konvertieren einer PDF-Datei in das HTML-Format mit Aspose.PDF für .NET behandelt. Wenn Sie die oben beschriebenen Anweisungen befolgen, sollten Sie nun in der Lage sein, PDF-Dateien in das HTML-Format zu konvertieren. Diese Funktion ist nützlich, wenn Sie PDF-Inhalte in Webseiten oder andere Anwendungen einbetten möchten, die das HTML-Format unterstützen.

