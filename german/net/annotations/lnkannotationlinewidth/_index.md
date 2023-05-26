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

##  Erstelle eine neue`Document` object.
```csharp
Document doc = new Document();
```
## Fügen Sie dem Dokument eine neue Seite hinzu.
```csharp
doc.Pages.Add();
```
##  Erstellen Sie eine Liste von`Point` arrays that represent the ink gesture for the annotation.
```csharp
IList<Point[]> inkList = new List<Point[]>();
```
##  Erstelle eine neue`LineInfo` object that defines the properties of the ink gesture.
```csharp
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = System.Drawing.Color.Red;
lineInfo.LineWidth = 2;
```
##  Erstelle eine neue`Aspose.Pdf.Point` array that represents the gesture from the `LineInfo` object.
```csharp
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
    gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}
```
## Fügen Sie die Geste zur Liste der Freihandgesten hinzu.
```csharp
inkList.Add(gesture);
```
##  Erstelle eine neue`InkAnnotation` object that represents the link annotation.
```csharp
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
```
## Legen Sie den Betreff und den Titel der Anmerkung fest.
```csharp
a1.Subject = "Test";
a1.Title = "Title";
```
## Legen Sie die Farbe der Anmerkung fest.
```csharp
a1.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
```
##  Erstelle eine neue`Border` object that defines the properties of the annotation's border.
```csharp
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
```
## Fügen Sie die Anmerkung zur Seite hinzu.
```csharp
doc.Pages[1].Annotations.Add(a1);
```
## Speichern Sie das Dokument in einer Datei.
```c// Save output file
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
