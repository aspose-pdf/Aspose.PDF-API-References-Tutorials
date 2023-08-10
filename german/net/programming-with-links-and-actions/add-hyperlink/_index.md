---
title: Hyperlink in PDF-Datei hinzufügen
linktitle: Hyperlink in PDF-Datei hinzufügen
second_title: Aspose.PDF für .NET API-Referenz
description: Fügen Sie mit Aspose.PDF für .NET ganz einfach interaktive Hyperlinks in eine PDF-Datei ein.
type: docs
weight: 10
url: /de/net/programming-with-links-and-actions/add-hyperlink/
---
Durch das Hinzufügen von Hyperlinks in einer PDF-Datei können Sie interaktive Hyperlinks zu anderen Seiten, Websites oder Zielen im Dokument erstellen. Mit Aspose.PDF für .NET können Sie ganz einfach Hyperlinks hinzufügen, indem Sie dem folgenden Quellcode folgen:

## Schritt 1: Erforderliche Bibliotheken importieren

Bevor Sie beginnen, müssen Sie die erforderlichen Bibliotheken für Ihr C#-Projekt importieren. Hier ist die notwendige Importanweisung:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
```

## Schritt 2: Legen Sie den Pfad zum Dokumentenordner fest

In diesem Schritt müssen Sie den Pfad zu dem Ordner angeben, der die PDF-Datei enthält, zu der Sie einen Hyperlink hinzufügen möchten. Ersetzen`"YOUR DOCUMENT DIRECTORY"`Geben Sie im folgenden Code den tatsächlichen Pfad zu Ihrem Dokumentenordner ein:

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
// Erstellen Sie ein Link-Anmerkungsobjekt
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
// Erstellen Sie ein Rahmenobjekt für LinkAnnotation
Border border = new Border(link);
// Legen Sie den Wert für die Rahmenbreite auf 0 fest
border.Width = 0;
// Legen Sie den Rahmen für LinkAnnotation fest
link.Border = border;
// Geben Sie den Linktyp als Remote-URI an
link.Action = new GoToURIAction("www.aspose.com");
//Fügen Sie der Anmerkungssammlung der ersten Seite der PDF-Datei eine Linkanmerkung hinzu
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

### FAQs zum Hinzufügen eines Hyperlinks in einer PDF-Datei

#### F: Warum sollte ich erwägen, Hyperlinks zu meinen PDF-Dateien hinzuzufügen?

A: Das Hinzufügen von Hyperlinks zu Ihren PDF-Dateien verbessert die Benutzererfahrung, indem es den Lesern ermöglicht, problemlos zu anderen Seiten, Websites oder Zielen innerhalb des Dokuments zu navigieren. Es bietet eine nahtlose Möglichkeit, auf zusätzliche Ressourcen oder verwandte Informationen zuzugreifen.

#### F: Ist Aspose.PDF für .NET für Anfänger geeignet?

A: Ja, Aspose.PDF für .NET ist für Anfänger geeignet. Die Schritt-für-Schritt-Anleitung in diesem Handbuch vereinfacht das Hinzufügen von Hyperlinks zu PDF-Dateien und macht es für Entwickler mit unterschiedlichen Erfahrungsniveaus zugänglich.

#### F: Kann ich das Erscheinungsbild der Hyperlinks anpassen?

A: Auf jeden Fall! Aspose.PDF für .NET bietet Anpassungsoptionen für das Erscheinungsbild von Hyperlinks, einschließlich Textfarbe, Stil und Formatierung. Dadurch können Sie die Hyperlinks an das Gesamtdesign Ihres Dokuments anpassen.

#### F: Werden Hyperlinks in allen Arten von PDF-Dokumenten unterstützt?

A: Ja, Hyperlinks können zu verschiedenen Arten von PDF-Dokumenten hinzugefügt werden, einschließlich textbasierten Dokumenten, Bildern und multimedialen Dateien. Aspose.PDF für .NET stellt sicher, dass die Hyperlinks in verschiedenen PDF-Formaten funktionieren.

#### F: Welche weiteren Funktionalitäten bietet Aspose.PDF für .NET?

A: Aspose.PDF für .NET ist eine robuste Bibliothek, die eine breite Palette von Funktionen bietet, einschließlich PDF-Generierung, -Bearbeitung, -Konvertierung und -Extraktion. Es unterstützt die Arbeit mit Text, Bildern, Anmerkungen und mehr und ist damit ein vielseitiges Werkzeug für PDF-bezogene Aufgaben.

#### F: Können Hyperlinks zu bestimmten Abschnitten im Dokument hinzugefügt werden?

 A: Ja, mit dem`LinkAnnotation` Mithilfe von Anmerkungen können Sie Hyperlinks erstellen, die Benutzer zu bestimmten Abschnitten im PDF-Dokument weiterleiten. Diese Funktion ist besonders nützlich für die Erstellung interaktiver Inhaltsverzeichnisse oder Referenzlinks.

#### F: Gibt es Einschränkungen beim Hinzufügen von Hyperlinks in PDF-Dateien?

A: Aspose.PDF für .NET bietet zwar umfassende Hyperlink-Funktionalität, es ist jedoch wichtig sicherzustellen, dass der verlinkte Inhalt zugänglich und aktuell bleibt. Hyperlinks zu externen Websites sollten regelmäßig überprüft werden, um fehlerhafte Links zu vermeiden.

#### F: Kann ich mit Aspose.PDF für .NET Hyperlinks zu externen Dateien erstellen?

A: Ja, zusätzlich zu Web-URLs können Sie Hyperlinks erstellen, die zu externen Dateien führen, beispielsweise zu anderen PDF-Dokumenten, Bildern oder Multimediadateien. Aspose.PDF für .NET bietet die Flexibilität, eine Verknüpfung zu verschiedenen Arten von Ressourcen herzustellen.