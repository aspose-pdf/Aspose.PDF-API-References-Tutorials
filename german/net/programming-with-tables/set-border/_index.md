---
title: Rand festlegen
linktitle: Rand festlegen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET einen Rahmen in einer PDF-Tabelle festlegen.
type: docs
weight: 200
url: /de/net/programming-with-tables/set-border/
---

In diesem Tutorial führen wir Sie Schritt für Schritt durch das Festlegen eines Rahmens in einer Tabelle eines PDF-Dokuments mit Aspose.PDF für .NET. Wir erklären Ihnen den bereitgestellten C#-Quellcode und zeigen Ihnen, wie Sie ihn implementieren.

## Schritt 1: Instanziieren des Document-Objekts
Zuerst instanziieren wir ein Document-Objekt:

```csharp
Document doc = new Document();
```

## Schritt 2: Hinzufügen einer Seite zum PDF-Dokument
Als Nächstes fügen wir dem PDF-Dokument eine Seite hinzu:

```csharp
Page page = doc.Pages.Add();
```

## Schritt 3: Erstellen des BorderInfo-Objekts
Wir erstellen nun ein BorderInfo-Objekt, um den Rand der Tabelle zu definieren:

```csharp
Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
```

## Schritt 4: Oberen und unteren Rand festlegen
Wir legen fest, dass die oberen und unteren Ränder doppelt sein werden:

```csharp
border.Top.IsDoubled = true;
border.Bottom.IsDoubled = true;
```

## Schritt 5: Instanziieren des Table-Objekts
Lassen Sie uns nun ein Table-Objekt instanziieren:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

## Schritt 6: Spaltenbreiten angeben
Wir geben die Breite der Spalten der Tabelle an:

```csharp
table. ColumnWidths = "100";
```

## Schritt 7: Erstellen des Zeilenobjekts
Wir erstellen ein Row-Objekt:

```csharp
Aspose.Pdf.Row row = table.Rows.Add();
```

## Schritt 8: Hinzufügen einer Zelle zur Zeile
Als Nächstes fügen wir der Zeile eine Zelle hinzu:

```csharp
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
```

## Schritt 9: Festlegen des Zellrandes
Wir werden den Rand der Zelle definieren (doppelter Rand):

```csharp
cell. Border = border;
```

## Schritt 10: Hinzufügen der Tabelle zur Seite
Fügen wir nun die Tabelle zur Dokumentseite hinzu:

```csharp
page.Paragraphs.Add(table);
```

## Schritt 11: PDF-Dokument speichern
Abschließend speichern wir das PDF-Dokument:

```csharp
dataDir = dataDir + "TableBorderTest_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nBorder setup successfully.\nFile saved at " + dataDir);
```

### Beispielquellcode für Set Border mit Aspose.PDF für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dokumentobjekt instanziieren
Document doc = new Document();
// Seite zum PDF-Dokument hinzufügen
Page page = doc.Pages.Add();
// Erstellen Sie ein BorderInfo-Objekt
Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
// Geben Sie an, dass der obere Rand doppelt sein soll
border.Top.IsDoubled = true;
// Geben Sie an, dass der untere Rand doppelt sein soll
border.Bottom.IsDoubled = true;
// Instanziieren Sie ein Tabellenobjekt
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Geben Sie Informationen zur Spaltenbreite an
table.ColumnWidths = "100";
// Erstellen Sie ein Zeilenobjekt
Aspose.Pdf.Row row = table.Rows.Add();
// Fügen Sie der Zellensammlung der Zeile eine Tabellenzelle hinzu
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
// Legen Sie den Rahmen für das Zellobjekt fest (doppelter Rahmen).
cell.Border = border;
// Fügen Sie der Absatzsammlung von Page eine Tabelle hinzu
page.Paragraphs.Add(table);
dataDir = dataDir + "TableBorderTest_out.pdf";
// Speichern Sie das PDF-Dokument
doc.Save(dataDir);

Console.WriteLine("\nBorder setup successfully.\nFile saved at " + dataDir);
```

## Abschluss
Herzlichen Glückwunsch! Sie haben nun gelernt, wie Sie mit Aspose.PDF für .NET einen Rahmen in einer Tabelle eines PDF-Dokuments festlegen. Diese Schritt-für-Schritt-Anleitung zeigte Ihnen, wie Sie ein Dokument erstellen, eine Seite hinzufügen, den Tabellenrahmen konfigurieren und das PDF-Dokument speichern. Jetzt können Sie dieses Wissen auf Ihre eigenen Projekte anwenden.