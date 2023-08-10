---
title: Dokumentlink erstellen
linktitle: Dokumentlink erstellen
second_title: Aspose.PDF für .NET API-Referenz
description: Erstellen Sie mit Aspose.PDF für .NET ganz einfach Links zu anderen PDF-Dokumenten.
type: docs
weight: 30
url: /de/net/programming-with-links-and-actions/create-document-link/
---
Durch die Verknüpfung mit einem anderen Dokument in einer PDF-Datei können Sie anklickbare Links erstellen, die Benutzer zu anderen PDF-Dokumenten weiterleiten. Mit Aspose.PDF für .NET können Sie solche Links ganz einfach erstellen, indem Sie dem folgenden Quellcode folgen:

## Schritt 1: Erforderliche Bibliotheken importieren

Bevor Sie beginnen, müssen Sie die erforderlichen Bibliotheken für Ihr C#-Projekt importieren. Hier ist die notwendige Importanweisung:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.InteractiveFeatures;
```

## Schritt 2: Legen Sie den Pfad zum Dokumentenordner fest

In diesem Schritt müssen Sie den Pfad zu dem Ordner angeben, der die PDF-Datei enthält, zu der Sie einen Link zu einem anderen Dokument hinzufügen möchten. Ersetzen`"YOUR DOCUMENT DIRECTORY"`Geben Sie im folgenden Code den tatsächlichen Pfad zu Ihrem Dokumentenordner ein:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 3: Öffnen Sie das PDF-Dokument

Nun öffnen wir das PDF-Dokument, zu dem wir den Link zu einem anderen Dokument hinzufügen möchten, mit dem folgenden Code:

```csharp
Document document = new Document(dataDir + "CreateDocumentLink.pdf");
```

## Schritt 4: Erstellen Sie den Link zu einem anderen Dokument

 In diesem Schritt erstellen wir mithilfe von den Link zu einem anderen Dokument`LinkAnnotation` Anmerkung. Wir geben die Koordinaten und den Bereich des Links sowie die Navigationsaktion zu einem externen Dokument an. Hier ist der entsprechende Code:

```csharp
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link. Action = new GoToRemoteAction(dataDir + "RemoveOpenAction.pdf", 1);
page.Annotations.Add(link);
```

## Schritt 5: Speichern Sie die aktualisierte Datei

 Speichern wir nun die aktualisierte PDF-Datei mit`Save` Methode der`document` Objekt. Hier ist der entsprechende Code:

```csharp
dataDir = dataDir + "CreateDocumentLink_out.pdf";
document. Save(dataDir);
```

### Beispielquellcode für „Dokumentverknüpfung erstellen“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
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

Herzlichen Glückwunsch! Sie verfügen nun über eine Schritt-für-Schritt-Anleitung zum Verknüpfen mit anderen Dokumenten mit Aspose.PDF für .NET. Mit diesem Code können Sie anklickbare Links in Ihren PDF-Dateien erstellen und Benutzer zu anderen Dokumenten weiterleiten.

Weitere Informationen zu den erweiterten Funktionen interaktiver Links finden Sie unbedingt in der offiziellen Aspose.PDF-Dokumentation.

### FAQs zum Erstellen eines Dokumentlinks

#### F: Was sind Dokumentlinks in PDF-Dateien?

A: Dokumentlinks in PDF-Dateien sind anklickbare Links, die Benutzer zu anderen PDF-Dokumenten weiterleiten. Diese Links verbessern die Navigation, indem sie eine effiziente Möglichkeit bieten, verwandte Inhalte zu verbinden und ein nahtloses Leseerlebnis zu ermöglichen.

#### F: Wie kann ich von der Erstellung von Dokumentverknüpfungen profitieren?

A: Durch das Erstellen von Dokumentverknüpfungen können Sie Verbindungen zwischen verschiedenen Abschnitten oder Themen in Ihren PDF-Dokumenten herstellen. Mit dieser Funktion können Benutzer problemlos auf ergänzende Informationen oder verwandte Materialien zugreifen.

#### F: Wie unterstützt Aspose.PDF für .NET die Erstellung von Dokumentlinks?

A: Aspose.PDF für .NET vereinfacht den Prozess der Erstellung von Dokumentverknüpfungen durch die Bereitstellung eines umfassenden Satzes von APIs. Das in diesem Handbuch beschriebene Schritt-für-Schritt-Tutorial zeigt, wie Sie Dokumentlinks zu Ihren PDF-Dateien hinzufügen.

#### F: Kann ich das Erscheinungsbild von Dokumentlinks anpassen?

A: Auf jeden Fall! Aspose.PDF für .NET bietet Anpassungsoptionen für das Erscheinungsbild von Dokumentlinks, einschließlich Farbe, Stil und Hover-Effekten. Sie können das Erscheinungsbild an das Design Ihres Dokuments anpassen.

#### F: Ist es möglich, auf bestimmte Abschnitte oder Seiten in einem anderen Dokument zu verlinken?

A: Ja, Sie können Links erstellen, die Benutzer zu bestimmten Seiten oder Abschnitten in einem anderen PDF-Dokument führen. Aspose.PDF für .NET bietet die Flexibilität, den Zielort innerhalb des verknüpften Dokuments zu definieren.

#### F: Wie kann ich sicherstellen, dass meine Dokumentverknüpfungen funktionieren?

A: Wenn Sie dem bereitgestellten Tutorial und dem Beispielcode folgen, können Sie problemlos funktionale Dokumentverknüpfungen erstellen. Sie können die Links testen, indem Sie das generierte PDF-Dokument öffnen und auf die Links klicken.

#### F: Kann ich in einer einzigen PDF-Datei mehrere Dokumentverknüpfungen erstellen?

 A: Auf jeden Fall! Sie können mit dem mehrere Dokumentverknüpfungen innerhalb eines einzelnen PDF-Dokuments erstellen`LinkAnnotation`Anmerkung. Auf diese Weise können Sie Benutzern Zugriff auf verschiedene verwandte Dokumente aus verschiedenen Abschnitten gewähren.

#### F: Gibt es Einschränkungen bei der Verknüpfung mit externen Dokumenten?

A: Stellen Sie beim Verknüpfen mit externen Dokumenten sicher, dass die verknüpften Dokumente zugänglich sind und sich in den angegebenen Pfaden befinden. Es ist auch wichtig, Benutzerberechtigungen und die Kompatibilität verknüpfter Dokumente zu berücksichtigen.

#### F: Kann ich auf Dokumente verlinken, die im Web oder in Online-Repositories gespeichert sind?

A: Während sich dieses Tutorial auf die Verknüpfung mit lokalen Dokumenten konzentriert, unterstützt Aspose.PDF für .NET auch die Verknüpfung mit Web-URLs oder Online-Repositorys. Sie können den bereitgestellten Code anpassen, um webbasierte Dokumentverknüpfungen zu erstellen.