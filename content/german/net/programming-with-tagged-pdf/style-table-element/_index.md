---
title: Stiltabellenelement
linktitle: Stiltabellenelement
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie Tabellenelemente mit Aspose.PDF für .NET formatieren. Schritt-für-Schritt-Anleitung zum Anpassen von Stilen und Eigenschaften.
type: docs
weight: 170
url: /de/net/programming-with-tagged-pdf/style-table-element/
---
In diesem ausführlichen Tutorial führen wir Sie Schritt für Schritt durch den bereitgestellten C#-Quellcode, um das Array-Element mit Aspose.PDF für .NET zu formatieren. Befolgen Sie die nachstehenden Anweisungen, um zu verstehen, wie Sie die Stile und Eigenschaften des Array-Elements anpassen.

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
taggedContent.SetTitle("Example of table formatting");
taggedContent.SetLanguage("fr-FR");
```

Wir haben ein neues Dokument erstellt und den Dokumenttitel und die Sprache festgelegt.

## Schritt 3: Abrufen des Stammstrukturelements

In diesem Schritt erhalten wir das Stammstrukturelement für unser Dokument.

```csharp
//Erhalten Sie das Stammstrukturelement
StructureElement rootElement = taggedContent.RootElement;
```

Wir haben das Stammstrukturelement, das als Container für das Array-Element dienen wird.

## Schritt 4: Erstellen des Array-Strukturelements

Lassen Sie uns nun ein neues Tabellenstrukturelement für unser Dokument erstellen.

```csharp
// Erstellen des Array-Strukturelements
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
```

Wir haben ein neues Array-Strukturelement erstellt und es dem Root-Strukturelement hinzugefügt.

## Schritt 5: Anpassen der Stile und Eigenschaften von Array-Elementen

In diesem Schritt passen wir die Stile und Eigenschaften des Array-Elements an.

```csharp
// Passen Sie die Stile und Eigenschaften des Array-Elements an
tableElement.BackgroundColor = Color.Beige;
tableElement.Border = new BorderInfo(BorderSide.All, 0.80F, Color.Gray);
tableElement. Alignment = HorizontalAlignment. Center;
tableElement.Broken = TableBroken.Vertical;
tableElement.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
tableElement. ColumnWidths = "80 80 80 80 80";
tableElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.DarkBlue);
tableElement. DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
tableElement.DefaultCellTextState.ForegroundColor = Color.DarkCyan;
tableElement.DefaultCellTextState.FontSize = 8F;
tableElement. DefaultColumnWidth = "70";
tableElement. IsBroken = false;
tableElement.IsBordersIncluded = true;
tableElement. Left = 0F;
tableElement. Top = 40F;
tableElement.RepeatingColumnsCount = 2;
tableElement.RepeatingRowsCount = 3;

// Passen Sie den Stil wiederholter Zeilen an
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
```

Wir haben verschiedene Eigenschaften verwendet, um das Tabellenelement anzupassen, wie etwa Hintergrundfarbe, Rahmen, Ausrichtung, Standardzellenstil, Ränder, Spaltenbreite usw.

## Schritt 6: Tabellenkopfzeilen, Textkörper und Fußzeile hinzufügen

Fügen wir nun dem Tabellenelement die Tabellenüberschriften, den Textkörper und die Fußzeile hinzu.
```csharp
// Tabellenüberschriften hinzufügen
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

// Anzahl der Zeilen und Spalten in der Tabelle
int rowCount = 10;
int colCount = 5;
int rowIndex;
int colIndex;

// Erstellen der Tabellenkopfzeile
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTHElement theElement = headTrElement.CreateTH();
     theElement.SetText(string.Format("Header {0}", colIndex));
}

//Fügen Sie die Zeilen des Tabellenkörpers hinzu
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
     TableTRElement trElement = tableTBodyElement.CreateTR();
     trElement.AlternativeText = string.Format("Row {0}", rowIndex);

     for (colIndex = 0; colIndex < colCount; colIndex++)
     {
         TableTDElement tdelement = trElement.CreateTD();
         tdElement.SetText(string.Format("Cell [{0}, {1}]", rowIndex, colIndex));
     }
}

// Fügen Sie die Fußzeile der Tabelle hinzu
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

Wir haben der Tabelle mithilfe der entsprechenden Elemente Kopf-, Text- und Fußzeilen hinzugefügt.

## Schritt 7: Speichern des getaggten PDF-Dokuments

Nachdem wir nun unser Dokument mit dem gestalteten Tabellenelement erstellt haben, speichern wir es als getaggtes PDF-Dokument.

```csharp
// Speichern des getaggten PDF-Dokuments
document.Save(dataDir + "StyleTableElement.pdf");
```

Wir haben das getaggte PDF-Dokument im angegebenen Verzeichnis gespeichert.

## Schritt 8: Validierung der PDF/UA-Konformität

Als nächstes validieren wir die PDF/UA-Konformität unseres Dokuments.

```csharp
// PDF/UA-Konformitätsprüfung
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

Wir haben das getaggte PDF-Dokument hochgeladen und seine PDF/UA-Konformität durch die Generierung eines XML-Berichts validiert.

### Beispielquellcode für Style Table Element mit Aspose.PDF für .NET 

```csharp

// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dokument erstellen
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table style");
taggedContent.SetLanguage("en-US");

// Stammstrukturelement abrufen
StructureElement rootElement = taggedContent.RootElement;

// Tabellenstrukturelement erstellen
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
tableElement.BackgroundColor = Color.Beige;
tableElement.Border = new BorderInfo(BorderSide.All, 0.80F, Color.Gray);
tableElement.Alignment = HorizontalAlignment.Center;
tableElement.Broken = TableBroken.Vertical;
tableElement.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
tableElement.ColumnWidths = "80 80 80 80 80";
tableElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.DarkBlue);
tableElement.DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
tableElement.DefaultCellTextState.ForegroundColor = Color.DarkCyan;
tableElement.DefaultCellTextState.FontSize = 8F;
tableElement.DefaultColumnWidth = "70";
tableElement.IsBroken = false;
tableElement.IsBordersIncluded = true;
tableElement.Left = 0F;
tableElement.Top = 40F;
tableElement.RepeatingColumnsCount = 2;
tableElement.RepeatingRowsCount = 3;
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 10;
int colCount = 5;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTHElement thElement = headTrElement.CreateTH();
	thElement.SetText(String.Format("Head {0}", colIndex));
}
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
	TableTRElement trElement = tableTBodyElement.CreateTR();
	trElement.AlternativeText = String.Format("Row {0}", rowIndex);
	for (colIndex = 0; colIndex < colCount; colIndex++)
	{
		TableTDElement tdElement = trElement.CreateTD();
		tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
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
document.Save(dataDir + "StyleTableElement.pdf");

// Überprüfung der PDF/UA-Konformität
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man das Array-Element mit Aspose.PDF für .NET formatiert. Wir haben die Stile und Eigenschaften des Tabellenelements angepasst, Kopfzeilen, Textzeilen und eine Fußzeile hinzugefügt, das getaggte PDF-Dokument gespeichert und seine PDF/UA-Konformität überprüft.

### Häufig gestellte Fragen

#### F: Was ist der Zweck dieses Tutorials zum Formatieren des Array-Elements mit Aspose.PDF für .NET?

A: Ziel dieses Tutorials ist es, Sie durch den Prozess der Formatierung des Array-Elements in einem PDF-Dokument mit Aspose.PDF für .NET zu führen. Es enthält schrittweise Anleitungen und C#-Quellcodebeispiele, die Ihnen dabei helfen, die Stile und Eigenschaften des Array-Elements anzupassen.

#### F: Welche Voraussetzungen müssen für die Teilnahme an diesem Tutorial erfüllt sein?

A: Stellen Sie vor dem Start sicher, dass Sie Ihre Entwicklungsumgebung für die Verwendung von Aspose.PDF für .NET eingerichtet haben. Dazu müssen Sie die Aspose.PDF-Bibliothek installieren und Ihr Projekt so konfigurieren, dass es darauf verweist.

#### F: Wie kann ich mit Aspose.PDF für .NET ein neues PDF-Dokument erstellen und dessen Titel und Sprache festlegen?

 A: Um ein neues PDF-Dokument zu erstellen, müssen Sie ein`Document` Objekt aus der Aspose.PDF-Bibliothek. Der im Tutorial bereitgestellte C#-Quellcode zeigt, wie ein Dokument erstellt und dessen Titel- und Spracheigenschaften festgelegt werden.

#### F: Welche Bedeutung hat das Stammstrukturelement in einem PDF-Dokument?

A: Das Stammstrukturelement fungiert als Container für andere Strukturelemente und hilft dabei, den Inhalt des PDF-Dokuments zu organisieren und zu kategorisieren. Es spielt eine entscheidende Rolle bei der Erstellung der logischen Struktur des Dokuments.

#### F: Wie erstelle und passe ich ein Array-Strukturelement mit Aspose.PDF für .NET an?

 A: Sie können ein Array-Strukturelement erstellen mit dem`CreateTableElement()` Methode. Der Quellcode des Tutorials enthält Beispiele zum Anpassen verschiedener Eigenschaften des Tabellenelements, wie Hintergrundfarbe, Rahmen, Ausrichtung, Spaltenbreite und mehr.

#### F: Kann ich die Stile und Eigenschaften von Tabellenzellen innerhalb des Array-Elements anpassen?

A: Ja, das Tutorial beschreibt, wie Sie die Stile und Eigenschaften des gesamten Tabellenelements anpassen, einschließlich Kopfzeilen, Textzeilen und Fußzeilen. Es geht jedoch nicht speziell auf die Anpassung einzelner Tabellenzellen ein.

#### F: Wie kann ich dem Tabellenelement Kopfzeilen, Textzeilen und eine Fußzeile hinzufügen?

A: Das Tutorial erklärt, wie Sie mit den entsprechenden Methoden von Aspose.PDF für .NET Kopfzeilen, Textzeilen und eine Fußzeile zum Tabellenelement erstellen und hinzufügen.

#### F: Was ist PDF/UA-Konformität und wie kann ich sie für mein getaggtes PDF-Dokument validieren?

 A: Die PDF/UA-Konformität stellt sicher, dass das PDF-Dokument den Zugänglichkeitsstandards entspricht und somit für Benutzer mit Behinderungen zugänglicher ist. Das Tutorial zeigt, wie Sie die PDF/UA-Konformität mithilfe des`Validate()` Methode und generieren Sie einen XML-Konformitätsbericht.

#### F: Wie kann ich diese Konzepte in meine eigenen .NET-Anwendungen integrieren?

A: Sie können die bereitgestellten C#-Quellcodebeispiele als Leitfaden zur Implementierung der Array-Elementformatierung in Ihren eigenen .NET-Anwendungen verwenden. Ändern und passen Sie den Code Ihren Anforderungen entsprechend an und integrieren Sie ihn in Ihre Projekte.

#### F: Gibt es empfohlene Best Practices zum Formatieren von Array-Elementen in PDF-Dokumenten?

A: Berücksichtigen Sie beim Formatieren von Array-Elementen (Tabellen) die Lesbarkeit und Zugänglichkeit des Inhalts. Verwenden Sie klare und lesbare Schriftarten, geeignete Farben und achten Sie auf ein einheitliches Layout. Überprüfen Sie die PDF/UA-Konformität, um sicherzustellen, dass die Zugänglichkeitsstandards eingehalten werden.

#### F: Welche anderen Funktionen von Aspose.PDF für .NET kann ich zur Anpassung von PDF-Dokumenten erkunden?

A: Aspose.PDF für .NET bietet eine Reihe von Funktionen zur Anpassung von PDF-Dokumenten, darunter Textbearbeitung, Bildeinfügung, Formularfeldverwaltung, digitale Signaturen, Anmerkungen und mehr. Weitere Funktionen finden Sie in der offiziellen Dokumentation und den Ressourcen.