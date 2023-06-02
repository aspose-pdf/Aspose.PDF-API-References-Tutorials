---
title: Werte aus allen Feldern abrufen
linktitle: Werte aus allen Feldern abrufen
second_title: Aspose.PDF für .NET API-Referenz
description: Mit Aspose.PDF für .NET erhalten Sie ganz einfach die Werte aller Formularfelder in Ihren PDF-Dokumenten.
type: docs
weight: 150
url: /de/net/programming-with-forms/get-values-from-all-fields/
---

In diesem Tutorial zeigen wir Ihnen, wie Sie mit Aspose.PDF für .NET die Werte aller Formularfelder in einem PDF-Dokument abrufen. Wir erklären Ihnen Schritt für Schritt den C#-Quellcode, um Sie durch diesen Prozess zu führen.

## Schritt 1: Vorbereitung

Stellen Sie sicher, dass Sie die erforderlichen Bibliotheken importiert und den Pfad zu Ihrem Dokumentenverzeichnis festgelegt haben:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Öffnen Sie das Dokument

Öffnen Sie das PDF-Dokument:

```csharp
Document pdfDocument = new Document(dataDir + "GetValuesFromAllFields.pdf");
```

## Schritt 3: Werte für alle Felder abrufen

Durchlaufen Sie alle Formularfelder im Dokument und ermitteln Sie deren Namen und Werte:

```csharp
foreach(Field formField in pdfDocument.Form)
{
Console.WriteLine("Field name: {0} ", formField.PartialName);
Console.WriteLine("Value: {0}", formField.Value);
}
```

### Beispielquellcode für „Werte aus allen Feldern abrufen“ mit Aspose.Words für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "GetValuesFromAllFields.pdf");
// Holen Sie sich Werte aus allen Feldern
foreach (Field formField in pdfDocument.Form)
{
	Console.WriteLine("Field Name : {0} ", formField.PartialName);
	Console.WriteLine("Value : {0} ", formField.Value);
}
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.PDF für .NET die Werte aller Formularfelder in einem PDF-Dokument erhält. Wenn Sie diese Schritte befolgen, können Sie mit Aspose.PDF ganz einfach die Werte aller Formularfelder aus Ihren PDF-Dokumenten extrahieren.