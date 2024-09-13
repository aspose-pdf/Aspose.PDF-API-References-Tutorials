---
title: Tabelle im PDF-Dokument ersetzen
linktitle: Tabelle im PDF-Dokument ersetzen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET eine Tabelle in einem PDF-Dokument ersetzen.
type: docs
weight: 180
url: /de/net/programming-with-tables/replace-table/
---
In diesem Tutorial führen wir Sie Schritt für Schritt durch das Ersetzen einer Tabelle in einem PDF-Dokument mithilfe von Aspose.PDF für .NET. Wir erklären den bereitgestellten C#-Quellcode und zeigen Ihnen, wie Sie ihn implementieren.

## Schritt 1: Vorhandenes PDF-Dokument laden
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
Wir besuchen nun mit dem Absorber die erste Seite des PDF-Dokuments:

```csharp
// Besuchen Sie die erste Seite mit dem Absorber
absorb.Visit(pdfDocument.Pages[1]);
```

## Schritt 4: Die erste Tabelle auf die Seite bringen
Um die Tabelle ersetzen zu können, holen wir uns die erste Tabelle der Seite:

```csharp
// Holen Sie sich die erste Tabelle auf der Seite
AbsorbedTable table = absorb.TableList[0];
```

## Schritt 5: Eine neue Tabelle erstellen
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
Wir ersetzen nun die vorhandene Tabelle durch die neue Tabelle auf der ersten Seite des Dokuments:

```csharp
// Ersetzen Sie die Tabelle durch die neue Tabelle
absorb.Replace(pdfDocument.Pages[1], table, newTable);
```

## Schritt 7: Speichern des Dokuments
Abschließend speichern wir das geänderte PDF-Dokument:

```csharp
pdfDocument.Save(dataDir + "TableReplaced_out.pdf");
```

### Beispielquellcode für „Replace Table“ mit Aspose.PDF für .NET

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Vorhandenes PDF-Dokument laden
Document pdfDocument = new Document(dataDir + @"Table_input.pdf");

// Erstellen Sie ein TableAbsorber-Objekt, um Tabellen zu finden
TableAbsorber absorber = new TableAbsorber();

// Besuchen Sie die erste Seite mit Absorber
absorber.Visit(pdfDocument.Pages[1]);

// Erste Tabelle auf der Seite abrufen
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
Herzlichen Glückwunsch! Sie haben nun gelernt, wie Sie mit Aspose.PDF für .NET eine Tabelle in einem PDF-Dokument ersetzen. Diese Schritt-für-Schritt-Anleitung hat Ihnen gezeigt, wie Sie das Dokument laden, die vorhandene Tabelle finden, eine neue Tabelle erstellen und sie ersetzen. Jetzt können Sie dieses Wissen in Ihren eigenen Projekten anwenden.

### FAQs zum Ersetzen von Tabellen in PDF-Dokumenten

#### F: Kann ich mit diesem Ansatz mehrere Tabellen im selben PDF-Dokument ersetzen?

 A: Ja, Sie können mehrere Tabellen im selben PDF-Dokument ersetzen, indem Sie für jede Tabelle, die Sie ersetzen möchten, den gleichen Vorgang ausführen. Nachdem Sie die`AbsorbedTable` Objekt für jede Tabelle mit dem`TableAbsorber` können Sie entsprechende neue Tabellen anlegen und anschließend mit dem`absorber.Replace()` Methode, um jede vorhandene Tabelle durch die entsprechende neue Tabelle zu ersetzen.

#### F: Was passiert, wenn die neue Tabelle eine andere Spaltenanzahl hat als die Originaltabelle?

A: Wenn die neue Tabelle eine andere Spaltenanzahl als die Originaltabelle hat, kann dies zu unerwartetem Verhalten oder Layoutproblemen im geänderten PDF-Dokument führen. Um einen nahtlosen Austausch zu gewährleisten, muss unbedingt sichergestellt werden, dass die Struktur der neuen Tabelle (Anzahl der Spalten und deren Breite) mit der Struktur der Originaltabelle übereinstimmt.

#### F: Kann ich eine Tabelle auf einer bestimmten Seite außer der ersten Seite ersetzen?

 A: Ja, Sie können eine Tabelle auf einer bestimmten Seite außer der ersten Seite ersetzen, indem Sie den Seitenindex im`pdfDocument.Pages[]` Methodenaufruf beim Abrufen der`AbsorbedTable` Objekt. Um beispielsweise eine Tabelle auf der zweiten Seite zu ersetzen, verwenden Sie`pdfDocument.Pages[2]`.

#### F: Kann ich das Erscheinungsbild der neuen Tabelle anpassen, beispielsweise durch Hinzufügen einer Hintergrundfarbe oder von Rändern?

 A: Ja, Sie können das Erscheinungsbild der neuen Tabelle anpassen, indem Sie verschiedene Eigenschaften der`Table` und seine Zellen. Sie können beispielsweise die`BackgroundColor` Eigenschaft von Zellen, um Hintergrundfarbe hinzuzufügen. Sie können auch die`DefaultCellBorder` -Eigenschaft der neuen Tabelle oder einzelner Zellen, um Ränder hinzuzufügen.

#### F: Hat das Ersetzen einer Tabelle Auswirkungen auf das Inhaltslayout des restlichen PDF-Dokuments?

A: Das Ersetzen einer Tabelle kann sich auf das Inhaltslayout auswirken, wenn die Größe oder Struktur der neuen Tabelle erheblich von der Originaltabelle abweicht. Der restliche Inhalt auf der Seite wird neu umbrochen, um der neuen Tabelle Platz zu bieten. Es ist wichtig, die neue Tabelle sorgfältig zu entwerfen, damit sie nahtlos in das vorhandene Layout passt und Layoutprobleme vermieden werden.