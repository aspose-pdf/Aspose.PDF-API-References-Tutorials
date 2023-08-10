---
title: Rand in PDF auf Tabelle setzen
linktitle: Rand in PDF auf Tabelle setzen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET einen Rahmen in einer PDF-Datei für eine Tabelle festlegen.
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
//Geben Sie an, dass der obere Rand doppelt sein soll
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

### FAQs

#### F: Kann ich für den oberen und unteren Rand der Tabelle unterschiedliche Rahmenstile (z. B. gestrichelt oder gepunktet) festlegen?

 A: Ja, Sie können unterschiedliche Rahmenstile für den oberen und unteren Rand der Tabelle festlegen, indem Sie die ändern`border.Top.Style` Und`border.Bottom.Style`Eigenschaften im bereitgestellten C#-Quellcode. Mit Aspose.PDF für .NET können Sie aus verschiedenen Rahmenstilen wählen, darunter einfarbig, gestrichelt, gepunktet, doppelt und mehr.

#### F: Wie kann ich die Farbe des Tabellenrandes festlegen?

 A: Sie können die Farbe des Tabellenrandes festlegen, indem Sie die ändern`border.Color` Eigenschaft im C#-Quellcode. Geben Sie einfach die gewünschte Farbe an, z`Aspose.Pdf.Color.Red` oder eine andere gültige Farbdarstellung, um die Rahmenfarbe anzupassen.

#### F: Ist es möglich, Rahmen auf einzelne Zellen innerhalb der Tabelle mit unterschiedlichen Einstellungen anzuwenden (z. B. unterschiedliche Farben oder Rahmenstile)?

 A: Ja, Sie können Rahmen auf einzelne Zellen innerhalb der Tabelle mit unterschiedlichen Einstellungen anwenden, indem Sie die konfigurieren`cell.Border` Eigenschaft für jede Zelle einzeln. Dadurch können Sie je nach Ihren Anforderungen zellspezifische Rahmenstile und -farben festlegen.

#### F: Kann ich den Rand von bestimmten Seiten der Tabelle entfernen (z. B. den linken und rechten Rand)?

 A: Ja, Sie können den Rand von bestimmten Seiten der Tabelle entfernen, indem Sie die ändern`border.Left`, `border.Right`, `border.Top` , Und`border.Bottom`Eigenschaften im C#-Quellcode. Festlegen dieser Eigenschaften auf`null` entfernt den Rand von den entsprechenden Seiten der Tabelle.

#### F: Wie kann ich die Dicke des Tabellenrandes anpassen?

 A: Sie können die Dicke des Tabellenrandes anpassen, indem Sie die ändern`border.Width` Eigenschaft im C#-Quellcode. Stellen Sie einfach die gewünschte Randbreite (in Punkt) ein, um die gewünschte Dicke zu erreichen.