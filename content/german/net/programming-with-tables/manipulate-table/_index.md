---
title: Tabelle in PDF-Datei bearbeiten
linktitle: Tabelle in PDF-Datei bearbeiten
second_title: Aspose.PDF für .NET API-Referenz
description: Bearbeiten Sie Tabellen in PDF-Dateien ganz einfach mit Aspose.PDF für .NET.
type: docs
weight: 130
url: /de/net/programming-with-tables/manipulate-table/
---
In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess der Bearbeitung von Tabellen in PDF-Dateien mit Aspose.PDF für .NET. Tabellen sind ein häufiges Element in PDF-Dokumenten, und die Möglichkeit, ihren Inhalt programmgesteuert zu ändern, kann in verschiedenen Szenarien äußerst nützlich sein. Wir werden den bereitgestellten C#-Quellcode verwenden, um den Prozess zu demonstrieren.

## Anforderungen

Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:

- Visual Studio oder eine andere C#-Entwicklungsumgebung installiert.
- Aspose.PDF für .NET-Bibliothek als Referenz zu Ihrem Projekt hinzugefügt.

Lassen Sie uns nun einen Blick auf die erforderlichen Schritte zum Bearbeiten von Tabellen in einem PDF-Dokument mit Aspose.PDF für .NET werfen.

## Schritt 1: Laden des PDF-Dokuments

Der erste Schritt besteht darin, das vorhandene PDF-Dokument in Ihre C#-Anwendung zu laden. Sie müssen den Pfad zum Verzeichnis angeben, in dem sich Ihr Dokument befindet.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "input.pdf");
```

Ersetzen Sie „IHR DOKUMENTVERZEICHNIS“ durch den tatsächlichen Pfad zum Verzeichnis, in dem sich Ihr PDF-Dokument befindet.

## Schritt 2: Tabellen im Dokument suchen

Um Tabellen zu bearbeiten, müssen wir sie im PDF-Dokument finden. Aspose.PDF für .NET bietet eine TableAbsorber-Klasse, mit der wir Tabellen aus dem Dokument extrahieren können. Wir erstellen eine Instanz der TableAbsorber-Klasse und besuchen die gewünschte Seite des Dokuments.

```csharp
TableAbsorber absorber = new TableAbsorber();
absorb.Visit(pdfDocument.Pages[1]);
```

In diesem Beispiel besuchen wir die erste Seite des Dokuments. Sie können die Seitenzahl nach Bedarf ändern.

## Schritt 3: Auf Tabellenzellen und Textfragmente zugreifen

Sobald wir die Tabellen haben, können wir auf ihre Zellen und Textfragmente zugreifen, um sie zu bearbeiten. Im bereitgestellten Quellcode greifen wir auf die erste Tabelle, die erste Zelle ihrer ersten Zeile und das zweite Textfragment innerhalb dieser Zelle zu.

```csharp
TextFragment fragment = absorb.TableList[0].RowList[0].CellList[0].TextFragments[1];
```

Sie können den Code entsprechend Ihren spezifischen Anforderungen ändern, um unterschiedliche Tabellen, Zellen oder Textfragmente anzusprechen.

## Schritt 4: Tabellentext bearbeiten

Nachdem wir auf das Textfragment zugegriffen haben, können wir nun dessen Inhalt ändern. Im angegebenen Beispiel ändern wir den Text in „Hallo Welt“.

```csharp
fragment.Text = "hi world";
```

Ersetzen Sie „Hi World“ gerne durch Ihren gewünschten Text.

## Schritt 5: Speichern des geänderten Dokuments

Sobald die gewünschten Änderungen vorgenommen wurden, müssen wir das geänderte PDF-Dokument speichern.

```csharp
dataDir = dataDir + "ManipulateTable_out.pdf";
pdfDocument.Save(dataDir);
```

Stellen Sie sicher, dass Sie den Pfad und den Dateinamen für das geänderte Dokument angeben.


### Beispielquellcode für „Tabelle manipulieren“ mit Aspose.PDF für .NET

```csharp
try
{
	
	// Der Pfad zum Dokumentverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Vorhandene PDF-Datei laden
	Document pdfDocument = new Document(dataDir + "input.pdf");
	// Erstellen Sie ein TableAbsorber-Objekt, um Tabellen zu finden
	TableAbsorber absorber = new TableAbsorber();

	// Besuchen Sie die erste Seite mit Absorber
	absorber.Visit(pdfDocument.Pages[1]);

	// Erhalten Sie Zugriff auf die erste Tabelle auf der Seite, ihre erste Zelle und die darin enthaltenen Textfragmente
	TextFragment fragment = absorber.TableList[0].RowList[0].CellList[0].TextFragments[1];

	// Text des ersten Textfragments in der Zelle ändern
	fragment.Text = "hi world";
	dataDir = dataDir + "ManipulateTable_out.pdf";
	pdfDocument.Save(dataDir);
	
	Console.WriteLine("\nTable manipulated successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man Tabellen in einem PDF-Dokument mit Aspose.PDF für .NET bearbeitet. Indem Sie der Schritt-für-Schritt-Anleitung folgen, können Sie problemlos ein PDF-Dokument laden, Tabellen finden, auf Zellen und Textfragmente zugreifen, Tabelleninhalte ändern und das geänderte Dokument speichern. Dieser Ansatz bietet Flexibilität und Effizienz bei der Tabellenbearbeitung in PDF-Dokumenten.

### FAQs zum Bearbeiten von Tabellen in PDF-Dateien

#### F: Kann ich Tabellen in mehrseitigen PDF-Dokumenten bearbeiten?

A: Ja, Sie können Tabellen in mehrseitigen PDF-Dokumenten mit Aspose.PDF für .NET bearbeiten. Im angegebenen Beispiel haben wir die erste Seite des Dokuments besucht (`pdfDocument.Pages[1]`), Sie können jedoch alle Seiten durchlaufen und die Tabellen auf jeder Seite nach Bedarf bearbeiten.

#### F: Wie kann ich einer vorhandenen Tabelle neue Zeilen oder Spalten hinzufügen?

 A: Um einer vorhandenen Tabelle neue Zeilen oder Spalten hinzuzufügen, können Sie die von Aspose.PDF für .NET bereitgestellten APIs verwenden. Sie können auf die`RowList` Und`CellList` Eigenschaften der`TableAbsorber.TableList` um programmgesteuert neue Zeilen und Zellen hinzuzufügen. Ausführliche Informationen und Codebeispiele finden Sie in der Aspose.PDF-Dokumentation für .NET.

#### F: Ist es möglich, eine Tabelle aus einem PDF-Dokument zu entfernen?

 A: Ja, Sie können eine Tabelle aus einem PDF-Dokument mit Aspose.PDF für .NET entfernen. Dazu können Sie die spezifische`Table` Objekt aus dem`Page.Paragraphs` Sammlung. Sie können die zu entfernende Tabelle anhand von Eigenschaften wie`Table.NumberOfColumns`, `Table.NumberOfRows`und andere eindeutige Kennungen.

#### F: Kann ich die Formatierung (Schriftart, Farbe, Ausrichtung) des Tabellentextes ändern?

 A: Ja, Sie können die Formatierung des Tabellentextes mit Aspose.PDF für .NET ändern. Sie können auf die`TextState` Eigentum der`TextFragment` Objekt, um Schriftart, Schriftgröße, Farbe und Ausrichtung des Textes zu ändern.

#### F: Unterstützt Aspose.PDF für .NET die Arbeit mit Tabellen in PDF-Formularen (AcroForms)?

A: Ja, Aspose.PDF für .NET unterstützt die Arbeit mit Tabellen in PDF-Formularen (AcroForms). Sie können auf Tabellenelemente in PDF-Formularen zugreifen und diese bearbeiten, ähnlich dem in diesem Tutorial gezeigten Ansatz. Aspose.PDF für .NET bietet umfassende Unterstützung für die Arbeit mit AcroForms und Formularfeldern.