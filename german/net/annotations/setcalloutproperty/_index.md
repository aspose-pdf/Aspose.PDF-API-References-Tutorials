---
title: Legen Sie die Callout-Eigenschaft fest
linktitle: Legen Sie die Callout-Eigenschaft fest
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie die Callout-Eigenschaft mit Aspose.PDF für .NET festlegen. Passen Sie Anmerkungen mit Beschriftungslinien, Textfarben und Endstilen an.
type: docs
weight: 130
url: /de/net/annotations/setcalloutproperty/
---
Aspose.PDF für .NET ist eine leistungsstarke Bibliothek zum Erstellen, Bearbeiten und Konvertieren von PDF-Dokumenten in C#. Eine der von dieser Bibliothek bereitgestellten Funktionen ist die Möglichkeit, Callout-Eigenschaften für Freitextanmerkungen in PDF-Dokumenten festzulegen. Dies kann mit der erfolgen`FreeTextAnnotation` Klasse, mit der Sie Anmerkungen mit Callouts erstellen können.

In diesem Tutorial führen wir Sie durch den Prozess des Festlegens von Callout-Eigenschaften für eine Freitextanmerkung mithilfe von Aspose.PDF für .NET in C#. Befolgen Sie die nachstehenden Schritte, um zu beginnen.

## Installieren Sie Aspose.PDF für .NET

 Falls Sie dies noch nicht getan haben, müssen Sie dies tun[herunterladen](https://releases.aspose.com/pdf/net/) und installieren Sie Aspose.PDF für .NET aus den Aspose-Releases oder über den NuGet-Paketmanager.

## Erstellen Sie ein neues PDF-Dokument

 Erstellen Sie ein neues PDF-Dokument mit`Document` Von Aspose.PDF für .NET bereitgestellte Klasse.

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Fügen Sie dem Dokument eine neue Seite hinzu

 Fügen Sie mit dem eine neue Seite zum Dokument hinzu`Pages` Sammlung der`Document` Klasse.

```csharp
Page page = doc.Pages.Add();
```

## Legen Sie das Standard-Erscheinungsbild fest

Legen Sie die Standarddarstellung für die Freitextanmerkung fest, indem Sie eine neue erstellen`DefaultAppearance` Objekt und das Festlegen seiner Eigenschaften wie z`TextColor` Und`FontSize`.

```csharp
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
```

## Erstellen Sie eine Freitextanmerkung mit Beschriftung

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

## Fügen Sie der Seite die Freitextanmerkung hinzu

 Fügen Sie der Seite die Freitextanmerkung hinzu, indem Sie die verwenden`Annotations` Sammlung der`Page` Klasse.

```csharp
page.Annotations.Add(fta);
```

## Fügen Sie der Anmerkung Text hinzu

 Fügen Sie der Anmerkung Text hinzu, indem Sie festlegen`RichText` -Eigenschaft auf eine Zeichenfolge aus formatiertem XML umstellen. In diesem Tutorial stellen wir die Textfarbe auf Rot und die Schriftgröße auf 9 ein.

```csharp
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" style=\"color:#FF
```

## 8. Speichern Sie das Dokument

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
