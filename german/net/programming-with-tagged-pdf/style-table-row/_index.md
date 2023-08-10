---
title: Stiltabellenzeile
linktitle: Stiltabellenzeile
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie Schritt für Schritt, wie Sie Tabellenzeilen mit Aspose.PDF für .NET anpassen und Zeilen formatieren und formatieren.
type: docs
weight: 180
url: /de/net/programming-with-tagged-pdf/style-table-row/
---
In diesem ausführlichen Tutorial führen wir Sie Schritt für Schritt durch den bereitgestellten C#-Quellcode, um die Tabellenzeile mit Aspose.PDF für .NET zu formatieren. Befolgen Sie die nachstehenden Anweisungen, um zu verstehen, wie Sie Tabellenzeilenstile und -eigenschaften anpassen.

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
taggedContent.SetTitle("Example of Table Row Formatting");
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

## Schritt 5: Passen Sie Tabellenzeilenstile und -eigenschaften an

In diesem Schritt passen wir die Tabellenzeilenstile und -eigenschaften an.

```csharp
// Passen Sie Tabellenzeilenstile und -eigenschaften an
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

int rowCount = 7;
int colCount = 3;
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

// Passen Sie die Zeilen des Tabellenkörpers an
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
     TableTRElement trElement = tableTBodyElement.CreateTR();
     trElement.AlternativeText = string.Format("Row {0}", rowIndex);
     trElement.BackgroundColor = Color.LightGoldenrodYellow;
     trElement.Border = new BorderInfo(BorderSide.All, 0.75F, Color.DarkGray);
     trElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.Blue);
     trElement.MinRowHeight = 100.0;
     trElement.FixedRowHeight = 120.0;
     trElement. IsInNewPage = (rowIndex % 3 == 1);
     trElement.IsRowBroken = true;
     TextState cellTextState = new TextState();
     cellTextState.ForegroundColor = Color.Red;
     trElement. DefaultCellTextState = cellTextState;
     trElement. DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
     trElement.VerticalAlignment = VerticalAlignment.Bottom;

     for (colIndex = 0; colIndex < colCount; colIndex++)
     {
         TableTDElement tdelement = trElement.CreateTD();
         tdElement.SetText(string.Format("Cell [{0}, {1}]", rowIndex, colIndex));
     }
}

// Erstellen Sie die Fußzeile der Tabelle
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

Wir haben verschiedene Aspekte der Tabellenzeile angepasst, z. B. Hintergrundfarbe, Rahmen, Zeilenhöhe, Paginierung, Standardzellenstil und mehr.

## Schritt 6: Speichern des getaggten PDF-Dokuments

Nachdem wir nun unser Dokument mit der formatierten Tabellenzeile erstellt haben, speichern wir es als getaggtes PDF-Dokument.
```csharp
// Speichern Sie das getaggte PDF-Dokument
document.Save(dataDir + "StyleTableRow.pdf");
```

Wir haben das getaggte PDF-Dokument im angegebenen Verzeichnis gespeichert.

## Schritt 7: PDF/UA-Konformitätsvalidierung

Als nächstes validieren wir die PDF/UA-Konformität unseres Dokuments.

```csharp
// Prüfung der PDF/UA-Konformität
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

Wir haben das getaggte PDF-Dokument hochgeladen und seine PDF/UA-Konformität durch die Erstellung eines XML-Berichts validiert.


### Beispielquellcode für Style Table Row mit Aspose.PDF für .NET 
```csharp

// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dokument erstellen
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table row style");
taggedContent.SetLanguage("en-US");

// Stammstrukturelement abrufen
StructureElement rootElement = taggedContent.RootElement;

// Erstellen Sie ein Tabellenstrukturelement
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 7;
int colCount = 3;
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
	trElement.BackgroundColor = Color.LightGoldenrodYellow;
	trElement.Border = new BorderInfo(BorderSide.All, 0.75F, Color.DarkGray);
	trElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.Blue);
	trElement.MinRowHeight = 100.0;
	trElement.FixedRowHeight = 120.0;
	trElement.IsInNewPage = (rowIndex % 3 == 1);
	trElement.IsRowBroken = true;
	TextState cellTextState = new TextState();
	cellTextState.ForegroundColor = Color.Red;
	trElement.DefaultCellTextState = cellTextState;
	trElement.DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
	trElement.VerticalAlignment = VerticalAlignment.Bottom;
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
document.Save(dataDir + "StyleTableRow.pdf");

// Überprüfung der PDF/UA-Konformität
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man Tabellenzeilen mit Aspose.PDF für .NET formatiert. Wir haben die Stile und Eigenschaften der Tabellenzeilen angepasst, die Kopfzeilen, Hauptzeilen und Fußzeilen hinzugefügt, das getaggte PDF-Dokument gespeichert und seine PDF/UA-Konformität validiert.

### FAQs

#### F: Was ist der Zweck dieses Tutorials zum Formatieren von Tabellenzeilen mit Aspose.PDF für .NET?

A: Der Zweck dieses Tutorials besteht darin, Sie durch den Prozess der Formatierung von Tabellenzeilen in einem PDF-Dokument mit Aspose.PDF für .NET zu führen. Es enthält Schritt-für-Schritt-Anleitungen und C#-Quellcode-Beispiele, die Sie bei der Anpassung von Tabellenzeilenstilen und -eigenschaften unterstützen.

#### F: Was sind die Voraussetzungen, um diesem Tutorial zu folgen?

A: Bevor Sie beginnen, stellen Sie sicher, dass Sie Ihre Entwicklungsumgebung für die Verwendung von Aspose.PDF für .NET eingerichtet haben. Dazu müssen Sie die Aspose.PDF-Bibliothek installieren und Ihr Projekt so konfigurieren, dass es darauf verweist.

#### F: Wie kann ich mit Aspose.PDF für .NET ein neues PDF-Dokument erstellen und dessen Titel und Sprache festlegen?

 A: Um ein neues PDF-Dokument zu erstellen, müssen Sie ein erstellen`Document` Objekt aus der Aspose.PDF-Bibliothek. Der im Tutorial bereitgestellte C#-Quellcode zeigt, wie ein Dokument erstellt und dessen Titel und Spracheigenschaften festgelegt werden.

#### F: Welche Bedeutung hat das Stammstrukturelement in einem PDF-Dokument?

A: Das Stammstrukturelement fungiert als Container für andere Strukturelemente und hilft dabei, den Inhalt des PDF-Dokuments zu organisieren und zu kategorisieren. Es spielt eine entscheidende Rolle bei der Festlegung der logischen Struktur des Dokuments.

#### F: Wie erstelle und passe ich ein Tabellenstrukturelement an, um Tabellenzeilen mit Aspose.PDF für .NET zu formatieren?

A: Das Tutorial erklärt, wie man ein Tabellenstrukturelement erstellt und seine Eigenschaften anpasst, um Tabellenzeilen zu formatieren. Es deckt Aspekte wie Hintergrundfarbe, Rahmen, Zeilenhöhe, Paginierung, Standardzellenstil und mehr ab.

#### F: Kann ich die Stile und Eigenschaften einzelner Zellen innerhalb einer Tabellenzeile anpassen?

A: Ja, Sie können die Stile und Eigenschaften einzelner Zellen innerhalb einer Tabellenzeile anpassen. Das Tutorial zeigt, wie Sie Eigenschaften wie Hintergrundfarbe, Rahmen, Textfarbe, Abstand und mehr für Tabellenzellen innerhalb der formatierten Tabellenzeile festlegen.

#### F: Wie kann ich der formatierten Tabellenzeile Kopfzeilen, Hauptzeilen und eine Fußzeile hinzufügen?

A: Das Tutorial enthält Beispiele für das Erstellen und Hinzufügen von Kopfzeilen, Hauptzeilen und einer Fußzeile zum Tabellenstrukturelement. Diese Elemente können mithilfe der im Tutorial beschriebenen Eigenschaften weiter angepasst werden.

#### F: Was ist PDF/UA-Konformität und wie kann ich sie für mein getaggtes PDF-Dokument validieren?

 A: Durch die PDF/UA-Konformität wird sichergestellt, dass das PDF-Dokument den Barrierefreiheitsstandards entspricht, sodass es für Benutzer mit Behinderungen leichter zugänglich ist. Das Tutorial zeigt, wie Sie die PDF/UA-Konformität mithilfe von validieren`Validate()` Methode und generieren Sie einen XML-Compliance-Bericht.

#### F: Wie kann ich diese Konzepte in meine eigenen .NET-Anwendungen integrieren?

A: Sie können die bereitgestellten C#-Quellcodebeispiele als Leitfaden für die Implementierung der Tabellenzeilenformatierung in Ihren eigenen .NET-Anwendungen verwenden. Ändern und passen Sie den Code an Ihre Anforderungen an und integrieren Sie ihn in Ihre Projekte.

#### F: Gibt es empfohlene Best Practices für die Formatierung von Tabellenzeilen in PDF-Dokumenten?

A: Berücksichtigen Sie beim Formatieren von Tabellenzeilen die Lesbarkeit und Zugänglichkeit des Inhalts. Achten Sie auf einen ausreichenden Kontrast der Farben, verwenden Sie klare und lesbare Schriftarten und achten Sie auf ein einheitliches Layout. Validieren Sie die PDF/UA-Konformität, um sicherzustellen, dass die Barrierefreiheitsstandards eingehalten werden.

#### F: Welche anderen Funktionen von Aspose.PDF für .NET kann ich für die Anpassung von PDF-Dokumenten erkunden?

A: Aspose.PDF für .NET bietet eine breite Palette von Funktionen zur Anpassung von PDF-Dokumenten, einschließlich Textbearbeitung, Bildeinfügung, Formularfeldverwaltung, digitale Signaturen, Anmerkungen und mehr. Konsultieren Sie die offizielle Dokumentation und Ressourcen, um zusätzliche Funktionen zu erkunden.