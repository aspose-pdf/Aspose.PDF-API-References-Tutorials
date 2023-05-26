---
title: Legen Sie die Eigenschaften für den Druckdialog fest
linktitle: Legen Sie die Eigenschaften für den Druckdialog fest
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie anhand der Schritt-für-Schritt-Anleitung, wie Sie Eigenschaften für den Druckdialog in Aspose.PDF für .NET festlegen.
type: docs
weight: 320
url: /de/net/programming-with-document/setpropertiesforprintdialog/
---
Hier ist eine Schritt-für-Schritt-Anleitung zum Festlegen von Eigenschaften für den Druckdialog mit Aspose.PDF für .NET:


## Schritt 1: Definieren Sie das Verzeichnis, in dem sich Ihr PDF-Dokument befindet:

```csharp
var dataDir = "YOUR DOCUMENT DIRECTORY";
```
   
##  Schritt 2: Erstellen Sie eine neue Instanz von`Document` class:

```csharp
using (Document doc = new Document())
{
  // Code hier
}
```
   
## Schritt 3: Fügen Sie dem Dokument eine neue Seite hinzu:

```csharp
doc.Pages.Add();
```
   
##  Schritt 4: Setzen Sie die Duplexeigenschaft auf`DuplexFlipLongEdge`:

```csharp
doc.Duplex = PrintDuplex.DuplexFlipLongEdge;
```
   
## Schritt 5: Speichern Sie das Dokument unter dem angegebenen Dateinamen und Format:

```csharp
doc.Save(dataDir + "35297_out.pdf", SaveFormat.Pdf);
```

## Abschluss

Mit Aspose.PDF für .NET können Sie ganz einfach Eigenschaften für den Druckdialog in Ihren PDF-Dateien festlegen. Wenn Sie der obigen Schritt-für-Schritt-Anleitung folgen, können Sie Ihre PDF-Dateien schnell für den Druck optimieren.

### Beispielquellcode für das Dialogfeld „Eigenschaften für Druck festlegen“ mit Aspose.PDF für .NET

```csharp

	var dataDir = "YOUR DOCUMENT DIRECTORY";

	using (Document doc = new Document())
	{
		doc.Pages.Add();
		doc.Duplex = PrintDuplex.DuplexFlipLongEdge;
		doc.Save(dataDir + "35297_out.pdf", SaveFormat.Pdf);
	}

```
