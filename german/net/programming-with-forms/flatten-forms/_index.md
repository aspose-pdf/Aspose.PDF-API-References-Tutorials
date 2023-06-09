---
title: Formen abflachen
linktitle: Formen abflachen
second_title: Aspose.PDF für .NET API-Referenz
description: Reduzieren Sie Formulare in Ihren PDF-Dokumenten ganz einfach mit Aspose.PDF für .NET.
type: docs
weight: 100
url: /de/net/programming-with-forms/flatten-forms/
---

In diesem Tutorial zeigen wir Ihnen, wie Sie Formulare mit Aspose.PDF für .NET reduzieren. Wir erklären Ihnen Schritt für Schritt den C#-Quellcode, um Sie durch diesen Prozess zu führen.

## Schritt 1: Vorbereitung

Stellen Sie zunächst sicher, dass Sie die erforderlichen Bibliotheken importiert haben und legen Sie den Pfad zum Dokumentenverzeichnis fest:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Laden Sie das Quell-PDF-Formular

Laden Sie das Quell-PDF-Formular:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Schritt 3: Glätten Sie die Formen

Überprüfen Sie zunächst, ob das Dokument Formularfelder enthält. Wenn ja, durchlaufen Sie jedes Feld und wenden Sie die Reduzierung an:

```csharp
if (doc.Form.Fields.Count() > 0)
{
foreach (var item in doc.Form.Fields)
{
item. Flatten();
}
}
```

## Schritt 4: Speichern Sie das aktualisierte Dokument

Speichern Sie das aktualisierte PDF-Dokument:

```csharp
dataDir = dataDir + "FlattenForms_out.pdf";
doc.Save(dataDir);
```

### Beispielquellcode für Flatten Forms mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Laden Sie das Quell-PDF-Formular
Document doc = new Document(dataDir + "input.pdf");
// Formen abflachen
if (doc.Form.Fields.Count() > 0)
{
	foreach (var item in doc.Form.Fields)
	{
		item.Flatten();
	}
}
dataDir = dataDir + "FlattenForms_out.pdf";
// Speichern Sie das aktualisierte Dokument
doc.Save(dataDir);
Console.WriteLine("\nForms flattened successfully.\nFile saved at " + dataDir);
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man Formulare mit Aspose.PDF für .NET reduziert. Wenn Sie diese Schritte befolgen, können Sie Formulare in Ihren PDF-Dokumenten ganz einfach reduzieren, Felder nicht mehr bearbeiten und Anmerkungen mit Dokumentinhalten zusammenführen.