---
title: Tabelle ersetzen
linktitle: Tabelle ersetzen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET eine Tabelle in einem PDF-Dokument ersetzen.
type: docs
weight: 180
url: /de/net/programming-with-tables/replace-table/
---

In diesem Tutorial führen wir Sie Schritt für Schritt durch das Ersetzen einer Tabelle in einem PDF-Dokument mit Aspose.PDF für .NET. Wir erklären Ihnen den bereitgestellten C#-Quellcode und zeigen Ihnen, wie Sie ihn implementieren.

## Schritt 1: Laden des vorhandenen PDF-Dokuments
Zuerst müssen Sie das vorhandene PDF-Dokument mit dem folgenden Code laden:

```csharp
// Pfad zum Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laden Sie das vorhandene PDF-Dokument
Document pdfDocument = new Document(dataDir + @"Table_input.pdf");
```

## Schritt 2: Erstellen des TableAbsorber-Objekts zum Suchen der Tabellen
Als Nächstes erstellen wir ein TableAbsorber-Objekt, um die Tabellen im PDF-Dokument zu finden:

```csharp
// Erstellen Sie ein TableAbsorber-Objekt, um die Tabellen zu finden
TableAbsorber absorber = new TableAbsorber();
```

## Schritt 3: Besuchen Sie die erste Seite mit dem Absorber
Wir besuchen nun die erste Seite des PDF-Dokuments mit dem Absorber:

```csharp
//Besuchen Sie die erste Seite mit dem Absorber
absorb.Visit(pdfDocument.Pages[1]);
```

## Schritt 4: Erste Tabelle auf der Seite erstellen
Um die Tabelle ersetzen zu können, erhalten wir die erste Tabelle der Seite:

```csharp
// Holen Sie sich die erste Tabelle auf der Seite
AbsorbedTable table = absorb.TableList[0];
```

## Schritt 5: Erstellen einer neuen Tabelle
Nun erstellen wir eine neue Tabelle mit den gewünschten Spalten und Zellen:

```csharp
Table newTable = new Table();
newTable.ColumnWidths = "100 100 100";
newTable.DefaultCellBorder = new BorderInfo(BorderSide.All, 1F);

Row row = newTable.Rows.Add();
row. Cells. Add("Col 1");
row. Cells. Add("Col 2");
row. Cells. Add("Col 3");
```

## Schritt 6: Ersetzen der vorhandenen Tabelle durch die neue Tabelle
Wir ersetzen nun die bestehende Tabelle durch die neue Tabelle auf der ersten Seite des Dokuments:

```csharp
// Ersetzen Sie die Tabelle durch die neue Tabelle
absorb.Replace(pdfDocument.Pages[1], table, newTable);
```

## Schritt 7: Speichern des Dokuments
Abschließend speichern wir das geänderte PDF-Dokument:

```csharp
pdfDocument.Save(dataDir + "TableReplaced_out.pdf");
```

### Beispielquellcode für „Tabelle ersetzen“ mit Aspose.Words für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Vorhandenes PDF-Dokument laden
Document pdfDocument = new Document(dataDir + @"Table_input.pdf");

// Erstellen Sie ein TableAbsorber-Objekt, um Tabellen zu finden
TableAbsorber absorber = new TableAbsorber();

// Besuchen Sie die erste Seite mit Absorber
absorber.Visit(pdfDocument.Pages[1]);

// Holen Sie sich die erste Tabelle auf der Seite
AbsorbedTable table = absorber.TableList[0];

// Neue Tabelle erstellen
Table newTable = new Table();
newTable.ColumnWidths = "100 100 100";
newTable.DefaultCellBorder = new BorderInfo(BorderSide.All, 1F);

Row row = newTable.Rows.Add();
row.Cells.Add("Col 1");
row.Cells.Add("Col 2");
row.Cells.Add("Col 3");

// Ersetzen Sie den Tisch durch einen neuen
absorber.Replace(pdfDocument.Pages[1], table, newTable);

// Dokument speichern
pdfDocument.Save(dataDir + "TableReplaced_out.pdf");
```

## Abschluss
Herzlichen Glückwunsch! Sie haben jetzt gelernt, wie Sie mit Aspose.PDF für .NET eine Tabelle in einem PDF-Dokument ersetzen. Diese Schritt-für-Schritt-Anleitung zeigte Ihnen, wie Sie das Dokument laden, die vorhandene Tabelle finden, eine neue Tabelle erstellen und diese ersetzen. Jetzt können Sie dieses Wissen auf Ihre eigenen Projekte anwenden.