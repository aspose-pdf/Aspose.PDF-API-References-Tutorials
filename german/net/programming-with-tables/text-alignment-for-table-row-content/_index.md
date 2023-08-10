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

### Beispielquellcode für die Textausrichtung für Tabellenzeileninhalte mit Aspose.PDF für .NET

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

### FAQs

#### F: Wie kann ich den Inhalt der Tabellenzellen horizontal ausrichten?

 A: Sie können den Inhalt der Tabellenzellen horizontal ausrichten, indem Sie festlegen`HorizontalAlign` Eigenschaft der Zelle`TextState` Objekt. Um beispielsweise den Text zentriert auszurichten, verwenden Sie`cell.TextState.HorizontalAlignment = HorizontalAlignment.Center` . Sie können es auch auf einstellen`HorizontalAlignment.Left` oder`HorizontalAlignment.Right` für die linke bzw. rechte Ausrichtung.

#### F: Kann ich auf einzelne Zellen in der Tabelle unterschiedliche Rahmenstile und -farben anwenden?

 A: Ja, Sie können auf einzelne Zellen in der Tabelle unterschiedliche Rahmenstile und -farben anwenden. Um den Rahmen für eine bestimmte Zelle anzupassen, legen Sie fest`cell.Border` Eigentum zu einem neuen`BorderInfo`Objekt mit den gewünschten Einstellungen wie Randseiten, Breite und Farbe.

#### F: Wie kann ich die vertikale Ausrichtung des Tabelleninhalts innerhalb der Zellen anpassen?

 A: Sie können die vertikale Ausrichtung des Tabelleninhalts innerhalb der Zellen anpassen, indem Sie die festlegen`VerticalAlignment` Eigenschaft der Zeile bis`VerticalAlignment.Center`, `VerticalAlignment.Top` , oder`VerticalAlignment.Bottom`. Diese Eigenschaft steuert die vertikale Ausrichtung aller Zellen in dieser Zeile.

#### F: Ist es möglich, der Tabelle dynamisch weitere Spalten oder Zeilen hinzuzufügen?

 A: Ja, Sie können der Tabelle dynamisch weitere Spalten und Zeilen hinzufügen, indem Sie die verwenden`table.Rows.Add()` Methode zum Hinzufügen neuer Zeilen und der`row.Cells.Add()` Methode zum Hinzufügen neuer Zellen zu den Zeilen. Sie können dies innerhalb von Schleifen oder basierend auf Ihren spezifischen Anforderungen tun.

#### F: Wie kann ich eine Hintergrundfarbe für bestimmte Zellen oder die gesamte Tabelle festlegen?

 A: Um eine Hintergrundfarbe für bestimmte Zellen oder die gesamte Tabelle festzulegen, verwenden Sie die`BackgroundColor` Eigentum der`Cell` oder`Table` Objekt. Um beispielsweise die Hintergrundfarbe einer Zelle festzulegen, verwenden Sie`cell.BackgroundColor = Aspose.Pdf.Color.LightBlue`.