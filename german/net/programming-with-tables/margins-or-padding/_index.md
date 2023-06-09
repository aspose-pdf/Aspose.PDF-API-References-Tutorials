---
title: Ränder oder Polsterung
linktitle: Ränder oder Polsterung
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Ränder oder Abstände in einer Tabelle festlegen.
type: docs
weight: 140
url: /de/net/programming-with-tables/margins-or-padding/
---

In diesem Tutorial führen wir Sie Schritt für Schritt durch die Verwendung von Aspose.PDF für .NET zum Festlegen von Rändern oder Abständen in einer Tabelle. Wir stellen Ihnen Erklärungen und Codeausschnitte zur Verfügung, die Ihnen helfen, diese Funktionalität zu verstehen und in Ihrem C#-Quellcode zu implementieren.

## Schritt 1: Einrichten des Dokuments und der Seite
Zunächst müssen Sie das Dokument und die Seite mit dem folgenden Code einrichten:

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instanziieren Sie das Document-Objekt, indem Sie seinen leeren Konstruktor aufrufen
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Schritt 2: Erstellen einer Tabelle
Als nächstes erstellen wir ein Tabellenobjekt mit der Klasse Aspose.Pdf.Table:

```csharp
// Instanziieren Sie ein Tabellenobjekt
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Fügen Sie die Tabelle zur Absatzsammlung des gewünschten Abschnitts hinzu
page.Paragraphs.Add(tab1);
```

## Schritt 3: Spaltenbreiten und Standard-Zellenrahmen festlegen
Verwenden Sie den folgenden Code, um die Spaltenbreiten und den Standardzellenrahmen der Tabelle festzulegen:

```csharp
// Legen Sie die Spaltenbreiten der Tabelle fest
tab1. ColumnWidths = "50 50 50";
// Legen Sie den Standard-Zellenrand mithilfe des BorderInfo-Objekts fest
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## Schritt 4: Tabellenrand und Zellabstand festlegen
Um den Tabellenrand und den Zellenabstand festzulegen, erstellen Sie ein MarginInfo-Objekt und legen Sie seine Eigenschaften fest:

```csharp
// Erstellen Sie ein MarginInfo-Objekt und legen Sie dessen linken, unteren, rechten und oberen Rand fest
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;

// Legen Sie den Standard-Zellenabstand für das MarginInfo-Objekt fest
tab1. DefaultCellPadding = margin;

// Legen Sie den Tabellenrand mit einem anderen benutzerdefinierten BorderInfo-Objekt fest
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
```

## Schritt 5: Zeilen und Zellen hinzufügen
Nun fügen wir der Tabelle Zeilen und Zellen hinzu. Wir erstellen eine neue Zeile und fügen ihr Zellen hinzu:

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

## Schritt 7: Speichern des PDF
Um das PDF-Dokument zu speichern, verwenden Sie den folgenden Code:

```csharp
dataDir = dataDir + "MarginsOrPadding_out.pdf";
// Speichern Sie das PDF
doc.Save(dataDir);

Console.WriteLine("\nCell and table border width setup successfully.\nFile saved at " + dataDir);
```

### Beispielquellcode für Ränder oder Auffüllung mit Aspose.PDF für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instanziieren Sie das Document-Objekt, indem Sie seinen leeren Konstruktor aufrufen
Document doc = new Document();
Page page = doc.Pages.Add();
// Instanziieren Sie ein Tabellenobjekt
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Fügen Sie die Tabelle in der Absatzsammlung des gewünschten Abschnitts hinzu
page.Paragraphs.Add(tab1);
// Mit den Spaltenbreiten der Tabelle festlegen
tab1.ColumnWidths = "50 50 50";
// Legen Sie den Standardzellenrahmen mithilfe des BorderInfo-Objekts fest
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// Legen Sie den Tabellenrand mithilfe eines anderen benutzerdefinierten BorderInfo-Objekts fest
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// Erstellen Sie ein MarginInfo-Objekt und legen Sie dessen linken, unteren, rechten und oberen Rand fest
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Legen Sie den Standard-Zellenabstand für das MarginInfo-Objekt fest
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
// Row1.Cells[2].Paragraphs[0].FixedWidth= 80;
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
Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.PDF für .NET Ränder oder Abstände in einer Tabelle festlegen. Dieses Wissen wird Ihnen helfen, Ihre Möglichkeiten zur Dokumentformatierung zu verbessern und Ihre Tabellen optisch ansprechend zu gestalten.