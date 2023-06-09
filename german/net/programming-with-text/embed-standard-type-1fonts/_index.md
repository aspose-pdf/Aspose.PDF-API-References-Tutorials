---
title: Betten Sie Standardschriftarten vom Typ 1 ein
linktitle: Betten Sie Standardschriftarten vom Typ 1 ein
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Standard-Typ-1-Schriftarten in ein PDF-Dokument einbetten.
type: docs
weight: 140
url: /de/net/programming-with-text/embed-standard-type-1fonts/
---

Dieses Tutorial führt Sie durch den Prozess der Einbettung von Standard-Typ-1-Schriftarten in ein PDF-Dokument mit Aspose.PDF für .NET. Der bereitgestellte C#-Quellcode demonstriert die notwendigen Schritte.

## Anforderungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Visual Studio oder ein anderer auf Ihrem Computer installierter C#-Compiler.
- Aspose.PDF für .NET-Bibliothek. Sie können es von der offiziellen Aspose-Website herunterladen oder einen Paketmanager wie NuGet verwenden, um es zu installieren.

## Schritt 1: Richten Sie das Projekt ein
1. Erstellen Sie ein neues C#-Projekt in Ihrer bevorzugten Entwicklungsumgebung.
2. Fügen Sie einen Verweis auf die Aspose.PDF für .NET-Bibliothek hinzu.

## Schritt 2: Erforderliche Namespaces importieren
Fügen Sie in der Codedatei, in die Sie Standardschriftarten vom Typ 1 einbetten möchten, die folgende using-Anweisung am Anfang der Datei hinzu:

```csharp
using Aspose.Pdf;
```

## Schritt 3: Legen Sie das Dokumentverzeichnis fest
 Suchen Sie im Code die Zeile mit der Aufschrift`string dataDir = "YOUR DOCUMENT DIRECTORY";` und ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem Pfad zu dem Verzeichnis, in dem Ihre Dokumente gespeichert sind.

## Schritt 4: Laden Sie das vorhandene PDF-Dokument
 Laden Sie ein vorhandenes PDF-Dokument mit`Document` Konstruktor und Übergabe des Pfads zur Eingabe-PDF-Datei.

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## Schritt 5: Legen Sie die EmbedStandardFonts-Eigenschaft fest
 Stellen Sie die ein`EmbedStandardFonts` Eigentum des Dokuments an`true` um die Einbettung von Standard-Typ-1-Schriftarten zu ermöglichen.

```csharp
pdfDocument.EmbedStandardFonts = true;
```

## Schritt 6: Betten Sie Schriftarten in jede Seite ein
 Gehen Sie jede Seite des PDF-Dokuments durch und prüfen Sie, ob die Schriftarten bereits eingebettet sind. Wenn nicht, stellen Sie die ein`IsEmbedded` Eigentum zu`true` um die Schriftart einzubetten.

```csharp
foreach(Page page in pdfDocument.Pages)
{
     if (page.Resources.Fonts != null)
     {
         foreach(Aspose.Pdf.Text.Font pageFont in page.Resources.Fonts)
         {
             if (!pageFont.IsEmbedded)
             {
                 pageFont.IsEmbedded = true;
             }
         }
     }
}
```

## Schritt 7: Speichern Sie das aktualisierte PDF-Dokument
 Speichern Sie das aktualisierte PDF-Dokument mit`Save` Methode der`Document` -Objekt und gibt den Pfad der Ausgabedatei an.

```csharp
pdfDocument.Save(dataDir + "EmbeddedFonts-updated_out.pdf");
```

### Beispielquellcode für das Einbetten von Standardschriftarten vom Typ 1 mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Laden Sie ein vorhandenes PDF-Dokument
Document pdfDocument = new Document(dataDir + "input.pdf");
// Legen Sie die EmbedStandardFonts-Eigenschaft des Dokuments fest
pdfDocument.EmbedStandardFonts = true;
foreach (Aspose.Pdf.Page page in pdfDocument.Pages)
{
	if (page.Resources.Fonts != null)
	{
		foreach (Aspose.Pdf.Text.Font pageFont in page.Resources.Fonts)
		{
			// Überprüfen Sie, ob die Schriftart bereits eingebettet ist
			if (!pageFont.IsEmbedded)
			{
				pageFont.IsEmbedded = true;
			}
		}
	}
}
pdfDocument.Save(dataDir + "EmbeddedFonts-updated_out.pdf");
```

## Abschluss
Sie haben mit Aspose.PDF für .NET erfolgreich Standardschriftarten vom Typ 1 in ein PDF-Dokument eingebettet. Die aktualisierte PDF-Datei mit eingebetteten Schriftarten wurde im angegebenen Ausgabedateipfad gespeichert.