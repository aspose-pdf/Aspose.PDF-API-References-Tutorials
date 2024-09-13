---
title: Tabellenzelle formatieren
linktitle: Tabellenzelle formatieren
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie Tabellenzellen mit Aspose.PDF für .NET formatieren. Schritt-für-Schritt-Anleitung zum Erstellen und Anpassen von Tabellen.
type: docs
weight: 160
url: /de/net/programming-with-tagged-pdf/style-table-cell/
---
Willkommen zu diesem ausführlichen Tutorial zum Formatieren von Tabellenzellen mit Aspose.PDF für .NET. In dieser Anleitung erklären wir jeden Schritt des bereitgestellten C#-Quellcodes im Detail, damit Sie verstehen, wie Sie Tabellenzellen formatieren. Stellen Sie sicher, dass Sie Aspose.PDF für .NET installiert und Ihre Entwicklungsumgebung eingerichtet haben, bevor Sie beginnen.

## Schritt 1: Einrichten der Umgebung

Bevor Sie beginnen, stellen Sie sicher, dass Sie Ihre Entwicklungsumgebung für die Verwendung von Aspose.PDF für .NET konfiguriert haben. Dazu gehört die Installation der Aspose.PDF-Bibliothek und die Konfiguration Ihres Projekts, um darauf zu verweisen.

## Schritt 2: Erstellen eines Dokuments

In diesem Schritt erstellen wir ein neues Dokumentobjekt Aspose.PDF.

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Dokumenterstellung
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example of table cell formatting");
taggedContent.SetLanguage("fr-FR");
```

Wir haben ein neues Dokument erstellt und den Dokumenttitel und die Sprache festgelegt.

## Schritt 3: Abrufen des Stammstrukturelements

In diesem Schritt erhalten wir das Stammstrukturelement für unser Dokument.

```csharp
// Erhalten Sie das Stammstrukturelement
StructureElement rootElement = taggedContent.RootElement;
```

Wir haben das Stammstrukturelement, das als Container für die Array-Elemente dient.

## Schritt 4: Erstellen des Array-Strukturelements

Lassen Sie uns nun ein neues Tabellenstrukturelement für unser Dokument erstellen.

```csharp
// Erstellen des Array-Strukturelements
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

Wir haben ein neues Array-Strukturelement erstellt und es dem Stammstrukturelement hinzugefügt. Außerdem haben wir die Tabellenkopf-, -text- und -fußzeilenelemente erstellt.

## Schritt 5: Tabellenüberschriften hinzufügen

In diesem Schritt fügen wir unserer Tabelle die Tabellenüberschriften hinzu.

```csharp
// Anzahl der Zeilen und Spalten in der Tabelle
int rowCount = 4;
int colCount = 4;

int rowIndex;
int colIndex;

// Erstellen der Tabellenkopfzeile
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTHElement theElement = headTrElement.CreateTH();
     theElement.SetText(string.Format("Header {0}", colIndex));
     theElement.BackgroundColor = Color.GreenYellow;
     theElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
     theElement. IsNoBorder = true;
     theElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
     theElement.Alignment = HorizontalAlignment.Right;
}
```

Wir haben eine Kopfzeile für unsere Tabelle erstellt und Kopfzellen mit Formatierungseigenschaften wie Hintergrundfarbe, Rahmen, Rändern und Ausrichtung hinzugefügt.

## Schritt 6: Hinzufügen der Zeilen des Tabellenkörpers

Fügen wir nun die Tabellentextzeilen zu unserer Tabelle hinzu.
```csharp
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
     TableTRElement trElement = tableTBodyElement.CreateTR();
     trElement.AlternativeText = string.Format("Row {0}", rowIndex);

     for (colIndex = 0; colIndex < colCount; colIndex++)
     {
         int colSpan = 1;
         int rowSpan = 1;

         if (colIndex == 1 && rowIndex == 1)
         {
             colSpan = 2;
             rowSpan = 2;
         }
         else if (colIndex == 2 && (rowIndex == 1 || rowIndex == 2))
         {
             keep on going;
         }
         else if (rowIndex == 2 && (colIndex == 1 || colIndex == 2))
         {
             keep on going;
         }

         TableTDElement tdelement = trElement.CreateTD();
         tdElement.SetText(string.Format("Cell [{0}, {1}]", rowIndex, colIndex));
         tdElement.BackgroundColor = Color.Yellow;
         tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
         tdElement.IsNoBorder = false;
         tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
         tdElement.Alignment = HorizontalAlignment.Center;

         TextState cellTextState = new TextState();
         cellTextState.ForegroundColor = Color.DarkBlue;
         cellTextState.FontSize = 7.5F;
         cellTextState.FontStyle = FontStyles.Bold;
         cellTextState.Font = FontRepository.FindFont("Arial");

         tdElement. DefaultCellTextState = cellTextState;
         tdElement.IsWordWrapped = true;
         tdElement.VerticalAlignment = VerticalAlignment.Center;
         tdElement.ColSpan = colSpan;
         tdElement. RowSpan = rowSpan;
     }
}
```

Wir haben dem Hauptteil der Tabelle Zeilen hinzugefügt, indem wir Schleifen verwendet haben, um über jede Tabellenzelle zu iterieren. Wir haben für jede Zelle Formatierungseigenschaften festgelegt, wie z. B. Hintergrundfarbe, Rahmen, Ränder, Textausrichtung usw.

## Schritt 7: Fußzeile hinzufügen

Zum Schluss fügen wir unserer Tabelle den Tabellenfuß hinzu.

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

Wir haben eine Fußzeile für unsere Tabelle erstellt und Fußzeilenzellen mit Text hinzugefügt.



## Schritt 8: Speichern des getaggten PDF-Dokuments

Nachdem wir nun unser Dokument mit der formatierten Tabelle erstellt haben, speichern wir es als getaggtes PDF-Dokument.

```csharp
// Speichern des getaggten PDF-Dokuments
document.Save(dataDir + "StyleTableCell.pdf");
```

Wir haben das getaggte PDF-Dokument im angegebenen Verzeichnis gespeichert.

## Schritt 9: Validierung der PDF/UA-Konformität

Als nächstes validieren wir die PDF/UA-Konformität unseres Dokuments.

```csharp
// PDF/UA-Konformitätsprüfung
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

Wir haben das getaggte PDF-Dokument hochgeladen und seine PDF/UA-Konformität durch die Generierung eines XML-Berichts validiert.

### Beispiel-Quellcode für Style Table Cell mit Aspose.PDF für .NET 
```csharp

// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dokument erstellen
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table cell style");
taggedContent.SetLanguage("en-US");

// Stammstrukturelement abrufen
StructureElement rootElement = taggedContent.RootElement;

// Tabellenstrukturelement erstellen
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 4;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTHElement thElement = headTrElement.CreateTH();
	thElement.SetText(String.Format("Head {0}", colIndex));
	thElement.BackgroundColor = Color.GreenYellow;
	thElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
	thElement.IsNoBorder = true;
	thElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
	thElement.Alignment = HorizontalAlignment.Right;
}
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
	TableTRElement trElement = tableTBodyElement.CreateTR();
	trElement.AlternativeText = String.Format("Row {0}", rowIndex);
	for (colIndex = 0; colIndex < colCount; colIndex++)
	{
		int colSpan = 1;
		int rowSpan = 1;
		if (colIndex == 1 && rowIndex == 1)
		{
			colSpan = 2;
			rowSpan = 2;
		}
		else if (colIndex == 2 && (rowIndex == 1 || rowIndex == 2))
		{
			continue;
		}
		else if (rowIndex == 2 && (colIndex == 1 || colIndex == 2))
		{
			continue;
		}
		TableTDElement tdElement = trElement.CreateTD();
		tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
		tdElement.BackgroundColor = Color.Yellow;
		tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
		tdElement.IsNoBorder = false;
		tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
		tdElement.Alignment = HorizontalAlignment.Center;
		TextState cellTextState = new TextState();
		cellTextState.ForegroundColor = Color.DarkBlue;
		cellTextState.FontSize = 7.5F;
		cellTextState.FontStyle = FontStyles.Bold;
		cellTextState.Font = FontRepository.FindFont("Arial");
		tdElement.DefaultCellTextState = cellTextState;
		tdElement.IsWordWrapped = true;
		tdElement.VerticalAlignment = VerticalAlignment.Center;
		tdElement.ColSpan = colSpan;
		tdElement.RowSpan = rowSpan;
	}
}
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTDElement tdElement = footTrElement.CreateTD();
	tdElement.SetText(String.Format("Foot {0}", colIndex));
}

// Getaggtes PDF-Dokument speichern
document.Save(dataDir + "StyleTableCell.pdf");

// Überprüfung der PDF/UA-Konformität
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man Tabellenzellen mit Aspose.PDF für .NET formatiert. Wir haben gesehen, wie man ein Dokument erstellt, eine Tabelle mit Kopfzeilen, Textzeilen und Fußzeilen hinzufügt und Zellenformate anpasst. Abschließend haben wir das getaggte PDF-Dokument gespeichert und seine PDF/UA-Konformität überprüft. Sie können jetzt Aspose.PDF für .NET verwenden, um Tabellen in Ihren .NET-Anwendungen zu erstellen und zu formatieren.

### Häufig gestellte Fragen

#### F: Was ist der Zweck dieses Tutorials zum Formatieren von Tabellenzellen mit Aspose.PDF für .NET?

A: Dieses Tutorial soll eine umfassende Anleitung zum Formatieren von Tabellenzellen in einem PDF-Dokument mithilfe der Aspose.PDF-Bibliothek für .NET bieten. Es enthält schrittweise Anleitungen und C#-Quellcodebeispiele, die Ihnen dabei helfen, die Formatierung von Tabellenzellen zu verstehen und umzusetzen.

#### F: Welche Voraussetzungen müssen für die Teilnahme an diesem Tutorial erfüllt sein?

A: Bevor Sie beginnen, stellen Sie sicher, dass Sie Aspose.PDF für .NET installiert und Ihre Entwicklungsumgebung eingerichtet haben. Dazu gehört die Konfiguration Ihres Projekts, um auf die Aspose.PDF-Bibliothek zu verweisen.

#### F: Wie erstelle ich mit Aspose.PDF für .NET ein neues PDF-Dokument?

 A: Um ein neues PDF-Dokument zu erstellen, müssen Sie eine`Document` Objekt aus der Aspose.PDF-Bibliothek. Der bereitgestellte C#-Quellcode zeigt, wie ein Dokument erstellt und dessen Titel und Sprache festgelegt wird.

#### F: Welche Bedeutung hat das Stammstrukturelement in einem PDF-Dokument?

A: Das Stammstrukturelement dient als Container für andere Strukturelemente und hilft dabei, den Inhalt des PDF-Dokuments zu organisieren und zu kategorisieren. Es spielt eine entscheidende Rolle bei der Erstellung der logischen Struktur des Dokuments.

#### F: Wie kann ich mit Aspose.PDF für .NET ein Tabellenstrukturelement erstellen und sein Erscheinungsbild anpassen?

 A: Sie können ein Tabellenstrukturelement erstellen, indem Sie`CreateTableElement()` Methode. Der bereitgestellte Quellcode zeigt, wie Sie das Erscheinungsbild der Tabelle (einschließlich Kopf-, Text- und Fußzeile) anpassen können, indem Sie Eigenschaften wie Hintergrundfarbe, Rahmen, Ränder und Ausrichtung festlegen.

#### F: Kann ich dem Tabellenkörper mehrere Zeilen und Spalten hinzufügen und deren Formatierung anpassen?

A: Ja, das Tutorial zeigt, wie Sie mithilfe von Schleifen mehrere Zeilen und Spalten zum Tabellenkörper hinzufügen. Es enthält auch Beispiele zum Anpassen der Zellenformatierung, wie Hintergrundfarbe, Rahmen, Textausrichtung, Schriftstil und mehr.

#### F: Was ist der Zweck der Validierung der PDF/UA-Konformität und wie kann ich diese Validierung durchführen?

 A: Durch die Validierung der PDF/UA-Konformität wird sichergestellt, dass das PDF-Dokument den Zugänglichkeitsstandards entspricht und somit für Benutzer mit Behinderungen besser zugänglich ist. Das Tutorial zeigt, wie Sie die PDF/UA-Konformität mithilfe des`Validate()` Methode und generieren Sie einen XML-Bericht.

#### F: Wie kann ich diese Konzepte auf meine eigenen .NET-Anwendungen anwenden?

A: Sie können die bereitgestellten C#-Quellcodebeispiele als Leitfaden zur Implementierung der Tabellenzellenformatierung in Ihren eigenen .NET-Anwendungen verwenden. Passen Sie den Code nach Bedarf an Ihre Anforderungen an und integrieren Sie ihn in Ihre Projekte.

#### F: Gibt es empfohlene Best Practices zum Formatieren von Tabellenzellen in PDF-Dokumenten?

A: Berücksichtigen Sie beim Gestalten von Tabellenzellen die Bedürfnisse Ihrer Zielgruppe, einschließlich der Zugänglichkeitsanforderungen. Verwenden Sie kontrastierende Farben, geeignete Schriftarten und eine klare Zellenausrichtung, um die Lesbarkeit zu verbessern. Überprüfen Sie außerdem die PDF/UA-Konformität, um sicherzustellen, dass die Zugänglichkeitsstandards eingehalten werden.

#### F: Welche anderen Funktionen von Aspose.PDF für .NET kann ich zur Bearbeitung von PDF-Dokumenten erkunden?

A: Aspose.PDF für .NET bietet eine breite Palette an Funktionen zur Bearbeitung von PDF-Dokumenten, darunter Textextraktion, Bildeinfügung, Formularfeldverwaltung, digitale Signaturen und mehr. Erkunden Sie die offizielle Dokumentation und Ressourcen, um mehr über zusätzliche Funktionen zu erfahren.
