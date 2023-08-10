---
title: Lesezeichen in PDF-Datei hinzufügen
linktitle: Lesezeichen in PDF-Datei hinzufügen
second_title: Aspose.PDF für .NET API-Referenz
description: Fügen Sie mit Aspose.PDF für .NET ganz einfach Lesezeichen zur PDF-Datei hinzu, um die Navigation zu verbessern.
type: docs
weight: 10
url: /de/net/programming-with-bookmarks/add-bookmark/
---
Das Hinzufügen von Lesezeichen in einer PDF-Datei ermöglicht eine einfache und schnelle Navigation. Mit Aspose.PDF für .NET können Sie ganz einfach ein Lesezeichen in eine PDF-Datei einfügen, indem Sie dem folgenden Quellcode folgen:

## Schritt 1: Erforderliche Bibliotheken importieren

Bevor Sie beginnen, müssen Sie die erforderlichen Bibliotheken für Ihr C#-Projekt importieren. Hier ist die notwendige Importanweisung:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## Schritt 2: Legen Sie den Pfad zum Dokumentenordner fest

 In diesem Schritt müssen Sie den Pfad zu dem Ordner angeben, der die PDF-Datei enthält, der Sie ein Lesezeichen hinzufügen möchten. Ersetzen`"YOUR DOCUMENT DIRECTORY"`Geben Sie im folgenden Code den tatsächlichen Pfad zu Ihrem Dokumentenordner ein:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 3: Öffnen Sie das PDF-Dokument

Nun öffnen wir das PDF-Dokument, zu dem wir ein Lesezeichen hinzufügen möchten, mit dem folgenden Code:

```csharp
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
```

## Schritt 4: Lesezeichenobjekt erstellen

 In diesem Schritt erstellen wir ein Lesezeichenobjekt mit`OutlineItemCollection` Klasse und legen Sie ihre Eigenschaften wie Titel, Kursivschrift-Attribut, Fettdruck-Attribut und Aktion fest, die beim Klicken ausgeführt werden soll. Hier ist der entsprechende Code:

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline. Italic = true;
pdfOutline. Bold = true;
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
```

## Schritt 5: Lesezeichen zum Dokument hinzufügen

 Abschließend fügen wir das erstellte Lesezeichen mithilfe von zur Lesezeichensammlung des Dokuments hinzu`Add` Methode der`Outlines` Eigentum. Hier ist der entsprechende Code:

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

### Beispielquellcode für „Lesezeichen hinzufügen“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
// Erstellen Sie ein Lesezeichenobjekt
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;
// Legen Sie die Zielseitennummer fest
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
// Fügen Sie der Gliederungssammlung des Dokuments ein Lesezeichen hinzu.
pdfDocument.Outlines.Add(pdfOutline);
dataDir = dataDir + "AddBookmark_out.pdf";
// Ausgabe speichern
pdfDocument.Save(dataDir);
Console.WriteLine("\nBookmark added successfully.\nFile saved at " + dataDir);
```

## Abschluss

Herzlichen Glückwunsch! Jetzt haben Sie eine Schritt-für-Schritt-Anleitung zum Hinzufügen eines Lesezeichens mit Aspose.PDF für .NET. Mit diesem Code können Sie die Navigation in Ihren PDF-Dokumenten verbessern, indem Sie benutzerdefinierte Lesezeichen hinzufügen.

Weitere Informationen zu erweiterten Funktionen zur Lesezeichenmanipulation finden Sie unbedingt in der offiziellen Aspose.PDF-Dokumentation.


### FAQs zum Hinzufügen von Lesezeichen in einer PDF-Datei

#### F: Was sind Lesezeichen in einer PDF-Datei?

A: Lesezeichen, auch Gliederungen genannt, sind interaktive Elemente, die für Navigation und Struktur innerhalb eines PDF-Dokuments sorgen. Sie ermöglichen Benutzern, schnell zu bestimmten Abschnitten oder Seiten zu springen.

#### F: Warum sollte ich Lesezeichen zu einer PDF-Datei hinzufügen?

A: Das Hinzufügen von Lesezeichen zu einer PDF-Datei verbessert die Benutzererfahrung und erleichtert den Lesern die Navigation durch den Inhalt des Dokuments. Lesezeichen können als Inhaltsverzeichnis dienen oder einen schnellen Zugriff auf wichtige Abschnitte ermöglichen.

#### F: Wie importiere ich die erforderlichen Bibliotheken für mein C#-Projekt?

A: Um die erforderlichen Bibliotheken für Ihr C#-Projekt zu importieren, schließen Sie die folgenden Importanweisungen ein:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

Mit diesen Anweisungen können Sie auf die Klassen und Methoden zugreifen, die für die Arbeit mit PDF-Dokumenten und Lesezeichen erforderlich sind.

#### F: Wie lege ich den Pfad zum Dokumentenordner fest?

 A: Ersetzen`"YOUR DOCUMENT DIRECTORY"` Geben Sie im bereitgestellten Quellcode den tatsächlichen Pfad zu dem Ordner an, der die PDF-Datei enthält, der Sie ein Lesezeichen hinzufügen möchten.

#### F: Wie öffne ich ein PDF-Dokument zum Hinzufügen von Lesezeichen?

A: Um ein PDF-Dokument zum Hinzufügen von Lesezeichen zu öffnen, verwenden Sie den folgenden Code:

```csharp
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
```

 Ersetzen`"AddBookmark.pdf"` mit dem tatsächlichen Dateinamen.

#### F: Wie erstelle ich ein Lesezeichenobjekt?

 A: Um ein Lesezeichenobjekt zu erstellen, verwenden Sie die`OutlineItemCollection` Klasse. Passen Sie seine Eigenschaften wie Titel, Kursivschrift, Fettschrift und Aktion an, die beim Klicken ausgeführt werden soll.

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
```

####  F: Was ist der Zweck des`Action` property in a bookmark?

 A: Die`Action` Die Eigenschaft gibt die Aktion an, die ausgeführt werden soll, wenn auf das Lesezeichen geklickt wird. In diesem Beispiel verwenden wir die`GoToAction`Klasse, um zu einer bestimmten Seite zu navigieren (in diesem Fall Seite 2).

#### F: Wie füge ich das Lesezeichen zum Dokument hinzu?

 A: Benutzen Sie die`Add` Methode der`Outlines` -Eigenschaft, um das erstellte Lesezeichen zur Lesezeichensammlung des Dokuments hinzuzufügen.

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

#### F: Kann ich mit dieser Methode mehrere Lesezeichen hinzufügen?

A: Ja, Sie können die Schritte 4 bis 8 wiederholen, um dem Dokument mehrere Lesezeichen hinzuzufügen. Passen Sie die Eigenschaften und Aktionen jedes Lesezeichens nach Bedarf an.

#### F: Wie speichere ich die aktualisierte PDF-Datei?

 A: Speichern Sie die aktualisierte PDF-Datei mit`Save` Methode der`pdfDocument` Objekt:

```csharp
dataDir = dataDir + "AddBookmark_out.pdf";
pdfDocument.Save(dataDir);
```

#### F: Wie kann ich bestätigen, dass die Lesezeichen hinzugefügt wurden?

A: Öffnen Sie die generierte PDF-Datei, um zu überprüfen, ob die angegebenen Lesezeichen zum Dokument hinzugefügt wurden.

#### F: Gibt es eine Begrenzung für die Anzahl der Lesezeichen, die ich hinzufügen kann?

A: Im Allgemeinen gibt es keine strenge Begrenzung für die Anzahl der Lesezeichen, die Sie hinzufügen können. Berücksichtigen Sie jedoch die Größe und Komplexität des Dokuments, um eine optimale Leistung zu erzielen.

#### F: Kann ich das Erscheinungsbild von Lesezeichen anpassen?

A: Ja, Sie können das Erscheinungsbild, die Farbe, den Stil und andere Attribute von Lesezeichen mithilfe der Aspose.PDF-Funktionen weiter anpassen.