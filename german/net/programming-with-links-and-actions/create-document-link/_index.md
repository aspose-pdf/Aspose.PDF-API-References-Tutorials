---
title: Dokumentlink erstellen
linktitle: Dokumentlink erstellen
second_title: Aspose.PDF für .NET API-Referenz
description: Erstellen Sie mit Aspose.PDF für .NET ganz einfach Links zu anderen PDF-Dokumenten.
type: docs
weight: 30
url: /de/net/programming-with-links-and-actions/create-document-link/
---

Durch die Verknüpfung mit einem anderen Dokument in einer PDF-Datei können Sie anklickbare Links erstellen, die Benutzer zu anderen PDF-Dokumenten weiterleiten. Mit Aspose.PDF für .NET können Sie solche Links ganz einfach erstellen, indem Sie dem folgenden Quellcode folgen:

## Schritt 1: Erforderliche Bibliotheken importieren

Bevor Sie beginnen, müssen Sie die erforderlichen Bibliotheken für Ihr C#-Projekt importieren. Hier ist die notwendige Importanweisung:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.InteractiveFeatures;
```

## Schritt 2: Legen Sie den Pfad zum Dokumentenordner fest

 In diesem Schritt müssen Sie den Pfad zu dem Ordner angeben, der die PDF-Datei enthält, zu der Sie einen Link zu einem anderen Dokument hinzufügen möchten. Ersetzen`"YOUR DOCUMENT DIRECTORY"` Geben Sie im folgenden Code den tatsächlichen Pfad zu Ihrem Dokumentenordner ein:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 3: Öffnen Sie das PDF-Dokument

Nun öffnen wir das PDF-Dokument, zu dem wir den Link zu einem anderen Dokument hinzufügen möchten, mit dem folgenden Code:

```csharp
Document document = new Document(dataDir + "CreateDocumentLink.pdf");
```

## Schritt 4: Erstellen Sie den Link zu einem anderen Dokument

 In diesem Schritt erstellen wir mithilfe von den Link zu einem anderen Dokument`LinkAnnotation` Anmerkung. Wir geben die Koordinaten und den Bereich des Links sowie die Navigationsaktion zu einem externen Dokument an. Hier ist der entsprechende Code:

```csharp
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link. Action = new GoToRemoteAction(dataDir + "RemoveOpenAction.pdf", 1);
page.Annotations.Add(link);
```

## Schritt 5: Speichern Sie die aktualisierte Datei

Speichern wir nun die aktualisierte PDF-Datei mit`Save` Methode der`document` Objekt. Hier ist der entsprechende Code:

```csharp
dataDir = dataDir + "CreateDocumentLink_out.pdf";
document. Save(dataDir);
```

### Beispielquellcode für „Dokumentverknüpfung erstellen“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document document = new Document(dataDir+ "CreateDocumentLink.pdf");
// Verknüpfung erstellen
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link.Action = new GoToRemoteAction(dataDir + "RemoveOpenAction.pdf", 1);
page.Annotations.Add(link);
dataDir = dataDir + "CreateDocumentLink_out.pdf";
// Aktualisiertes Dokument speichern
document.Save(dataDir);
Console.WriteLine("\nDocument link created successfully.\nFile saved at " + dataDir);            
```

## Abschluss

Herzlichen Glückwunsch! Sie verfügen nun über eine Schritt-für-Schritt-Anleitung zum Verknüpfen mit anderen Dokumenten mit Aspose.PDF für .NET. Mit diesem Code können Sie anklickbare Links in Ihren PDF-Dateien erstellen und Benutzer zu anderen Dokumenten weiterleiten.

Weitere Informationen zu den erweiterten Funktionen interaktiver Links finden Sie unbedingt in der offiziellen Aspose.PDF-Dokumentation.