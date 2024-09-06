---
title: Öffnen-Aktion entfernen
linktitle: Öffnen-Aktion entfernen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET die Öffnungsaktion aus einer PDF-Datei entfernen.
type: docs
weight: 80
url: /de/net/programming-with-links-and-actions/remove-open-action/
---
Erfahren Sie in dieser Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.PDF für .NET die Öffnungsaktion aus einer PDF-Datei entfernen.

## Schritt 1: Einrichten der Umgebung

Stellen Sie sicher, dass Sie Ihre Entwicklungsumgebung mit einem C#-Projekt und den entsprechenden Aspose.PDF-Referenzen eingerichtet haben.

## Schritt 2: Laden der PDF-Datei

Legen Sie den Verzeichnispfad Ihrer Dokumente fest und laden Sie die PDF-Datei mit dem folgenden Code hoch:

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Öffnen Sie das Dokument
Document document = new Document(dataDir + "RemoveOpenAction.pdf");
```

## Schritt 3: Offene Aktion löschen

 Entfernen Sie die Öffnungsaktion aus dem Dokument, indem Sie den`OpenAction` Eigenschaft auf null:

```csharp
document. OpenAction = null;
```

## Schritt 4: Speichern Sie das aktualisierte Dokument

 Speichern Sie das aktualisierte Dokument mit dem`Save` Verfahren:

```csharp
dataDir = dataDir + "RemoveOpenAction_out.pdf";
document. Save(dataDir);
```

## Schritt 5: Ergebnis anzeigen

Zeigen Sie eine Meldung an, dass die Öffnungsaktion erfolgreich entfernt wurde, und geben Sie den Speicherort der gespeicherten Datei an:

```csharp
Console.WriteLine("\nOpen action deleted successfully.\nFile saved to location: " + dataDir);
```

### Beispielquellcode für die Aktion „Remove Open“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document document = new Document(dataDir + "RemoveOpenAction.pdf");
// Aktion „Dokument öffnen“ entfernen
document.OpenAction = null;
dataDir = dataDir + "RemoveOpenAction_out.pdf";
// Aktualisiertes Dokument speichern
document.Save(dataDir);
Console.WriteLine("\nOpen action removed successfully.\nFile saved at " + dataDir); 
```

## Abschluss

Herzlichen Glückwunsch! Jetzt wissen Sie, wie Sie mit Aspose.PDF für .NET die Öffnungsaktion aus einer PDF-Datei entfernen. Verwenden Sie dieses Wissen, um die Eigenschaften und das Verhalten von PDF-Dateien in Ihren Projekten anzupassen.

Nachdem Sie dieses Handbuch abgeschlossen haben, können Sie diese Konzepte auf Ihre eigenen Projekte anwenden und die von Aspose.PDF für .NET angebotenen Funktionen weiter erkunden.

### Häufig gestellte Fragen 

#### F: Was ist die „Öffnen-Aktion“ in einer PDF-Datei?

A: Die „Öffnen-Aktion“ in einer PDF-Datei ist eine Anweisung, die angibt, was beim Öffnen der PDF-Datei passieren soll. Dazu können Aktionen wie das Navigieren zu einer bestimmten Seite oder Stelle im Dokument, das Starten einer externen Anwendung oder das Anzeigen einer bestimmten Ansicht gehören.

#### F: Warum sollte ich die Öffnungsaktion aus einer PDF-Datei entfernen wollen?

A: Das Entfernen der Öffnungsaktion kann die Sicherheit, das Benutzererlebnis und die Kontrolle über die Darstellung der PDF-Datei beim Öffnen verbessern. Beispielsweise möchten Sie möglicherweise die automatische Navigation verhindern oder bestimmte Aktionen beim Öffnen des Dokuments deaktivieren.

#### F: Wie hilft Aspose.PDF für .NET beim Entfernen der Öffnungsaktion?

A: Aspose.PDF für .NET bietet APIs zur Bearbeitung verschiedener Aspekte von PDF-Dateien. Dieses Tutorial zeigt, wie die Öffnungsaktion mit C#-Code entfernt wird.

#### F: Gibt es potenzielle Risiken oder Überlegungen beim Entfernen der offenen Aktion?

A: Das Entfernen der Öffnungsaktion kann das Standardverhalten der PDF-Datei ändern. Stellen Sie daher sicher, dass es der beabsichtigten Benutzererfahrung entspricht. Testen Sie die geänderte PDF-Datei gründlich, um sicherzustellen, dass das Entfernen keine Auswirkungen auf andere Funktionen hat.

#### F: Kann ich die Öffnungsaktion anpassen, um andere Aktionen auszuführen?

A: Ja, Aspose.PDF für .NET ermöglicht Ihnen, die Öffnungsaktion anzupassen, indem Sie sie auf verschiedene Aktionstypen einstellen, wie z. B. das Navigieren zu einer bestimmten Seite oder das Ausführen von JavaScript.

#### F: Kann ich offene Aktionen aus passwortgeschützten PDFs entfernen?
A: Ja, Sie können offene Aktionen aus kennwortgeschützten PDF-Dateien entfernen, solange Sie die entsprechenden Anmeldeinformationen für den Zugriff auf das Dokument und dessen Änderung angeben.

#### F: Ist die Entfernung der offenen Aktion umkehrbar?

A: Nein, sobald die Öffnungsaktion entfernt und die PDF-Datei gespeichert wurde, kann die ursprüngliche Öffnungsaktion nicht aus der geänderten PDF-Datei wiederhergestellt werden.

#### F: Wie überprüfe ich, ob die offene Aktion erfolgreich entfernt wurde?

A: Nachdem Sie die Öffnungsaktion mit dem bereitgestellten Code entfernt haben, öffnen Sie die geänderte PDF-Datei und bestätigen Sie, dass beim Öffnen keine bestimmte Aktion ausgeführt wird.

#### F: Kann ich offene Aktionen aus mehreren PDF-Dateien gleichzeitig entfernen?

A: Ja, Sie können denselben Ansatz verwenden, um offene Aktionen aus mehreren PDF-Dateien in einem Stapelverarbeitungsszenario zu entfernen.