---
title: Fügen Sie eine lnk-Anmerkung hinzu
linktitle: Fügen Sie eine lnk-Anmerkung hinzu
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie mit einer Schritt-für-Schritt-Anleitung und vollständigem Quellcode, wie Sie mit Aspose.PDF für .NET die Funktion „Ink Annotation“ zu PDF-Dokumenten in C# hinzufügen.
type: docs
weight: 20
url: /de/net/annotations/addlnkannotation/
---
Aspose.PDF für .NET ist eine leistungsstarke Bibliothek, die Entwicklern die Durchführung verschiedener PDF-Vorgänge ermöglicht. Ein solcher Vorgang ist das Hinzufügen von Freihandanmerkungen zu PDF-Dokumenten. In diesem Artikel stellen wir eine Schritt-für-Schritt-Anleitung zur Erläuterung des C#-Quellcodes zum Hinzufügen von Ink Annotation mit Aspose.PDF für .NET bereit. Lass uns anfangen!

## Grundlegendes zur Freihandanmerkungsfunktion von Aspose.PDF für .NET

Bevor wir uns mit dem C#-Quellcode befassen, wollen wir zunächst verstehen, was Ink Annotation ist und welche Verwendung es hat.

Ink Annotation ist eine Möglichkeit, Freihand-Anmerkungen in PDF-Dokumenten zu zeichnen. Sie können Anmerkungen mit einem Stift oder einer Maus erstellen. Diese Funktion ist in Situationen nützlich, in denen Sie Diagramme, Skizzen oder andere Arten von Anmerkungen zeichnen müssen.

## Schritt 1: Erstellen eines neuen Dokuments

Der erste Schritt beim Hinzufügen von Ink Annotation zu einem PDF-Dokument besteht darin, eine neue Instanz der Document-Klasse zu erstellen. Dies wird mithilfe des folgenden Codeausschnitts erreicht:

```csharp
string dataDir = "YOUR DATA DIRECTORY";
Document doc = new Document();
Page pdfPage = doc.Pages.Add();
```

Hier erstellen wir eine neue Instanz der Document-Klasse und fügen ihr eine neue Seite hinzu.

## Schritt 2: Freihandanmerkung erstellen

Der nächste Schritt besteht darin, eine Instanz der InkAnnotation-Klasse zu erstellen. Dies geschieht mithilfe des folgenden Codeausschnitts:

```csharp
System.Drawing.Rectangle drect = new System.Drawing.Rectangle();
drect.Height = (int)pdfPage.Rect.Height;
drect.Width = (int)pdfPage.Rect.Width;
drect.X = 0;
drect.Y = 0;
Aspose.Pdf.Rectangle arect = Aspose.Pdf.Rectangle.FromRect(drect);
IList<Point[]> inkList = new List<Point[]>();
Aspose.Pdf.Point[] arrpt = new Aspose.Pdf.Point[3];
inkList.Add(arrpt);
arrpt[0] = new Aspose.Pdf.Point(100, 800);
arrpt[1] = new Aspose.Pdf.Point(200, 800);
arrpt[2] = new Aspose.Pdf.Point(200, 700);
InkAnnotation ia = new InkAnnotation(pdfPage, arect, inkList);
ia.Title = "XXX";
ia.Color = Aspose.Pdf.Color.LightBlue; // (GetColorFromString(Stroke.InkColor));
ia.CapStyle = CapStyle.Rounded;
Border border = new Border(ia);
border.Width = 25;
ia.Opacity = 0.5;
pdfPage.Annotations.Add(ia);
```

Hier erstellen wir zunächst ein Rechteck mit der Klasse System.Drawing.Rectangle und konvertieren es mit der Methode FromRect in Aspose.Pdf.Rectangle. Anschließend erstellen wir eine Instanz der InkAnnotation-Klasse unter Verwendung des Rechtecks, einer Liste von Punkten und der Seite, auf der die Anmerkung hinzugefügt wird.

Anschließend legen wir verschiedene Eigenschaften der InkAnnotation fest, z. B. Titel, Farbe, Kappenstil, Rahmen und Deckkraft. Abschließend fügen wir die Anmerkung mit der Methode „Annotations.Add“ zur Seite hinzu.

## Schritt 3: Speichern des Dokuments

Der letzte Schritt besteht darin, das PDF-Dokument mit der hinzugefügten Tintenanmerkung zu speichern. Dies wird mithilfe des folgenden Codeausschnitts erreicht:

```csharp
dataDir = dataDir + "AddlnkAnnotation_out.pdf";
doc.Save(dataDir);
```

Hier verketten wir den Namen der Ausgabedatei mit dem Datenverzeichnis und speichern das Dokument mit der Save-Methode.

### Beispielquellcode für das Hinzufügen von Freihandanmerkungen mit Aspose.PDF für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DATA DIRECTORY";


Document doc = new Document();
Page pdfPage = doc.Pages.Add();
System.Drawing.Rectangle drect = new System.Drawing.Rectangle();
drect.Height = (int)pdfPage.Rect.Height;
drect.Width = (int)pdfPage.Rect.Width;
drect.X = 0;
drect.Y = 0;
Aspose.Pdf.Rectangle arect = Aspose.Pdf.Rectangle.FromRect(drect);
IList<Point[]> inkList = new List<Point[]>();
Aspose.Pdf.Point[] arrpt = new Aspose.Pdf.Point[3];
inkList.Add(arrpt);
arrpt[0] = new Aspose.Pdf.Point(100, 800);
arrpt[1] = new Aspose.Pdf.Point(200, 800);
arrpt[2] = new Aspose.Pdf.Point(200, 700);
InkAnnotation ia = new InkAnnotation(pdfPage, arect, inkList);
ia.Title = "XXX";
ia.Color = Aspose.Pdf.Color.LightBlue; // (GetColorFromString(Stroke.InkColor));
ia.CapStyle = CapStyle.Rounded;
Border border = new Border(ia);
border.Width = 25;
ia.Opacity = 0.5;
pdfPage.Annotations.Add(ia);

dataDir = dataDir + "AddlnkAnnotation_out.pdf";
// Ausgabedatei speichern
doc.Save(dataDir);
```

## Abschluss

In diesem Tutorial haben wir untersucht, wie man mit Aspose.PDF für .NET Freihandanmerkungen zu einem PDF-Dokument hinzufügt. Durch Befolgen der Schritt-für-Schritt-Anleitung und des bereitgestellten C#-Quellcodes können Entwickler die Ink Annotation-Funktionalität problemlos in ihre PDF-Verarbeitungsanwendungen implementieren.

### FAQs

#### F: Was ist eine Freihandanmerkung in einem PDF-Dokument?

A: Eine Freihandanmerkung in einem PDF-Dokument ermöglicht es Benutzern, Freiform-Freihandanmerkungen mit einem Stift oder einer Maus zu zeichnen. Es wird häufig verwendet, um handgezeichnete Skizzen, Diagramme oder andere freihändige Anmerkungen zu einer PDF-Datei hinzuzufügen.

#### F: Kann ich das Erscheinungsbild der Freihandanmerkung anpassen?

A: Ja, Aspose.PDF für .NET bietet verschiedene Eigenschaften, um das Erscheinungsbild der Freihandanmerkung anzupassen, wie z. B. Farbe, Deckkraft, Versalstil, Rahmenbreite und mehr. Entwickler können diese Eigenschaften an ihre spezifischen Anforderungen anpassen.

#### F: Ist es möglich, einer einzelnen PDF-Seite mehrere Freihandanmerkungen hinzuzufügen?

A: Ja, Sie können mit Aspose.PDF für .NET mehrere Freihandanmerkungen zu einer einzelnen PDF-Seite hinzufügen. Jede Freihandanmerkung kann über einen eigenen Satz von Punkten und ein individuelles Erscheinungsbild verfügen.

#### F: Kann ich Freihandanmerkungen zu vorhandenen PDF-Dokumenten hinzufügen?

A: Ja, mit Aspose.PDF für .NET können Sie Freihandanmerkungen sowohl zu neu erstellten PDF-Dokumenten als auch zu vorhandenen PDF-Dateien hinzufügen. Sie können eine vorhandene PDF-Datei öffnen, Freihandanmerkungen hinzufügen und das aktualisierte Dokument speichern.

#### F: Was sind einige häufige Anwendungsfälle für Freihandanmerkungen in PDF-Dokumenten?

A: Tintenanmerkungen sind für eine Vielzahl von Anwendungen nützlich, darunter das Hinzufügen von Unterschriften oder handschriftlichen Notizen zu PDF-Formularen, das Kommentieren von Architekturplänen oder technischen Zeichnungen und das Markieren von Dokumenten für die gemeinsame Überprüfung.