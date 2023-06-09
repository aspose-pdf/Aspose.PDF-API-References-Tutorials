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