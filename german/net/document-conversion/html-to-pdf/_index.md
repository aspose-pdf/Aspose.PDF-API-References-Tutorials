---
title: HTML zu PDF
linktitle: HTML zu PDF
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Konvertieren von HTML in PDF mit Aspose.PDF für .NET.
type: docs
weight: 50
url: /de/net/document-conversion/html-to-pdf/
---

In diesem Tutorial führen wir Sie durch den Prozess der Konvertierung einer HTML-Datei in PDF mit Aspose.PDF für .NET. HTML (HyperText Markup Language) ist eine Auszeichnungssprache, die zur Strukturierung und Darstellung von Webinhalten verwendet wird. Wenn Sie die folgenden Schritte ausführen, können Sie HTML-Dateien in das PDF-Format konvertieren.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

- Grundkenntnisse der Programmiersprache C#.
- Aspose.PDF-Bibliothek für .NET auf Ihrem System installiert.
- Eine Entwicklungsumgebung wie Visual Studio.

## Schritt 1: Laden der HTML-Datei
In diesem Schritt laden wir die HTML-Datei mit Aspose.PDF für .NET. Befolgen Sie den folgenden Code:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

HtmlLoadOptions options = new HtmlLoadOptions();
options.CustomLoaderOfExternalResources = new LoadOptions.ResourceLoadingStrategy(SamePictureLoader);

Document pdfDocument = new Document(dataDir + "HTMLToPDF.html", options);
```

 Unbedingt ersetzen`"YOUR DOCUMENTS DIRECTORY"` mit dem tatsächlichen Verzeichnis, in dem sich Ihre HTML-Datei befindet.

## Schritt 2: HTML-Ladeoptionen
Nachdem wir nun die HTML-Datei geladen haben, können wir bestimmte Ladeoptionen festlegen. Verwenden Sie den folgenden Code:

```csharp
options.CustomLoaderOfExternalResources = new LoadOptions.ResourceLoadingStrategy(SamePictureLoader);
```

Der obige Code weist Aspose.PDF an, eine benutzerdefinierte Ladestrategie für externe Ressourcen wie Bilder zu verwenden. Sie können diese Richtlinie an Ihre Bedürfnisse anpassen.

## Schritt 3: Konvertierung von HTML in PDF
Nachdem wir die HTML-Datei geladen und die Ladeoptionen festgelegt haben, können wir mit der Konvertierung in PDF fortfahren. Verwenden Sie den folgenden Code:

```csharp
pdfDocument.Save("HTMLToPDF_out.pdf");
```

### Beispielquellcode für HTML in PDF mit Aspose.Words für .NET

```csharp
try
{
	
	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	HtmlLoadOptions options = new HtmlLoadOptions();
	options.CustomLoaderOfExternalResources = new LoadOptions.ResourceLoadingStrategy(SamePictureLoader);

	Document pdfDocument = new Document(dataDir + "HTMLToPDF.html", options);
	pdfDocument.Save("HTMLToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Abschluss
In diesem Tutorial haben wir den Prozess Schritt für Schritt behandelt. Schritt der Konvertierung einer HTML-Datei in PDF mit Aspose.PDF für .NET. Wenn Sie die oben beschriebenen Anweisungen befolgen, sollten Sie nun in der Lage sein, HTML-Dateien in das PDF-Format zu konvertieren. Diese Funktion kann nützlich sein, wenn Sie PDF-Dokumente aus HTML-Inhalten generieren müssen.

