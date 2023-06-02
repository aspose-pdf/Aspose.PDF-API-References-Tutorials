---
title: Schriftart einbetten
linktitle: Schriftart einbetten
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie in dieser Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.PDF für .NET Schriftarten in eine PDF-Datei einbetten. Stellen Sie sicher, dass Ihre Dokumente auf jedem Gerät korrekt angezeigt werden.
type: docs
weight: 120
url: /de/net/programming-with-document/embedfont/
---

In diesem Tutorial besprechen wir, wie Sie mit Aspose.PDF für .NET Schriftarten in eine PDF-Datei einbetten. Aspose.PDF für .NET ist eine leistungsstarke Bibliothek, mit der Entwickler PDF-Dokumente programmgesteuert erstellen, bearbeiten und bearbeiten können. Diese Bibliothek bietet zahlreiche Funktionen für die Arbeit mit PDF-Dokumenten, darunter das Hinzufügen von Text, Bildern, Tabellen und vielem mehr. Das Einbetten von Schriftarten in eine PDF-Datei ist eine häufige Anforderung für Entwickler, die sicherstellen möchten, dass die PDF-Datei auf verschiedenen Geräten korrekt angezeigt wird, unabhängig davon, ob die erforderlichen Schriftarten auf diesen Geräten installiert sind oder nicht.

## Schritt 1: Erstellen Sie eine neue C#-Konsolenanwendung
Erstellen Sie zunächst eine neue C#-Konsolenanwendung in Visual Studio. Sie können es beliebig benennen. Sobald das Projekt erstellt ist, müssen Sie einen Verweis auf die Bibliothek Aspose.PDF für .NET hinzufügen.

## Schritt 2: Importieren Sie den Aspose.PDF-Namespace
Fügen Sie oben in Ihrer C#-Datei die folgende Codezeile hinzu, um den Aspose.PDF-Namespace zu importieren:

```csharp
using Aspose.Pdf;
```

## Schritt 3: Laden Sie eine vorhandene PDF-Datei
Um Schriftarten in eine vorhandene PDF-Datei einzubetten, müssen Sie diese Datei mithilfe der Document-Klasse laden. Der folgende Code zeigt, wie eine vorhandene PDF-Datei geladen wird:

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Laden Sie eine vorhandene PDF-Datei
Document doc = new Document(dataDir + "input.pdf");
```

## Schritt 4: Durchlaufen Sie alle Seiten
Nachdem Sie die PDF-Datei geladen haben, müssen Sie alle Seiten im Dokument durchlaufen. Sie müssen für jede Seite prüfen, ob Schriftarten verwendet werden, und wenn ja, müssen Sie diese Schriftarten einbetten. Der folgende Code zeigt, wie alle Seiten in der PDF-Datei durchlaufen und die Schriftarten eingebettet werden:

```csharp
foreach (Page page in doc.Pages)
{
    if (page.Resources.Fonts != null)
    {
        foreach (Aspose.Pdf.Text.Font pageFont in page.Resources.Fonts)
        {
            // Überprüfen Sie, ob die Schriftart bereits eingebettet ist
            if (!pageFont.IsEmbedded)
                pageFont.IsEmbedded = true;
        }
    }

    // Suchen Sie nach den Formularobjekten
    foreach (XForm form in page.Resources.Forms)
    {
        if (form.Resources.Fonts != null)
        {
            foreach (Aspose.Pdf.Text.Font formFont in form.Resources.Fonts)
            {
                // Überprüfen Sie, ob die Schriftart eingebettet ist
                if (!formFont.IsEmbedded)
                    formFont.IsEmbedded = true;
            }
        }
    }
}
```

## Schritt 5: Speichern Sie das PDF-Dokument
Nachdem Sie alle Schriftarten in die PDF-Datei eingebettet haben, müssen Sie das Dokument speichern. Der folgende Code zeigt, wie die PDF-Datei gespeichert wird:

```csharp
dataDir = dataDir + "EmbedFont_out.pdf";
// PDF-Dokument speichern
doc.Save(dataDir);

Console.WriteLine("\nFont embedded successfully in a PDF file.\nFile saved at " + dataDir);
```

### Beispielquellcode für Embed Font mit Aspose.PDF für .NET

Hier ist der vollständige Quellcode zum Einbetten einer Schriftart mit Aspose.PDF für .NET.


```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Laden Sie eine vorhandene PDF-Datei
Document doc = new Document(dataDir + "input.pdf");

// Durchlaufen Sie alle Seiten
foreach (Page page in doc.Pages)
{
	if (page.Resources.Fonts != null)
	{
		foreach (Aspose.Pdf.Text.Font pageFont in page.Resources.Fonts)
		{
			// Überprüfen Sie, ob die Schriftart bereits eingebettet ist
			if (!pageFont.IsEmbedded)
				pageFont.IsEmbedded = true;
		}
	}

	// Suchen Sie nach den Formularobjekten
	foreach (XForm form in page.Resources.Forms)
	{
		if (form.Resources.Fonts != null)
		{
			foreach (Aspose.Pdf.Text.Font formFont in form.Resources.Fonts)
			{
				// Überprüfen Sie, ob die Schriftart eingebettet ist
				if (!formFont.IsEmbedded)
					formFont.IsEmbedded = true;
			}
		}
	}
}
dataDir = dataDir + "EmbedFont_out.pdf";
// PDF-Dokument speichern
doc.Save(dataDir);

Console.WriteLine("\nFont embedded successfully in a PDF file.\nFile saved at " + dataDir);
```


## Abschluss
In diesem Artikel haben wir erläutert, wie Sie mit Aspose.PDF für .NET Schriftarten in eine PDF-Datei einbetten. Aspose.PDF für .NET bietet eine einfache und benutzerfreundliche API für die Arbeit mit PDF-Dokumenten, einschließlich des Hinzufügens und Einbettens von Schriftarten. Das Einbetten von Schriftarten in eine PDF-Datei ist ein wichtiger Schritt, um sicherzustellen, dass das Dokument auf verschiedenen Geräten korrekt angezeigt wird, unabhängig davon, ob die erforderlichen Schriftarten auf diesen Geräten installiert sind
