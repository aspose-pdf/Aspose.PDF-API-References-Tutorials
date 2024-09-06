---
title: Ziellink in PDF-Datei festlegen
linktitle: Ziellink in PDF-Datei festlegen
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
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Laden Sie die PDF-Datei
Document document = new Document(dataDir + "UpdateLinks.pdf");
```

## Schritt 3: Ziellink bearbeiten

Rufen Sie die zu ändernde Link-Annotation mit dem folgenden Code ab:

```csharp
LinkAnnotation linkAnnot = (LinkAnnotation)document.Pages[1].Annotations[1];
GoToRemoteAction goToR = (GoToRemoteAction)linkAnnot.Action;
```

 Sie können die`[1]` Indizes, um eine bestimmte Seite oder Anmerkung auszuwählen.

Aktualisieren Sie als Nächstes das Ziel, ohne die Datei zu aktualisieren:

```csharp
goToR.Destination = new XYZExplicitDestination(2, 0, 0, 1.5);
```

Und wenn Sie die Datei auch aktualisieren möchten:

```csharp
goToR.File = new FileSpecification(dataDir + "input.pdf");
```

## Schritt 4: Speichern Sie das Dokument mit dem aktualisierten Link

 Speichern Sie das Dokument mit dem aktualisierten Link über den`Save` Verfahren:

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
	// Der Pfad zum Dokumentverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Laden Sie die PDF-Datei
	Document document = new Document(dataDir + "UpdateLinks.pdf");
	LinkAnnotation linkAnnot = (LinkAnnotation)document.Pages[1].Annotations[1];
	GoToRemoteAction goToR = (GoToRemoteAction)linkAnnot.Action;
	// Nächste Zeile: Ziel aktualisieren, Datei nicht aktualisieren
	goToR.Destination = new XYZExplicitDestination(2, 0, 0, 1.5);
	// Nächste Zeile der Update-Datei
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

Herzlichen Glückwunsch! Sie wissen jetzt, wie Sie mit Aspose.PDF für .NET einen Ziellink in einer PDF-Datei festlegen. Verwenden Sie dieses Wissen, um Links in Ihren PDF-Dokumenten anzupassen und interaktive Erlebnisse für Benutzer zu erstellen.

Nachdem Sie dieses Handbuch abgeschlossen haben, können Sie diese Konzepte auf Ihre eigenen Projekte anwenden und die von Aspose.PDF für .NET angebotenen Funktionen weiter erkunden.

### FAQs zum Setzen eines Ziellinks in einer PDF-Datei

#### F: Was ist ein Ziellink in einer PDF-Datei?

A: Ein Ziellink in einer PDF-Datei ist ein anklickbarer Link, der den Leser zu einem bestimmten Ziel innerhalb desselben Dokuments oder zu einer anderen PDF-Datei führt.

#### F: Warum sollte ich in einer PDF-Datei einen Ziellink festlegen?

A: Durch das Festlegen von Ziellinks können Sie ein nahtloses Navigationserlebnis innerhalb eines PDF-Dokuments erstellen oder auf bestimmte Abschnitte oder Seiten in anderen PDF-Dateien verlinken.

#### F: Wie hilft Aspose.PDF für .NET beim Festlegen von Ziellinks?

A: Aspose.PDF für .NET bietet APIs zur Bearbeitung verschiedener Aspekte von PDF-Dateien, einschließlich der Erstellung und Änderung von Links. Dieses Tutorial zeigt, wie Sie mit C#-Code einen Ziellink festlegen.

#### F: Kann ich Ziellinks festlegen, um zu bestimmten Seiten innerhalb desselben Dokuments zu navigieren?

A: Ja, Aspose.PDF für .NET ermöglicht Ihnen das Festlegen von Ziellinks, um zu bestimmten Seiten innerhalb desselben Dokuments zu navigieren.

#### F: Kann ich Ziellinks festlegen, um zu bestimmten Seiten in einer anderen PDF-Datei zu navigieren?

A: Ja, Sie können mit Aspose.PDF für .NET Ziellinks festlegen, um zu bestimmten Seiten innerhalb einer anderen PDF-Datei zu navigieren.

#### F: Gibt es Einschränkungen beim Setzen von Ziellinks?

A: Ziellinks können nur innerhalb desselben Dokuments oder zu bestimmten Seiten in anderen PDF-Dateien navigieren. Sie können nicht direkt auf bestimmte Inhalte in anderen Dokumenten verweisen.

#### F: Wie kann ich das Erscheinungsbild eines Ziellinks anpassen?

A: Das Erscheinungsbild eines Ziellinks, beispielsweise seine Farbe und sein Stil, kann mit den von Aspose.PDF für .NET bereitgestellten Eigenschaften angepasst werden.

#### F: Kann ich mehrere Ziellinks im selben PDF-Dokument festlegen?

A: Ja, Sie können mehrere Ziellinks im selben PDF-Dokument festlegen. Wiederholen Sie den Vorgang einfach für jeden Link, den Sie erstellen möchten.

#### F: Kann ich einen Ziellink mit einer bestimmten Form oder einem bestimmten Text festlegen?

A: Ja, Sie können mithilfe der entsprechenden Eigenschaften und Methoden von Aspose.PDF für .NET einen Ziellink an bestimmte Formen oder Texte im PDF-Dokument anhängen.

#### F: Wie kann ich testen, ob der Ziellink wie vorgesehen funktioniert?

A: Nachdem Sie den Ziellink mit dem bereitgestellten Code festgelegt haben, öffnen Sie die geänderte PDF-Datei und klicken Sie auf den Link, um sicherzustellen, dass er zum gewünschten Ziel navigiert.

#### F: Kann ich Ziellinks in passwortgeschützten PDFs festlegen?

A: Ja, Sie können Ziellinks in kennwortgeschützten PDF-Dateien festlegen, solange Sie die entsprechenden Anmeldeinformationen für den Zugriff auf das Dokument und dessen Änderung angeben.