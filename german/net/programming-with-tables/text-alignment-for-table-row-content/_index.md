---
title: Textausrichtung für Tabellenzeileninhalte
linktitle: Textausrichtung für Tabellenzeileninhalte
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie Zeileninhalte in einer PDF-Tabelle mit Aspose.PDF für .NET ausrichten.
type: docs
weight: 210
url: /de/net/programming-with-tables/text-alignment-for-table-row-content/
---

In diesem Tutorial führen wir Sie Schritt für Schritt durch die Ausrichtung des Inhalts einer Zeile in einer Tabelle eines PDF-Dokuments mit Aspose.PDF für .NET. Wir erklären Ihnen den bereitgestellten C#-Quellcode und zeigen Ihnen, wie Sie ihn implementieren.

## Schritt 1: Erstellen des PDF-Dokuments
Zuerst erstellen wir das PDF-Dokument:

```csharp
var dataDir = "YOUR DOCUMENTS DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## Schritt 2: Tabelleninitialisierung
Als nächstes initialisieren wir die Tabelle:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

## Schritt 3: Festlegen der Tabellenrandfarbe
Wir konfigurieren die Randfarbe der Tabelle:

```csharp
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## Schritt 4: Konfigurieren des Tabellenzellenrahmens
Wir werden den Tabellenzellenrand konfigurieren:

```csharp
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## Schritt 5: Schleife, um der Tabelle 10 Zeilen hinzuzufügen
Wir werden nun eine Schleife verwenden, um der Tabelle 10 Zeilen hinzuzufügen:

```csharp
for (int row_count = 0; row_count < 10; row_count++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row.VerticalAlignment = VerticalAlignment.Center;

     row.Cells.Add("Column("+row_count+",1)"+DateTime.Now.Ticks);
     row.Cells.Add("Column("+row_count+",2)");
     row.Cells.Add("Column("+row_count+",3)");
}
```

## Schritt 6: Konfigurieren der vertikalen Linienausrichtung
Wir werden die vertikale Ausrichtung der Tabellenzeilen konfigurieren:

```csharp
row.VerticalAlignment = VerticalAlignment.Center;
```

## Schritt 7: Inhalt zu Zeilenzellen hinzufügen
Wir werden den Zeilenzellen Inhalte hinzufügen:

```csharp
row.Cells.Add("Column("+row_count+",1)"+DateTime.Now.Ticks);
row.Cells.Add("Column("+row_count+",2)");
row.Cells.Add("Column("+row_count+",3)");
```

## Schritt 8: Hinzufügen der Tabelle zur Dokumentseite
Fügen wir nun die Tabelle zur Dokumentseite hinzu:

```csharp
Page tocPage = doc.Pages.Add();
tocPage.Paragraphs.Add(table);
```

## Schritt 9: Speichern des PDF-Dokuments
Abschließend speichern wir das PDF-Dokument:

```csharp
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

### Beispielquellcode für die Textausrichtung für Tabellenzeileninhalte mit Aspose.Words für .NET

```csharp
var dataDir = "YOUR DOCUMENT DIRECTORY";

// PDF-Dokument erstellen
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// Initialisiert eine neue Instanz der Tabelle
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Legen Sie die Rahmenfarbe der Tabelle auf „LightGray“ fest
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Legen Sie den Rand für Tabellenzellen fest
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Erstellen Sie eine Schleife, um 10 Zeilen hinzuzufügen
for (int row_count = 0; row_count < 10; row_count++)
{
	// Zeile zur Tabelle hinzufügen
	Aspose.Pdf.Row row = table.Rows.Add();
	row.VerticalAlignment = VerticalAlignment.Center;

	row.Cells.Add("Column (" + row_count + ", 1)" + DateTime.Now.Ticks);
	row.Cells.Add("Column (" + row_count + ", 2)");
	row.Cells.Add("Column (" + row_count + ", 3)");
}
Page tocPage = doc.Pages.Add();
// Tabellenobjekt zur ersten Seite des Eingabedokuments hinzufügen
tocPage.Paragraphs.Add(table);
// Speichern Sie das aktualisierte Dokument, das das Tabellenobjekt enthält
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

## Abschluss
Herzlichen Glückwunsch! Sie haben jetzt gelernt, wie Sie den Inhalt einer Zeile in einer Tabelle in einem PDF-Dokument mit Aspose.PDF für .NET ausrichten. Diese Schritt-für-Schritt-Anleitung zeigte Ihnen, wie Sie ein Dokument erstellen, eine Tabelle initialisieren, Rahmen und Ausrichtung konfigurieren, Inhalte hinzufügen und das PDF-Dokument speichern. Jetzt können Sie dieses Wissen auf Ihre eigenen Projekte anwenden.