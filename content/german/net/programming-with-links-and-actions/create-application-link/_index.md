---
title: Anwendungslink in PDF-Datei erstellen
linktitle: Anwendungslink in PDF-Datei erstellen
second_title: Aspose.PDF für .NET API-Referenz
description: Erstellen Sie mit Aspose.PDF für .NET ganz einfach Anwendungslinks in PDF-Dateien.
type: docs
weight: 20
url: /de/net/programming-with-links-and-actions/create-application-link/
---
Durch das Erstellen eines Anwendungslinks in einer PDF-Datei können Sie Links zu externen Anwendungen erstellen, z. B. ausführbare Dateien oder URLs. Mit Aspose.PDF für .NET können Sie ganz einfach App-Links erstellen, indem Sie dem folgenden Quellcode folgen:

## Schritt 1: Erforderliche Bibliotheken importieren

Bevor Sie beginnen, müssen Sie die erforderlichen Bibliotheken für Ihr C#-Projekt importieren. Hier ist die erforderliche Importanweisung:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.InteractiveFeatures;
```

## Schritt 2: Pfad zum Dokumentenordner festlegen

In diesem Schritt müssen Sie den Pfad zum Ordner angeben, der die PDF-Datei enthält, zu der Sie einen App-Link hinzufügen möchten. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` ersetzen Sie den folgenden Code durch den tatsächlichen Pfad zu Ihrem Dokumentordner:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 3: Öffnen Sie das PDF-Dokument

Nun öffnen wir mit dem folgenden Code das PDF-Dokument, dem wir einen Anwendungslink hinzufügen möchten:

```csharp
Document document = new Document(dataDir + "CreateApplicationLink.pdf");
```

## Schritt 4: Erstellen Sie den Anwendungslink

 In diesem Schritt erstellen wir den Anwendungslink mit dem`LinkAnnotation` Annotation. Wir werden die Koordinaten und den Bereich des Links sowie die Aktion zum Starten der Anwendung angeben. Hier ist der entsprechende Code:

```csharp
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link. Action = new LaunchAction(document, dataDir + "CreateApplicationLink.pdf");
page.Annotations.Add(link);
```

## Schritt 5: Speichern Sie die aktualisierte Datei

Speichern wir nun die aktualisierte PDF-Datei mit dem`Save` Methode der`document` Objekt. Hier ist der entsprechende Code:

```csharp
dataDir = dataDir + "CreateApplicationLink_out.pdf";
document. Save(dataDir);
```

### Beispielquellcode zum Erstellen eines Anwendungslinks mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
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

Herzlichen Glückwunsch! Sie haben jetzt eine Schritt-für-Schritt-Anleitung zum Erstellen von App-Links mit Aspose.PDF für .NET. Mit diesem Code können Sie Ihren PDF-Dokumenten Links zu externen Anwendungen hinzufügen.

Weitere Informationen zu den erweiterten Funktionen interaktiver Links finden Sie in der offiziellen Aspose.PDF-Dokumentation.

### FAQs zum Erstellen eines Bewerbungslinks in einer PDF-Datei

#### F: Was sind Anwendungslinks in PDF-Dateien?

A: Mit Anwendungslinks in PDF-Dateien können Sie Links erstellen, die beim Anklicken externe Anwendungen wie ausführbare Dateien oder URLs öffnen. Diese Funktion verbessert die Interaktivität und bietet eine bequeme Möglichkeit, Benutzer mit externen Ressourcen zu verbinden.

#### F: Wie erleichtert Aspose.PDF für .NET die Erstellung von Anwendungslinks?

A: Aspose.PDF für .NET vereinfacht das Erstellen von Anwendungslinks, indem es einen umfassenden Satz an Tools und APIs bereitstellt. Das in diesem Handbuch enthaltene Schritt-für-Schritt-Tutorial zeigt, wie Sie Ihren PDF-Dokumenten Anwendungslinks hinzufügen.

#### F: Kann ich das Erscheinungsbild von Anwendungslinks anpassen?

A: Absolut! Mit Aspose.PDF für .NET haben Sie Kontrolle über das Erscheinungsbild von Anwendungslinks. Sie können Attribute wie Farbe, Stil und Hover-Effekte angeben, um ein optisch ansprechendes Benutzererlebnis zu gewährleisten.

#### F: Gibt es Einschränkungen hinsichtlich der Arten externer Anwendungen, auf die ich verlinken kann?

A: Aspose.PDF für .NET ermöglicht Ihnen die Verknüpfung mit einer Vielzahl externer Anwendungen, einschließlich ausführbarer Dateien, URLs und Dokumente. Beim Verknüpfen mit ausführbaren Dateien ist jedoch die Benutzersicherheit und Kompatibilität zu berücksichtigen.

#### F: Wie kann ich überprüfen, ob meine Anwendungslinks ordnungsgemäß funktionieren?

A: Wenn Sie den Anweisungen des Tutorials folgen und den bereitgestellten Beispielcode verwenden, können Sie problemlos funktionsfähige Anwendungslinks erstellen. Anschließend können Sie die Links testen, indem Sie das generierte PDF-Dokument öffnen und auf die Anwendungslinks klicken.

#### F: Kann ich mehrere Anwendungslinks innerhalb eines einzelnen PDF-Dokuments erstellen?

 A: Ja, Sie können mehrere Anwendungslinks innerhalb eines einzigen PDF-Dokuments erstellen, indem Sie`LinkAnnotation` Anmerkung. Auf diese Weise können Sie Benutzern von verschiedenen Abschnitten des Dokuments aus Zugriff auf verschiedene externe Anwendungen gewähren.

#### F: Gibt es Sicherheitsaspekte bei der Verwendung von Anwendungslinks?
A: Beim Verknüpfen mit ausführbaren Dateien ist es wichtig, sicherzustellen, dass die verknüpften Anwendungen sicher und vertrauenswürdig sind. Berücksichtigen Sie außerdem die Benutzerberechtigungen und informieren Sie Benutzer über den möglichen Start externer Anwendungen.

#### F: Wie füge ich Anwendungslinks zu URLs oder Webseiten hinzu?

A: Während sich dieses Tutorial auf das Erstellen von Links zu externen Anwendungen konzentriert, unterstützt Aspose.PDF für .NET auch das Erstellen von Hyperlinks zu URLs oder Webseiten. Sie können den bereitgestellten Code anpassen, um Weblinks in Ihren PDF-Dokumenten zu erstellen.

#### F: Kann ich Aspose.PDF für .NET verwenden, um Informationen aus verknüpften externen Anwendungen zu extrahieren?

A: Ja, Aspose.PDF für .NET bietet Funktionen zum Extrahieren und Bearbeiten von Informationen aus verknüpften externen Anwendungen. Sie können die umfangreichen Funktionen der Bibliothek erkunden, um verschiedene Aufgaben im Zusammenhang mit verknüpften Inhalten auszuführen.