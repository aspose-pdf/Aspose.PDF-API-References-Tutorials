---
title: Seitenumbruch einfügen
linktitle: Seitenumbruch einfügen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET einen Seitenumbruch in ein PDF-Dokument einfügen.
type: docs
weight: 110
url: /de/net/programming-with-tables/insert-page-break/
---

In diesem Tutorial erfahren Sie, wie Sie mit Aspose.PDF für .NET einen Seitenumbruch in ein PDF-Dokument einfügen. Wir erklären Ihnen Schritt für Schritt den Quellcode in C#. Am Ende dieses Tutorials erfahren Sie, wie Sie nach einer bestimmten Anzahl von Zeilen in einer Tabelle eines PDF-Dokuments einen Seitenumbruch einfügen. Lasst uns beginnen!

## Schritt 1: Einrichten der Umgebung
Stellen Sie sicher, dass Sie Ihre C#-Entwicklungsumgebung mit Aspose.PDF für .NET konfiguriert haben. Fügen Sie den Verweis zur Bibliothek hinzu und importieren Sie die erforderlichen Namespaces.

## Schritt 2: Dokument und Tabelle erstellen
Wir erstellen eine neue Dokumentinstanz und fügen diesem Dokument eine Seite hinzu. Als Nächstes erstellen wir eine Tabelleninstanz, um unsere Tabelle im PDF-Dokument darzustellen. Wir definieren auch die Rahmenstile für die Tabelle.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab. ColumnWidths = "100 100";
```

## Schritt 3: Zeilen zur Tabelle hinzufügen
Wir verwenden eine Schleife, um dem Array 200 Zeilen hinzuzufügen. Für jede Zeile erstellen wir eine Instanz von Row und fügen zwei Zellen mit Textinhalt hinzu.

```csharp
for (int counter = 0; counter <= 200; counter++)
{
     Aspose.Pdf.Row row = new Aspose.Pdf.Row();
     tab. Rows. Add(row);
    
     Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
     cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
     row. Cells. Add(cell1);
    
     Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
     cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
     row. Cells. Add(cell2);
    
     // Wenn 10 Zeilen hinzugefügt werden, fügen wir einen neuen Seitenumbruch ein
     if (counter % 10 == 0 && counter != 0)
         row. IsInNewPage = true;
}
```

## Schritt 4: Tabelle zum Dokument hinzufügen
Wir fügen die Tabelle zur Absatzsammlung der Dokumentseite hinzu.

```csharp
doc.Pages[1].Paragraphs.Add(tab);
```

## Schritt 5: Speichern Sie das Dokument
Wir speichern das PDF-Dokument mit eingefügtem Seitenumbruch.

```csharp
doc.Save(dataDir + "InsertPageBreak_out.pdf");
```

### Beispielquellcode für „Seitenumbruch einfügen“ mit Aspose.Words für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dokumentinstanz instanziieren
Document doc = new Document();
// Seite zur Seitensammlung der PDF-Datei hinzufügen
doc.Pages.Add();
// Tabelleninstanz erstellen
Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
// Legen Sie den Rahmenstil für die Tabelle fest
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// Legen Sie den Standardrahmenstil für die Tabelle mit der Rahmenfarbe Rot fest
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// Geben Sie die Spaltenbreite der Tabelle an
tab.ColumnWidths = "100 100";
// Erstellen Sie eine Schleife, um 200 Zeilen für die Tabelle hinzuzufügen
for (int counter = 0; counter <= 200; counter++)
{
	Aspose.Pdf.Row row = new Aspose.Pdf.Row();
	tab.Rows.Add(row);
	Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
	cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
	row.Cells.Add(cell1); Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
	cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
	row.Cells.Add(cell2);
	// Wenn 10 Zeilen hinzugefügt werden, rendern Sie die neue Zeile auf einer neuen Seite
	if (counter % 10 == 0 && counter != 0) row.IsInNewPage = true;
}
// Fügen Sie der Absatzsammlung der PDF-Datei eine Tabelle hinzu
doc.Pages[1].Paragraphs.Add(tab);

dataDir = dataDir + "InsertPageBreak_out.pdf";
// Speichern Sie das PDF-Dokument
doc.Save(dataDir);

Console.WriteLine("\nPage break inserted successfully.\nFile saved at " + dataDir);
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.PDF für .NET einen Seitenumbruch in ein PDF-Dokument einfügt. Mit dieser Schritt-für-Schritt-Anleitung können Sie mit C# nach einer bestimmten Anzahl von Zeilen in einer Tabelle in einem PDF-Dokument einen Seitenumbruch einfügen.