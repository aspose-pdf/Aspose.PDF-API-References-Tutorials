---
title: Felder aus der Region abrufen
linktitle: Felder aus der Region abrufen
second_title: Aspose.PDF für .NET API-Referenz
description: Mit Aspose.PDF für .NET können Sie ganz einfach Felder aus einer bestimmten Region in Ihre PDF-Dokumente integrieren.
type: docs
weight: 130
url: /de/net/programming-with-forms/get-fields-from-region/
---

In diesem Tutorial zeigen wir Ihnen, wie Sie mit Aspose.PDF für .NET die Felder einer bestimmten Region in einem PDF-Dokument abrufen. Wir erklären Ihnen Schritt für Schritt den C#-Quellcode, um Sie durch diesen Prozess zu führen.

## Schritt 1: Vorbereitung

Stellen Sie sicher, dass Sie die erforderlichen Bibliotheken importiert und den Pfad zu Ihrem Dokumentenverzeichnis festgelegt haben:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Öffnen Sie die PDF-Datei

Öffnen Sie die PDF-Datei:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
```

## Schritt 3: Erstellen Sie ein rechteckiges Objekt, um den Bereich zu begrenzen

Erstellen Sie ein rechteckiges Objekt, um den Bereich zu begrenzen, in dem Sie die Felder erhalten möchten:

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
```

## Schritt 4: Besorgen Sie sich das PDF-Formular

Holen Sie sich das PDF-Formular des Dokuments:

```csharp
Aspose.Pdf.Forms.Form form = doc.Form;
```

## Schritt 5: Holen Sie sich die Felder im rechteckigen Bereich

Rufen Sie die Felder ab, die sich im angegebenen rechteckigen Bereich befinden:

```csharp
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
```

## Schritt 6: Feldnamen und Werte anzeigen

Durchlaufen Sie die resultierenden Felder und zeigen Sie deren Namen und Werte an:

```csharp
foreach (Field field in fields)
{
Console.Out.WriteLine("Field name: " + field.FullName + "-" + "Field value: " + field.Value);
}
```

### Beispielquellcode für „Felder aus Region abrufen“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// PDF-Datei öffnen
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
// Erstellen Sie ein rechteckiges Objekt, um Felder in diesem Bereich abzurufen
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
// Holen Sie sich das PDF-Formular
Aspose.Pdf.Forms.Form form = doc.Form;
//Holen Sie sich Felder im rechteckigen Bereich
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
// Feldnamen und -werte anzeigen
foreach (Field field in fields)
{
	// Bildplatzierungseigenschaften für alle Platzierungen anzeigen
	Console.Out.WriteLine("Field Name: " + field.FullName + "-" + "Field Value: " + field.Value);
}
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.PDF für .NET die Felder einer bestimmten Region in einem PDF-Dokument abruft. Wenn Sie diese Schritte befolgen, können Sie mit Aspose.PDF ganz einfach die Felder extrahieren, die sich in einem bestimmten rechteckigen Bereich Ihres PDF-Dokuments befinden.