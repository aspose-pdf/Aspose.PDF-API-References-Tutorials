---
title: Offene Aktion entfernen
linktitle: Offene Aktion entfernen
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
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Öffnen Sie das Dokument
Document document = new Document(dataDir + "RemoveOpenAction.pdf");
```

## Schritt 3: Löschen der offenen Aktion

 Entfernen Sie die Öffnungsaktion aus dem Dokument, indem Sie die festlegen`OpenAction` Eigenschaft auf null setzen:

```csharp
document. OpenAction = null;
```

## Schritt 4: Speichern Sie das aktualisierte Dokument

 Speichern Sie das aktualisierte Dokument mit`Save` Methode:

```csharp
dataDir = dataDir + "RemoveOpenAction_out.pdf";
document. Save(dataDir);
```

## Schritt 5: Ergebnis anzeigen

Zeigen Sie eine Meldung an, die angibt, dass die Öffnungsaktion erfolgreich entfernt wurde, und geben Sie den Speicherort der gespeicherten Datei an:

```csharp
Console.WriteLine("\nOpen action deleted successfully.\nFile saved to location: " + dataDir);
```

### Beispielquellcode für die Aktion „Öffnen entfernen“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document document = new Document(dataDir + "RemoveOpenAction.pdf");
// Aktion zum Öffnen des Dokuments entfernen
document.OpenAction = null;
dataDir = dataDir + "RemoveOpenAction_out.pdf";
// Aktualisiertes Dokument speichern
document.Save(dataDir);
Console.WriteLine("\nOpen action removed successfully.\nFile saved at " + dataDir); 
```

## Abschluss

Herzlichen Glückwunsch! Jetzt wissen Sie, wie Sie mit Aspose.PDF für .NET die Öffnungsaktion aus einer PDF-Datei entfernen. Nutzen Sie dieses Wissen, um die Eigenschaften und das Verhalten von PDF-Dateien in Ihren Projekten anzupassen.

Nachdem Sie dieses Handbuch abgeschlossen haben, können Sie diese Konzepte auf Ihre eigenen Projekte anwenden und die von Aspose.PDF für .NET angebotenen Funktionen weiter erkunden.

### FAQs 

#### F: Was ist die „Öffnen-Aktion“ in einer PDF-Datei?

A: Die „Öffnen-Aktion“ in einer PDF-Datei ist eine Anweisung, die angibt, was passieren soll, wenn die PDF-Datei geöffnet wird. Dies kann Aktionen wie das Navigieren zu einer bestimmten Seite oder Stelle im Dokument, das Starten einer externen Anwendung oder das Anzeigen einer bestimmten Ansicht umfassen.

#### F: Warum sollte ich die Öffnungsaktion aus einer PDF-Datei entfernen wollen?

A: Das Entfernen der Öffnungsaktion kann die Sicherheit, das Benutzererlebnis und die Kontrolle darüber verbessern, wie die PDF-Datei beim Öffnen dargestellt wird. Beispielsweise möchten Sie möglicherweise die automatische Navigation verhindern oder bestimmte Aktionen beim Öffnen des Dokuments deaktivieren.

#### F: Wie hilft Aspose.PDF für .NET beim Entfernen der Öffnungsaktion?

A: Aspose.PDF für .NET bietet APIs zur Bearbeitung verschiedener Aspekte von PDF-Dateien. In diesem Tutorial wird gezeigt, wie Sie die Öffnungsaktion mithilfe von C#-Code entfernen.

#### F: Gibt es mögliche Risiken oder Überlegungen beim Entfernen der offenen Aktion?

A: Das Entfernen der Öffnungsaktion kann das Standardverhalten der PDF-Datei ändern. Stellen Sie daher sicher, dass sie mit der beabsichtigten Benutzererfahrung übereinstimmt. Testen Sie das geänderte PDF gründlich, um sicherzustellen, dass die Entfernung keine Auswirkungen auf andere Funktionen hat.

#### F: Kann ich die Öffnungsaktion anpassen, um andere Aktionen auszuführen?

A: Ja, mit Aspose.PDF für .NET können Sie die Öffnungsaktion anpassen, indem Sie sie auf verschiedene Arten von Aktionen festlegen, z. B. das Navigieren zu einer bestimmten Seite oder das Ausführen von JavaScript.

#### F: Kann ich offene Aktionen aus passwortgeschützten PDFs entfernen?
A: Ja, Sie können offene Aktionen aus passwortgeschützten PDFs entfernen, solange Sie die entsprechenden Anmeldeinformationen angeben, um auf das Dokument zuzugreifen und es zu ändern.

#### F: Ist die Entfernung der offenen Aktion umkehrbar?

A: Nein, sobald die Öffnungsaktion entfernt und die PDF-Datei gespeichert wurde, kann die ursprüngliche Öffnungsaktion nicht aus der geänderten PDF-Datei wiederhergestellt werden.

#### F: Wie kann ich überprüfen, ob die offene Aktion erfolgreich entfernt wurde?

A: Nachdem Sie die Öffnungsaktion mit dem bereitgestellten Code entfernt haben, öffnen Sie die geänderte PDF-Datei und bestätigen Sie, dass beim Öffnen keine bestimmte Aktion ausgeführt wird.

#### F: Kann ich offene Aktionen gleichzeitig aus mehreren PDF-Dateien entfernen?

A: Ja, Sie können den gleichen Ansatz verwenden, um offene Aktionen aus mehreren PDF-Dateien in einem Stapelverarbeitungsszenario zu entfernen.