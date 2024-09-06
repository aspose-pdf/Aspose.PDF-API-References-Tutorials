---
title: Links in PDF-Datei extrahieren
linktitle: Links in PDF-Datei extrahieren
second_title: Aspose.PDF für .NET API-Referenz
description: Extrahieren Sie mit Aspose.PDF für .NET ganz einfach Links aus PDF-Dateien.
type: docs
weight: 50
url: /de/net/programming-with-links-and-actions/extract-links/
---
Durch das Extrahieren von Links in PDF-Dateien können Sie alle im Dokument vorhandenen Hypertext-Links wiederherstellen. Mit Aspose.PDF für .NET können Sie diese Links einfach extrahieren, indem Sie dem folgenden Quellcode folgen:

## Schritt 1: Erforderliche Bibliotheken importieren

Bevor Sie beginnen, müssen Sie die erforderlichen Bibliotheken für Ihr C#-Projekt importieren. Hier ist die erforderliche Importanweisung:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
```

## Schritt 2: Pfad zum Dokumentenordner festlegen

 In diesem Schritt müssen Sie den Pfad zum Ordner angeben, der die PDF-Datei enthält, aus der Sie die Links extrahieren möchten. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` ersetzen Sie den folgenden Code durch den tatsächlichen Pfad zu Ihrem Dokumentordner:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 3: Öffnen Sie das PDF-Dokument

 Wir öffnen das PDF-Dokument mit dem`Document` Klasse. Hier ist der entsprechende Code:

```csharp
Document document = new Document(dataDir + "ExtractLinks.pdf");
```

## Schritt 4: Links extrahieren

 In diesem Schritt extrahieren wir die im PDF-Dokument vorhandenen Links mithilfe des`AnnotationSelector` Klasse. Hier ist der entsprechende Code:

```csharp
Page page = document.Pages[1];
AnnotationSelector selector = new AnnotationSelector(new LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
page. Accept(selector);
IList<Annotation> list = selector. Selected;
Annotation annotation = (Annotation)list[0];
```

## Schritt 5: Speichern Sie das aktualisierte Dokument

Speichern wir nun die aktualisierte PDF-Datei mit dem`Save` Methode der`document` Objekt. Hier ist der entsprechende Code:

```csharp
dataDir = dataDir + "ExtractLinks_out.pdf";
document. Save(dataDir);
```

### Beispielquellcode zum Extrahieren von Links mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document document = new Document(dataDir+ "ExtractLinks.pdf");
// Extrahieren von Aktionen
Page page = document.Pages[1];
AnnotationSelector selector = new AnnotationSelector(new LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
page.Accept(selector);
IList<Annotation> list = selector.Selected;
Annotation annotation = (Annotation)list[0];
dataDir = dataDir + "ExtractLinks_out.pdf";
// Aktualisiertes Dokument speichern
document.Save(dataDir);
Console.WriteLine("\nLinks extracted successfully.\nFile saved at " + dataDir);
```

## Abschluss

Herzlichen Glückwunsch! Sie haben jetzt eine Schritt-für-Schritt-Anleitung zum Extrahieren von Links aus einem PDF-Dokument mit Aspose.PDF für .NET. Mit diesem Code können Sie alle im Dokument vorhandenen Hyperlinks abrufen.

Weitere Informationen zu erweiterten Funktionen zur Linkextraktion finden Sie in der offiziellen Aspose.PDF-Dokumentation.

### FAQs zum Extrahieren von Links in PDF-Dateien

#### F: Was ist Link-Extraktion in einer PDF-Datei?

A: Unter Linkextraktion in einer PDF-Datei versteht man den Vorgang, alle im Dokument vorhandenen Hypertextlinks wiederherzustellen. Auf diese Weise können Sie URLs, interne Dokumentlinks und andere interaktive Elemente abrufen.

#### F: Wie kann die Link-Extraktion meiner PDF-Dokumentanalyse zugute kommen?

A: Die Linkextraktion ist für verschiedene Zwecke nützlich, z. B. zur Inhaltsvalidierung, zum Data Mining und zur Analyse. Sie können damit alle Links in einem PDF-Dokument identifizieren und katalogisieren, um sie später zu untersuchen.

#### F: Wie unterstützt Aspose.PDF für .NET die Linkextraktion?

A: Aspose.PDF für .NET bietet leistungsstarke APIs zum einfachen Extrahieren von Links aus PDF-Dokumenten. Das in diesem Handbuch beschriebene Schritt-für-Schritt-Tutorial zeigt, wie Sie Links mit C# extrahieren.

#### F: Kann ich bestimmte Linktypen extrahieren, z. B. Hyperlinks oder interne Dokumentlinks?

 A: Ja, Sie können gezielt bestimmte Linktypen extrahieren, indem Sie`AnnotationSelector`Klasse. Dadurch können Sie die gewünschten Links entsprechend Ihren Anforderungen filtern und abrufen.

#### F: Ist es möglich, Links aus bestimmten Seiten eines PDF-Dokuments zu extrahieren?

 A: Absolut! Sie können Links von bestimmten Seiten eines PDF-Dokuments extrahieren, indem Sie die Zielseite mit dem`Document.Pages` Sammlung. So können Sie sich auf bestimmte Abschnitte konzentrieren.

#### F: In welchem Format werden die extrahierten Links zurückgegeben?

 A: Die extrahierten Links werden als Instanzen des`Annotation` Klasse. Sie können diese Anmerkungen verarbeiten und analysieren, um Linkdetails abzurufen, einschließlich Ziel-URLs und Linktypen.

#### F: Wie kann ich überprüfen, ob die Linkextraktion korrekt ist?

A: Indem Sie dem bereitgestellten Tutorial und Beispielcode folgen, können Sie eine genaue Linkextraktion sicherstellen. Sie können die extrahierten Anmerkungen analysieren und die URLs und Linkattribute validieren.

#### F: Gibt es beim Extrahieren von Links irgendwelche Einschränkungen?

A: Obwohl die Linkextraktion eine leistungsstarke Funktion ist, ist es wichtig, die Struktur des PDF-Dokuments zu berücksichtigen. In Bildern, Tabellen oder Multimedia-Inhalten eingebettete Links erfordern möglicherweise zusätzliche Bearbeitung.

#### F: Kann ich Links aus passwortgeschützten PDF-Dokumenten extrahieren?

A: Aspose.PDF für .NET kann Links aus passwortgeschützten PDF-Dokumenten extrahieren, solange Sie beim Öffnen des Dokuments die erforderlichen Authentifizierungsdaten angeben.