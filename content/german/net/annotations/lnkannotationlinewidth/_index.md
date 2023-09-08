---
title: Linienbreite der lnk-Anmerkung
linktitle: Linienbreite der lnk-Anmerkung
second_title: Aspose.PDF für .NET API-Referenz
description: Dieser Artikel enthält eine Schritt-für-Schritt-Anleitung zum Festlegen der Linienbreite der lnk-Annotation mit Aspose.PDF für .NET.
type: docs
weight: 110
url: /de/net/annotations/lnkannotationlinewidth/
---
Aspose.PDF ist ein leistungsstarkes und weit verbreitetes Tool zum Arbeiten mit PDF-Dateien in .NET-Anwendungen. Es bietet eine Vielzahl von Funktionen zum Erstellen, Bearbeiten und Bearbeiten von PDF-Dateien, einschließlich der Möglichkeit, Anmerkungen zu Seiten hinzuzufügen. In diesem Tutorial erklären wir, wie Sie die Linienbreite einer Linkanmerkung mithilfe von Aspose.PDF für .NET festlegen.

Sobald Sie diese Voraussetzungen erfüllen, erstellen Sie ein neues Konsolenanwendungsprojekt in Visual Studio. Fügen Sie dann einen Verweis auf die Aspose.PDF für .NET-Bibliothek hinzu, indem Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt klicken, „NuGet-Pakete verwalten“ auswählen und im NuGet-Paket-Manager nach „Aspose.PDF“ suchen.

Gehen Sie folgendermaßen vor, um einem PDF-Dokument eine LNK-Anmerkung hinzuzufügen:

##  Schritt 1: Erstellen Sie ein neues`Document` object.
```csharp
Document doc = new Document();
```
## Schritt 2: Fügen Sie dem Dokument eine neue Seite hinzu.
```csharp
doc.Pages.Add();
```
##  Schritt 3: Erstellen Sie eine Liste mit`Point` arrays that represent the ink gesture for the annotation.
```csharp
IList<Point[]> inkList = new List<Point[]>();
```
##  Schritt 4: Erstellen Sie ein neues`LineInfo` object that defines the properties of the ink gesture.
```csharp
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = System.Drawing.Color.Red;
lineInfo.LineWidth = 2;
```
##  Schritt 5: Erstellen Sie ein neues`Aspose.Pdf.Point` array that represents the gesture from the `LineInfo` object.
```csharp
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
    gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}
```
## Schritt 6: Fügen Sie die Geste zur Liste der Freihandgesten hinzu.
```csharp
inkList.Add(gesture);
```
##  Schritt 7: Erstellen Sie ein neues`InkAnnotation` object that represents the link annotation.
```csharp
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
```
## Schritt 8: Legen Sie Betreff und Titel der Anmerkung fest.
```csharp
a1.Subject = "Test";
a1.Title = "Title";
```
## Schritt 9: Legen Sie die Farbe der Anmerkung fest.
```csharp
a1.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
```
##  Schritt 10: Erstellen Sie ein neues`Border` object that defines the properties of the annotation's border.
```csharp
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
```
## Schritt 11: Fügen Sie die Anmerkung zur Seite hinzu.
```csharp
doc.Pages[1].Annotations.Add(a1);
```
## Schritt 12: Speichern Sie das Dokument in einer Datei.
```csharp
// Ausgabedatei speichern
doc.Save(dataDir);


```
### Das Beispiel zeigt die Linienbreite von lnk-Anmerkungen mit Aspose.PDF für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
IList<Point[]> inkList = new List<Point[]>();
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = System.Drawing.Color.Red;
lineInfo.LineWidth = 2;
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}

inkList.Add(gesture);
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
a1.Subject = "Test";
a1.Title = "Title";
a1.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
doc.Pages[1].Annotations.Add(a1);

dataDir = dataDir + "lnkAnnotationLineWidth_out.pdf";
// Ausgabedatei speichern
doc.Save(dataDir);
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.PDF für .NET die Linienbreite einer Linkanmerkung in einem PDF-Dokument festlegt. Aspose.PDF für .NET bietet eine breite Palette an Tools und Funktionen für die Arbeit mit PDF-Dokumenten, einschließlich der Möglichkeit, Linkanmerkungen zu erstellen und anzupassen. Durch Befolgen der Schritt-für-Schritt-Anleitung und Verwendung des bereitgestellten C#-Quellcodes können Entwickler ganz einfach interaktive Links zu ihren PDF-Dokumenten hinzufügen und so das Benutzererlebnis und die Interaktivität ihrer Anwendungen verbessern. Aspose.PDF für .NET ist eine vielseitige Bibliothek, die .NET-Entwicklern die effiziente und effektive Arbeit mit PDF-Dateien ermöglicht.

### FAQs

#### F: Was ist eine Linkanmerkung in einem PDF-Dokument?

A: Eine Linkanmerkung in einem PDF-Dokument ist ein interaktives Element, mit dem Sie Hyperlinks oder Aktionen erstellen können, die den Benutzer zu einer anderen Stelle innerhalb desselben Dokuments, einer externen Website oder eines anderen PDF-Dokuments weiterleiten.

#### F: Wie kann ich die Linienbreite einer Linkanmerkung mit Aspose.PDF für .NET festlegen?

A: Um die Linienbreite einer Linkanmerkung mit Aspose.PDF für .NET festzulegen, können Sie eine erstellen`InkAnnotation` Objekt und geben Sie die Eigenschaft „Linienbreite“ an.

#### F: Welche Eigenschaften können für eine Linkanmerkung in Aspose.PDF für .NET angepasst werden?

A: Sie können verschiedene Eigenschaften einer Linkanmerkung in Aspose.PDF für .NET anpassen, z. B. Position, Größe, Farbe, Rahmeneigenschaften (Breite, Stil, Strichmuster und Effekt), Betreff, Titel und Sichtbarkeit.

#### F: Kann ich eine Linkanmerkung erstellen, die mehrere Freihandgesten enthält?

 A: Ja, Sie können eine Linkanmerkung erstellen, die mehrere Freihandgesten enthält, indem Sie mehrere hinzufügen`Point` Arrays zum`InkAnnotation` Objekt.

#### F: Wie kann ich einer bestimmten Seite des PDF-Dokuments eine Linkanmerkung hinzufügen?

 A: Um eine Linkanmerkung zu einer bestimmten Seite des PDF-Dokuments hinzuzufügen, müssen Sie beim Erstellen die Seitenzahl angeben`InkAnnotation` Objekt. Zum Beispiel,`new InkAnnotation(doc.Pages[1], ...)` Fügt die Linkanmerkung zur ersten Seite hinzu.