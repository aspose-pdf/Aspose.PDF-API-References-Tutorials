---
title: Tabelle im PDF-Dokument rendern
linktitle: Tabelle im PDF-Dokument rendern
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET eine Tabelle in einem PDF-Dokument anzeigen.
type: docs
weight: 170
url: /de/net/programming-with-tables/render-table/
---
In diesem Tutorial führen wir Sie Schritt für Schritt durch die Anzeige einer Tabelle in einem PDF-Dokument mit Aspose.PDF für .NET. Wir erklären den bereitgestellten C#-Quellcode und zeigen Ihnen, wie Sie ihn implementieren.

## Schritt 1: Erstellen des Dokuments
Zuerst erstellen wir ein neues PDF-Dokument:

```csharp
// Pfad zum Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Neues Dokument erstellen
Document doc = new Document();
```

## Schritt 2: Seitenränder und -ausrichtung konfigurieren
Als Nächstes konfigurieren wir die Seitenränder und stellen die Ausrichtung auf Querformat ein:

```csharp
PageInfo pageInfo = doc.PageInfo;
Aspose.Pdf.MarginInfo marginInfo = pageInfo.Margin;

marginInfo. Left = 37;
marginInfo. Right = 37;
marginInfo. Top = 37;
marginInfo.Bottom = 37;

pageInfo.IsLandscape = true;
```

## Schritt 3: Tabelle und Spalten erstellen
Lassen Sie uns nun eine Tabelle erstellen und die Spaltenbreiten festlegen:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "50 100";
```

## Schritt 4: Zeilen und Zellen zur Tabelle hinzufügen
Als Nächstes fügen wir der Tabelle mithilfe einer Schleife Zeilen und Zellen hinzu:

```csharp
for (int i = 1; i <= 120; i++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row. FixedRowHeight = 15;
     Aspose.Pdf.Cell cell1 = row.Cells.Add();
     cell1.Paragraphs.Add(new TextFragment("Content 1"));
     Aspose.Pdf.Cell cell2 = row.Cells.Add();
     cell2.Paragraphs.Add(new TextFragment("HHHHH"));
}
```

## Schritt 5: Hinzufügen der Tabelle zur Seite
Fügen wir nun die Tabelle zur Dokumentseite hinzu:

```csharp
Page curPage = doc.Pages.Add();
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs. Add(table);
```

## Schritt 6: Tabelle auf einer neuen Seite anzeigen
Als nächstes erstellen wir eine neue Tabelle und setzen die Eigenschaft „IsInNewPage“ auf „true“, um die Tabelle auf einer neuen Seite anzuzeigen:

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table. ColumnWidths = "100 100";
for (int i = 1; i <= 10; i++)
{
     Aspose.Pdf.Row row = table1.Rows.Add();
     Aspose.Pdf.Cell cell1 = row.Cells.Add();
     cell1.Paragraphs.Add(new TextFragment("LAAAAAAA"));
     Aspose.Pdf.Cell cell2 = row.Cells.Add();
     cell2.Paragraphs.Add(new TextFragment("LAAGGGGGG"));
}
table1.IsInNewPage = true;
paragraphs. Add(table1);
```

## Schritt 7: PDF speichern
Abschließend speichern wir das PDF-Dokument:

```csharp
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable displayed successfully on a page.\nFile saved at location: " + dataDir);
```

### Beispielquellcode für Render Table mit Aspose.PDF für .NET

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
PageInfo pageInfo = doc.PageInfo;
Aspose.Pdf.MarginInfo marginInfo = pageInfo.Margin;

marginInfo.Left = 37;
marginInfo.Right = 37;
marginInfo.Top = 37;
marginInfo.Bottom = 37;

pageInfo.IsLandscape = true;

Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table.ColumnWidths = "50 100";
// Seite hinzugefügt.
Page curPage = doc.Pages.Add();
for (int i = 1; i <= 120; i++)
{
	Aspose.Pdf.Row row = table.Rows.Add();
	row.FixedRowHeight = 15;
	Aspose.Pdf.Cell cell1 = row.Cells.Add();
	cell1.Paragraphs.Add(new TextFragment("Content 1"));
	Aspose.Pdf.Cell cell2 = row.Cells.Add();
	cell2.Paragraphs.Add(new TextFragment("HHHHH"));
}
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs.Add(table);
/********************************************/
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table.ColumnWidths = "100 100";
for (int i = 1; i <= 10; i++)
{
	Aspose.Pdf.Row row = table1.Rows.Add();
	Aspose.Pdf.Cell cell1 = row.Cells.Add();
	cell1.Paragraphs.Add(new TextFragment("LAAAAAAA"));
	Aspose.Pdf.Cell cell2 = row.Cells.Add();
	cell2.Paragraphs.Add(new TextFragment("LAAGGGGGG"));
}
table1.IsInNewPage = true;
// Ich möchte bitte Tabelle 1 auf der nächsten Seite behalten ...
paragraphs.Add(table1);
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable render successfully on a page.\nFile saved at " + dataDir);
```

## Abschluss
Herzlichen Glückwunsch! Sie haben nun gelernt, wie Sie mit Aspose.PDF für .NET eine Tabelle in einem PDF-Dokument anzeigen. Diese Schritt-für-Schritt-Anleitung hat Ihnen gezeigt, wie Sie ein Dokument erstellen, Seitenränder und -ausrichtung konfigurieren, eine Tabelle hinzufügen und eine Tabelle auf einer neuen Seite anzeigen. Jetzt können Sie dieses Wissen in Ihren eigenen Projekten anwenden.

### FAQs zum Rendern von Tabellen in PDF-Dokumenten

#### F: Wie kann ich das Erscheinungsbild der Tabelle ändern, beispielsweise die Zellenfarben ändern oder Rahmen hinzufügen?

 A: Um das Aussehen der Tabelle zu ändern, können Sie verschiedene Eigenschaften der`Aspose.Pdf.Table` und seine Zellen. Sie können beispielsweise die`BackgroundColor` Eigenschaft von Zellen, um deren Hintergrundfarbe zu ändern. Sie können auch die`Border` Eigenschaft der Tabelle oder einzelner Zellen, um Rahmen hinzuzufügen. Darüber hinaus können Sie die Schriftart, Textfarbe und Ausrichtung des Tabelleninhalts anpassen, indem Sie die`TextState` der`TextFragment` Objekte, die den Zellen hinzugefügt werden.

#### F: Kann ich der Tabelle Kopf- oder Fußzeilen hinzufügen?

A: Ja, Sie können der Tabelle Kopf- oder Fußzeilen hinzufügen, indem Sie am Anfang oder Ende der Tabelle zusätzliche Zeilen erstellen und den entsprechenden Inhalt in die Zellen eingeben. Sie können die Kopf- oder Fußzeilen unabhängig vom restlichen Tabelleninhalt anpassen, indem Sie diesen bestimmten Zeilen unterschiedliche Stile oder Inhalte hinzufügen.

#### F: Wie kann ich die Position der Tabelle auf der Seite steuern?

A: Um die Position der Tabelle auf der Seite zu steuern, können Sie die`MarginInfo` der`PageInfo` Objekt. Das`MarginInfo` können Sie die linken, rechten, oberen und unteren Ränder der Seite festlegen, was sich auf den verfügbaren Platz für die Tabelle auswirkt. Sie können auch die`PositioningType` Eigentum der`Aspose.Pdf.Table` um die horizontale und vertikale Ausrichtung innerhalb des Inhaltsbereichs der Seite zu steuern.

#### F: Kann ich die Tabelle in andere Dateiformate wie Excel oder CSV exportieren?

A: Aspose.PDF für .NET ist in erster Linie für die Arbeit mit PDF-Dokumenten konzipiert. Obwohl es das PDF-Dokument als Bild oder XPS exportieren kann, unterstützt es nicht direkt den Export von Tabellen in Formate wie Excel oder CSV. Um die Tabellendaten in verschiedene Dateiformate zu exportieren, müssen Sie möglicherweise zusätzliche Bibliotheken oder Methoden verwenden, um den PDF-Inhalt in das gewünschte Format zu konvertieren.

#### F: Wie kann ich den Tabellenzellen Hyperlinks hinzufügen?

 A: Um Hyperlinks zu den Tabellenzellen hinzuzufügen, können Sie das`Aspose.Pdf.WebHyperlink` Klasse, um einen Hyperlink zu erstellen und ihn dann als Anker zum`TextFragment`innerhalb der Zelle. Dadurch können Sie eine URL oder ein Linkziel mit einem bestimmten Text oder Inhalt innerhalb der Zelle verknüpfen und anklickbare Hyperlinks erstellen.