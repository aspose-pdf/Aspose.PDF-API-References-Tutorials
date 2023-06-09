---
title: Tabelle manipulieren
linktitle: Tabelle manipulieren
second_title: Aspose.PDF für .NET API-Referenz
description: Bearbeiten Sie Tabellen in PDF-Dokumenten ganz einfach mit Aspose.PDF für .NET.
type: docs
weight: 130
url: /de/net/programming-with-tables/manipulate-table/
---

In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess der Bearbeitung von Tabellen in einem PDF-Dokument mit Aspose.PDF für .NET. Tabellen sind ein häufiges Element in PDF-Dokumenten und die Möglichkeit, ihren Inhalt programmgesteuert zu ändern, kann in verschiedenen Szenarien von großem Vorteil sein. Wir werden den bereitgestellten C#-Quellcode verwenden, um den Prozess zu demonstrieren.

## Anforderungen

Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Visual Studio oder eine andere C#-Entwicklungsumgebung installiert.
- Aspose.PDF für .NET-Bibliothek als Referenz zu Ihrem Projekt hinzugefügt.

Schauen wir uns nun die Schritte an, die zum Bearbeiten von Tabellen in einem PDF-Dokument mit Aspose.PDF für .NET erforderlich sind.

## Schritt 1: Laden des PDF-Dokuments

Der erste Schritt besteht darin, das vorhandene PDF-Dokument in Ihre C#-Anwendung zu laden. Sie müssen den Pfad zu dem Verzeichnis angeben, in dem sich Ihr Dokument befindet.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "input.pdf");
```

Ersetzen Sie „IHR DOKUMENTVERZEICHNIS“ durch den tatsächlichen Pfad zu dem Verzeichnis, in dem sich Ihr PDF-Dokument befindet.

## Schritt 2: Tabellen im Dokument suchen

Um Tabellen zu manipulieren, müssen wir sie im PDF-Dokument finden. Aspose.PDF für .NET bietet eine TableAbsorber-Klasse, die es uns ermöglicht, Tabellen aus dem Dokument zu extrahieren. Wir erstellen eine Instanz der TableAbsorber-Klasse und besuchen die gewünschte Seite des Dokuments.

```csharp
TableAbsorber absorber = new TableAbsorber();
absorb.Visit(pdfDocument.Pages[1]);
```

In diesem Beispiel besuchen wir die erste Seite des Dokuments. Sie können die Seitenzahl entsprechend Ihren Anforderungen ändern.

## Schritt 3: Zugriff auf Tabellenzellen und Textfragmente

Sobald wir die Tabellen haben, können wir zur Bearbeitung auf ihre Zellen und Textfragmente zugreifen. Im bereitgestellten Quellcode greifen wir auf die erste Tabelle, die erste Zelle ihrer ersten Zeile und das zweite Textfragment innerhalb dieser Zelle zu.

```csharp
TextFragment fragment = absorb.TableList[0].RowList[0].CellList[0].TextFragments[1];
```

Sie können den Code so ändern, dass er je nach Ihren spezifischen Anforderungen auf verschiedene Tabellen, Zellen oder Textfragmente abzielt.

## Schritt 4: Tabellentext bearbeiten

Nachdem wir auf das Textfragment zugegriffen haben, können wir nun seinen Inhalt ändern. Im gegebenen Beispiel ändern wir den Text in „hi world“.

```csharp
fragment.Text = "hi world";
```

Ersetzen Sie „hi world“ gerne durch Ihren Wunschtext.

## Schritt 5: Speichern des geänderten Dokuments

Sobald die gewünschten Änderungen vorgenommen wurden, müssen wir das geänderte PDF-Dokument speichern.

```csharp
dataDir = dataDir + "ManipulateTable_out.pdf";
pdfDocument.Save(dataDir);
```

Stellen Sie sicher, dass Sie den Pfad und Dateinamen für das geänderte Dokument angeben.


### Beispielquellcode für Manipulate Table mit Aspose.PDF für .NET

```csharp
try
{
	
	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Vorhandene PDF-Datei laden
	Document pdfDocument = new Document(dataDir + "input.pdf");
	// Erstellen Sie ein TableAbsorber-Objekt, um Tabellen zu finden
	TableAbsorber absorber = new TableAbsorber();

	// Besuchen Sie die erste Seite mit Absorber
	absorber.Visit(pdfDocument.Pages[1]);

	// Erhalten Sie Zugriff auf die erste Tabelle auf der Seite, ihre erste Zelle und Textfragmente darin
	TextFragment fragment = absorber.TableList[0].RowList[0].CellList[0].TextFragments[1];

	// Ändern Sie den Text des ersten Textfragments in der Zelle
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

In diesem Tutorial haben wir gelernt, wie man Tabellen in einem PDF-Dokument mit Aspose.PDF für .NET manipuliert. Wenn Sie der Schritt-für-Schritt-Anleitung folgen, können Sie ganz einfach ein PDF-Dokument laden, Tabellen finden, auf Zellen und Textfragmente zugreifen, Tabelleninhalte ändern und das geänderte Dokument speichern. Dieser Ansatz bietet Flexibilität und Effizienz beim Umgang mit Tabellenmanipulationen in PDF-Dokumenten.