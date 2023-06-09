---
title: Austauschbare Symbole in der Kopf- und Fußzeile
linktitle: Austauschbare Symbole in der Kopf- und Fußzeile
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET austauschbare Symbole in der Kopf- und Fußzeile eines PDF-Dokuments verwenden.
type: docs
weight: 320
url: /de/net/programming-with-text/replaceable-symbols-in-header-footer/
---

In diesem Tutorial erklären wir, wie Sie mit der Aspose.PDF-Bibliothek für .NET ersetzbare Symbole in der Kopf- und Fußzeile eines PDF-Dokuments verwenden. Wir werden den Schritt-für-Schritt-Prozess zum Erstellen einer PDF-Datei, zum Festlegen von Rändern, zum Hinzufügen von Kopf- und Fußzeilen mit ersetzbaren Symbolen und zum Speichern der PDF-Datei mit dem bereitgestellten C#-Quellcode durchgehen.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Die Aspose.PDF für .NET-Bibliothek installiert.
- Ein grundlegendes Verständnis der C#-Programmierung.

## Schritt 1: Richten Sie das Dokumentenverzeichnis ein

 Zunächst müssen Sie den Pfad zu dem Verzeichnis festlegen, in dem Sie die generierte PDF-Datei speichern möchten. Ersetzen`"YOUR DOCUMENT DIRECTORY"` im`dataDir` Variable mit dem Pfad zu Ihrem gewünschten Verzeichnis.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Erstellen Sie ein PDF-Dokument und eine Seite

Als nächstes erstellen wir ein neues PDF-Dokument und fügen ihm mithilfe von eine Seite hinzu`Document` Klasse und`Page` Klasse aus der Aspose.PDF-Bibliothek.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Schritt 3: Ränder festlegen

 Wir legen die Ränder für die Seite mit fest`MarginInfo` Klasse. Passen Sie die Randwerte entsprechend Ihren Anforderungen an.

```csharp
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
page.PageInfo.Margin = marginInfo;
```

## Schritt 4: Kopfzeile mit austauschbaren Symbolen hinzufügen

 Wir erstellen ein`HeaderFooter` Objekt für die Seite und fügen Sie ein hinzu`TextFragment` mit austauschbaren Symbolen dazu.

```csharp
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;

TextFragment t1 = new TextFragment("report title");
// Legen Sie bei Bedarf Texteigenschaften fest
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t1.TextState.LineSpacing = 5f;

hfFirst.Paragraphs.Add(t1);

// Fügen Sie weitere TextFragmente hinzu oder passen Sie sie nach Bedarf an
```

## Schritt 5: Fußzeile mit austauschbaren Symbolen hinzufügen

 Ebenso erstellen wir eine`HeaderFooter` Objekt für den Seitenfuß und hinzufügen`TextFragment` Objekte mit austauschbaren Symbolen hinzufügen.

```csharp
HeaderFooter hfFoot = new HeaderFooter();
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;

TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");

// Fügen Sie weitere TextFragmente hinzu oder passen Sie sie nach Bedarf an

hfFoot.Paragraphs.Add(tab2);
```

## Schritt 6: Speichern Sie das PDF-Dokument

Abschließend speichern wir das PDF-Dokument in der angegebenen Ausgabedatei.

```csharp
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols replaced successfully in the header and footer.\nFile saved at " + dataDir);
```

### Beispielquellcode für austauschbare Symbole in der Kopf- und Fußzeile mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
//Weisen Sie die marginInfo-Instanz der Margin-Eigenschaft von sec1.PageInfo zu
page.PageInfo.Margin = marginInfo;
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;
// Instanziieren Sie einen Textabsatz, der den als Kopfzeile anzuzeigenden Inhalt speichert
TextFragment t1 = new TextFragment("report title");
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t1.TextState.LineSpacing = 5f;
hfFirst.Paragraphs.Add(t1);
TextFragment t2 = new TextFragment("Report_Name");
t2.TextState.Font = FontRepository.FindFont("Arial");
t2.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t2.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t2.TextState.LineSpacing = 5f;
t2.TextState.FontSize = 12;
hfFirst.Paragraphs.Add(t2);
// Erstellen Sie ein HeaderFooter-Objekt für den Abschnitt
HeaderFooter hfFoot = new HeaderFooter();
// Stellen Sie das HeaderFooter-Objekt auf ungerade und gerade Fußzeile ein
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;
// Fügen Sie einen Textabsatz hinzu, der die aktuelle Seitenzahl der Gesamtseitenzahl enthält
TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");
// Instanziieren Sie ein Tabellenobjekt
Table tab2 = new Table();
// Fügen Sie die Tabelle in der Absatzsammlung des gewünschten Abschnitts hinzu
hfFoot.Paragraphs.Add(tab2);
// Mit den Spaltenbreiten der Tabelle festlegen
tab2.ColumnWidths = "165 172 165";
// Erstellen Sie Zeilen in der Tabelle und dann Zellen in den Zeilen
Row row3 = tab2.Rows.Add();
row3.Cells.Add();
row3.Cells.Add();
row3.Cells.Add();
// Stellen Sie die vertikale Ausrichtung des Textes auf zentriert ein
row3.Cells[0].Alignment = Aspose.Pdf.HorizontalAlignment.Left;
row3.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
row3.Cells[2].Alignment = Aspose.Pdf.HorizontalAlignment.Right;
row3.Cells[0].Paragraphs.Add(t3);
row3.Cells[1].Paragraphs.Add(t4);
row3.Cells[2].Paragraphs.Add(t5);
//Sec1.Paragraphs.Add(New Text("Aspose.Total für Java ist eine Zusammenstellung aller von Aspose angebotenen Java-Komponenten. Es wird täglich kompiliert, um sicherzustellen, dass es jeweils die aktuellsten Versionen enthält unserer Java-Komponenten. #$NL " + "Mit Aspose.Total für Java können Entwickler eine breite Palette von Anwendungen erstellen. #$NL #$NL #$NP" + "Aspose.Total für Java ist eine Zusammenstellung aller Java-Komponenten angeboten von Aspose. Es wird täglich kompiliert, um sicherzustellen, dass es die aktuellsten Versionen jeder unserer Java-Komponenten enthält. #$NL " + "Mit Aspose.Total für Java können Entwickler eine breite Palette erstellen Anwendungsbereich. #$NL #$NL #$NP" + "Aspose.Total für Java ist eine Zusammenstellung aller von Aspose angebotenen Java-Komponenten. Es wird täglich zusammengestellt, um sicherzustellen, dass es die meisten enthält aktuelle Versionen jeder unserer Java-Komponenten. #$NL " + "Mit Aspose.Total für Java können Entwickler eine breite Palette von Anwendungen erstellen. #$NL #$NL"))
Table table = new Table();
table.ColumnWidths = "33% 33% 34%";
table.DefaultCellPadding = new MarginInfo();
table.DefaultCellPadding.Top = 10;
table.DefaultCellPadding.Bottom = 10;
// Fügen Sie die Tabelle in der Absatzsammlung des gewünschten Abschnitts hinzu
page.Paragraphs.Add(table);
// Legen Sie den Standardzellenrahmen mithilfe des BorderInfo-Objekts fest
table.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1f);
// Legen Sie den Tabellenrand mithilfe eines anderen benutzerdefinierten BorderInfo-Objekts fest
table.Border = new BorderInfo(BorderSide.All, 1f);
table.RepeatingRowsCount = 1;
// Erstellen Sie Zeilen in der Tabelle und dann Zellen in den Zeilen
Row row1 = table.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");
const string CRLF = "\r\n";
for (int i = 0; i <= 10; i++)
{
	Row row = table.Rows.Add();
	row.IsRowBroken = true;
	for (int c = 0; c <= 2; c++)
	{
		Cell c1;
		if (c == 2)
			c1 = row.Cells.Add("Aspose.Total for Java is a compilation of every Java component offered by Aspose. It is compiled on a" + CRLF + "daily basis to ensure it contains the most up to date versions of each of our Java components. " + CRLF + "daily basis to ensure it contains the most up to date versions of each of our Java components. " + CRLF + "Using Aspose.Total for Java developers can create a wide range of applications.");
		else
			c1 = row.Cells.Add("item1" + c);
		c1.Margin = new MarginInfo();
		c1.Margin.Left = 30;
		c1.Margin.Top = 10;
		c1.Margin.Bottom = 10;
	}
}
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nSymbols replaced successfully in header and footer.\nFile saved at " + dataDir);
```

## Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie mit der Aspose.PDF-Bibliothek für .NET ersetzbare Symbole in der Kopf- und Fußzeile eines PDF-Dokuments verwenden. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Code ausführen, können Sie eine PDF-Datei erstellen, Ränder festlegen, Kopf- und Fußzeilen mit ersetzbaren Symbolen hinzufügen und die PDF-Datei speichern.