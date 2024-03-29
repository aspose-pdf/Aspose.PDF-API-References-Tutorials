---
title: Holen Sie sich Hyperlink-Ziele in eine PDF-Datei
linktitle: Holen Sie sich Hyperlink-Ziele in eine PDF-Datei
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Hyperlink-Ziele in eine PDF-Datei extrahieren.
type: docs
weight: 60
url: /de/net/programming-with-links-and-actions/get-hyperlink-destinations/
---
Aspose.PDF für .NET ist eine leistungsstarke Bibliothek zum Bearbeiten und Extrahieren von Informationen in PDF-Dateien mithilfe der Programmiersprache C#. In diesem Tutorial konzentrieren wir uns auf das Extrahieren von Hyperlink-Zielen aus einer PDF-Datei mit Aspose.PDF für .NET.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Eine integrierte Entwicklungsumgebung (IDE) wie Visual Studio.
- Die auf Ihrem Computer installierte Aspose.PDF-Bibliothek für .NET.

## Schritt 1: Einrichten der Entwicklungsumgebung

Bevor Sie mit dem Schreiben von Code beginnen, müssen Sie Ihre Entwicklungsumgebung einrichten, indem Sie ein neues C#-Projekt in Ihrer bevorzugten IDE erstellen.

## Schritt 2: Aspose.PDF-Referenzen importieren

Um Aspose.PDF für .NET verwenden zu können, müssen Sie Ihrem Projekt die entsprechenden Referenzen hinzufügen. Führen Sie die folgenden Schritte aus, um die erforderlichen Referenzen zu importieren:

1. Klicken Sie in Ihrem Projekt mit der rechten Maustaste auf „Referenzen“ und wählen Sie „Referenz hinzufügen“.
2. Suchen Sie im Fenster „Referenz hinzufügen“ nach den DLL-Dateien von Aspose.PDF für .NET und wählen Sie sie aus.
3. Klicken Sie auf „OK“, um die Referenzen in Ihr Projekt zu importieren.

## Schritt 3: Laden der PDF-Datei

Bevor Sie Hyperlink-Ziele extrahieren können, müssen Sie die PDF-Datei in Ihre Anwendung laden. Verwenden Sie den folgenden Code, um die PDF-Datei zu laden:

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Laden Sie die PDF-Datei
Document document = new Document(dataDir + "input.pdf");
```

Stellen Sie sicher, dass Sie den korrekten Pfad zu Ihrem Dokumentverzeichnis und der PDF-Datei angeben, die Sie verarbeiten möchten.

## Schritt 4: Navigieren durch die Seiten des Dokuments

Nachdem die PDF-Datei nun geladen ist, müssen Sie alle Seiten des Dokuments durchgehen. Dies wird Ihnen ermöglichen, zu bekommen

ir die auf jeder Seite vorhandenen Hyperlink-Anmerkungen. Verwenden Sie den folgenden Code, um die Seiten des Dokuments zu durchlaufen:

```csharp
foreach(Aspose.Pdf.Page page in document.Pages)
{
     // Rufen Sie die Linkanmerkungen einer bestimmten Seite ab
     AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
     page. Accept(selector);
     // Erstellen Sie eine Liste, um alle Links zu speichern
     IList<Annotation> list = selector. Selected;
     // Durchlaufen Sie jedes Element in der Liste
     foreach(LinkAnnotation a in list)
     {
         // Ziel-URL drucken
         Console.WriteLine("\nDestination: " + (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI + "\n");
     }
}
```

Dieser Code durchläuft jede Seite des Dokuments und wählt die auf jeder Seite vorhandenen Hyperlink-Anmerkungen aus. Anschließend speichert es diese Anmerkungen in einer Liste und gibt die Ziel-URL für jeden Link aus.

## Schritt 5: Abrufen von Hyperlink-Zielen

Der letzte Schritt besteht darin, die Hyperlinkziele aus den Hyperlinkanmerkungen zu extrahieren. Der folgende Code zeigt Ihnen, wie es geht:

```csharp
foreach(Aspose.Pdf.Page page in document.Pages)
{
     AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
     page. Accept(selector);
     IList<Annotation> list = selector. Selected;
     foreach(LinkAnnotation a in list)
     {
         string destination = (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI;
         // Nutzen Sie das Ziel nach Ihren Wünschen
     }
}
```

In diesem Code erhalten wir jedes Hyperlinkziel aus den Linkanmerkungen und speichern das Ziel in einer Variablen. Dieses Ziel können Sie dann in Ihrer Bewerbung beliebig verwenden.

### Beispielquellcode für „Get Hyperlink Destinations“ mit Aspose.PDF für .NET 
```csharp
try
{
	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Laden Sie die PDF-Datei
	Document document = new Document(dataDir + "input.pdf");
	// Durchsuchen Sie die gesamte PDF-Seite
	foreach (Aspose.Pdf.Page page in document.Pages)
	{
		// Rufen Sie die Linkanmerkungen von einer bestimmten Seite ab
		AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
		page.Accept(selector);
		// Erstellen Sie eine Liste mit allen Links
		IList<Annotation> list = selector.Selected;
		// Durchlaufen Sie einzelne Elemente in der Liste
		foreach (LinkAnnotation a in list)
		{
			// Drucken Sie die Ziel-URL aus
			Console.WriteLine("\nDestination: " + (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI + "\n");
		}
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

### FAQs zum Abrufen von Hyperlink-Zielen in einer PDF-Datei

#### F: Was ist ein Hyperlink-Ziel in einer PDF-Datei?

A: Ein Hyperlink-Ziel in einer PDF-Datei ist ein bestimmter Ort oder ein bestimmtes Ziel, auf das ein Hyperlink verweist. Dabei kann es sich um eine URL, eine Seite innerhalb desselben Dokuments oder ein externes Dokument handeln.

#### F: Wie kann das Extrahieren von Hyperlink-Zielen meine PDF-Dokumentanalyse verbessern?

A: Durch das Extrahieren von Hyperlinkzielen können Sie alle Ziele identifizieren und katalogisieren, auf die Hyperlinks in einem PDF-Dokument verweisen. Diese Informationen können für die Inhaltsvalidierung, Linküberprüfung und Datenanalyse nützlich sein.

#### F: Wie hilft Aspose.PDF für .NET beim Extrahieren von Hyperlink-Zielen?

A: Aspose.PDF für .NET bietet leistungsstarke APIs zum einfachen Extrahieren von Hyperlink-Zielen. Dieses Tutorial zeigt Schritt für Schritt, wie Sie Hyperlinkziele mit C# extrahieren.

#### F: Kann ich Hyperlink-Ziele anhand bestimmter Kriterien selektiv extrahieren?

A: Ja, Sie können Hyperlink-Ziele selektiv extrahieren, indem Sie die Seiten des PDF-Dokuments durchlaufen und die gewünschten Hyperlink-Anmerkungen basierend auf Ihren Kriterien filtern.

#### F: Ist es möglich, Hyperlink-Ziele aus passwortgeschützten PDF-Dokumenten zu extrahieren?

A: Aspose.PDF für .NET kann Hyperlink-Ziele aus passwortgeschützten PDF-Dokumenten extrahieren, sofern Sie beim Öffnen des Dokuments die erforderlichen Authentifizierungsdaten angeben.

#### F: Wie kann ich die extrahierten Hyperlink-Ziele in meiner Anwendung verwenden?

A: Sobald Sie die Hyperlink-Ziele extrahiert haben, können Sie sie zum Ausführen verschiedener Aktionen verwenden, z. B. zum Überprüfen von Link-URLs, zum Erstellen von Berichten oder zum Implementieren einer benutzerdefinierten Navigation.

#### F: Gibt es Einschränkungen beim Extrahieren von Hyperlink-Zielen?

A: Obwohl die Extraktion von Hyperlinkzielen leistungsstark ist, ist es wichtig, die Struktur des PDF-Dokuments zu berücksichtigen. In komplexe Grafiken oder Multimedia-Inhalte eingebettete Hyperlinks erfordern möglicherweise eine zusätzliche Bearbeitung.

#### F: Kann ich andere Attribute von Hyperlinks extrahieren, z. B. Linktypen oder Koordinaten?

A: Das Tutorial konzentriert sich auf das Extrahieren von Hyperlink-Zielen. Sie können jedoch die offizielle Aspose.PDF-Dokumentation lesen, um erweiterte Funktionen zu erkunden, einschließlich der Extraktion von Linktypen und Koordinaten.