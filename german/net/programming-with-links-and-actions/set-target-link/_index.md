---
title: Ziellink festlegen
linktitle: Ziellink festlegen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET einen Ziellink in einer PDF-Datei festlegen.
type: docs
weight: 100
url: /de/net/programming-with-links-and-actions/set-target-link/
---

Erfahren Sie in dieser Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.PDF für .NET einen Ziellink in einer PDF-Datei festlegen.

## Schritt 1: Einrichten der Umgebung

Stellen Sie sicher, dass Sie Ihre Entwicklungsumgebung mit einem C#-Projekt und den entsprechenden Aspose.PDF-Referenzen eingerichtet haben.

## Schritt 2: Laden der PDF-Datei

Legen Sie den Verzeichnispfad Ihrer Dokumente fest und laden Sie die PDF-Datei mit dem folgenden Code hoch:

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Laden Sie die PDF-Datei
Document document = new Document(dataDir + "UpdateLinks.pdf");
```

## Schritt 3: Bearbeiten des Ziellinks

Rufen Sie die zu ändernde Linkanmerkung mit dem folgenden Code ab:

```csharp
LinkAnnotation linkAnnot = (LinkAnnotation)document.Pages[1].Annotations[1];
GoToRemoteAction goToR = (GoToRemoteAction)linkAnnot.Action;
```

 Sie können die anpassen`[1]` Indizes, um eine bestimmte Seite oder Anmerkung auszuwählen.

Als nächstes aktualisieren Sie das Ziel, ohne die Datei zu aktualisieren:

```csharp
goToR.Destination = new XYZExplicitDestination(2, 0, 0, 1.5);
```

Und wenn Sie die Datei auch aktualisieren möchten:

```csharp
goToR.File = new FileSpecification(dataDir + "input.pdf");
```

## Schritt 4: Speichern Sie das Dokument mit dem aktualisierten Link

Speichern Sie das Dokument mit dem aktualisierten Link mithilfe von`Save` Methode:

```csharp
dataDir = dataDir + "SetTargetLink_out.pdf";
document. Save(dataDir);
```

## Schritt 5: Ergebnis anzeigen

Zeigen Sie eine Meldung an, die angibt, dass der Ziellink erfolgreich konfiguriert wurde, und geben Sie den Speicherort der gespeicherten Datei an:

```csharp
Console.WriteLine("\nConfiguration of target link successful.\nFile saved at location: " + dataDir);
```

### Beispielquellcode für Set Target Link mit Aspose.PDF für .NET 
```csharp
try
{
	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Laden Sie die PDF-Datei
	Document document = new Document(dataDir + "UpdateLinks.pdf");
	LinkAnnotation linkAnnot = (LinkAnnotation)document.Pages[1].Annotations[1];
	GoToRemoteAction goToR = (GoToRemoteAction)linkAnnot.Action;
	// Nächste Zeile: Aktualisierungsziel, Datei nicht aktualisieren
	goToR.Destination = new XYZExplicitDestination(2, 0, 0, 1.5);
	// Aktualisierungsdatei für die nächste Zeile
	goToR.File = new FileSpecification(dataDir +  "input.pdf");
	dataDir = dataDir + "SetTargetLink_out.pdf";
	// Speichern Sie das Dokument mit dem aktualisierten Link
	document.Save(dataDir);
	Console.WriteLine("\nTarget link setup successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Abschluss

Herzlichen Glückwunsch! Sie wissen jetzt, wie Sie mit Aspose.PDF für .NET einen Ziellink in einer PDF-Datei festlegen. Nutzen Sie dieses Wissen, um Links in Ihren PDF-Dokumenten anzupassen und interaktive Erlebnisse für Benutzer zu erstellen.

Nachdem Sie dieses Handbuch abgeschlossen haben, können Sie diese Konzepte auf Ihre eigenen Projekte anwenden und die von Aspose.PDF für .NET angebotenen Funktionen weiter erkunden.