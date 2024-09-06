---
title: Seitenumbruch in PDF-Datei einfügen
linktitle: Seitenumbruch in PDF-Datei einfügen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET einen Seitenumbruch in eine PDF-Datei einfügen.
type: docs
weight: 110
url: /de/net/programming-with-tables/insert-page-break/
---
In diesem Tutorial lernen wir, wie man mit Aspose.PDF für .NET einen Seitenumbruch in eine PDF-Datei einfügt. Wir erklären den Quellcode in C# Schritt für Schritt. Am Ende dieses Tutorials wissen Sie, wie Sie nach einer bestimmten Anzahl von Zeilen in einer Tabelle eines PDF-Dokuments einen Seitenumbruch einfügen. Fangen wir an!

## Schritt 1: Einrichten der Umgebung
Stellen Sie sicher, dass Sie Ihre C#-Entwicklungsumgebung mit Aspose.PDF für .NET konfiguriert haben. Fügen Sie den Verweis auf die Bibliothek hinzu und importieren Sie die erforderlichen Namespaces.

## Schritt 2: Erstellen des Dokuments und der Tabelle
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

## Schritt 4: Hinzufügen der Tabelle zum Dokument
Wir fügen die Tabelle der Absatzsammlung der Dokumentseite hinzu.

```csharp
doc.Pages[1].Paragraphs.Add(tab);
```

## Schritt 5: Speichern Sie das Dokument
Wir speichern das PDF-Dokument mit eingefügtem Seitenumbruch.

```csharp
doc.Save(dataDir + "InsertPageBreak_out.pdf");
```

### Beispielquellcode zum Einfügen eines Seitenumbruchs mit Aspose.PDF für .NET

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dokumentinstanz instantiieren
Document doc = new Document();
// Seite zur Seitensammlung der PDF-Datei hinzufügen
doc.Pages.Add();
// Tabelleninstanz erstellen
Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
// Rahmenstil für Tabelle festlegen
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// Legen Sie den Standardrahmenstil für die Tabelle mit der Rahmenfarbe Rot fest
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// Breite der Tabellenspalten festlegen
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
	// Wenn 10 Zeilen hinzugefügt werden, wird eine neue Zeile auf einer neuen Seite angezeigt.
	if (counter % 10 == 0 && counter != 0) row.IsInNewPage = true;
}
// Tabelle zur Absatzsammlung der PDF-Datei hinzufügen
doc.Pages[1].Paragraphs.Add(tab);

dataDir = dataDir + "InsertPageBreak_out.pdf";
// Speichern des PDF-Dokuments
doc.Save(dataDir);

Console.WriteLine("\nPage break inserted successfully.\nFile saved at " + dataDir);
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.PDF für .NET einen Seitenumbruch in ein PDF-Dokument einfügt. Mit dieser Schritt-für-Schritt-Anleitung können Sie mit C# einen Seitenumbruch nach einer bestimmten Anzahl von Zeilen in einer Tabelle in einem PDF-Dokument einfügen.

### FAQs zum Einfügen eines Seitenumbruchs in eine PDF-Datei

#### F: Wie kann ich die Seitengröße für die nach dem Seitenumbruch erstellten neuen Seiten ändern?

 A: Um die Seitengröße für die neuen Seiten zu ändern, die nach dem Seitenumbruch erstellt werden, können Sie die`PageSize` Eigentum der`Page` Objekt. Mit dem folgenden Code können Sie beispielsweise die Seitengröße auf A4 einstellen:

```csharp
// Stellen Sie die Seitengröße auf A4 ein
doc.Pages[1].SetPageSize(PageSize.A4);
```

#### F: Kann ich die Seitenränder für die neuen Seiten nach dem Seitenumbruch steuern?

 A: Ja, Sie können die Seitenränder für die neuen Seiten nach dem Seitenumbruch steuern. Verwenden Sie die`Margin` Eigentum der`Page` Objekt, um die Seitenränder festzulegen. Um beispielsweise alle Ränder auf 10 Punkte festzulegen, können Sie den folgenden Code verwenden:

```csharp
// Alle Ränder auf 10 Punkte setzen
doc.Pages[1].Margin = new MarginInfo(10, 10, 10, 10);
```

#### F: Ist es möglich, den neuen Seiten nach dem Seitenumbruch Kopf- und Fußzeilen hinzuzufügen?

 A: Ja, Sie können den neuen Seiten nach dem Seitenumbruch Kopf- und Fußzeilen hinzufügen. Verwenden Sie die`Page.Header` Und`Page.Footer` Eigenschaften, um Inhalt zu den Kopf- und Fußzeilenabschnitten der Seite hinzuzufügen. Beispiel:

```csharp
// Kopfzeile zu den neuen Seiten hinzufügen
doc.Pages[1].Header = new HeaderFooter()
{
    Margin = new MarginInfo(10, 10, 10, 10),
    Paragraphs = { new TextFragment("Header content") }
};

// Fußzeile zu den neuen Seiten hinzufügen
doc.Pages[1].Footer = new HeaderFooter()
{
    Margin = new MarginInfo(10, 10, 10, 10),
    Paragraphs = { new TextFragment("Footer content") }
};
```

#### F: Kann ich Seitenumbrüche an bestimmten Stellen und nicht erst nach einer bestimmten Zeilenanzahl einfügen?

 A: Ja, Sie können Seitenumbrüche an bestimmten Stellen einfügen, anstatt nach einer bestimmten Anzahl von Zeilen. Sie können die`IsInNewPage` Eigenschaft einer Zeile zu`true` um die Tabelle zu zwingen, nach dieser Zeile eine neue Seite zu beginnen.

#### F: Wie kann ich das Seitenumbruchverhalten basierend auf der Inhaltshöhe anpassen?

 A: Sie können die`IsBroken` Eigenschaft der Tabelle, um den automatischen Zeilenumbruch über mehrere Seiten hinweg zu aktivieren oder zu deaktivieren. Wenn diese Einstellung auf`true`, ermöglicht es, Zeilen basierend auf der Inhaltshöhe über mehrere Seiten hinweg umzubrechen.