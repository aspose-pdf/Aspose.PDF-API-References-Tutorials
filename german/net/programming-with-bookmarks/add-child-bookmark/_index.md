---
title: Untergeordnetes Lesezeichen in PDF-Datei hinzufügen
linktitle: Untergeordnetes Lesezeichen in PDF-Datei hinzufügen
second_title: Aspose.PDF für .NET API-Referenz
description: Fügen Sie mit Aspose.PDF für .NET ganz einfach untergeordnete Lesezeichen zur PDF-Datei hinzu, um das Surfen besser zu organisieren.
type: docs
weight: 20
url: /de/net/programming-with-bookmarks/add-child-bookmark/
---
Das Hinzufügen untergeordneter Lesezeichen in einer PDF-Datei ermöglicht eine strukturiertere Organisation und Navigation. Mit Aspose.PDF für .NET können Sie ganz einfach ein Unterlesezeichen hinzufügen, indem Sie dem folgenden Quellcode folgen:

## Schritt 1: Erforderliche Bibliotheken importieren

Bevor Sie beginnen, müssen Sie die erforderlichen Bibliotheken für Ihr C#-Projekt importieren. Hier ist die notwendige Importanweisung:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## Schritt 2: Legen Sie den Pfad zum Dokumentenordner fest

 In diesem Schritt müssen Sie den Pfad zu dem Ordner angeben, der die PDF-Datei enthält, der Sie ein Unterlesezeichen hinzufügen möchten. Ersetzen`"YOUR DOCUMENT DIRECTORY"`Geben Sie im folgenden Code den tatsächlichen Pfad zu Ihrem Dokumentenordner ein:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 3: Öffnen Sie das PDF-Dokument

Nun öffnen wir das PDF-Dokument, zu dem wir ein Unterlesezeichen hinzufügen möchten, mit dem folgenden Code:

```csharp
Document pdfDocument = new Document(dataDir + "AddChildBookmark.pdf");
```

## Schritt 4: Erstellen Sie ein übergeordnetes Lesezeichenobjekt

 In diesem Schritt erstellen wir mithilfe von ein übergeordnetes Lesezeichenobjekt`OutlineItemCollection` Klasse und legen Sie ihre Eigenschaften wie Titel, Kursivschrift-Attribut und Fettdruck-Attribut fest. Hier ist der entsprechende Code:

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Parent bookmark";
pdfOutline. Italic = true;
pdfOutline. Bold = true;
```

## Schritt 5: Erstellen Sie ein untergeordnetes Lesezeichenobjekt

In diesem Schritt erstellen wir erneut ein Unter-Lesezeichen-Objekt mit`OutlineItemCollection` Klasse und legen Sie ihre Eigenschaften fest. Hier ist der entsprechende Code:

```csharp
OutlineItemCollection pdfChildOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfChildOutline.Title = "Sub Bookmark";
pdfChildOutline. Italic = true;
pdfChildOutline. Bold = true;
```

## Schritt 6: Fügen Sie das Unter-Lesezeichen zum übergeordneten Lesezeichen hinzu

 Schließlich fügen wir das erstellte Unterlesezeichen mithilfe von zur Unterlesezeichensammlung des übergeordneten Lesezeichens hinzu`Add` Methode des übergeordneten Objekts. Hier ist der entsprechende Code:

```csharp
pdfOutline.Add(pdfChildOutline);
```

## Schritt 7: Fügen Sie das übergeordnete Lesezeichen zur Lesezeichensammlung des Dokuments hinzu

 Schließlich fügen wir das übergeordnete Lesezeichen mithilfe von zur Lesezeichensammlung des Dokuments hinzu`Add` Methode der`Outlines` Eigentum. Hier ist der entsprechende Code:

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

### Beispielquellcode für „Untergeordnetes Lesezeichen hinzufügen“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "AddChildBookmark.pdf");
// Erstellen Sie ein übergeordnetes Lesezeichenobjekt
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Parent Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;      
// Erstellen Sie ein untergeordnetes Lesezeichenobjekt
OutlineItemCollection pdfChildOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfChildOutline.Title = "Child Outline";
pdfChildOutline.Italic = true;
pdfChildOutline.Bold = true;
// Fügen Sie ein untergeordnetes Lesezeichen zur Sammlung des übergeordneten Lesezeichens hinzu
pdfOutline.Add(pdfChildOutline);
// Fügen Sie der Gliederungssammlung des Dokuments ein übergeordnetes Lesezeichen hinzu.
pdfDocument.Outlines.Add(pdfOutline);
dataDir = dataDir + "AddChildBookmark_out.pdf";
// Ausgabe speichern
pdfDocument.Save(dataDir);
Console.WriteLine("\nChild bookmark added successfully.\nFile saved at " + dataDir);
```

## Abschluss

Herzlichen Glückwunsch! Jetzt haben Sie eine Schritt-für-Schritt-Anleitung zum Hinzufügen eines Unterlesezeichens mit Aspose.PDF für .NET. Mit diesem Code können Sie Ihre Lesezeichen in Ihren PDF-Dokumenten organisieren und strukturieren.

Weitere Informationen zu erweiterten Funktionen zur Lesezeichenmanipulation finden Sie unbedingt in der offiziellen Aspose.PDF-Dokumentation.

### FAQs zum Hinzufügen eines untergeordneten Lesezeichens in einer PDF-Datei

#### F: Was sind untergeordnete Lesezeichen in einer PDF-Datei?

A: Untergeordnete Lesezeichen, auch Unterlesezeichen genannt, sind Navigationselemente innerhalb eines PDF-Dokuments, die hierarchisch unter einem übergeordneten Lesezeichen strukturiert sind. Sie bieten eine Möglichkeit, ein besser organisiertes und detaillierteres Inhaltsverzeichnis für das Dokument zu erstellen.

#### F: Wie importiere ich die erforderlichen Bibliotheken für mein C#-Projekt?

A: Um die erforderlichen Bibliotheken für Ihr C#-Projekt zu importieren, können Sie die folgende Importanweisung verwenden:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

Diese Bibliotheken stellen die notwendigen Klassen und Funktionen für die Arbeit mit PDF-Dokumenten und interaktiven Funktionen bereit.

#### F: Wie lege ich den Pfad zum Dokumentenordner fest?

 A: Der bereitgestellte Quellcode muss ersetzt werden`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu dem Ordner, der die PDF-Datei enthält, mit der Sie arbeiten möchten. Dadurch wird sichergestellt, dass der Code die Ziel-PDF-Datei korrekt lokalisiert.

#### F: Kann ich mehrere Ebenen untergeordneter Lesezeichen erstellen?

A: Ja, Sie können mehrere Ebenen untergeordneter Lesezeichen erstellen, indem Sie den im Tutorial beschriebenen Prozess erweitern. Indem Sie übergeordnete Lesezeichen mit Unterlesezeichen erstellen und diese weiter verschachteln, können Sie eine hierarchische Struktur von Lesezeichen für komplexe PDF-Dokumente erstellen.

####  F: Was ist der Zweck des`OutlineItemCollection` class?

 A: Die`OutlineItemCollection` Die Klasse in Aspose.PDF für .NET wird zum Erstellen und Verwalten von Gliederungen verwendet, bei denen es sich im Wesentlichen um Lesezeichen in einem PDF-Dokument handelt. Mit dieser Klasse können Sie Eigenschaften wie Titel, Schriftart und Aktionen für Lesezeichen festlegen.

#### F: Wie füge ich ein Unterlesezeichen zu einem übergeordneten Lesezeichen hinzu?

 A: Um ein Unter-Lesezeichen zu einem übergeordneten Lesezeichen hinzuzufügen, erstellen Sie ein neues`OutlineItemCollection` Objekt für das Unter-Lesezeichen und legen Sie seine Eigenschaften fest. Dann verwenden Sie die`Add` Methode der übergeordneten Lesezeichen`OutlineItemCollection` um das Unter-Lesezeichen zur übergeordneten Sammlung hinzuzufügen.

#### F: Kann ich das Erscheinungsbild von untergeordneten Lesezeichen anpassen?

A: Ja, ähnlich wie bei übergeordneten Lesezeichen können Sie das Erscheinungsbild untergeordneter Lesezeichen anpassen, indem Sie Eigenschaften wie Titel, Schriftstil und andere Attribute festlegen. Dadurch können Sie optisch markante und informative Lesezeichen erstellen.

#### F: Ist Aspose.PDF für .NET mit anderen Programmiersprachen kompatibel?

A: Aspose.PDF für .NET wurde speziell für C#- und .NET-Umgebungen entwickelt. Aspose bietet jedoch ähnliche Bibliotheken für andere Programmiersprachen wie Java und Android an, die jeweils auf die jeweilige Plattform zugeschnitten sind.

#### F: Wie verbessern untergeordnete Lesezeichen die PDF-Navigation?

A: Untergeordnete Lesezeichen verbessern die PDF-Navigation, indem sie ein strukturierteres und organisierteres Inhaltsverzeichnis bereitstellen. Über die hierarchische Lesezeichenstruktur können Benutzer schnell auf bestimmte Abschnitte des Dokuments zugreifen.