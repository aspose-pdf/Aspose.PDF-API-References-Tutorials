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
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Dokumentenerstellung
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example of table formatting");
taggedContent.SetLanguage("fr-FR");
```

Wir haben ein neues Dokument erstellt und den Dokumenttitel und die Sprache festgelegt.

## Schritt 3: Erhalten des Wurzelstrukturelements

In diesem Schritt erhalten wir das Stammstrukturelement für unser Dokument.

```csharp
//Rufen Sie das Wurzelstrukturelement ab
StructureElement rootElement = taggedContent.RootElement;
```

Wir haben das Wurzelstrukturelement erhalten, das als Container für das Array-Element dient.

## Schritt 4: Erstellen des Array-Strukturelements

Jetzt erstellen wir ein neues Tabellenstrukturelement für unser Dokument.

```csharp
// Erstellen Sie das Array-Strukturelement
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

// Passen Sie den Stil wiederholter Linien an
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
```

Wir haben verschiedene Eigenschaften verwendet, um das Tabellenelement anzupassen, wie z. B. Hintergrundfarbe, Rahmen, Ausrichtung, Standardzellenstil, Ränder, Spaltenbreite usw.

## Schritt 6: Fügen Sie Tabellenkopfzeilen, -text und -fußzeile hinzu

Fügen wir nun die Tabellenkopfzeilen, den Hauptteil und die Fußzeile zum Tabellenelement hinzu.
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

// Erstellen Sie die Tabellenkopfzeile
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

Wir haben die Kopfzeilen, Hauptzeilen und Fußzeilen mithilfe der entsprechenden Elemente zur Tabelle hinzugefügt.

## Schritt 7: Speichern des getaggten PDF-Dokuments

Nachdem wir unser Dokument nun mit dem gestalteten Tabellenelement erstellt haben, speichern wir es als getaggtes PDF-Dokument.

```csharp
// Speichern Sie das getaggte PDF-Dokument
document.Save(dataDir + "StyleTableElement.pdf");
```

Wir haben das getaggte PDF-Dokument im angegebenen Verzeichnis gespeichert.

## Schritt 8: Validierung der PDF/UA-Konformität

Als nächstes validieren wir die PDF/UA-Konformität unseres Dokuments.

```csharp
// Prüfung der PDF/UA-Konformität
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

Wir haben das getaggte PDF-Dokument hochgeladen und seine PDF/UA-Konformität durch die Erstellung eines XML-Berichts validiert.

### Beispielquellcode für Style Table Element mit Aspose.PDF für .NET 

```csharp

// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dokument erstellen
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table style");
taggedContent.SetLanguage("en-US");

// Stammstrukturelement abrufen
StructureElement rootElement = taggedContent.RootElement;

// Erstellen Sie ein Tabellenstrukturelement
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

// Markiertes PDF-Dokument speichern
document.Save(dataDir + "StyleTableElement.pdf");

// Überprüfung der PDF/UA-Konformität
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man das Array-Element mit Aspose.PDF für .NET formatiert. Wir haben die Stile und Eigenschaften des Tabellenelements angepasst, Kopfzeilen, Hauptzeilen und eine Fußzeile hinzugefügt, das getaggte PDF-Dokument gespeichert und seine PDF/UA-Konformität validiert.

### FAQs

#### F: Was ist der Zweck dieses Tutorials zum Formatieren des Array-Elements mit Aspose.PDF für .NET?

A: Ziel dieses Tutorials ist es, Sie durch den Prozess der Formatierung des Array-Elements in einem PDF-Dokument mit Aspose.PDF für .NET zu führen. Es enthält Schritt-für-Schritt-Anleitungen und C#-Quellcodebeispiele, die Ihnen beim Anpassen der Stile und Eigenschaften des Array-Elements helfen.

#### F: Was sind die Voraussetzungen, um diesem Tutorial zu folgen?

A: Bevor Sie beginnen, stellen Sie sicher, dass Sie Ihre Entwicklungsumgebung für die Verwendung von Aspose.PDF für .NET eingerichtet haben. Dazu müssen Sie die Aspose.PDF-Bibliothek installieren und Ihr Projekt so konfigurieren, dass es darauf verweist.

#### F: Wie kann ich mit Aspose.PDF für .NET ein neues PDF-Dokument erstellen und dessen Titel und Sprache festlegen?

 A: Um ein neues PDF-Dokument zu erstellen, müssen Sie ein erstellen`Document` Objekt aus der Aspose.PDF-Bibliothek. Der im Tutorial bereitgestellte C#-Quellcode zeigt, wie ein Dokument erstellt und dessen Titel und Spracheigenschaften festgelegt werden.

#### F: Welche Bedeutung hat das Stammstrukturelement in einem PDF-Dokument?

A: Das Stammstrukturelement fungiert als Container für andere Strukturelemente und hilft dabei, den Inhalt des PDF-Dokuments zu organisieren und zu kategorisieren. Es spielt eine entscheidende Rolle bei der Festlegung der logischen Struktur des Dokuments.

#### F: Wie erstelle und passe ich ein Array-Strukturelement mit Aspose.PDF für .NET an?

 A: Sie können ein Array-Strukturelement mit erstellen`CreateTableElement()` Methode. Der Quellcode des Tutorials enthält Beispiele für die Anpassung verschiedener Eigenschaften des Tabellenelements, wie z. B. Hintergrundfarbe, Rahmen, Ausrichtung, Spaltenbreite und mehr.

#### F: Kann ich die Stile und Eigenschaften von Tabellenzellen innerhalb des Array-Elements anpassen?

A: Ja, das Tutorial behandelt, wie Sie die Stile und Eigenschaften des gesamten Tabellenelements anpassen, einschließlich Kopfzeilen, Textzeilen und Fußzeilen. Es wird jedoch nicht speziell auf das Anpassen einzelner Tabellenzellen eingegangen.

#### F: Wie kann ich dem Tabellenelement Kopfzeilen, Hauptzeilen und eine Fußzeile hinzufügen?

A: Das Tutorial erklärt, wie man mit den entsprechenden Methoden von Aspose.PDF für .NET Kopfzeilen, Hauptzeilen und eine Fußzeile erstellt und zum Tabellenelement hinzufügt.

#### F: Was ist PDF/UA-Konformität und wie kann ich sie für mein getaggtes PDF-Dokument validieren?

 A: Durch die PDF/UA-Konformität wird sichergestellt, dass das PDF-Dokument den Barrierefreiheitsstandards entspricht, sodass es für Benutzer mit Behinderungen leichter zugänglich ist. Das Tutorial zeigt, wie Sie die PDF/UA-Konformität mithilfe von validieren`Validate()` Methode und generieren Sie einen XML-Compliance-Bericht.

#### F: Wie kann ich diese Konzepte in meine eigenen .NET-Anwendungen integrieren?

A: Sie können die bereitgestellten C#-Quellcodebeispiele als Leitfaden für die Implementierung der Array-Elementformatierung in Ihren eigenen .NET-Anwendungen verwenden. Ändern und passen Sie den Code an Ihre Anforderungen an und integrieren Sie ihn in Ihre Projekte.

#### F: Gibt es empfohlene Best Practices für die Formatierung von Array-Elementen in PDF-Dokumenten?

A: Berücksichtigen Sie beim Formatieren von Array-Elementen (Tabellen) die Lesbarkeit und Zugänglichkeit des Inhalts. Verwenden Sie klare und lesbare Schriftarten, geeignete Farben und achten Sie auf ein einheitliches Layout. Validieren Sie die PDF/UA-Konformität, um sicherzustellen, dass die Barrierefreiheitsstandards eingehalten werden.

#### F: Welche anderen Funktionen von Aspose.PDF für .NET kann ich für die Anpassung von PDF-Dokumenten erkunden?

A: Aspose.PDF für .NET bietet eine Reihe von Funktionen zur Anpassung von PDF-Dokumenten, darunter Textbearbeitung, Bildeinfügung, Formularfeldverwaltung, digitale Signaturen, Anmerkungen und mehr. Konsultieren Sie die offizielle Dokumentation und Ressourcen, um zusätzliche Funktionen zu erkunden.