---
title: Bild in der Fußzeile
linktitle: Bild in der Fußzeile
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET ein Bild in den Fußzeilenbereich eines PDF-Dokuments einfügen.
type: docs
weight: 130
url: /de/net/programming-with-stamps-and-watermarks/image-in-footer/
---
In diesem Tutorial zeigen wir Ihnen Schritt für Schritt, wie Sie mit Aspose.PDF für .NET ein Bild in den Fußzeilenbereich eines PDF-Dokuments einfügen. Wir verwenden den bereitgestellten C#-Quellcode, um ein vorhandenes PDF-Dokument zu öffnen, einen Bildpuffer zu erstellen, seine Eigenschaften festzulegen und ihn allen Seiten des PDF-Dokuments hinzuzufügen.

## Schritt 1: Einrichten der Umgebung

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Eine installierte .NET-Entwicklungsumgebung.
- Die Aspose.PDF-Bibliothek für .NET wurde heruntergeladen und in Ihrem Projekt referenziert.

## Schritt 2: Vorhandenes PDF-Dokument laden

Der erste Schritt besteht darin, das vorhandene PDF-Dokument in Ihr Projekt zu laden. So geht's:

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Öffnen Sie das vorhandene PDF-Dokument
Document pdfDocument = new Document(dataDir + "ImageInFooter.pdf");
```

Ersetzen Sie „IHR DOKUMENTVERZEICHNIS“ unbedingt durch den tatsächlichen Pfad zum Verzeichnis, in dem sich Ihr PDF-Dokument befindet.

## Schritt 3: Erstellen und Hinzufügen des Bildes im Fußzeilenbereich

Nachdem das PDF-Dokument geladen ist, können wir einen Bildstempel erstellen und ihn allen Seiten des Dokuments hinzufügen. So geht's:

```csharp
// Erstellen Sie den Frame-Puffer
ImageStamp imageStamp = new ImageStamp(dataDir + "aspose-logo.jpg");

// Bildpuffereigenschaften festlegen
imageStamp.BottomMargin = 10;
imageStamp.HorizontalAlignment = HorizontalAlignment.Center;
imageStamp.VerticalAlignment = VerticalAlignment.Bottom;

//Bildpuffer zu allen Seiten hinzufügen
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(imageStamp);
}
```

Der obige Code erstellt einen Bildpuffer aus der Datei „aspose-logo.jpg“ und legt dessen Eigenschaften fest, wie z. B. unteren Rand, horizontale und vertikale Ausrichtung. Anschließend wird der Bildpuffer zu allen Seiten des PDF-Dokuments hinzugefügt.

## Schritt 4: Speichern des geänderten PDF-Dokuments

Sobald das Bild zum Fußzeilenabschnitt hinzugefügt wurde, können wir das geänderte PDF-Dokument speichern. So geht's:

```csharp
// Speichern Sie das geänderte PDF-Dokument
pdfDocument.Save(dataDir + "ImageInFooter_out.pdf");
```

Der obige Code speichert das bearbeitete PDF-Dokument im angegebenen Verzeichnis.

### Beispielquellcode für Image In Footer mit Aspose.PDF für .NET 
```csharp

// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dokument öffnen
Document pdfDocument = new Document(dataDir+ "ImageInFooter.pdf");

// Fußzeile erstellen
ImageStamp imageStamp = new ImageStamp(dataDir+ "aspose-logo.jpg");

// Eigenschaften des Stempels festlegen
imageStamp.BottomMargin = 10;
imageStamp.HorizontalAlignment = HorizontalAlignment.Center;
imageStamp.VerticalAlignment = VerticalAlignment.Bottom;

// Fußzeile auf allen Seiten hinzufügen
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(imageStamp);
}
dataDir = dataDir + "ImageInFooter_out.pdf";

// Aktualisierte PDF-Datei speichern
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage in footer added successfully.\nFile saved at " + dataDir);
```

## Abschluss

Herzlichen Glückwunsch! Sie haben gelernt, wie Sie mit Aspose.PDF für .NET ein Bild in den Fußzeilenbereich eines PDF-Dokuments einfügen. Sie können jetzt die Fußzeilen Ihrer PDF-Dokumente anpassen, indem Sie Bilder hinzufügen.

### FAQs zum Bild in der Fußzeile

#### F: Welchen Zweck hat das Hinzufügen eines Bildes zum Fußzeilenbereich eines PDF-Dokuments?

A: Wenn Sie dem Fußzeilenabschnitt eines PDF-Dokuments ein Bild hinzufügen, können Sie am unteren Rand jeder Seite visuelle Elemente wie ein Logo oder ein Wasserzeichen einfügen. Dies kann das Branding und die Ästhetik des PDF-Inhalts verbessern.

#### F: Wie erreicht man mit dem bereitgestellten C#-Quellcode das Hinzufügen eines Bilds zum Fußzeilenabschnitt eines PDF-Dokuments?

 A: Der bereitgestellte Code zeigt, wie man ein vorhandenes PDF-Dokument lädt, ein`ImageStamp` Objekt aus einer Bilddatei, legen Sie Eigenschaften wie unteren Rand und Ausrichtung fest und fügen Sie dann den Bildstempel in die Fußzeile aller Seiten ein.

#### F: Kann ich die Position und Ausrichtung des Bildes im Fußzeilenbereich anpassen?

 A: Ja, Sie können die Position und Ausrichtung des Bildes im Fußzeilenbereich anpassen, indem Sie die Eigenschaften des`ImageStamp` Objekt. Der Codeausschnitt setzt Eigenschaften wie`BottomMargin`, `HorizontalAlignment` , Und`VerticalAlignment`.

#### F: Ist es möglich, dem Fußzeilenbereich auf verschiedenen Seiten des PDF-Dokuments unterschiedliche Bilder hinzuzufügen?

A: Ja, Sie können dem Fußzeilenbereich auf verschiedenen Seiten unterschiedliche Bilder hinzufügen, indem Sie separate`ImageStamp` Objekte mit unterschiedlichen Bilddateien und Eigenschaften und fügen Sie sie dann bestimmten Seiten hinzu.

#### F: Wie stellt der Code sicher, dass das Bild allen Seiten des PDF-Dokuments hinzugefügt wird?

 A: Der bereitgestellte Code verwendet eine`foreach` Schleife, um alle Seiten des PDF-Dokuments zu durchlaufen und fügt die gleiche`ImageStamp` zum Fußzeilenbereich jeder Seite.

#### F: Kann ich mit einem ähnlichen Ansatz andere Elemente wie Text oder Formen zum Fußzeilenbereich hinzufügen?

 A: Ja, Sie können mit einem ähnlichen Ansatz weitere Elemente wie Text oder Formen zum Fußzeilenabschnitt hinzufügen, indem Sie die entsprechenden Stempelobjekte erstellen (z. B.`TextStamp`) und legen Sie deren Eigenschaften entsprechend fest.

#### F: Wie gebe ich den Pfad zur Bilddatei an, die ich der Fußzeile hinzufügen möchte?

 A: Der Pfad zur Image-Datei wird bei der Erstellung des`ImageStamp` Objekt, wie im Code gezeigt. Stellen Sie sicher, dass Sie den richtigen Pfad zur Bilddatei angeben.

#### F: Kann ich die Bildgröße im Fußzeilenbereich anpassen?

 A: Ja, Sie können die Größe des Bildes im Fußzeilenbereich anpassen, indem Sie die Abmessungen des`ImageStamp` mit Eigenschaften wie`Width` Und`Height`.

#### F: Ist es möglich, das Bild im Fußzeilenbereich zu entfernen oder zu ersetzen, nachdem es hinzugefügt wurde?

 A: Ja, Sie können das Bild im Fußzeilenbereich entfernen oder ersetzen, indem Sie den Inhalt des`ImageStamp` Objekt oder Entfernen des Stempels von bestimmten Seiten.

#### F: Wie geht der Code mit Szenarien um, in denen die Abmessungen des Bildes den verfügbaren Platz in der Fußzeile überschreiten?

 A: Der Code setzt Eigenschaften wie`BottomMargin`, `HorizontalAlignment` , Und`VerticalAlignment` um die Positionierung und Ausrichtung des Bildes zu steuern. Stellen Sie sicher, dass diese Eigenschaften angepasst sind, um Überlappungen oder Layoutprobleme zu vermeiden.