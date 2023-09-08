---
title: Legen Sie die Callout-Eigenschaft in der PDF-Datei fest
linktitle: Legen Sie die Callout-Eigenschaft in der PDF-Datei fest
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET die Callout-Eigenschaft in einer PDF-Datei festlegen. Passen Sie Anmerkungen mit Beschriftungslinien, Textfarben und Endstilen an.
type: docs
weight: 130
url: /de/net/annotations/setcalloutproperty/
---
 Aspose.PDF für .NET ist eine leistungsstarke Bibliothek zum Erstellen, Bearbeiten und Konvertieren von PDF-Dokumenten in C#. Eine der von dieser Bibliothek bereitgestellten Funktionen ist die Möglichkeit, Callout-Eigenschaften für Freitextanmerkungen in PDF-Dokumenten festzulegen. Dies kann mit der erfolgen`FreeTextAnnotation` Klasse, mit der Sie Anmerkungen mit Callouts erstellen können.

In diesem Tutorial führen wir Sie durch den Prozess des Festlegens von Callout-Eigenschaften für eine Freitextanmerkung mithilfe von Aspose.PDF für .NET in C#. Befolgen Sie die nachstehenden Schritte, um zu beginnen.

## Installieren Sie Aspose.PDF für .NET

 Falls Sie dies noch nicht getan haben, müssen Sie dies tun[herunterladen](https://releases.aspose.com/pdf/net/) und installieren Sie Aspose.PDF für .NET aus den Aspose-Releases oder über den NuGet-Paketmanager.

## Schritt 1: Erstellen Sie ein neues PDF-Dokument

 Erstellen Sie ein neues PDF-Dokument mit`Document`Von Aspose.PDF für .NET bereitgestellte Klasse.

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Schritt 2: Fügen Sie dem Dokument eine neue Seite hinzu

 Fügen Sie mit dem eine neue Seite zum Dokument hinzu`Pages` Sammlung der`Document` Klasse.

```csharp
Page page = doc.Pages.Add();
```

## Schritt 3: Standarddarstellung festlegen

 Legen Sie die Standarddarstellung für die Freitextanmerkung fest, indem Sie eine neue erstellen`DefaultAppearance` Objekt und das Festlegen seiner Eigenschaften wie z`TextColor` Und`FontSize`.

```csharp
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
```

## Schritt 4: Erstellen Sie eine Freitextanmerkung mit Beschriftung

 Erstellen Sie mithilfe von eine neue Freitextanmerkung mit Beschriftung`FreeTextAnnotation` Klasse. Stellen Sie die ein`Intent` Eigentum zu`FreeTextIntent.FreeTextCallout` um anzugeben, dass es sich um eine Callout-Anmerkung handelt. Stellen Sie die ein`EndingStyle` Eigentum zu`LineEnding.OpenArrow` um den Stil des Pfeils am Ende der Beschriftung anzugeben. Stellen Sie die ein`Callout` Eigenschaft zu einem Array von`Point` Objekte, die die Punkte auf der Seite darstellen, an denen die Beschriftungslinie gezeichnet werden soll.

```csharp
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
fta.Callout = new Point[]
{
    new Point(428.25,651.75), new Point(462.75,681.375), new Point(474,681.375)
};
```

## Schritt 5: Fügen Sie der Seite die Freitextanmerkung hinzu

 Fügen Sie der Seite die Freitextanmerkung hinzu, indem Sie die verwenden`Annotations` Sammlung der`Page` Klasse.

```csharp
page.Annotations.Add(fta);
```

## Schritt 6: Fügen Sie der Anmerkung Text hinzu

 Fügen Sie der Anmerkung Text hinzu, indem Sie festlegen`RichText`-Eigenschaft auf eine Zeichenfolge aus formatiertem XML umstellen. In diesem Tutorial stellen wir die Textfarbe auf Rot und die Schriftgröße auf 9 ein.

```csharp
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" style=\"color:#FF
```

## Schritt 7: Speichern Sie das Dokument

Speichern Sie nun das Dokument mit dem folgenden Code:

```csharp
doc.Save(dataDir + "SetCalloutProperty.pdf")
```

### Beispielquellcode für Set Callout Property mit Aspose.PDF für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
Page page = doc.Pages.Add();
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
fta.Callout = new Point[]
{
	new Point(428.25,651.75), new Point(462.75,681.375), new Point(474,681.375)
};
page.Annotations.Add(fta);
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" style=\"color:#FF0000;font-weight:normal;font-style:normal;font-stretch:normal\"><p dir=\"ltr\"> <span style=\"font-size:9.0pt;font-family:Helvetica\">Dies ist ein Beispiel</span></p></body>";
doc.Save(dataDir + "SetCalloutProperty.pdf");
```

## Abschluss

In diesem Tutorial haben wir untersucht, wie man mithilfe von Aspose.PDF für .NET Callout-Eigenschaften für eine Freitextanmerkung in einem PDF-Dokument festlegt. Legendenanmerkungen sind nützlich, um zusätzliche Informationen oder Erklärungen zu bestimmten Bereichen in einem Dokument bereitzustellen. Aspose.PDF für .NET bietet eine breite Palette an Funktionen und Möglichkeiten für die Arbeit mit PDF-Dateien, einschließlich der Erstellung und Anpassung von Anmerkungen wie Legenden. Durch Befolgen der Schritt-für-Schritt-Anleitung und Verwendung des bereitgestellten C#-Quellcodes können Entwickler problemlos Callout-Anmerkungen in ihre PDF-Dokumente implementieren und so die Benutzerfreundlichkeit und Klarheit ihrer Dokumente verbessern. Aspose.PDF für .NET ist eine vielseitige und zuverlässige Bibliothek für PDF-Vorgänge in .NET-Anwendungen und bietet leistungsstarke Tools zur effizienten Bearbeitung verschiedener PDF-bezogener Aufgaben.

### FAQs zum Festlegen der Callout-Eigenschaft in einer PDF-Datei

#### F: Was ist eine Callout-Anmerkung in einem PDF-Dokument?

A: Eine Callout-Anmerkung in einem PDF-Dokument ist eine Art Anmerkung, die es Ihnen ermöglicht, ein Textfeld mit einer Führungslinie zu erstellen, die auf einen bestimmten Bereich im Dokument zeigt. Es wird häufig verwendet, um zusätzliche Informationen oder Kommentare zu einem bestimmten Abschnitt oder Element im Dokument bereitzustellen.

#### F: Kann ich das Erscheinungsbild der Callout-Anmerkung mit Aspose.PDF für .NET anpassen?

A: Ja, Sie können verschiedene Eigenschaften der Beschriftungsanmerkung anpassen, z. B. Farbe, Schriftgröße, Textausrichtung, Linienstil, Pfeilstil und mehr.

#### F: Wie füge ich der Callout-Anmerkung Text hinzu?

 A: Um der Callout-Anmerkung Text hinzuzufügen, können Sie Folgendes festlegen`RichText` Eigentum der`FreeTextAnnotation` Objekt. Der`RichText` -Eigenschaft akzeptiert eine Zeichenfolge aus formatiertem XML, die den Text darstellt, der in der Callout-Anmerkung angezeigt werden soll.

#### F: Kann ich mit Aspose.PDF für .NET mehrere Callout-Anmerkungen zu einem PDF-Dokument hinzufügen?

 A: Ja, Sie können mehrere Callout-Anmerkungen in einem PDF-Dokument erstellen, indem Sie mehrere Instanzen davon erstellen`FreeTextAnnotation`Objekt und fügen Sie sie an verschiedenen Seiten oder Stellen im Dokument hinzu.