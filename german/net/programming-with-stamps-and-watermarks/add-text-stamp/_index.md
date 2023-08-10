---
title: Textstempel in PDF-Datei hinzufügen
linktitle: Textstempel in PDF-Datei hinzufügen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET ganz einfach einen Textstempel in eine PDF-Datei einfügen.
type: docs
weight: 50
url: /de/net/programming-with-stamps-and-watermarks/add-text-stamp/
---
In diesem Tutorial zeigen wir Ihnen Schritt für Schritt, wie Sie mit Aspose.PDF für .NET einen Textstempel in eine PDF-Datei einfügen. Wir zeigen Ihnen, wie Sie mit dem bereitgestellten C#-Quellcode einen benutzerdefinierten Textstempel zu einer bestimmten Seite der PDF-Datei hinzufügen.

## Schritt 1: Einrichten der Umgebung

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Eine installierte .NET-Entwicklungsumgebung.
- Die Aspose.PDF-Bibliothek für .NET wurde heruntergeladen und in Ihrem Projekt referenziert.

## Schritt 2: Laden des PDF-Dokuments

Der erste Schritt besteht darin, das vorhandene PDF-Dokument in Ihr Projekt zu laden. Hier ist wie:

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Öffnen Sie das Dokument
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

Ersetzen Sie „IHR DOKUMENTENVERZEICHNIS“ unbedingt durch den tatsächlichen Pfad zu dem Verzeichnis, in dem sich Ihr PDF-Dokument befindet.

## Schritt 3: Erstellen des Textpuffers

Nachdem Sie das PDF-Dokument hochgeladen haben, können Sie den hinzuzufügenden Textstempel erstellen. So geht's:

```csharp
// Erstellen Sie den Textpuffer
TextStamp textStamp = new TextStamp("Example Stamp");
```

Der obige Code erstellt einen neuen Textpuffer, der den angegebenen Text enthält.

## Schritt 4: Konfigurieren der Textstempeleigenschaften

Bevor Sie den Textstempel zum PDF-Dokument hinzufügen, können Sie verschiedene Eigenschaften des Stempels konfigurieren, wie Hintergrund, Position, Drehung, Schriftart, Größe usw. So geht's:

```csharp
// Konfigurieren Sie die Eigenschaften des Textpuffers
textStamp. Background = true;
textStamp. XIndent = 100;
textStamp. YIndent = 100;
textStamp.Rotate = Rotate.on90;
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Aqua);
```

Sie können diese Eigenschaften entsprechend Ihren Bedürfnissen anpassen.

## Schritt 5: Textstempel zum PDF hinzufügen

Da der Textstempel nun fertig ist, können Sie ihn einer bestimmten Seite des PDF-Dokuments hinzufügen. Hier ist wie:

```csharp
//Textpuffer zu einer bestimmten Seite hinzufügen
pdfDocument.Pages[1].AddStamp(textStamp);
```

Der obige Code fügt den Textstempel auf der ersten Seite des PDF-Dokuments hinzu. Bei Bedarf können Sie eine andere Seite angeben.

## Schritt 6: Speichern Sie das Ausgabedokument

Nachdem Sie den Textstempel hinzugefügt haben, können Sie das bearbeitete PDF-Dokument speichern. Hier ist wie:

```csharp
// Speichern Sie das Ausgabedokument
pdfDocument.Save(dataDir);
```

Der obige Code speichert das geänderte PDF-Dokument im angegebenen Verzeichnis.

### Beispielquellcode für „Textstempel hinzufügen“ mit Aspose.PDF für .NET 
```csharp

// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dokument öffnen
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");

// Textstempel erstellen
TextStamp textStamp = new TextStamp("Sample Stamp");

// Legen Sie fest, ob der Stempel im Hintergrund angezeigt wird
textStamp.Background = true;

// Ursprung festlegen
textStamp.XIndent = 100;
textStamp.YIndent = 100;

// Stempel drehen
textStamp.Rotate = Rotation.on90;

// Texteigenschaften festlegen
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold;
textStamp.TextState.FontStyle = FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Aqua);

// Stempel zu einer bestimmten Seite hinzufügen
pdfDocument.Pages[1].AddStamp(textStamp);
dataDir = dataDir + "AddTextStamp_out.pdf";

// Ausgabedokument speichern
pdfDocument.Save(dataDir);
Console.WriteLine("\nText stamp added successfully.\nFile saved at " + dataDir);            

```

## Abschluss

Herzlichen Glückwunsch! Sie haben gelernt, wie Sie mit Aspose.PDF für .NET einen Textstempel hinzufügen. Jetzt können Sie dieses Wissen auf Ihre eigenen Projekte anwenden, um benutzerdefinierte Textstempel zu PDF-Dokumenten hinzuzufügen.

### FAQs zum Hinzufügen eines Textstempels in einer PDF-Datei

#### F: Was ist der Zweck des Hinzufügens eines Textstempels in einer PDF-Datei mit Aspose.PDF für .NET?

A: Durch das Hinzufügen eines Textstempels können Sie benutzerdefinierten Text auf einer bestimmten Seite eines PDF-Dokuments platzieren. Diese Funktion ist nützlich, um Beschriftungen, Kommentare, Wasserzeichen oder andere Textinformationen hinzuzufügen, um den Inhalt des Dokuments zu verbessern und zusätzlichen Kontext bereitzustellen.

#### F: Kann ich das Erscheinungsbild des Textstempels anpassen, z. B. Schriftart, Größe, Farbe und Drehung?

 A: Ja, Sie können das Erscheinungsbild des Textstempels vollständig anpassen. Der bereitgestellte C#-Quellcode zeigt, wie verschiedene Eigenschaften festgelegt werden`TextStamp` Objekt, einschließlich Schriftart, Schriftgröße, Schriftstil, Textfarbe, Hintergrundfarbe und Drehung.

#### F: Ist es möglich, mehrere Textstempel auf verschiedenen Seiten desselben PDF-Dokuments hinzuzufügen?

A: Auf jeden Fall können Sie mehrere Textstempel auf verschiedenen Seiten desselben PDF-Dokuments hinzufügen. Mit dem im Tutorial bereitgestellten Code können Sie die Zielseite für das Hinzufügen des Textstempels angeben und ihn so vielseitig für verschiedene Seiten im Dokument verwenden.

#### F: Wie lege ich die Position des Textstempels im PDF-Dokument fest?

 A: Sie können die Position des Textstempels anpassen, indem Sie die ändern`XIndent` Und`YIndent` Eigenschaften der`TextStamp` Objekt. Diese Eigenschaften definieren die Koordinaten der oberen linken Ecke des Stempels relativ zum Ursprung der Seite.

#### F: Kann ich diese Methode auf vorhandene PDF-Dokumente anwenden, um Textstempel hinzuzufügen?

A: Ja, Sie können diese Methode auf vorhandene PDF-Dokumente anwenden, um Textstempel hinzuzufügen. Der bereitgestellte Code des Tutorials zeigt, wie man ein vorhandenes PDF-Dokument lädt und einer bestimmten Seite einen Textstempel hinzufügt.

#### F: Kann ich dem Textstempel sowohl Hintergrund- als auch Vordergrundfarben hinzufügen?

 A: Ja, Sie können dem Textstempel sowohl Hintergrund- als auch Vordergrundfarben hinzufügen. Durch Einstellen der`Background` Eigentum zu`true` können Sie dem Textstempel einen farbigen Hintergrund verleihen. Darüber hinaus können Sie die festlegen`TextState.ForegroundColor` -Eigenschaft, um die Farbe des Textes selbst anzugeben.

#### F: Wie kann ich sicherstellen, dass der Textstempel den zugrunde liegenden Inhalt des PDF-Dokuments nicht verdeckt?

 A: Achten Sie beim Hinzufügen eines Textstempels auf die Platzierung, um sicherzustellen, dass er wichtige Informationen nicht verdeckt oder die Lesbarkeit des Dokuments beeinträchtigt. Sie können die anpassen`XIndent` Und`YIndent` Eigenschaften, um den Textstempel entsprechend zu positionieren.

#### F: Kann ich diese Methode verwenden, um andere Stempel als Text hinzuzufügen, beispielsweise Bilder oder Logos?

A: Dieses spezielle Tutorial konzentriert sich auf das Hinzufügen von Textstempeln, aber Sie können mit Aspose.PDF für .NET auch andere Stempeltypen wie Bilder oder Logos hinzufügen. Der Prozess umfasst das Erstellen des entsprechenden Stempelobjekts und das Konfigurieren seiner Eigenschaften.

#### F: Wie kann ich das Hinzufügen von Textstempeln zu mehreren PDF-Dokumenten automatisieren?

A: Sie können den Prozess des Hinzufügens von Textstempeln zu mehreren PDF-Dokumenten automatisieren, indem Sie ein Skript oder Programm erstellen, das eine Liste von Dokumenten durchläuft und auf jedes einzelne den gleichen Textstempelprozess anwendet.