---
title: Erstellen Sie einen Anwendungslink in einer PDF-Datei
linktitle: Erstellen Sie einen Anwendungslink in einer PDF-Datei
second_title: Aspose.PDF für .NET API-Referenz
description: Erstellen Sie mit Aspose.PDF für .NET ganz einfach Anwendungslinks in einer PDF-Datei.
type: docs
weight: 20
url: /de/net/programming-with-links-and-actions/create-application-link/
---
Durch das Erstellen eines Anwendungslinks in einer PDF-Datei können Sie Links zu externen Anwendungen erstellen, beispielsweise zu ausführbaren Dateien oder URLs. Mit Aspose.PDF für .NET können Sie ganz einfach App-Links erstellen, indem Sie dem folgenden Quellcode folgen:

## Schritt 1: Erforderliche Bibliotheken importieren

Bevor Sie beginnen, müssen Sie die erforderlichen Bibliotheken für Ihr C#-Projekt importieren. Hier ist die notwendige Importanweisung:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.InteractiveFeatures;
```

## Schritt 2: Legen Sie den Pfad zum Dokumentenordner fest

 In diesem Schritt müssen Sie den Pfad zu dem Ordner angeben, der die PDF-Datei enthält, zu der Sie einen App-Link hinzufügen möchten. Ersetzen`"YOUR DOCUMENT DIRECTORY"`Geben Sie im folgenden Code den tatsächlichen Pfad zu Ihrem Dokumentenordner ein:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 3: Öffnen Sie das PDF-Dokument

Nun öffnen wir das PDF-Dokument, zu dem wir einen Bewerbungslink hinzufügen möchten, mit dem folgenden Code:

```csharp
Document document = new Document(dataDir + "CreateApplicationLink.pdf");
```

## Schritt 4: Erstellen Sie den Anwendungslink

 In diesem Schritt erstellen wir den Anwendungslink mithilfe von`LinkAnnotation`Anmerkung. Wir geben die Koordinaten und den Bereich des Links sowie die Aktion zum Starten der Anwendung an. Hier ist der entsprechende Code:

```csharp
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link. Action = new LaunchAction(document, dataDir + "CreateApplicationLink.pdf");
page.Annotations.Add(link);
```

## Schritt 5: Speichern Sie die aktualisierte Datei

 Speichern wir nun die aktualisierte PDF-Datei mit`Save` Methode der`document` Objekt. Hier ist der entsprechende Code:

```csharp
dataDir = dataDir + "CreateApplicationLink_out.pdf";
document. Save(dataDir);
```

### Beispielquellcode für „Anwendungslink erstellen“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document document = new Document( dataDir + "CreateApplicationLink.pdf");
// Verknüpfung erstellen
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link.Action = new LaunchAction(document, dataDir + "CreateApplicationLink.pdf");
page.Annotations.Add(link);
dataDir = dataDir + "CreateApplicationLink_out.pdf";
// Aktualisiertes Dokument speichern
document.Save(dataDir);
Console.WriteLine("\nApplication link created successfully.\nFile saved at " + dataDir);
```

## Abschluss

Herzlichen Glückwunsch! Sie haben jetzt eine Schritt-für-Schritt-Anleitung zum Erstellen von App-Links mit Aspose.PDF für .NET. Mit diesem Code können Sie Links zu externen Anwendungen in Ihre PDF-Dokumente einfügen.

Weitere Informationen zu den erweiterten Funktionen interaktiver Links finden Sie unbedingt in der offiziellen Aspose.PDF-Dokumentation.

### FAQs zum Erstellen eines Anwendungslinks in einer PDF-Datei

#### F: Was sind Anwendungslinks in PDF-Dateien?

A: Mit Anwendungslinks in PDF-Dateien können Sie Links erstellen, die beim Klicken externe Anwendungen wie ausführbare Dateien oder URLs öffnen. Diese Funktion verbessert die Interaktivität und bietet eine bequeme Möglichkeit, Benutzer mit externen Ressourcen zu verbinden.

#### F: Wie erleichtert Aspose.PDF für .NET die Erstellung von Anwendungslinks?

A: Aspose.PDF für .NET vereinfacht den Prozess der Erstellung von Anwendungsverknüpfungen durch die Bereitstellung eines umfassenden Satzes an Tools und APIs. Die Schritt-für-Schritt-Anleitung in diesem Handbuch zeigt, wie Sie App-Links zu Ihren PDF-Dokumenten hinzufügen.

#### F: Kann ich das Erscheinungsbild von Anwendungslinks anpassen?

A: Auf jeden Fall! Mit Aspose.PDF für .NET haben Sie die Kontrolle über das Erscheinungsbild von Anwendungslinks. Sie können Attribute wie Farbe, Stil und Hover-Effekte angeben, um ein optisch ansprechendes Benutzererlebnis zu gewährleisten.

#### F: Gibt es Einschränkungen hinsichtlich der Arten externer Anwendungen, zu denen ich verlinken kann?

A: Aspose.PDF für .NET ermöglicht Ihnen die Verknüpfung mit einer Vielzahl externer Anwendungen, einschließlich ausführbarer Dateien, URLs und Dokumente. Beim Verknüpfen mit ausführbaren Dateien ist es jedoch wichtig, die Benutzersicherheit und -kompatibilität zu berücksichtigen.

#### F: Wie kann ich überprüfen, ob meine Anwendungslinks ordnungsgemäß funktionieren?

A: Indem Sie den Anweisungen des Tutorials folgen und den bereitgestellten Beispielcode verwenden, können Sie sicher funktionierende Anwendungslinks erstellen. Anschließend können Sie die Links testen, indem Sie das generierte PDF-Dokument öffnen und auf die Anwendungslinks klicken.

#### F: Kann ich in einem einzigen PDF-Dokument mehrere Bewerbungslinks erstellen?

 A: Ja, Sie können mit dem mehrere Anwendungslinks in einem einzigen PDF-Dokument erstellen`LinkAnnotation` Anmerkung. Dadurch können Sie Benutzern Zugriff auf verschiedene externe Anwendungen aus verschiedenen Abschnitten des Dokuments gewähren.

#### F: Gibt es Sicherheitsaspekte bei der Verwendung von Anwendungslinks?
A: Beim Verknüpfen mit ausführbaren Dateien ist es wichtig sicherzustellen, dass die verknüpften Anwendungen sicher und vertrauenswürdig sind. Berücksichtigen Sie außerdem Benutzerberechtigungen und informieren Sie Benutzer über den möglichen Start externer Anwendungen.

#### F: Wie füge ich Anwendungslinks zu URLs oder Webseiten hinzu?

A: Während sich dieses Tutorial auf die Erstellung von Links zu externen Anwendungen konzentriert, unterstützt Aspose.PDF für .NET auch die Erstellung von Hyperlinks zu URLs oder Webseiten. Sie können den bereitgestellten Code anpassen, um Weblinks in Ihren PDF-Dokumenten zu erstellen.

#### F: Kann ich Aspose.PDF für .NET verwenden, um Informationen aus verknüpften externen Anwendungen zu extrahieren?

A: Ja, Aspose.PDF für .NET bietet Funktionen zum Extrahieren und Bearbeiten von Informationen aus verknüpften externen Anwendungen. Sie können die umfangreichen Funktionen der Bibliothek erkunden, um verschiedene Aufgaben im Zusammenhang mit verknüpften Inhalten auszuführen.