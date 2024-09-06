---
title: Textausrichtung für Tabellenzeileninhalte
linktitle: Textausrichtung für Tabellenzeileninhalte
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie Zeileninhalte in einer PDF-Tabelle mit Aspose.PDF für .NET ausrichten.
type: docs
weight: 210
url: /de/net/programming-with-tables/text-alignment-for-table-row-content/
---
In diesem Tutorial führen wir Sie Schritt für Schritt durch die Ausrichtung des Inhalts einer Zeile in einer Tabelle eines PDF-Dokuments mithilfe von Aspose.PDF für .NET. Wir erklären den bereitgestellten C#-Quellcode und zeigen Ihnen, wie Sie ihn implementieren.

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

## Schritt 3: Festlegen der Tabellenrahmenfarbe
Wir konfigurieren die Tabellenrahmenfarbe:

```csharp
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## Schritt 4: Konfigurieren des Tabellenzellenrahmens
Wir werden den Rahmen der Tabellenzelle konfigurieren:

```csharp
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## Schritt 5: Schleife, um 10 Zeilen zur Tabelle hinzuzufügen
Wir verwenden nun eine Schleife, um der Tabelle 10 Zeilen hinzuzufügen:

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
Wir werden die vertikale Ausrichtung der Zeilen der Tabelle konfigurieren:

```csharp
row.VerticalAlignment = VerticalAlignment.Center;
```

## Schritt 7: Inhalt zu Zeilenzellen hinzufügen
Wir werden den Zeilenzellen Inhalt hinzufügen:

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
// Stellen Sie die Tabellenrahmenfarbe auf Hellgrau ein
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Festlegen der Rahmen für Tabellenzellen
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
// Aktualisiertes Dokument mit Tabellenobjekt speichern
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

## Abschluss
Herzlichen Glückwunsch! Sie haben nun gelernt, wie Sie den Inhalt einer Zeile in einer Tabelle in einem PDF-Dokument mit Aspose.PDF für .NET ausrichten. Diese Schritt-für-Schritt-Anleitung hat Ihnen gezeigt, wie Sie ein Dokument erstellen, eine Tabelle initialisieren, Rahmen und Ausrichtung konfigurieren, Inhalt hinzufügen und das PDF-Dokument speichern. Jetzt können Sie dieses Wissen in Ihren eigenen Projekten anwenden.

### Häufig gestellte Fragen

#### F: Wie kann ich den Inhalt der Tabellenzellen horizontal ausrichten?

 A: Sie können den Inhalt der Tabellenzellen horizontal ausrichten, indem Sie die`HorizontalAlign` Eigenschaft der Zelle`TextState` Objekt. Um den Text beispielsweise zentriert auszurichten, verwenden Sie`cell.TextState.HorizontalAlignment = HorizontalAlignment.Center` Sie können es auch so einstellen:`HorizontalAlignment.Left` oder`HorizontalAlignment.Right` für die Links- bzw. Rechtsausrichtung.

#### F: Kann ich einzelnen Zellen in der Tabelle unterschiedliche Rahmenstile und Farben zuweisen?

 A: Ja, Sie können den einzelnen Zellen in der Tabelle unterschiedliche Rahmenstile und Farben zuweisen. Um den Rahmen für eine bestimmte Zelle anzupassen, legen Sie die`cell.Border` Eigentum an einem neuen`BorderInfo`Objekt mit den gewünschten Einstellungen wie Randseiten, Breite und Farbe.

#### F: Wie kann ich die vertikale Ausrichtung des Tabelleninhalts innerhalb der Zellen anpassen?

 A: Sie können die vertikale Ausrichtung des Tabelleninhalts innerhalb der Zellen anpassen, indem Sie die`VerticalAlignment` Eigenschaft der Zeile zu`VerticalAlignment.Center`, `VerticalAlignment.Top` , oder`VerticalAlignment.Bottom`. Diese Eigenschaft steuert die vertikale Ausrichtung aller Zellen in dieser Zeile.

#### F: Ist es möglich, der Tabelle dynamisch weitere Spalten oder Zeilen hinzuzufügen?

 A: Ja, Sie können der Tabelle dynamisch weitere Spalten und Zeilen hinzufügen, indem Sie die`table.Rows.Add()` Methode zum Hinzufügen neuer Zeilen und der`row.Cells.Add()` Methode, um den Zeilen neue Zellen hinzuzufügen. Sie können dies innerhalb von Schleifen oder basierend auf Ihren spezifischen Anforderungen tun.

#### F: Wie kann ich eine Hintergrundfarbe für bestimmte Zellen oder die gesamte Tabelle festlegen?

 A: Um eine Hintergrundfarbe für bestimmte Zellen oder die gesamte Tabelle festzulegen, verwenden Sie die`BackgroundColor` Eigentum der`Cell` oder`Table` Objekt. Um beispielsweise die Hintergrundfarbe einer Zelle festzulegen, verwenden Sie`cell.BackgroundColor = Aspose.Pdf.Color.LightBlue`.