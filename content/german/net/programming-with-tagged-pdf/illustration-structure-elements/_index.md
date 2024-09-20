---
title: Abbildung Strukturelemente
linktitle: Abbildung Strukturelemente
second_title: Aspose.PDF für .NET API-Referenz
description: Erstellen Sie strukturierte PDFs mit Illustrationselementen in Aspose.PDF für .NET, indem Sie unserem Schritt-für-Schritt-Tutorial folgen.
type: docs
weight: 100
url: /de/net/programming-with-tagged-pdf/illustration-structure-elements/
---
## Einführung

Sind Sie bereit, beeindruckende, strukturierte PDFs in Ihren .NET-Anwendungen zu erstellen? Egal, ob Sie an einem Projekt arbeiten, bei dem Inhalte markiert werden müssen, oder ob Sie Ihre PDFs einfach auf die nächste Ebene bringen möchten, Aspose.PDF für .NET bietet alle Tools, die Sie zum Arbeiten mit Illustrationsstrukturelementen benötigen. In diesem Tutorial führe ich Sie Schritt für Schritt durch den Prozess und stelle sicher, dass selbst die komplexesten Teile kristallklar sind.

## Voraussetzungen

Bevor wir in die Details eintauchen, stellen wir sicher, dass Sie alles haben, was Sie brauchen, um reibungslos mitmachen zu können.

1.  Aspose.PDF für .NET – Sie müssen die Aspose.PDF-Bibliothek installiert haben. Sie haben sie noch nicht? Sie können[Laden Sie es hier herunter](https://releases.aspose.com/pdf/net/) Wenn Sie es zuerst testen möchten, können Sie sich ein[Kostenlose Testversion](https://releases.aspose.com/).
2. Visual Studio – Wir werden in C# programmieren, stellen Sie also sicher, dass Visual Studio oder eine kompatible IDE installiert ist.
3. .NET Framework – Stellen Sie sicher, dass Sie eine mit Aspose.PDF für .NET kompatible Version haben.
4.  Temporäre Lizenz – Aspose.PDF hat im Testmodus einige Einschränkungen, also holen Sie sich eine[vorläufige Lizenz](https://purchase.aspose.com/temporary-license/) um alle Funktionen freizuschalten.

Das ist alles! Jetzt importieren wir die erforderlichen Namespaces und fahren mit der Codierung fort.

## Namespaces importieren

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Dies ist die Grundlage – ohne das Importieren dieser Namespaces können wir nicht mit den Aspose.PDF-Funktionen interagieren oder getaggte PDF-Inhalte verarbeiten. Lassen Sie uns nun die Schritte im Detail aufschlüsseln.

## Schritt 1: Einrichten Ihres Dokumentverzeichnisses

Bevor Sie mit der Erstellung Ihrer PDF-Datei beginnen, müssen Sie den Pfad zu Ihrem Dokumentverzeichnis angeben, in dem die Datei gespeichert wird. Dies ist der Ordner auf Ihrem System, in dem Ihre Bilder oder andere Assets gespeichert sind.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Dieser Schritt ist einfach, aber wichtig. Sie sagen dem Programm, wo es die Dateien finden und speichern soll, mit denen Sie arbeiten werden. Es ist, als hätten Sie eine Homebase für Ihre PDFs. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad auf Ihrem Computer.

## Schritt 2: Ein neues PDF-Dokument erstellen

Nun ist es an der Zeit, das PDF-Dokument zu erstellen. In diesem Schritt erstellen wir ein leeres PDF-Dokument, das wir in den folgenden Schritten ändern und verbessern.
 Erstellen des Dokuments

```csharp
Document document = new Document();
```

Diese Zeile erledigt den ganzen Zauber. Sie erstellt eine neue PDF-Datei, die völlig leer ist und darauf wartet, dass Sie ihr Inhalt hinzufügen. Stellen Sie es sich so vor, als würden Sie eine neue Leinwand öffnen.

## Schritt 3: Zugriff auf den getaggten PDF-Inhalt

Um mit Illustrationsstrukturelementen arbeiten zu können, müssen wir auf den getaggten Inhalt des Dokuments zugreifen. Dadurch können wir spezifische Tags definieren, wodurch das PDF strukturierter und zugänglicher wird.

```csharp
ITaggedContent taggedContent = document.TaggedContent;
```

 Hier geschieht die Magie! Die`TaggedContent` Objekt können wir definieren, wie Elemente im PDF interpretiert werden. Wenn Sie mit Zugänglichkeit oder Struktur arbeiten, ist dieser Schritt entscheidend.

## Schritt 4: Titel und Sprache des Dokuments festlegen

Wir erstellen ein strukturiertes PDF. Daher ist es wichtig, einen Titel und eine Sprache festzulegen. Dies trägt nicht nur zur Zugänglichkeit bei, sondern macht das Dokument auch professioneller und durchsuchbarer.

```csharp
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");
```

Indem Sie einen Titel und eine Sprache angeben, verleihen Sie Ihrem PDF im Wesentlichen eine persönliche Note. Der Titel wird in den Dokumenteigenschaften angezeigt und die Spracheinstellung stellt die Kompatibilität mit Bildschirmleseprogrammen und anderen Hilfsmitteln sicher.

## Schritt 5: Erstellen eines Illustrationselements (Abbildungselements)

Jetzt kommt der spannende Teil – das Hinzufügen einer Abbildung! In diesem Fall erstellen wir ein Abbildungselement, das ein Bild, eine alternative Textbeschreibung und einen Titel enthält.

```csharp
IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
```

Dieser Code erstellt ein neues Abbildungselement und hängt es an das Stammelement des Dokuments an. Stellen Sie sich das so vor, als würden Sie Ihrem Dokument einen Bildplatzhalter hinzufügen.

## Schritt 6: Alternativtext, Titel und Bild hinzufügen

Um sicherzustellen, dass Ihr PDF barrierefrei ist, sollten Sie Ihrer Illustration einen Alternativtext und einen Titel hinzufügen. Wir werden auch ein Bild anhängen.

```csharp
figure1.AlternativeText = "Figure One";
figure1.Title = "Image 1";
figure1.SetTag("Fig1");
figure1.SetImage(dataDir + "image.jpg");
```

 Dies ist der letzte Schliff. Wir geben unserem Bild einen beschreibenden Alternativtext (der für Bildschirmleseprogramme nützlich ist), einen Titel und legen die eigentliche Bilddatei fest. Die`SetTag`Die Methode markiert die Abbildung und erleichtert so die spätere Referenzierung.

 Wichtiger Hinweis: Stellen Sie sicher, dass der Bildpfad in`SetImage` verweist auf eine gültige Bilddatei auf Ihrem Computer.

## Schritt 7: Speichern des getaggten PDF-Dokuments

Sobald der gesamte Inhalt hinzugefügt und strukturiert ist, ist es an der Zeit, das PDF zu speichern. Dieser Schritt schließt alles ab und generiert die eigentliche Datei.

```csharp
document.Save(dataDir + "IllustrationStructureElements.pdf");
```

Einfach, oder? Dieser Befehl übernimmt all Ihre Arbeit und erstellt eine neue PDF-Datei in dem zuvor angegebenen Verzeichnis. Überprüfen Sie nun Ihren Ordner und voilà – Sie haben eine strukturierte PDF-Datei mit Illustrationselementen!

## Abschluss

Herzlichen Glückwunsch! Sie haben gerade gelernt, wie Sie mit Aspose.PDF für .NET ein getaggtes PDF mit Illustrationsstrukturelementen erstellen. Dieser Ansatz stellt sicher, dass Ihre PDFs nicht nur optisch ansprechend, sondern auch strukturiert und zugänglich sind. Indem Sie Inhalte taggen und alternativen Text hinzufügen, stellen Sie sicher, dass jeder, auch diejenigen, die unterstützende Technologien verwenden, Ihre Dokumente genießen können.

## Häufig gestellte Fragen

### Was ist getaggter PDF-Inhalt?
Ein getaggtes PDF ist ein PDF, das Tags oder Beschriftungen zum Identifizieren verschiedener Elemente wie Überschriften, Absätze und Abbildungen enthält, wodurch das Dokument leichter zugänglich wird.

### Wie hilft das Festlegen von Alternativtext?
Alternativtext bietet Beschreibungen für Bilder, die von Bildschirmleseprogrammen gelesen werden können und so die Zugänglichkeit für sehbehinderte Benutzer verbessern.

### Kann ich einer getaggten PDF-Datei mehrere Bilder hinzufügen?
 Ja! Sie können mehrere`FigureElement` Objekte und hängen Sie jedes an Ihr Dokument an, genau wie wir es mit dem einzelnen Bild gemacht haben.

### Benötige ich eine Lizenz, um Aspose.PDF für .NET zu verwenden?
 Ja, Aspose.PDF ist eine kostenpflichtige Bibliothek, aber Sie können eine[vorläufige Lizenz](https://purchase.aspose.com/temporary-license/) oder beginnen Sie mit einem[Kostenlose Testversion](https://releases.aspose.com/).

### Ist es möglich, das Figurelement nach dem Erstellen des PDFs zu ändern?
Sobald die PDF-Datei gespeichert ist, können Sie sie nicht direkt ändern, aber Sie können das Dokument erneut öffnen, Änderungen vornehmen und es mit Aspose.PDF erneut speichern.