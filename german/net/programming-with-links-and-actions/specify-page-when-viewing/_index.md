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