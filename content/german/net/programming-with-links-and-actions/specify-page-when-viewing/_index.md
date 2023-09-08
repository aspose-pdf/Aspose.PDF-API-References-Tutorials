---
title: Geben Sie beim Anzeigen die Seite an
linktitle: Geben Sie beim Anzeigen die Seite an
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
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Laden Sie die PDF-Datei
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
```

## Schritt 3: Zielseite angeben

Rufen Sie die Zielseiteninstanz mit dem folgenden Code ab:

```csharp
Page page2 = doc.Pages[2];
```

 Sie können den Index anpassen`[2]` um die gewünschte Seite auszuwählen.

## Schritt 4: Konfigurieren der Zoomeinstellung

Erstellen Sie eine Variable, um den Zoomfaktor der Zielseite festzulegen:

```csharp
double zoom = 1;
```

Sie können den Zoomwert entsprechend Ihren Anforderungen anpassen.

## Schritt 5: Erstellen Sie die Navigationsaktion

Erstellen Sie eine Instanz der Navigationsaktion mit der angegebenen Zielseite:

```csharp
GoToAction action = new GoToAction(doc.Pages[2]);
```

## Schritt 6: Ziel festlegen

Legen Sie das Ziel fest, um mithilfe von Koordinaten und Zoom zur Zielseite zu gelangen:

```csharp
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
```

## Schritt 7: Konfigurieren der Aktion zum Öffnen des Dokuments

Legen Sie die Aktion zum Öffnen des Dokuments mit der erstellten Navigationsaktion fest:

```csharp
doc. OpenAction = action;
```

## Schritt 8: Speichern Sie das aktualisierte Dokument

 Speichern Sie das aktualisierte Dokument mit`Save` Methode:

```csharp
doc.Save(dataDir + "goto2page_out.pdf");
```

### Beispielquellcode für „Seite beim Anzeigen angeben“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Laden Sie die PDF-Datei
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
// Rufen Sie die Instanz der zweiten Seite des Dokuments ab
Page page2 = doc.Pages[2];
// Erstellen Sie die Variable, um den Zoomfaktor der Zielseite festzulegen
double zoom = 1;
// Erstellen Sie eine GoToAction-Instanz
GoToAction action = new GoToAction(doc.Pages[2]);
// Gehe zu Seite 2
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
// Legen Sie die Aktion zum Öffnen des Dokuments fest
doc.OpenAction = action;
// Aktualisiertes Dokument speichern
doc.Save(dataDir + "goto2page_out.pdf");
```

## Abschluss

Herzlichen Glückwunsch! Sie wissen jetzt, wie Sie beim Anzeigen einer PDF-Datei mit Aspose.PDF für .NET eine Seite angeben. Nutzen Sie dieses Wissen, um das Benutzererlebnis in Ihren PDF-Dokumenten anzupassen.

Nachdem Sie dieses Handbuch abgeschlossen haben, können Sie diese Konzepte auf Ihre eigenen Projekte anwenden und die von Aspose.PDF für .NET angebotenen Funktionen weiter erkunden.

### FAQs 

#### F: Wozu dient die Angabe einer Zielseite beim Anzeigen einer PDF-Datei?

A: Durch die Angabe einer Zielseite können Sie steuern, welche Seite eines PDF-Dokuments beim Öffnen der Datei angezeigt wird. Dies kann die Benutzererfahrung verbessern, indem sie auf eine bestimmte Seite weitergeleitet wird, die sie interessiert.

#### F: Wie kann die Angabe einer Zielseite in PDF-Dokumenten nützlich sein?

A: Die Angabe einer Zielseite ist von Vorteil, wenn Sie Benutzer zu einem bestimmten Abschnitt oder Inhalt in einem PDF-Dokument führen möchten, ohne dass sie manuell durch die Seiten navigieren müssen.

#### F: Wie erleichtert Aspose.PDF für .NET die Angabe einer Zielseite für die Anzeige?

A: Aspose.PDF für .NET bietet APIs, mit denen Sie die anfängliche Ansicht eines PDF-Dokuments festlegen können, einschließlich der Zielseite, der Zoomstufe und anderer Anzeigeeigenschaften.

#### F: Kann ich eine beliebige Seite als Zielseite angeben?

A: Ja, Sie können jede Seite im PDF-Dokument als Zielseite für die Anzeige angeben. Wählen Sie einfach über den entsprechenden Index die gewünschte Seite aus.

#### F: Welche Bedeutung hat der Zoomfaktor bei der Angabe einer Zielseite?

A: Der Zoomfaktor bestimmt die Vergrößerungsstufe, die beim Öffnen des PDF-Dokuments auf die Zielseite angewendet wird. Es steuert, wie viel Inhalt im Ansichtsfenster angezeigt wird.

#### F: Kann ich für verschiedene Zielseiten unterschiedliche Zoomfaktoren festlegen?

A: Ja, Sie können unterschiedliche Zoomfaktoren für verschiedene Zielseiten festlegen, indem Sie separate erstellen`GoToAction` Instanzen und konfigurieren ihre Ziele entsprechend.

#### F: Gibt es Einschränkungen bei der Angabe einer Zielseite?

A: Die Angabe einer Zielseite beschränkt sich auf die Steuerung der ersten Ansicht beim Öffnen der PDF-Datei. Sobald die PDF-Datei angezeigt wird, hat dies keinen Einfluss auf Benutzerinteraktionen oder Navigation.

#### F: Kann ich diese Funktion verwenden, um Präsentationen innerhalb eines PDF-Dokuments zu erstellen?

A: Ja, Sie können diese Funktion verwenden, um präsentationsähnliche Erlebnisse innerhalb eines PDF-Dokuments zu erstellen und Benutzer durch verschiedene Abschnitte oder Themen zu führen.

#### F: Kann ich andere Aspekte der ersten Ansicht anpassen, beispielsweise das Seitenlayout?

A: Ja, Aspose.PDF für .NET bietet Eigenschaften zum Anpassen anderer Aspekte der Erstansicht, einschließlich Seitenlayout, Seitenmodus und mehr.

#### F: Wie kann ich testen, ob die angegebene Zielseite und der Zoomfaktor wie vorgesehen funktionieren?

A: Nachdem Sie den bereitgestellten Code zur Angabe der Zielseite und des Zoomfaktors angewendet haben, öffnen Sie die geänderte PDF-Datei und überprüfen Sie, ob sie mit der richtigen Seite und Zoomstufe geöffnet wird.