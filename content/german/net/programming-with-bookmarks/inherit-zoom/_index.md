---
title: Vergrößern der PDF-Datei übernehmen
linktitle: Vergrößern der PDF-Datei übernehmen
second_title: Aspose.PDF für .NET API-Referenz
description: Mit Aspose.PDF für .NET können Sie ganz einfach den Lesezeichen-Zoom in einer PDF-Datei übernehmen.
type: docs
weight: 90
url: /de/net/programming-with-bookmarks/inherit-zoom/
---
Mit der Zoomvererbung in einer PDF-Datei können Sie eine Standardzoomstufe für Lesezeichen festlegen. Mit Aspose.PDF für .NET können Sie Zoom ganz einfach erben, indem Sie dem folgenden Quellcode folgen:

## Schritt 1: Erforderliche Bibliotheken importieren

Bevor Sie beginnen, müssen Sie die erforderlichen Bibliotheken für Ihr C#-Projekt importieren. Hier ist die notwendige Importanweisung:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## Schritt 2: Legen Sie den Pfad zum Dokumentenordner fest

 In diesem Schritt müssen Sie den Pfad zu dem Ordner angeben, der die PDF-Datei enthält, von der Sie den Zoom übernehmen möchten. Ersetzen`"YOUR DOCUMENT DIRECTORY"`Geben Sie im folgenden Code den tatsächlichen Pfad zu Ihrem Dokumentenordner ein:

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

### FAQs zum Vererben des Zooms in PDF-Dateien

#### F: Was ist Zoom-Vererbung in einer PDF-Datei?

A: Unter Zoomvererbung versteht man die Möglichkeit, eine Standardzoomstufe für Lesezeichen in einem PDF-Dokument anzugeben. Dies ermöglicht eine konsistente und benutzerfreundliche Navigation, wenn Benutzer mit den Lesezeichen interagieren.

#### F: Warum sollte ich Zoomstufen für Lesezeichen erben wollen?

A: Durch die Übernahme von Zoomstufen wird sichergestellt, dass Benutzer beim Navigieren durch Lesezeichen in einem PDF-Dokument ein einheitliches Anzeigeerlebnis haben. Dies kann besonders nützlich sein, wenn Sie eine bestimmte Ansicht für verschiedene Abschnitte eines Dokuments bereitstellen möchten.

#### F: Wie importiere ich die erforderlichen Bibliotheken für mein C#-Projekt?

A: Um die erforderlichen Bibliotheken für Ihr C#-Projekt zu importieren, schließen Sie die folgenden Importanweisungen ein:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

Mit diesen Anweisungen können Sie auf die Klassen und Methoden zugreifen, die zum Arbeiten mit PDF-Dokumenten und Lesezeichen erforderlich sind.

#### F: Wie lege ich den Pfad zum Dokumentenordner fest?

 A: Ersetzen Sie im bereitgestellten Quellcode`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu dem Ordner, der die PDF-Datei enthält, für die Sie die Zoomstufen erben möchten.

#### F: Wie öffne ich ein PDF-Dokument, um Zoomstufen zu übernehmen?

A: Um ein PDF-Dokument zum Erben von Zoomstufen zu öffnen, verwenden Sie den folgenden Code:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

 Ersetzen`"input.pdf"` mit dem tatsächlichen Dateinamen.

#### F: Wie stelle ich die Zoomstufe für Lesezeichen ein?

 A: Um die Zoomstufe festzulegen, erstellen Sie ein`XYZExplicitDestination` Objekt mit den gewünschten Koordinaten und dem gewünschten Zoomfaktor. Hier ist ein Beispiel:

```csharp
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
```

Dadurch wird die Zoomstufe bei den Koordinaten (100, 100) auf 2 gesetzt.

#### F: Wie füge ich die Zoomstufe zu Lesezeichen hinzu?

 A: Fügen Sie das hinzu`XYZExplicitDestination` Objekt als Aktion für die Lesezeichensammlung:

```csharp
item.Action = new GoToAction(dest);
```

 Wo`item` ist ein`OutlineItemCollection` stellt ein Lesezeichen dar.

#### F: Wie speichere ich die aktualisierte PDF-Datei?

 A: Speichern Sie die aktualisierte PDF-Datei mit`Save` Methode der`doc` Objekt:

```csharp
dataDir = dataDir + "InheritZoom_out.pdf";
doc.Save(dataDir);
```

#### F: Kann ich die Zoomstufen für verschiedene Lesezeichen anpassen?

 A: Ja, Sie können die Zoomstufen für verschiedene Lesezeichen anpassen, indem Sie mehrere erstellen`XYZExplicitDestination` Objekte mit unterschiedlichen Koordinaten und Zoomfaktoren.

#### F: Gibt es eine Begrenzung für die Anzahl der Lesezeichen, auf die ich die Zoom-Vererbung anwenden kann?

A: Normalerweise gibt es keine strenge Begrenzung für die Anzahl der Lesezeichen, auf die Sie die Zoom-Vererbung anwenden können. Allerdings erfordern sehr große Dokumente mit einer übermäßigen Anzahl an Lesezeichen möglicherweise eine effiziente Speicherverwaltung.

#### F: Wie kann ich bestätigen, dass die Zoom-Vererbung angewendet wurde?

A: Öffnen Sie die generierte PDF-Datei, um zu überprüfen, ob die angegebenen Zoomstufen von den Lesezeichen übernommen wurden.