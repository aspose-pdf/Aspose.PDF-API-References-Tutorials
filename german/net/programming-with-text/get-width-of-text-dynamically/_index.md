---
title: Ermitteln Sie die Textbreite dynamisch
linktitle: Ermitteln Sie die Textbreite dynamisch
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET dynamisch die Textbreite ermitteln.
type: docs
weight: 220
url: /de/net/programming-with-text/get-width-of-text-dynamically/
---

In diesem Tutorial erklären wir, wie Sie Aspose.PDF für .NET verwenden, um die Breite von Text in C# dynamisch zu messen. Dies kann nützlich sein, wenn Sie die Größe einer Textzeichenfolge bestimmen müssen, bevor Sie sie in einem PDF-Dokument rendern. Wir führen Sie Schritt für Schritt durch den bereitgestellten C#-Quellcode.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Aspose.PDF für .NET-Bibliothek installiert.
- Visual Studio oder eine andere C#-Entwicklungsumgebung.

## Schritt 1: Legen Sie das Dokumentverzeichnis fest

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem Pfad zu dem Verzeichnis, in dem sich Ihre Dokumente befinden. Dies wird zum Speichern aller generierten PDF-Dateien verwendet.

## Schritt 2: Finden Sie die Schriftart

```csharp
Aspose.Pdf.Text.Font font = FontRepository.FindFont("Arial");
```

 Der obige Code findet die Arial-Schriftart mithilfe von`FindFont` Methode aus der`FontRepository` Klasse. Wenn Sie eine andere Schriftart verwenden möchten, ersetzen Sie diese`"Arial"` mit dem gewünschten Schriftartnamen.

## Schritt 3: Legen Sie den Textstatus fest

```csharp
TextState ts = new TextState();
ts.Font = font;
ts.FontSize = 14;
```

 Hier erstellen wir ein neues`TextState` Objekt und legen Sie seine Eigenschaften fest. Wir weisen die zuvor gefundene Schriftart zu (`font`) und stellen Sie die Schriftgröße auf 14 ein. Passen Sie die Schriftgröße nach Bedarf an.

## Schritt 4: Messen Sie die Breite des Textes

```csharp
if (Math.Abs(font.MeasureString("A", 14) - 9.337) > 0.001)
	Console.WriteLine("Unexpected font string measure!");

if (Math.Abs(ts.MeasureString("z") - 7.0) > 0.001)
	Console.WriteLine("Unexpected font string measure!");

for (char c = 'A'; c <= 'z'; c++)
{
	double fnMeasure = font.MeasureString(c.ToString(), 14);
	double tsMeasure = ts.MeasureString(c.ToString());
	if (Math.Abs(fnMeasure - tsMeasure) > 0.001)
		Console.WriteLine("Font and state string measuring doesn't match!");
}
```

Der obige Code zeigt, wie die Breite von Text mithilfe der Schriftart direkt gemessen wird (`font.MeasureString`) und der Textstatus (`ts.MeasureString`). Es umfasst einige Validierungsprüfungen, um sicherzustellen, dass die Messungen korrekt sind.

### Beispielquellcode für dynamisches Abrufen der Textbreite mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Text.Font font = FontRepository.FindFont("Arial");
TextState ts = new TextState();
ts.Font = font;
ts.FontSize = 14;
if (Math.Abs(font.MeasureString("A", 14) - 9.337) > 0.001)
	Console.WriteLine("Unexpected font string measure!");
if (Math.Abs(ts.MeasureString("z") - 7.0) > 0.001)
	Console.WriteLine("Unexpected font string measure!");
for (char c = 'A'; c <= 'z'; c++)
{
	double fnMeasure = font.MeasureString(c.ToString(), 14);
	double tsMeasure = ts.MeasureString(c.ToString());
	if (Math.Abs(fnMeasure - tsMeasure) > 0.001)
		Console.WriteLine("Font and state string measuring doesn't match!");
}
```


## Abschluss

Sie haben gelernt, wie Sie Aspose.PDF für .NET verwenden, um die Breite von Text in C# dynamisch zu messen. Indem Sie die in diesem Tutorial beschriebenen Schritte befolgen, können Sie die Breite von Textzeichenfolgen genau bestimmen, bevor Sie sie in einem PDF-Dokument rendern.