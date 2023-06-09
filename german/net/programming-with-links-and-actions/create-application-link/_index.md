---
title: Anwendungslink erstellen
linktitle: Anwendungslink erstellen
second_title: Aspose.PDF für .NET API-Referenz
description: Erstellen Sie mit Aspose.PDF für .NET ganz einfach Anwendungslinks in Ihren PDF-Dateien.
type: docs
weight: 20
url: /de/net/programming-with-links-and-actions/create-application-link/
---

Durch das Erstellen eines Anwendungslinks in einem PDF-Dokument können Sie Links zu externen Anwendungen erstellen, beispielsweise zu ausführbaren Dateien oder URLs. Mit Aspose.PDF für .NET können Sie ganz einfach App-Links erstellen, indem Sie dem folgenden Quellcode folgen:

## Schritt 1: Erforderliche Bibliotheken importieren

Bevor Sie beginnen, müssen Sie die erforderlichen Bibliotheken für Ihr C#-Projekt importieren. Hier ist die notwendige Importanweisung:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.InteractiveFeatures;
```

## Schritt 2: Legen Sie den Pfad zum Dokumentenordner fest

In diesem Schritt müssen Sie den Pfad zu dem Ordner angeben, der die PDF-Datei enthält, zu der Sie einen App-Link hinzufügen möchten. Ersetzen`"YOUR DOCUMENT DIRECTORY"` Geben Sie im folgenden Code den tatsächlichen Pfad zu Ihrem Dokumentenordner ein:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 3: Öffnen Sie das PDF-Dokument

Nun öffnen wir das PDF-Dokument, zu dem wir einen Bewerbungslink hinzufügen möchten, mit dem folgenden Code:

```csharp
Document document = new Document(dataDir + "CreateApplicationLink.pdf");
```

## Schritt 4: Erstellen Sie den Anwendungslink

 In diesem Schritt erstellen wir den Anwendungslink mithilfe von`LinkAnnotation` Anmerkung. Wir geben die Koordinaten und den Bereich des Links sowie die Aktion zum Starten der Anwendung an. Hier ist der entsprechende Code:

```csharp
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link. Action = new LaunchAction(document, dataDir + "CreateApplicationLink.pdf");
page.Annotations.Add(link);
```

## Schritt 5: Speichern Sie die aktualisierte Datei

Speichern wir nun die aktualisierte PDF-Datei mit`Save` Methode der`document` Objekt. Hier ist der entsprechende Code:

```csharp
dataDir = dataDir + "CreateApplicationLink_out.pdf";
document. Save(dataDir);
```

### Beispielquellcode für „Anwendungslink erstellen“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document document = new Document( dataDir + "CreateApplicationLink.pdf");
// Verknüpfung erstellen
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link.Action = new LaunchAction(document, dataDir + "CreateApplicationLink.pdf");
page.Annotations.Add(link);
dataDir = dataDir + "CreateApplicationLink_out.pdf";
// Aktualisiertes Dokument speichern
document.Save(dataDir);
Console.WriteLine("\nApplication link created successfully.\nFile saved at " + dataDir);
```

## Abschluss

Herzlichen Glückwunsch! Sie haben jetzt eine Schritt-für-Schritt-Anleitung zum Erstellen von App-Links mit Aspose.PDF für .NET. Mit diesem Code können Sie Links zu externen Anwendungen in Ihre PDF-Dokumente einfügen.

Weitere Informationen zu den erweiterten Funktionen interaktiver Links finden Sie unbedingt in der offiziellen Aspose.PDF-Dokumentation.