---
title: Hyperlink hinzufügen
linktitle: Hyperlink hinzufügen
second_title: Aspose.PDF für .NET API-Referenz
description: Fügen Sie mit Aspose.PDF für .NET ganz einfach interaktive Hyperlinks in Ihre PDF-Dateien ein.
type: docs
weight: 10
url: /de/net/programming-with-links-and-actions/add-hyperlink/
---

Durch das Hinzufügen von Hyperlinks in einem PDF-Dokument können Sie interaktive Hyperlinks zu anderen Seiten, Websites oder Zielen im Dokument erstellen. Mit Aspose.PDF für .NET können Sie ganz einfach Hyperlinks hinzufügen, indem Sie dem folgenden Quellcode folgen:

## Schritt 1: Erforderliche Bibliotheken importieren

Bevor Sie beginnen, müssen Sie die erforderlichen Bibliotheken für Ihr C#-Projekt importieren. Hier ist die notwendige Importanweisung:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
```

## Schritt 2: Legen Sie den Pfad zum Dokumentenordner fest

 In diesem Schritt müssen Sie den Pfad zu dem Ordner angeben, der die PDF-Datei enthält, zu der Sie einen Hyperlink hinzufügen möchten. Ersetzen`"YOUR DOCUMENT DIRECTORY"` Geben Sie im folgenden Code den tatsächlichen Pfad zu Ihrem Dokumentenordner ein:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 3: Öffnen Sie das PDF-Dokument

Nun öffnen wir das PDF-Dokument, zu dem wir einen Hyperlink hinzufügen möchten, mit dem folgenden Code:

```csharp
Document document = new Document(dataDir + "AddHyperlink.pdf");
```

## Schritt 4: Erstellen Sie einen Link

 In diesem Schritt erstellen wir einen Hyperlink mit`LinkAnnotation` Anmerkung. Wir geben dabei die Kontaktdaten und den Bereich der Verlinkung, die Art der Verlinkung und den Inhalt der Verlinkung an. Hier ist der entsprechende Code:

```csharp
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
Border border = new Border(link);
border. Width = 0;
link. Border = border;
link. Action = new GoToURIAction("www.aspose.com");
page.Annotations.Add(link);
```

## Schritt 5: Fügen Sie zusätzlichen Text hinzu

 Zusätzlich zum Hyperlink können wir mit dem auch zusätzlichen Text hinzufügen`FreeTextAnnotation` Anmerkung. Wir legen Koordinaten, Textaussehen und Textinhalt fest. Hier ist der entsprechende Code:

```csharp
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(document.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), new DefaultAppearance(Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman"), 10, System .Drawing.Color.Blue));
textAnnotation.Contents = "Link to Aspose website";
textAnnotation. Border = border;
document.Pages[1].Annotations.Add(textAnnotation);
```

## Schritt 6: Speichern Sie die aktualisierte Datei

Speichern wir nun die aktualisierte PDF-Datei mit`Save` Methode der`document` Objekt. Hier ist der entsprechende Code:

```csharp
dataDir = dataDir + "AddHyperlink_out.pdf";
document. Save(dataDir);
```

### Beispielquellcode für „Hyperlink hinzufügen“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document document = new Document(dataDir + "AddHyperlink.pdf");
// Verknüpfung erstellen
Page page = document.Pages[1];
//Erstellen Sie ein Link-Anmerkungsobjekt
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
// Erstellen Sie ein Rahmenobjekt für LinkAnnotation
Border border = new Border(link);
// Legen Sie den Wert für die Rahmenbreite auf 0 fest
border.Width = 0;
// Legen Sie den Rahmen für LinkAnnotation fest
link.Border = border;
// Geben Sie den Linktyp als Remote-URI an
link.Action = new GoToURIAction("www.aspose.com");
// Fügen Sie der Anmerkungssammlung der ersten Seite der PDF-Datei eine Linkanmerkung hinzu
page.Annotations.Add(link);
// Erstellen Sie eine Freitext-Anmerkung
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(document.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), new DefaultAppearance(Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman"), 10, System.Drawing.Color.Blue));
// Zeichenfolge, die als Freitext hinzugefügt werden soll
textAnnotation.Contents = "Link to Aspose website";
// Legen Sie den Rahmen für Freitextanmerkungen fest
textAnnotation.Border = border;
// Fügen Sie der Anmerkungssammlung der ersten Seite des Dokuments eine Freitextanmerkung hinzu
document.Pages[1].Annotations.Add(textAnnotation);
dataDir = dataDir + "AddHyperlink_out.pdf";
// Aktualisiertes Dokument speichern
document.Save(dataDir);
Console.WriteLine("\nHyperlink added successfully.\nFile saved at " + dataDir);            
```

## Abschluss

Herzlichen Glückwunsch! Sie haben jetzt eine Schritt-für-Schritt-Anleitung zum Hinzufügen von Hyperlinks mit Aspose.PDF für .NET. Mit diesem Code können Sie interaktive Links in Ihren PDF-Dokumenten erstellen.