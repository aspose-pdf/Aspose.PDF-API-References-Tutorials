---
title: Zoom erben
linktitle: Zoom erben
second_title: Aspose.PDF für .NET API-Referenz
description: Mit Aspose.PDF für .NET können Sie ganz einfach den Lesezeichen-Zoom in Ihren PDF-Dateien übernehmen.
type: docs
weight: 90
url: /de/net/programming-with-bookmarks/inherit-zoom/
---

Durch die Zoomvererbung in einem PDF-Dokument können Sie eine Standardzoomstufe für Lesezeichen festlegen. Mit Aspose.PDF für .NET können Sie Zoom ganz einfach erben, indem Sie dem folgenden Quellcode folgen:

## Schritt 1: Erforderliche Bibliotheken importieren

Bevor Sie beginnen, müssen Sie die erforderlichen Bibliotheken für Ihr C#-Projekt importieren. Hier ist die notwendige Importanweisung:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## Schritt 2: Legen Sie den Pfad zum Dokumentenordner fest

In diesem Schritt müssen Sie den Pfad zu dem Ordner angeben, der die PDF-Datei enthält, von der Sie den Zoom übernehmen möchten. Ersetzen`"YOUR DOCUMENT DIRECTORY"` Geben Sie im folgenden Code den tatsächlichen Pfad zu Ihrem Dokumentenordner ein:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 3: Öffnen Sie das PDF-Dokument

Jetzt öffnen wir das PDF-Dokument, für das wir den Zoom erben möchten, mit dem folgenden Code:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Schritt 4: Holen Sie sich die Lesezeichensammlung

 In diesem Schritt erhalten wir mithilfe von die Sammlung von Lesezeichen oder Orientierungspunkten des Dokuments`Outlines` Eigentum der`doc` Objekt. Hier ist der entsprechende Code:

```csharp
OutlineItemCollection item = new OutlineItemCollection(doc.Outlines);
```

## Schritt 5: Zoomstufe einstellen

 Jetzt legen wir die Zoomstufe fest, indem wir eine erstellen`XYZExplicitDestination` Objekt mit den angegebenen x-, y- und z-Koordinaten. Hier verwenden wir die Koordinaten (100, 100, 0) mit einem Zoom von 2. Hier ist der entsprechende Code:

```csharp
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
```

## Schritt 6: Zoomstufe zu Lesezeichen hinzufügen

 In diesem Schritt fügen wir das hinzu`XYZExplicitDestination` Objekt als Aktion zu den Lesezeichen des`item` Sammlung. Hier ist der entsprechende Code:

```csharp
item. Action = new GoToAction(dest);
```

## Schritt 7: Fügen Sie die aktualisierten Lesezeichen zum Dokument hinzu

 Abschließend fügen wir die aktualisierten Lesezeichen mithilfe von der Lesezeichensammlung des Dokuments hinzu`Add` Methode der`doc.Outlines` Objekt. Hier ist der entsprechende Code:

```csharp
doc. Outlines. Add(item);
```

## Schritt 8: Speichern Sie die aktualisierte Datei

Speichern wir nun die aktualisierte PDF-Datei mit`Save` Methode der`doc` Objekt. Hier ist der entsprechende Code:

```csharp
dataDir = dataDir + "InheritZoom_out.pdf";
doc.Save(dataDir);
```

### Beispielquellcode für Inherit Zoom mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document doc = new Document(dataDir + "input.pdf");
// Holen Sie sich eine Sammlung von Umrissen/Lesezeichen für PDF-Dateien
OutlineItemCollection item = new OutlineItemCollection(doc.Outlines);
// Stellen Sie die Zoomstufe auf 0 ein
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
// Fügen Sie XYZExplicitDestination als Aktion zur Übersichtssammlung von PDF hinzu
item.Action = new GoToAction(dest);
// Element zur Gliederungssammlung der PDF-Datei hinzufügen
doc.Outlines.Add(item);
dataDir = dataDir + "InheritZoom_out.pdf";
// Ausgabe speichern
doc.Save(dataDir);
Console.WriteLine("\nBookmarks updated successfully.\nFile saved at " + dataDir);
```

## Abschluss

Herzlichen Glückwunsch! Jetzt haben Sie eine Schritt-für-Schritt-Anleitung zum Erben von Zoom mit Aspose.PDF für .NET. Mit diesem Code können Sie eine Standardzoomstufe für Lesezeichen in Ihren PDF-Dokumenten festlegen.

Weitere Informationen zu erweiterten Funktionen zur Lesezeichenmanipulation finden Sie unbedingt in der offiziellen Aspose.PDF-Dokumentation.