---
title: Ziellink in PDF-Datei festlegen
linktitle: Ziellink in PDF-Datei festlegen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET einen Ziellink in einer PDF-Datei festlegen.
type: docs
weight: 90
url: /de/net/programming-with-links-and-actions/set-destination-link/
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
Document doc = new Document(dataDir + "UpdateLinks.pdf");
```

## Schritt 3: Bearbeiten des Ziellinks

Rufen Sie die zu ändernde Linkanmerkung mit dem folgenden Code ab:

```csharp
LinkAnnotation linkAnnot = (LinkAnnotation)doc.Pages[1].Annotations[1];
```

 Sie können die anpassen`[1]` Indizes, um eine bestimmte Seite oder Anmerkung auszuwählen.

Bearbeiten Sie als Nächstes den Link, indem Sie die Linkaktion ändern und das Ziel als Webadresse festlegen:

```csharp
linkAnnot.Action = new GoToURIAction("www.aspose.com");
```

## Schritt 4: Speichern Sie das Dokument mit dem aktualisierten Link

 Speichern Sie das Dokument mit dem aktualisierten Link mithilfe von`Save` Methode:

```csharp
dataDir = dataDir + "SetDestinationLink_out.pdf";
doc.Save(dataDir);
```

## Schritt 5: Ergebnis anzeigen

Zeigen Sie eine Meldung an, dass der Ziellink erfolgreich konfiguriert wurde, und geben Sie den Speicherort der gespeicherten Datei an:

```csharp
Console.WriteLine("\nDestination link configured successfully.\nFile saved to location: " + dataDir);
```

### Beispielquellcode für Set Destination Link mit Aspose.PDF für .NET 
```csharp
try
{
	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Laden Sie die PDF-Datei
	Document doc = new Document(dataDir + "UpdateLinks.pdf");
	// Holen Sie sich die erste Linkanmerkung von der ersten Seite des Dokuments
	LinkAnnotation linkAnnot = (LinkAnnotation)doc.Pages[1].Annotations[1];
	// Änderungslink: Linkaktion ändern und Ziel als Webadresse festlegen
	linkAnnot.Action = new GoToURIAction("www.aspose.com");           
	dataDir = dataDir + "SetDestinationLink_out.pdf";
	// Speichern Sie das Dokument mit dem aktualisierten Link
	doc.Save(dataDir);
	Console.WriteLine("\nDestination link setup successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Abschluss

Herzlichen Glückwunsch! Sie wissen jetzt, wie Sie mit Aspose.PDF für .NET einen Ziellink in einer PDF-Datei festlegen. Nutzen Sie dieses Wissen, um Links in Ihren PDF-Dokumenten anzupassen und interaktive Erlebnisse für Benutzer zu erstellen.

Nachdem Sie dieses Handbuch abgeschlossen haben, können Sie diese Konzepte auf Ihre eigenen Projekte anwenden und die von Aspose.PDF für .NET angebotenen Funktionen weiter erkunden.

### FAQs zum Festlegen eines Ziellinks in einer PDF-Datei

#### F: Was ist ein Ziellink in einer PDF-Datei?

A: Ein Ziellink in einer PDF-Datei ist ein anklickbarer Link, der den Leser zu einem bestimmten Ziel innerhalb desselben Dokuments oder zu einer externen Webadresse führt.

#### F: Warum sollte ich einen Ziellink in einer PDF-Datei festlegen?

A: Durch das Festlegen von Ziellinks können Sie ein nahtloses Navigationserlebnis innerhalb eines PDF-Dokuments schaffen. Dies ist besonders nützlich zum Erstellen von Inhaltsverzeichnissen, Indexseiten oder zum Verknüpfen mit relevanten externen Ressourcen.

#### F: Wie hilft Aspose.PDF für .NET beim Festlegen von Ziellinks?
A: Aspose.PDF für .NET bietet APIs zur Bearbeitung verschiedener Aspekte von PDF-Dateien, einschließlich der Erstellung und Änderung von Links. In diesem Tutorial wird gezeigt, wie Sie mithilfe von C#-Code einen Ziellink festlegen.

#### F: Kann ich Ziellinks festlegen, um zu bestimmten Seiten innerhalb desselben Dokuments zu navigieren?

A: Ja, mit Aspose.PDF für .NET können Sie Ziellinks festlegen, um zu bestimmten Seiten innerhalb desselben Dokuments zu navigieren.

#### F: Kann ich Ziellinks festlegen, um zu externen Webadressen zu navigieren?

A: Ja, Sie können Ziellinks festlegen, um zu externen Webadressen zu navigieren, sodass Benutzer direkt aus der PDF-Datei auf Online-Ressourcen zugreifen können.

#### F: Gibt es Einschränkungen beim Festlegen von Ziellinks?

A: Ziellinks können nur innerhalb desselben Dokuments oder zu externen URLs navigieren. Sie können nicht direkt auf bestimmte Inhalte in anderen Dokumenten verweisen.

#### F: Wie kann ich das Erscheinungsbild eines Ziellinks anpassen?

A: Das Erscheinungsbild eines Ziellinks, beispielsweise seine Farbe und sein Stil, kann mithilfe der von Aspose.PDF für .NET bereitgestellten Eigenschaften angepasst werden.

#### F: Kann ich mehrere Ziellinks im selben PDF-Dokument festlegen?

A: Ja, Sie können mehrere Ziellinks im selben PDF-Dokument festlegen. Wiederholen Sie den Vorgang einfach für jeden Link, den Sie erstellen möchten.

#### F: Kann ich einen Ziellink mithilfe einer bestimmten Form oder eines bestimmten Textes festlegen?

A: Ja, Sie können mithilfe der entsprechenden Eigenschaften und Methoden von Aspose.PDF für .NET einen Ziellink an bestimmte Formen oder Texte im PDF-Dokument anhängen.

#### F: Wie kann ich testen, ob der Ziellink wie vorgesehen funktioniert?

A: Nachdem Sie den Ziellink mithilfe des bereitgestellten Codes festgelegt haben, öffnen Sie das geänderte PDF und klicken Sie auf den Link, um sicherzustellen, dass er zum gewünschten Ziel führt.

#### F: Kann ich Ziellinks in passwortgeschützten PDFs festlegen?

A: Ja, Sie können Ziellinks in passwortgeschützten PDFs festlegen, sofern Sie die entsprechenden Anmeldeinformationen angeben, um auf das Dokument zuzugreifen und es zu ändern.
