---
title: Ränder oder Polsterung
linktitle: Ränder oder Polsterung
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Ränder oder Abstände in einer Tabelle festlegen.
type: docs
weight: 140
url: /de/net/programming-with-tables/margins-or-padding/
---
In diesem Tutorial führen wir Sie Schritt für Schritt durch die Verwendung von Aspose.PDF für .NET zum Festlegen von Rändern oder Abständen in einer Tabelle. Wir stellen Erklärungen und Codeausschnitte bereit, die Ihnen helfen, diese Funktionalität zu verstehen und in Ihrem C#-Quellcode zu implementieren.

## Schritt 1: Dokument und Seite einrichten
Zu Beginn müssen Sie das Dokument und die Seite mit dem folgenden Code einrichten:

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instanziieren Sie das Document-Objekt, indem Sie seinen leeren Konstruktor aufrufen
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Schritt 2: Erstellen einer Tabelle
Als Nächstes erstellen wir ein Tabellenobjekt mit der Klasse Aspose.Pdf.Table:

```csharp
// Instanziieren eines Tabellenobjekts
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Fügen Sie die Tabelle zur Absatzsammlung des gewünschten Abschnitts hinzu
page.Paragraphs.Add(tab1);
```

## Schritt 3: Festlegen der Spaltenbreiten und der Standardzellenränder
Um die Spaltenbreiten und Standardzellenränder der Tabelle festzulegen, verwenden Sie den folgenden Code:

```csharp
// Festlegen der Spaltenbreiten der Tabelle
tab1. ColumnWidths = "50 50 50";
// Festlegen des Standardzellenrahmens mithilfe des BorderInfo-Objekts
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## Schritt 4: Festlegen der Tabellenränder und Zellenabstände
Um den Tabellenrahmen und die Zellenpolsterung festzulegen, erstellen Sie ein MarginInfo-Objekt und legen Sie seine Eigenschaften fest:

```csharp
// Erstellen Sie ein MarginInfo-Objekt und legen Sie dessen linken, unteren, rechten und oberen Rand fest
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;

// Festlegen der Standardzellenpolsterung auf das MarginInfo-Objekt
tab1. DefaultCellPadding = margin;

// Festlegen des Tabellenrahmens mithilfe eines anderen benutzerdefinierten BorderInfo-Objekts
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
```

## Schritt 5: Zeilen und Zellen hinzufügen
Fügen wir nun der Tabelle Zeilen und Zellen hinzu. Wir erstellen eine neue Zeile und fügen ihr Zellen hinzu:

```csharp
// Erstellen Sie Zeilen in der Tabelle und dann Zellen in den Zeilen
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add();
```

## Schritt 6: Text zu Zellen hinzufügen
Um einer Zelle Text hinzuzufügen, erstellen Sie ein TextFragment-Objekt und fügen Sie es der gewünschten Zelle hinzu:

```csharp
TextFragment mytext = new TextFragment("col3 with large text string");
row1.Cells[2].Paragraphs.Add(mytext);
row1.Cells[2].IsWordWrapped = false;
```

## Schritt 7: Speichern der PDF
Um das PDF-Dokument zu speichern, verwenden Sie den folgenden Code:

```csharp
dataDir = dataDir + "MarginsOrPadding_out.pdf";
// Speichern Sie das PDF
doc.Save(dataDir);

Console.WriteLine("\nCell and table border width setup successfully.\nFile saved at " + dataDir);
```

### Beispielquellcode für Ränder oder Polsterung mit Aspose.PDF für .NET

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instanziieren Sie das Document-Objekt, indem Sie seinen leeren Konstruktor aufrufen
Document doc = new Document();
Page page = doc.Pages.Add();
// Instanziieren eines Tabellenobjekts
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Fügen Sie die Tabelle in die Absatzsammlung des gewünschten Abschnitts ein
page.Paragraphs.Add(tab1);
// Mit Spaltenbreiten der Tabelle festlegen
tab1.ColumnWidths = "50 50 50";
// Festlegen des Standardzellenrahmens mithilfe des BorderInfo-Objekts
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// Festlegen des Tabellenrahmens mithilfe eines anderen benutzerdefinierten BorderInfo-Objekts
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// Erstellen Sie ein MarginInfo-Objekt und legen Sie dessen linken, unteren, rechten und oberen Rand fest.
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Festlegen der Standardzellenpolsterung auf das MarginInfo-Objekt
tab1.DefaultCellPadding = margin;
// Erstellen Sie Zeilen in der Tabelle und dann Zellen in den Zeilen
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add();
TextFragment mytext = new TextFragment("col3 with large text string");
// Row1.Cells.Add("col3 mit großer Textzeichenfolge, die in die Zelle eingefügt werden soll");
row1.Cells[2].Paragraphs.Add(mytext);
row1.Cells[2].IsWordWrapped = false;
// Zeile1.Zellen[2].Absätze[0].FesteBreite= 80;
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");
dataDir = dataDir + "MarginsOrPadding_out.pdf";
// Speichern Sie das PDF
doc.Save(dataDir);

Console.WriteLine("\nCell and table border width setup successfully.\nFile saved at " + dataDir); 
```

## Abschluss
Herzlichen Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.PDF für .NET Ränder oder Abstände in einer Tabelle festlegen. Mit diesem Wissen können Sie Ihre Dokumentformatierungsfunktionen verbessern und Ihre Tabellen optisch ansprechend gestalten.

### Häufig gestellte Fragen

#### F: Kann ich für einzelne Zellen einer Tabelle unterschiedliche Ränder oder Abstände festlegen?

A: Ja, Sie können mit Aspose.PDF für .NET unterschiedliche Ränder oder Abstände für einzelne Zellen in einer Tabelle festlegen. Im angegebenen Beispiel legen wir den Standard-Zellenabstand für die gesamte Tabelle fest, indem wir`DefaultCellPadding` Eigenschaft. Um unterschiedliche Auffüllungen für bestimmte Zellen festzulegen, können Sie auf die`MarginInfo` jeder Zelle einzeln und ändern Sie deren Ränder.

#### F: Wie kann ich die Rahmenfarbe oder den Stil der Tabelle ändern?

 A: Um die Rahmenfarbe oder den Stil der Tabelle zu ändern, können Sie die`Color` Und`Width` Eigenschaften der`BorderInfo` Objekt. Im angegebenen Beispiel setzen wir die Rahmenfarbe auf Schwarz und eine Breite von 1F (ein Punkt) mit`tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);`. Sie können die Farbe und Breite nach Ihren Wünschen anpassen.

#### F: Ist es möglich, der Tabelle Kopf- oder Fußzeilen hinzuzufügen?

A: Ja, Sie können der Tabelle mit Aspose.PDF für .NET Kopf- oder Fußzeilen hinzufügen. Kopf- und Fußzeilen sind normalerweise separate Zeilen, die zusätzliche Informationen wie Spaltenbeschriftungen, Tabellentitel oder Zusammenfassungsdaten enthalten. Sie können zusätzliche Zeilen erstellen, sie anders formatieren und sie über oder unter dem Tabelleninhalt hinzufügen.

#### F: Wie passe ich die Textausrichtung innerhalb einer Tabellenzelle an?

 A: Um die Textausrichtung innerhalb einer Tabellenzelle anzupassen, können Sie das`HorizontalAlignment` Und`VerticalAlignment` Eigenschaften der`TextFragment` Objekt. Um den Text beispielsweise horizontal zu zentrieren, können Sie`mytext.HorizontalAlignment = HorizontalAlignment.Center;` Ebenso können Sie festlegen`mytext.VerticalAlignment` um die vertikale Ausrichtung zu steuern.

#### F: Kann ich den Tabellenzellen statt Text Bilder hinzufügen?

 A: Ja, Sie können mit Aspose.PDF für .NET Bilder zu den Tabellenzellen hinzufügen. Anstatt ein`TextFragment` Objekt können Sie ein`Image` Objekt, laden Sie die Bilddatei und fügen Sie sie mit dem`cell.Paragraphs.Add(image);` -Methode. Dadurch können Sie neben Textinhalten auch Bilder in die Tabelle einfügen.