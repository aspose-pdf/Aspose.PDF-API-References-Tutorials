---
title: Seite beim Anzeigen angeben
linktitle: Seite beim Anzeigen angeben
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie beim Anzeigen einer PDF-Datei mit Aspose.PDF für .NET eine Seite angeben.
type: docs
weight: 110
url: /de/net/programming-with-links-and-actions/specify-page-when-viewing/
---
Erfahren Sie in dieser Schritt-für-Schritt-Anleitung, wie Sie beim Anzeigen einer PDF-Datei mit Aspose.PDF für .NET eine Seite angeben.

## Schritt 1: Einrichten der Umgebung

Stellen Sie sicher, dass Sie Ihre Entwicklungsumgebung mit einem C#-Projekt und den entsprechenden Aspose.PDF-Referenzen eingerichtet haben.

## Schritt 2: Laden der PDF-Datei

Legen Sie den Verzeichnispfad Ihrer Dokumente fest und laden Sie die PDF-Datei mit dem folgenden Code hoch:

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Laden Sie die PDF-Datei
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
```

## Schritt 3: Zielseite festlegen

Rufen Sie die Zielseiteninstanz mit dem folgenden Code ab:

```csharp
Page page2 = doc.Pages[2];
```

 Sie können den Index anpassen`[2]` , um die gewünschte Seite auszuwählen.

## Schritt 4: Zoom-Einstellung konfigurieren

Erstellen Sie eine Variable, um den Zoomfaktor der Zielseite festzulegen:

```csharp
double zoom = 1;
```

Sie können den Zoomwert Ihren Bedürfnissen entsprechend anpassen.

## Schritt 5: Erstellen der Navigationsaktion

Erstellen Sie eine Instanz der Navigationsaktion unter Verwendung der angegebenen Zielseite:

```csharp
GoToAction action = new GoToAction(doc.Pages[2]);
```

## Schritt 6: Ziel festlegen

Legen Sie das Ziel fest, um über Koordinaten und Zoom zur Zielseite zu gelangen:

```csharp
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
```

## Schritt 7: Konfigurieren der Aktion „Dokument öffnen“

Legen Sie die Dokument-Öffnen-Aktion mit der erstellten Navigationsaktion fest:

```csharp
doc. OpenAction = action;
```

## Schritt 8: Speichern Sie das aktualisierte Dokument

 Speichern Sie das aktualisierte Dokument mit dem`Save` Verfahren:

```csharp
doc.Save(dataDir + "goto2page_out.pdf");
```

### Beispielquellcode für „Seite beim Anzeigen angeben“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Laden Sie die PDF-Datei
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
// Holen Sie sich die Instanz der zweiten Seite des Dokuments
Page page2 = doc.Pages[2];
// Erstellen Sie die Variable, um den Zoomfaktor der Zielseite festzulegen
double zoom = 1;
// Erstellen einer GoToAction-Instanz
GoToAction action = new GoToAction(doc.Pages[2]);
// Gehe zu Seite 2
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
// Festlegen der Aktion zum Öffnen des Dokuments
doc.OpenAction = action;
// Aktualisiertes Dokument speichern
doc.Save(dataDir + "goto2page_out.pdf");
```

## Abschluss

Herzlichen Glückwunsch! Sie wissen jetzt, wie Sie beim Anzeigen einer PDF-Datei mit Aspose.PDF für .NET eine Seite angeben. Verwenden Sie dieses Wissen, um das Benutzererlebnis beim Anzeigen Ihrer PDF-Dokumente anzupassen.

Nachdem Sie dieses Handbuch abgeschlossen haben, können Sie diese Konzepte auf Ihre eigenen Projekte anwenden und die von Aspose.PDF für .NET angebotenen Funktionen weiter erkunden.

### Häufig gestellte Fragen 

#### F: Welchen Zweck hat die Angabe einer Zielseite beim Anzeigen einer PDF-Datei?

A: Durch die Angabe einer Zielseite können Sie steuern, welche Seite eines PDF-Dokuments beim Öffnen der Datei angezeigt wird. Dies kann das Benutzererlebnis verbessern, indem der Benutzer auf eine bestimmte Seite von Interesse weitergeleitet wird.

#### F: Warum ist die Angabe einer Zielseite in PDF-Dokumenten hilfreich?

A: Das Angeben einer Zielseite ist nützlich, wenn Sie Benutzer zu einem bestimmten Abschnitt oder Inhalt innerhalb eines PDF-Dokuments führen möchten, ohne dass sie manuell durch die Seiten navigieren müssen.

#### F: Wie erleichtert Aspose.PDF für .NET die Angabe einer Zielseite zur Anzeige?

A: Aspose.PDF für .NET bietet APIs, mit denen Sie die Anfangsansicht eines PDF-Dokuments festlegen können, einschließlich der Zielseite, der Zoomstufe und anderer Anzeigeeigenschaften.

#### F: Kann ich jede beliebige Seite als Zielseite angeben?

A: Ja, Sie können jede beliebige Seite innerhalb des PDF-Dokuments als Zielseite für die Anzeige angeben. Verwenden Sie dazu einfach den entsprechenden Index, um die gewünschte Seite auszuwählen.

#### F: Welche Bedeutung hat der Zoomfaktor bei der Angabe einer Zielseite?

A: Der Zoomfaktor bestimmt den Vergrößerungsgrad, der beim Öffnen des PDF-Dokuments auf die Zielseite angewendet wird. Er steuert, wie viel Inhalt im Ansichtsfenster angezeigt wird.

#### F: Kann ich für unterschiedliche Zielseiten unterschiedliche Zoomfaktoren einstellen?

A: Ja, Sie können verschiedene Zoomfaktoren für verschiedene Zielseiten festlegen, indem Sie separate`GoToAction` Instanzen und entsprechende Konfiguration ihrer Ziele.

#### F: Gibt es Einschränkungen bei der Angabe einer Zielseite?

A: Die Angabe einer Zielseite beschränkt sich auf die Steuerung der anfänglichen Ansicht beim Öffnen der PDF-Datei. Sobald die PDF-Datei angezeigt wird, hat sie keine Auswirkungen auf Benutzerinteraktionen oder die Navigation.

#### F: Kann ich diese Funktion verwenden, um Präsentationen innerhalb eines PDF-Dokuments zu erstellen?

A: Ja, Sie können diese Funktion verwenden, um präsentationsähnliche Erlebnisse innerhalb eines PDF-Dokuments zu erstellen und Benutzer durch verschiedene Abschnitte oder Themen zu führen.

#### F: Kann ich andere Aspekte der Anfangsansicht anpassen, beispielsweise das Seitenlayout?

A: Ja, Aspose.PDF für .NET bietet Eigenschaften zum Anpassen anderer Aspekte der Anfangsansicht, einschließlich Seitenlayout, Seitenmodus und mehr.

#### F: Wie kann ich testen, ob die angegebene Zielseite und der Zoomfaktor wie gewünscht funktionieren?

A: Nachdem Sie den bereitgestellten Code angewendet haben, um die Zielseite und den Zoomfaktor festzulegen, öffnen Sie die geänderte PDF-Datei und überprüfen Sie, ob sie mit der richtigen Seite und Zoomstufe geöffnet wird.