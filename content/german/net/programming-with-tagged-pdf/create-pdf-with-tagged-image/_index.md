---
title: PDF mit markiertem Bild erstellen
linktitle: PDF mit markiertem Bild erstellen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET ein getaggtes PDF mit Bildern erstellen. Folgen Sie unserer Schritt-für-Schritt-Anleitung zur barrierefreien und professionellen Dokumenterstellung.
type: docs
weight: 40
url: /de/net/programming-with-tagged-pdf/create-pdf-with-tagged-image/
---
## Einführung

Das Erstellen von PDFs kann eine komplexe Aufgabe sein, muss es aber nicht! Heute werden wir uns damit befassen, wie man mit Aspose.PDF für .NET ein PDF-Dokument mit einem getaggten Bild erstellt. Wenn Sie neugierig sind, wie Sie Bilder in Ihre PDFs integrieren und sicherstellen können, dass sie zugänglich sind, sind Sie hier richtig. Lassen Sie uns diesen Prozess Schritt für Schritt durchgehen, damit Sie mit Leichtigkeit professionelle und zugängliche PDFs erstellen können.

## Voraussetzungen

Bevor Sie mit der Erstellung Ihrer PDF-Datei mit getaggten Bildern beginnen, benötigen Sie einige Dinge:

1. Aspose.PDF für .NET: Diese leistungsstarke Bibliothek ist für die Handhabung von PDF-Dokumenten in .NET-Anwendungen unverzichtbar. Sie finden die Bibliothek hier:[Aspose.PDF für .NET herunterladen](https://releases.aspose.com/pdf/net/).
2. .NET Framework oder .NET Core: Stellen Sie sicher, dass Sie eine kompatible Version von .NET Framework oder .NET Core auf Ihrem Computer haben. Diese Bibliothek unterstützt beides.
3. Bilddatei: Sie benötigen eine Bilddatei, die Sie in Ihr PDF einbetten können. In unserem Beispiel verwenden wir „aspose-logo.png“. Stellen Sie sicher, dass Sie die Datei in Ihrem Dokumentenverzeichnis bereit haben. 

Wenn Sie sicherstellen, dass diese Voraussetzungen erfüllt sind, können Sie beginnen!

## Pakete importieren

Um unser Programmierabenteuer zu starten, müssen wir unseren Arbeitsbereich einrichten, indem wir die erforderlichen Aspose.PDF-Namespaces importieren. So können Sie das tun:

### Neues Projekt erstellen

- Öffnen Sie Ihre bevorzugte IDE (z. B. Visual Studio).
- Erstellen Sie ein neues Konsolenanwendungsprojekt. Warum eine Konsolenanwendung? Sie ist einfach und perfekt für Tutorials!

### Aspose.PDF-Referenz hinzufügen

- Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf Ihr Projekt und wählen Sie „NuGet-Pakete verwalten“ aus.
- Suchen Sie nach „Aspose.PDF“ und installieren Sie es. 
- Dadurch werden alle erforderlichen Pakete zu Ihrem Projekt hinzugefügt und Sie erhalten Zugriff auf die Funktionen, die wir zur PDF-Bearbeitung benötigen.

### Importieren der erforderlichen Namespaces

 Oben in Ihrer Hauptprogrammdatei (wie`Program.cs`), importieren Sie die folgenden Namespaces:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Indem Sie diese Pakete importieren, weisen Sie Ihre Anwendung an, die von uns genutzten Aspose.PDF-Funktionen einzubinden.

Nachdem wir nun alles eingerichtet haben, erstellen wir Schritt für Schritt unser PDF mit einem getaggten Bild.

## Schritt 1: Initialisieren Sie das Dokument

Zuerst müssen wir ein neues PDF-Dokument erstellen:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Legen Sie den Pfad zu Ihrem Verzeichnis fest
Document document = new Document();
```

-  Was ist hier los? Wir instantiieren ein neues`Document` Objekt, das unser PDF darstellt. Betrachten Sie es als eine leere Leinwand, die auf Ihre Meisterwerke wartet!

## Schritt 2: Einrichten des getaggten Inhalts

Als Nächstes richten wir den getaggten Inhalt ein:

```csharp
ITaggedContent taggedContent = document.TaggedContent;
```

- Warum getaggte Inhalte verwenden? Getaggte PDF-Dateien sind für die Zugänglichkeit unerlässlich, da sie es Bildschirmleseprogrammen ermöglichen, die Struktur des Dokuments zu verstehen.

## Schritt 3: Metadaten konfigurieren

Fügen wir nun einige Metadaten hinzu, die unser PDF beschreiben:

```csharp
taggedContent.SetTitle("CreatePDFwithTaggedImage");
taggedContent.SetLanguage("en-US");
```

- Meta was? Das Hinzufügen eines Titels und einer Sprache ist wie das Anbringen eines Namensschilds an Ihrer Kreation – es hilft anderen zu verstehen, worum es geht!

## Schritt 4: Erstellen Sie ein Illustrationselement

Wir müssen das Element erstellen, das unser Bild enthält:

```csharp
IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
```

-  Einfach so?! Ja! Die`CreateFigureElement` Methode ermöglicht es uns, eine neue Illustration zu erstellen und sie an das Stammelement unseres getaggten Inhalts anzuhängen.

## Schritt 5: Bildeigenschaften festlegen

Als Nächstes legen wir die Eigenschaften für das Bild fest:

```csharp
figure1.AlternativeText = "Aspose Logo";
figure1.Title = "Image 1";
figure1.SetTag("Fig");
```

- Warum all diese Eigenschaften? Alternativtext beschreibt das Bild für diejenigen, die es nicht sehen können, während Titel und Tag das Bild für eine bessere Zugänglichkeit kategorisieren.

## Schritt 6: Bild hinzufügen

Jetzt ist es Zeit, das eigentliche Bild zu unserem PDF hinzuzufügen:

```csharp
figure1.SetImage(dataDir + @"aspose-logo.png"); // Stellen Sie sicher, dass Ihr Bildpfad korrekt ist!
```

- Und hier geschieht die Magie! Sie betten das Bild direkt in Ihre PDF-Datei ein. 

## Schritt 7: Speichern Sie das PDF-Dokument

Zum Schluss speichern wir unsere Kreation in einer Datei:

```csharp
document.Save(dataDir + "PDFwithTaggedImage.pdf");
```

- Das große Finale! Nach der Ausführung dieser Zeile findest Du Dein neues PDF im angegebenen Verzeichnis.

## Abschluss

Das Erstellen von PDFs mit getaggten Bildern mit Aspose.PDF für .NET ist ein Kinderspiel, wenn Sie es in überschaubare Schritte aufteilen. Indem Sie dieser Anleitung folgen, haben Sie gelernt, nicht nur ein PDF zu erstellen, sondern auch dessen Zugänglichkeit mit getaggten Inhalten zu verbessern. Egal, ob Sie Dokumente für ein breiteres Publikum vorbereiten oder einfach Ihre PDF-Kreationen verfeinern, dieses Wissen wird Ihnen von Nutzen sein.

## Häufig gestellte Fragen

### Was ist ein getaggtes PDF?
Ein getaggtes PDF ist so konzipiert, dass es barrierefrei ist. Es enthält Metadaten, die es unterstützenden Technologien ermöglichen, es richtig zu lesen und darin zu navigieren.

### Kann ich mit Aspose.PDF mehrere Bilder hinzufügen?
 Absolut! Wiederholen Sie einfach die Schritte zum Erstellen neuer`IllustrationElement` Instanzen in Ihrem Dokument.

### Wo finde ich weitere Dokumentation zu Aspose.PDF?
 Schauen Sie sich die Dokumentation an[Hier](https://reference.aspose.com/pdf/net/).

### Gibt es eine kostenlose Testversion für Aspose.PDF?
 Ja! Sie können auf eine kostenlose Testversion zugreifen[Hier](https://releases.aspose.com/).

### Wie kann ich Support für Aspose.PDF erhalten?
 Sie erhalten Unterstützung unter[Aspose-Foren](https://forum.aspose.com/c/pdf/10).