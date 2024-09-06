---
title: Hyperlink in PDF-Datei hinzufügen
linktitle: Hyperlink in PDF-Datei hinzufügen
second_title: Aspose.PDF für .NET API-Referenz
description: Fügen Sie mit Aspose.PDF für .NET ganz einfach interaktive Hyperlinks in PDF-Dateien ein.
type: docs
weight: 10
url: /de/net/programming-with-links-and-actions/add-hyperlink/
---
Durch das Hinzufügen von Hyperlinks in PDF-Dateien können Sie interaktive Hyperlinks zu anderen Seiten, Websites oder Zielen im Dokument erstellen. Mit Aspose.PDF für .NET können Sie ganz einfach Hyperlinks hinzufügen, indem Sie dem folgenden Quellcode folgen:

## Schritt 1: Erforderliche Bibliotheken importieren

Bevor Sie beginnen, müssen Sie die erforderlichen Bibliotheken für Ihr C#-Projekt importieren. Hier ist die erforderliche Importanweisung:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
```

## Schritt 2: Pfad zum Dokumentenordner festlegen

 In diesem Schritt müssen Sie den Pfad zum Ordner angeben, der die PDF-Datei enthält, zu der Sie einen Hyperlink hinzufügen möchten. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` ersetzen Sie den folgenden Code durch den tatsächlichen Pfad zu Ihrem Dokumentordner:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 3: Öffnen Sie das PDF-Dokument

Nun öffnen wir das PDF-Dokument, dem wir mit dem folgenden Code einen Hyperlink hinzufügen möchten:

```csharp
Document document = new Document(dataDir + "AddHyperlink.pdf");
```

## Schritt 4: Link erstellen

 In diesem Schritt erstellen wir einen Hyperlink mit dem`LinkAnnotation` Annotation. Wir geben die Kontaktdaten und den Bereich des Links, die Art des Links und den Inhalt des Links an. Hier ist der entsprechende Code:

```csharp
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
Border border = new Border(link);
border. Width = 0;
link. Border = border;
link. Action = new GoToURIAction("www.aspose.com");
page.Annotations.Add(link);
```

## Schritt 5: Zusätzlichen Text hinzufügen

 Zusätzlich zum Hyperlink können wir auch zusätzlichen Text hinzufügen, indem wir`FreeTextAnnotation` Annotation. Wir werden Koordinaten, Textdarstellung und Textinhalt angeben. Hier ist der entsprechende Code:

```csharp
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(document.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), new DefaultAppearance(Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman"), 10, System .Drawing.Color.Blue));
textAnnotation.Contents = "Link to Aspose website";
textAnnotation. Border = border;
document.Pages[1].Annotations.Add(textAnnotation);
```

## Schritt 6: Speichern Sie die aktualisierte Datei

Speichern wir nun die aktualisierte PDF-Datei mit dem`Save` Methode der`document` Objekt. Hier ist der entsprechende Code:

```csharp
dataDir = dataDir + "AddHyperlink_out.pdf";
document. Save(dataDir);
```

### Beispielquellcode zum Hinzufügen eines Hyperlinks mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document document = new Document(dataDir + "AddHyperlink.pdf");
// Verknüpfung erstellen
Page page = document.Pages[1];
// Link-Annotationsobjekt erstellen
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
// Rahmenobjekt für LinkAnnotation erstellen
Border border = new Border(link);
// Setzen Sie den Wert für die Rahmenbreite auf 0
border.Width = 0;
// Legen Sie den Rahmen für LinkAnnotation fest
link.Border = border;
// Geben Sie den Linktyp als Remote-URI an
link.Action = new GoToURIAction("www.aspose.com");
// Linkanmerkung zur Anmerkungssammlung der ersten Seite der PDF-Datei hinzufügen
page.Annotations.Add(link);
// Freitextanmerkungen erstellen
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(document.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), new DefaultAppearance(Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman"), 10, System.Drawing.Color.Blue));
// Als Freitext hinzuzufügende Zeichenfolge
textAnnotation.Contents = "Link to Aspose website";
// Festlegen des Rahmens für Freitextanmerkungen
textAnnotation.Border = border;
// FreeText-Anmerkung zur Anmerkungssammlung der ersten Seite des Dokuments hinzufügen
document.Pages[1].Annotations.Add(textAnnotation);
dataDir = dataDir + "AddHyperlink_out.pdf";
// Aktualisiertes Dokument speichern
document.Save(dataDir);
Console.WriteLine("\nHyperlink added successfully.\nFile saved at " + dataDir);            
```

## Abschluss

Herzlichen Glückwunsch! Sie haben jetzt eine Schritt-für-Schritt-Anleitung zum Hinzufügen von Hyperlinks mit Aspose.PDF für .NET. Sie können diesen Code verwenden, um interaktive Links in Ihren PDF-Dokumenten zu erstellen.

### FAQs zum Hinzufügen von Hyperlinks in PDF-Dateien

#### F: Warum sollte ich meinen PDF-Dateien Hyperlinks hinzufügen?

A: Das Hinzufügen von Hyperlinks zu Ihren PDF-Dateien verbessert das Benutzererlebnis, da Leser so problemlos zu anderen Seiten, Websites oder Zielen innerhalb des Dokuments navigieren können. Dies bietet eine nahtlose Möglichkeit, auf zusätzliche Ressourcen oder verwandte Informationen zuzugreifen.

#### F: Ist Aspose.PDF für .NET für Anfänger geeignet?

A: Ja, Aspose.PDF für .NET ist anfängerfreundlich. Das in diesem Handbuch bereitgestellte Schritt-für-Schritt-Tutorial vereinfacht das Hinzufügen von Hyperlinks zu PDF-Dateien und macht es für Entwickler mit unterschiedlichen Kenntnissen zugänglich.

#### F: Kann ich das Erscheinungsbild der Hyperlinks anpassen?

A: Absolut! Aspose.PDF für .NET bietet Anpassungsoptionen für das Erscheinungsbild von Hyperlinks, einschließlich Textfarbe, Stil und Formatierung. So können Sie die Hyperlinks an das Gesamtdesign Ihres Dokuments anpassen.

#### F: Werden Hyperlinks in allen Arten von PDF-Dokumenten unterstützt?

A: Ja, Hyperlinks können zu verschiedenen Arten von PDF-Dokumenten hinzugefügt werden, darunter textbasierte Dokumente, Bilder und Multimediadateien. Aspose.PDF für .NET stellt sicher, dass die Hyperlinks in verschiedenen PDF-Formaten funktionieren.

#### F: Welche anderen Funktionen bietet Aspose.PDF für .NET?

A: Aspose.PDF für .NET ist eine robuste Bibliothek, die eine breite Palette an Funktionen bietet, darunter PDF-Erstellung, -Bearbeitung, -Konvertierung und -Extraktion. Es unterstützt die Arbeit mit Text, Bildern, Anmerkungen und mehr und ist somit ein vielseitiges Tool für PDF-bezogene Aufgaben.

#### F: Können Hyperlinks zu bestimmten Abschnitten im Dokument hinzugefügt werden?

 A: Ja, mit dem`LinkAnnotation` Annotation können Sie Hyperlinks erstellen, die Benutzer zu bestimmten Abschnitten im PDF-Dokument führen. Diese Funktion ist besonders nützlich zum Erstellen interaktiver Inhaltsverzeichnisse oder Referenzlinks.

#### F: Gibt es Einschränkungen beim Hinzufügen von Hyperlinks in PDF-Dateien?

A: Obwohl Aspose.PDF für .NET umfassende Hyperlink-Funktionen bietet, ist es wichtig sicherzustellen, dass der verlinkte Inhalt zugänglich und aktuell bleibt. Hyperlinks zu externen Websites sollten regelmäßig überprüft werden, um defekte Links zu vermeiden.

#### F: Kann ich mit Aspose.PDF für .NET Hyperlinks zu externen Dateien erstellen?

A: Ja, zusätzlich zu Web-URLs können Sie Hyperlinks erstellen, die zu externen Dateien wie anderen PDF-Dokumenten, Bildern oder Multimediadateien führen. Aspose.PDF für .NET bietet die Flexibilität, auf verschiedene Arten von Ressourcen zu verlinken.