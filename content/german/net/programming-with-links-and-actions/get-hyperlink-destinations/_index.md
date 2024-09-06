---
title: Holen Sie sich Hyperlink-Ziele in PDF-Datei
linktitle: Holen Sie sich Hyperlink-Ziele in PDF-Datei
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Hyperlinkziele in PDF-Dateien extrahieren.
type: docs
weight: 60
url: /de/net/programming-with-links-and-actions/get-hyperlink-destinations/
---
Aspose.PDF für .NET ist eine leistungsstarke Bibliothek zum Bearbeiten und Extrahieren von Informationen in PDF-Dateien mithilfe der Programmiersprache C#. In diesem Tutorial konzentrieren wir uns auf das Extrahieren von Hyperlink-Zielen aus einer PDF-Datei mithilfe von Aspose.PDF für .NET.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Eine integrierte Entwicklungsumgebung (IDE) wie Visual Studio.
- Die Aspose.PDF-Bibliothek für .NET ist auf Ihrem Computer installiert.

## Schritt 1: Einrichten der Entwicklungsumgebung

Bevor Sie mit dem Schreiben von Code beginnen, müssen Sie Ihre Entwicklungsumgebung einrichten, indem Sie in Ihrer bevorzugten IDE ein neues C#-Projekt erstellen.

## Schritt 2: Aspose.PDF-Referenzen importieren

Um Aspose.PDF für .NET zu verwenden, müssen Sie Ihrem Projekt die entsprechenden Referenzen hinzufügen. Befolgen Sie die folgenden Schritte, um die erforderlichen Referenzen zu importieren:

1. Klicken Sie in Ihrem Projekt mit der rechten Maustaste auf „Verweise“ und wählen Sie „Verweis hinzufügen“.
2. Suchen und wählen Sie im Fenster „Referenz hinzufügen“ die DLL-Dateien von Aspose.PDF für .NET aus.
3. Klicken Sie auf „OK“, um die Referenzen in Ihr Projekt zu importieren.

## Schritt 3: Laden der PDF-Datei

Bevor Sie Hyperlinkziele extrahieren können, müssen Sie die PDF-Datei in Ihre Anwendung laden. Verwenden Sie den folgenden Code, um die PDF-Datei zu laden:

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Laden Sie die PDF-Datei
Document document = new Document(dataDir + "input.pdf");
```

Achten Sie darauf, den richtigen Pfad zu Ihrem Dokumentverzeichnis und der zu verarbeitenden PDF-Datei anzugeben.

## Schritt 4: Navigieren durch die Seiten des Dokuments

Nachdem die PDF-Datei geladen wurde, müssen Sie alle Seiten des Dokuments durchgehen. Auf diese Weise erhalten Sie

in den Hyperlink-Anmerkungen auf jeder Seite. Verwenden Sie den folgenden Code, um durch die Seiten des Dokuments zu iterieren:

```csharp
foreach(Aspose.Pdf.Page page in document.Pages)
{
     // Holen Sie sich die Linkanmerkungen einer bestimmten Seite
     AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
     page. Accept(selector);
     // Erstellen Sie eine Liste zum Speichern aller Links
     IList<Annotation> list = selector. Selected;
     // Durchlaufen Sie jedes Element in der Liste
     foreach(LinkAnnotation a in list)
     {
         // Ziel-URL drucken
         Console.WriteLine("\nDestination: " + (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI + "\n");
     }
}
```

Dieser Code durchläuft jede Seite des Dokuments und wählt die auf jeder Seite vorhandenen Hyperlink-Anmerkungen aus. Anschließend speichert er diese Anmerkungen in einer Liste und druckt die Ziel-URL für jeden Link aus.

## Schritt 5: Abrufen von Hyperlink-Zielen

Der letzte Schritt besteht darin, die Hyperlinkziele aus den Hyperlinkanmerkungen zu extrahieren. Der folgende Code zeigt Ihnen, wie das geht:

```csharp
foreach(Aspose.Pdf.Page page in document.Pages)
{
     AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
     page. Accept(selector);
     IList<Annotation> list = selector. Selected;
     foreach(LinkAnnotation a in list)
     {
         string destination = (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI;
         // Nutzen Sie das Ziel nach Belieben
     }
}
```

In diesem Code erhalten wir jedes Hyperlinkziel aus den Linkanmerkungen und speichern das Ziel in einer Variablen. Sie können dieses Ziel dann nach Belieben in Ihrer Anwendung verwenden.

### Beispielquellcode zum Abrufen von Hyperlinkzielen mit Aspose.PDF für .NET 
```csharp
try
{
	// Der Pfad zum Dokumentverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Laden Sie die PDF-Datei
	Document document = new Document(dataDir + "input.pdf");
	// Alle PDF-Seiten durchsuchen
	foreach (Aspose.Pdf.Page page in document.Pages)
	{
		// Holen Sie sich die Linkanmerkungen von einer bestimmten Seite
		AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
		page.Accept(selector);
		// Erstellen Sie eine Liste mit allen Links
		IList<Annotation> list = selector.Selected;
		// Durchlaufen Sie einzelne Elemente in der Liste
		foreach (LinkAnnotation a in list)
		{
			// Drucken Sie die Ziel-URL
			Console.WriteLine("\nDestination: " + (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI + "\n");
		}
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

### FAQs zum Abrufen von Hyperlink-Zielen in PDF-Dateien

#### F: Was ist ein Hyperlink-Ziel in einer PDF-Datei?

A: Ein Hyperlinkziel in einer PDF-Datei ist ein bestimmter Ort oder ein bestimmtes Ziel, auf das ein Hyperlink verweist. Dies kann eine URL, eine Seite innerhalb desselben Dokuments oder ein externes Dokument sein.

#### F: Welche Vorteile bietet das Extrahieren von Hyperlink-Zielen bei der Analyse meines PDF-Dokuments?

A: Durch das Extrahieren von Hyperlink-Zielen können Sie alle Ziele identifizieren und katalogisieren, auf die Hyperlinks in einem PDF-Dokument verweisen. Diese Informationen können für die Inhaltsvalidierung, Linküberprüfung und Datenanalyse nützlich sein.

#### F: Wie hilft Aspose.PDF für .NET beim Extrahieren von Hyperlink-Zielen?

A: Aspose.PDF für .NET bietet leistungsstarke APIs zum einfachen Extrahieren von Hyperlink-Zielen. Dieses Tutorial zeigt Schritt für Schritt, wie Sie Hyperlink-Ziele mit C# extrahieren.

#### F: Kann ich Hyperlink-Ziele selektiv anhand bestimmter Kriterien extrahieren?

A: Ja, Sie können Hyperlink-Ziele selektiv extrahieren, indem Sie die Seiten des PDF-Dokuments durchsuchen und die gewünschten Hyperlink-Anmerkungen basierend auf Ihren Kriterien filtern.

#### F: Ist es möglich, Hyperlinkziele aus passwortgeschützten PDF-Dokumenten zu extrahieren?

A: Aspose.PDF für .NET kann Hyperlink-Ziele aus passwortgeschützten PDF-Dokumenten extrahieren, solange Sie beim Öffnen des Dokuments die erforderlichen Authentifizierungsdaten angeben.

#### F: Wie kann ich die extrahierten Hyperlink-Ziele in meiner Anwendung nutzen?

A: Nachdem Sie die Hyperlinkziele extrahiert haben, können Sie diese für verschiedene Aktionen verwenden, z. B. zum Validieren von Link-URLs, zum Erstellen von Berichten oder zum Implementieren einer benutzerdefinierten Navigation.

#### F: Gibt es beim Extrahieren von Hyperlink-Zielen irgendwelche Einschränkungen?

A: Obwohl die Extraktion von Hyperlink-Zielen leistungsstark ist, muss die Struktur des PDF-Dokuments unbedingt berücksichtigt werden. In komplexe Grafiken oder Multimedia-Inhalte eingebettete Hyperlinks erfordern möglicherweise zusätzliche Bearbeitung.

#### F: Kann ich andere Attribute von Hyperlinks extrahieren, beispielsweise Linktypen oder Koordinaten?

A: Das Tutorial konzentriert sich auf das Extrahieren von Hyperlink-Zielen. Sie können jedoch auch die offizielle Aspose.PDF-Dokumentation zu Rate ziehen, um erweiterte Funktionen kennenzulernen, darunter das Extrahieren von Linktypen und Koordinaten.