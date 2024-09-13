---
title: Austauschbare Symbole in Kopf- und Fußzeile
linktitle: Austauschbare Symbole in Kopf- und Fußzeile
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET austauschbare Symbole in der Kopf- und Fußzeile eines PDF-Dokuments verwenden.
type: docs
weight: 320
url: /de/net/programming-with-text/replaceable-symbols-in-header-footer/
---
In diesem Tutorial erklären wir, wie man mithilfe der Aspose.PDF-Bibliothek für .NET austauschbare Symbole in der Kopf- und Fußzeile eines PDF-Dokuments verwendet. Wir gehen Schritt für Schritt durch den Prozess der Erstellung eines PDF-Dokuments, der Festlegung von Rändern, des Hinzufügens von Kopf- und Fußzeilen mit austauschbaren Symbolen und des Speicherns des PDF-Dokuments mithilfe des bereitgestellten C#-Quellcodes.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Die Aspose.PDF-Bibliothek für .NET ist installiert.
- Grundlegende Kenntnisse der C#-Programmierung.

## Schritt 1: Einrichten des Dokumentverzeichnisses

 Zunächst müssen Sie den Pfad zum Verzeichnis festlegen, in dem Sie die generierte PDF-Datei speichern möchten. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` im`dataDir` Variable durch den Pfad zu Ihrem gewünschten Verzeichnis.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Erstellen Sie ein PDF-Dokument und eine Seite

 Als nächstes erstellen wir ein neues PDF-Dokument und fügen ihm eine Seite hinzu mit dem`Document` Klasse und`Page` Klasse aus der Aspose.PDF-Bibliothek.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Schritt 3: Ränder festlegen

 Wir setzen die Ränder für die Seite mit dem`MarginInfo` Klasse. Passen Sie die Randwerte entsprechend Ihren Anforderungen an.

```csharp
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
page.PageInfo.Margin = marginInfo;
```

## Schritt 4: Kopfzeile mit austauschbaren Symbolen hinzufügen

 Wir schaffen eine`HeaderFooter` Objekt für die Seite und fügen Sie ein`TextFragment` mit austauschbaren Symbolen dazu.

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

 Ebenso erstellen wir eine`HeaderFooter` Objekt für die Seitenfußzeile und fügen Sie`TextFragment` Objekte mit austauschbaren Symbolen.

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

### Beispielquellcode für austauschbare Symbole in Kopf- und Fußzeilen mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
//Weisen Sie die marginInfo-Instanz der Margin-Eigenschaft von sec1.PageInfo zu.
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
// Stellen Sie das HeaderFooter-Objekt auf ungerade und gerade Fußzeilen ein
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;
// Fügen Sie einen Textabsatz mit der aktuellen Seitenzahl oder der Gesamtseitenzahl hinzu
TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");
// Instanziieren eines Tabellenobjekts
Table tab2 = new Table();
// Fügen Sie die Tabelle in die Absatzsammlung des gewünschten Abschnitts ein
hfFoot.Paragraphs.Add(tab2);
// Mit Spaltenbreiten der Tabelle festlegen
tab2.ColumnWidths = "165 172 165";
//Erstellen Sie Zeilen in der Tabelle und dann Zellen in den Zeilen
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
//Sec1.Paragraphs.Add(New Text("Aspose.Total für Java ist eine Kompilierung aller von Aspose angebotenen Java-Komponenten. Es wird täglich kompiliert, um sicherzustellen, dass es die aktuellsten Versionen aller unserer Java-Komponenten enthält. #$NL " + "Mit Aspose.Total für Java können Entwickler eine breite Palette von Anwendungen erstellen. #$NL #$NL #$NP" + "Aspose.Total für Java ist eine Kompilierung aller von Aspose angebotenen Java-Komponenten. Es wird täglich kompiliert, um sicherzustellen, dass es die aktuellsten Versionen aller unserer Java-Komponenten enthält. #$NL " + "Mit Aspose.Total für Java können Entwickler eine breite Palette von Anwendungen erstellen. #$NL #$NL #$NP" + "Aspose.Total für Java ist eine Kompilierung aller von Aspose angebotenen Java-Komponenten. Es wird täglich kompiliert, um sicherzustellen, dass es die aktuellsten Versionen aller unserer Java-Komponenten enthält. #$NL " + „Mit Aspose.Total für Java können Entwickler eine breite Palette von Anwendungen erstellen. #$NL #$NL“))
Table table = new Table();
table.ColumnWidths = "33% 33% 34%";
table.DefaultCellPadding = new MarginInfo();
table.DefaultCellPadding.Top = 10;
table.DefaultCellPadding.Bottom = 10;
// Fügen Sie die Tabelle in die Absatzsammlung des gewünschten Abschnitts ein
page.Paragraphs.Add(table);
// Festlegen des Standardzellenrahmens mithilfe des BorderInfo-Objekts
table.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1f);
// Festlegen des Tabellenrahmens mithilfe eines anderen benutzerdefinierten BorderInfo-Objekts
table.Border = new BorderInfo(BorderSide.All, 1f);
table.RepeatingRowsCount = 1;
//Erstellen Sie Zeilen in der Tabelle und dann Zellen in den Zeilen
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

In diesem Tutorial haben Sie gelernt, wie Sie mithilfe der Aspose.PDF-Bibliothek für .NET austauschbare Symbole in der Kopf- und Fußzeile eines PDF-Dokuments verwenden. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Code ausführen, können Sie ein PDF erstellen, Ränder festlegen, Kopf- und Fußzeilen mit austauschbaren Symbolen hinzufügen und das PDF speichern.

### Häufig gestellte Fragen

#### F: Was ist der Zweck des Tutorials „Austauschbare Symbole in Kopf- und Fußzeilen“?

A: Das Tutorial „Ersetzbare Symbole in Kopf- und Fußzeile“ führt Sie durch den Prozess der Verwendung der Aspose.PDF-Bibliothek für .NET, um der Kopf- und Fußzeile eines PDF-Dokuments austauschbare Symbole hinzuzufügen. Mit austauschbaren Symbolen können Sie beim Generieren des PDFs bestimmte Platzhalter dynamisch durch tatsächliche Werte ersetzen.

#### F: Was sind ersetzbare Symbole im Kontext einer PDF-Kopf- und Fußzeile?

A: Ersetzbare Symbole sind Platzhalter, die Sie in die Kopf- und Fußzeile eines PDF-Dokuments einfügen können. Diese Symbole fungieren als dynamische Platzhalter für Werte, die zur Laufzeit eingefügt werden können, wie Seitenzahlen, Daten und benutzerdefinierte Informationen.

#### F: Warum sollte ich austauschbare Symbole in einer PDF-Kopf- und Fußzeile verwenden wollen?

A: Austauschbare Symbole in der Kopf- und Fußzeile sind nützlich, wenn Sie dynamische Informationen in Ihre PDF-Dokumente aufnehmen möchten, wie etwa Seitenzahlen, Daten oder andere variable Daten, die sich beim Erstellen des Dokuments ändern können.

#### F: Wie kann ich die Ränder für die PDF-Seite festlegen?

 A: Sie können die Ränder für die PDF-Seite mit dem`MarginInfo` Klasse und ordnet sie dem`Margin` Eigentum der`PageInfo` der Seite. Passen Sie die Randwerte nach Bedarf an.

#### F: Wie füge ich austauschbare Symbole zur Kopf- und Fußzeile hinzu?

 A: Sie können austauschbare Symbole hinzufügen, indem Sie ein`HeaderFooter` Objekt für die Kopf- und Fußzeile der Seite. Anschließend können Sie`TextFragment`Objekte mit dem gewünschten Text, inklusive austauschbarer Symbole, an die`Paragraphs` Sammlung der`HeaderFooter` Objekt.

#### F: Kann ich das Erscheinungsbild der austauschbaren Symbole anpassen?

 A: Ja, Sie können das Erscheinungsbild der austauschbaren Symbole anpassen, indem Sie die Eigenschaften des`TextFragment` Objekte, die die Symbole enthalten. Sie können Eigenschaften wie Schriftart, Schriftgröße, Farbe, Ausrichtung und Zeilenabstand festlegen.

#### F: Welche Art von austauschbaren Symbolen kann ich verwenden?

A: Sie können verschiedene austauschbare Symbole verwenden, beispielsweise:

- `$p`: Aktuelle Seitenzahl.
- `$P`: Gesamtseitenzahl.
- `$d`: Aktuelles Datum.
- `$t`: Aktuelle Uhrzeit.
- Benutzerdefinierte Platzhalter, die Sie definieren.

#### F: Kann ich rund um die austauschbaren Symbole anderen Text und andere Formatierungen einfügen?

 A: Ja, Sie können anderen Text und Formatierungen um die austauschbaren Symbole herum einfügen.`TextFragment` Objekte. Dadurch können Sie komplexere Kopf- und Fußzeilen erstellen, die dynamische und statische Inhalte enthalten.

#### F: Wie kann ich das generierte PDF-Dokument speichern?

 A: Um das generierte PDF-Dokument zu speichern, können Sie den`Save` Methode der`Document`Klasse. Geben Sie den gewünschten Ausgabedateipfad und -namen als Argument an.

#### F: Ist für dieses Tutorial eine gültige Aspose-Lizenz erforderlich?

A: Ja, eine gültige Aspose-Lizenz ist erforderlich, um den Code in diesem Tutorial erfolgreich auszuführen. Sie können eine Volllizenz oder eine 30-tägige temporäre Lizenz von der Aspose-Website erhalten.