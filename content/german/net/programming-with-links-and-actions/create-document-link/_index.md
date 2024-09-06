---
title: Dokumentverknüpfung erstellen
linktitle: Dokumentverknüpfung erstellen
second_title: Aspose.PDF für .NET API-Referenz
description: Erstellen Sie mit Aspose.PDF für .NET ganz einfach Links zu anderen PDF-Dokumenten.
type: docs
weight: 30
url: /de/net/programming-with-links-and-actions/create-document-link/
---
Durch Verknüpfen mit einem anderen Dokument in einer PDF-Datei können Sie anklickbare Links erstellen, die Benutzer zu anderen PDF-Dokumenten weiterleiten. Mit Aspose.PDF für .NET können Sie solche Links ganz einfach erstellen, indem Sie dem folgenden Quellcode folgen:

## Schritt 1: Erforderliche Bibliotheken importieren

Bevor Sie beginnen, müssen Sie die erforderlichen Bibliotheken für Ihr C#-Projekt importieren. Hier ist die erforderliche Importanweisung:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.InteractiveFeatures;
```

## Schritt 2: Pfad zum Dokumentenordner festlegen

 In diesem Schritt müssen Sie den Pfad zum Ordner angeben, der die PDF-Datei enthält, zu der Sie einen Link zu einem anderen Dokument hinzufügen möchten. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` ersetzen Sie den folgenden Code durch den tatsächlichen Pfad zu Ihrem Dokumentordner:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 3: Öffnen Sie das PDF-Dokument

Nun öffnen wir das PDF-Dokument, dem wir den Link zu einem anderen Dokument hinzufügen möchten, mit dem folgenden Code:

```csharp
Document document = new Document(dataDir + "CreateDocumentLink.pdf");
```

## Schritt 4: Link zu einem anderen Dokument erstellen

 In diesem Schritt erstellen wir den Link zu einem anderen Dokument mit dem`LinkAnnotation` Annotation. Wir werden die Koordinaten und den Bereich des Links sowie die Navigationsaktion zu einem externen Dokument angeben. Hier ist der entsprechende Code:

```csharp
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link. Action = new GoToRemoteAction(dataDir + "RemoveOpenAction.pdf", 1);
page.Annotations.Add(link);
```

## Schritt 5: Speichern Sie die aktualisierte Datei

Speichern wir nun die aktualisierte PDF-Datei mit dem`Save` Methode der`document` Objekt. Hier ist der entsprechende Code:

```csharp
dataDir = dataDir + "CreateDocumentLink_out.pdf";
document. Save(dataDir);
```

### Beispielquellcode zum Erstellen eines Dokumentlinks mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document document = new Document(dataDir+ "CreateDocumentLink.pdf");
// Verknüpfung erstellen
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link.Action = new GoToRemoteAction(dataDir + "RemoveOpenAction.pdf", 1);
page.Annotations.Add(link);
dataDir = dataDir + "CreateDocumentLink_out.pdf";
// Aktualisiertes Dokument speichern
document.Save(dataDir);
Console.WriteLine("\nDocument link created successfully.\nFile saved at " + dataDir);            
```

## Abschluss

Herzlichen Glückwunsch! Sie haben jetzt eine Schritt-für-Schritt-Anleitung zum Verknüpfen mit anderen Dokumenten mit Aspose.PDF für .NET. Sie können diesen Code verwenden, um anklickbare Links in Ihren PDF-Dateien zu erstellen und Benutzer zu anderen Dokumenten weiterzuleiten.

Weitere Informationen zu den erweiterten Funktionen interaktiver Links finden Sie in der offiziellen Aspose.PDF-Dokumentation.

### FAQs zum Erstellen eines Dokumentlinks

#### F: Was sind Dokumentlinks in PDF-Dateien?

A: Dokumentlinks in PDF-Dateien sind anklickbare Links, die Benutzer zu anderen PDF-Dokumenten weiterleiten. Diese Links verbessern die Navigation, indem sie eine effiziente Möglichkeit bieten, verwandte Inhalte zu verknüpfen und ein nahtloses Leseerlebnis zu ermöglichen.

#### F: Welche Vorteile bietet mir die Erstellung von Dokumentlinks?

A: Durch das Erstellen von Dokumentlinks können Sie Verbindungen zwischen verschiedenen Abschnitten oder Themen in Ihren PDF-Dokumenten herstellen. Mit dieser Funktion können Benutzer problemlos auf zusätzliche Informationen oder verwandte Materialien zugreifen.

#### F: Wie unterstützt Aspose.PDF für .NET die Erstellung von Dokumentlinks?

A: Aspose.PDF für .NET vereinfacht das Erstellen von Dokumentlinks durch die Bereitstellung eines umfassenden Satzes von APIs. Das in diesem Handbuch beschriebene Schritt-für-Schritt-Tutorial zeigt, wie Sie Ihren PDF-Dateien Dokumentlinks hinzufügen.

#### F: Kann ich das Erscheinungsbild von Dokumentlinks anpassen?

A: Absolut! Aspose.PDF für .NET bietet Anpassungsoptionen für das Erscheinungsbild von Dokumentlinks, einschließlich Farbe, Stil und Hover-Effekten. Sie können das Erscheinungsbild an das Design Ihres Dokuments anpassen.

#### F: Ist es möglich, auf bestimmte Abschnitte oder Seiten innerhalb eines anderen Dokuments zu verlinken?

A: Ja, Sie können Links erstellen, die Benutzer zu bestimmten Seiten oder Abschnitten in einem anderen PDF-Dokument führen. Aspose.PDF für .NET bietet die Flexibilität, den Zielort innerhalb des verknüpften Dokuments zu definieren.

#### F: Wie kann ich sicherstellen, dass meine Dokumentlinks funktionieren?

A: Indem Sie dem bereitgestellten Tutorial und dem Beispielcode folgen, können Sie problemlos funktionsfähige Dokumentlinks erstellen. Sie können die Links testen, indem Sie das generierte PDF-Dokument öffnen und auf die Links klicken.

#### F: Kann ich mehrere Dokumentlinks innerhalb einer einzelnen PDF-Datei erstellen?

 A: Natürlich! Sie können mehrere Dokumentlinks innerhalb eines einzelnen PDF-Dokuments erstellen, indem Sie`LinkAnnotation` Anmerkung. Auf diese Weise können Sie Benutzern Zugriff auf verschiedene verwandte Dokumente aus unterschiedlichen Abschnitten gewähren.

#### F: Gibt es Einschränkungen beim Verlinken auf externe Dokumente?

A: Beim Verknüpfen mit externen Dokumenten ist darauf zu achten, dass die verknüpften Dokumente zugänglich sind und sich in den angegebenen Pfaden befinden. Außerdem ist es wichtig, Benutzerberechtigungen und die Kompatibilität der verknüpften Dokumente zu berücksichtigen.

#### F: Kann ich auf im Internet oder in Online-Repositorys gespeicherte Dokumente verlinken?

A: Während sich dieses Tutorial auf das Verknüpfen mit lokalen Dokumenten konzentriert, unterstützt Aspose.PDF für .NET auch das Verknüpfen mit Web-URLs oder Online-Repositories. Sie können den bereitgestellten Code anpassen, um webbasierte Dokumentlinks zu erstellen.