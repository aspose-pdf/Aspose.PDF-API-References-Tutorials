---
title: Text mit Schattierungsfarben in PDF-Datei einfügen
linktitle: Text mit Schattierungsfarben in PDF-Datei einfügen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Text mit Schattierungsfarben in eine PDF-Datei einfügen.
type: docs
weight: 80
url: /de/net/programming-with-text/add-text-with-shading-colors/
---
Dieses Tutorial führt Sie durch den Prozess des Hinzufügens von Text mit Schattierungsfarben in eine PDF-Datei mithilfe von Aspose.PDF für .NET. Der bereitgestellte C#-Quellcode demonstriert die erforderlichen Schritte.

## Anforderungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Visual Studio oder ein anderer C#-Compiler muss auf Ihrem Computer installiert sein.
- Aspose.PDF für .NET-Bibliothek. Sie können es von der offiziellen Aspose-Website herunterladen oder einen Paketmanager wie NuGet verwenden, um es zu installieren.

## Schritt 1: Einrichten des Projekts
1. Erstellen Sie ein neues C#-Projekt in Ihrer bevorzugten Entwicklungsumgebung.
2. Fügen Sie einen Verweis auf die Aspose.PDF-Bibliothek für .NET hinzu.

## Schritt 2: Erforderliche Namespaces importieren
Fügen Sie in der Codedatei, in der Sie Text mit Schattierungsfarben hinzufügen möchten, oben in der Datei die folgende using-Direktive hinzu:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

## Schritt 3: Dokumentverzeichnis festlegen
 Suchen Sie im Code nach der Zeile, die besagt:`string dataDir = "YOUR DOCUMENT DIRECTORY";` und ersetzen`"YOUR DOCUMENT DIRECTORY"` durch den Pfad zum Verzeichnis, in dem Ihre Dokumente gespeichert sind.

## Schritt 4: Laden Sie das PDF-Dokument
 Laden Sie das vorhandene PDF-Dokument mit dem`Document` Konstruktor und geben Sie den Pfad zur Dokumentdatei an.

```csharp
using(Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
     // Der Code kommt hier hin...
}
```

## Schritt 5: Suchen Sie den zu ändernden Text
 Verwenden`TextFragmentAbsorber` um den gewünschten Text im Dokument zu finden. Im bereitgestellten Code wird nach dem Text „Lorem ipsum“ gesucht.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
pdfDocument.Pages.Accept(absorb);
TextFragment textFragment = absorb.TextFragments[1];
```

## Schritt 6: Schattierungsfarbe für den Text festlegen
 Erstellen Sie ein neues`Color` Objekt mit einem Musterfarbraum und geben Sie die Schattierungsfarben des Farbverlaufs an. Weisen Sie diese Farbe dem`ForegroundColor` Eigentum der`TextState` der`TextFragment` Objekt.

```csharp
textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
{
     PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
};
```

## Schritt 7: Zusätzliche Textformatierung anwenden (optional)
 Sie können dem Textfragment zusätzliche Formatierungen wie Unterstreichungen zuweisen, indem Sie die Eigenschaften des`TextState` Objekt.

```csharp
textFragment.TextState.Underline = true;
```

## Schritt 8: Speichern Sie das geänderte PDF-Dokument
 Speichern Sie das geänderte PDF-Dokument mit dem`Save` Methode der`Document` Objekt.

```csharp
pdfDocument.Save(dataDir + "text_out.pdf");
```

### Beispielquellcode zum Hinzufügen von Text mit Schattierungsfarben unter Verwendung von Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
using (Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
	TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
	pdfDocument.Pages.Accept(absorber);
	TextFragment textFragment = absorber.TextFragments[1];
	// Neue Farbe mit Musterfarbraum erstellen
	textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
	{
		PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
	};
	textFragment.TextState.Underline = true;
	pdfDocument.Save(dataDir + "text_out.pdf");
}
```

## Abschluss
Sie haben Ihrem PDF-Dokument mithilfe von Aspose.PDF für .NET erfolgreich Text mit Schattierungsfarben hinzugefügt. Die resultierende PDF-Datei befindet sich jetzt im angegebenen Ausgabedateipfad.

### Häufig gestellte Fragen

#### F: Worauf liegt der Schwerpunkt dieses Tutorials?

A: Dieses Tutorial führt Sie durch den Prozess des Hinzufügens von Text mit Schattierungsfarben zu einer PDF-Datei mithilfe der Aspose.PDF für .NET-Bibliothek. Der bereitgestellte C#-Quellcode demonstriert die dafür erforderlichen Schritte.

#### F: Welche Namespaces muss ich für dieses Tutorial importieren?

A: Importieren Sie in der Codedatei, in der Sie Text mit Schattierungsfarben hinzufügen möchten, am Anfang der Datei die folgenden Namespaces:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

#### F: Wie gebe ich das Dokumentverzeichnis an?

 A: Suchen Sie im Code die Zeile`string dataDir = "YOUR DOCUMENT DIRECTORY";` und ersetzen`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

#### F: Wie lade ich ein vorhandenes PDF-Dokument?

 A: In Schritt 4 laden Sie ein vorhandenes PDF-Dokument mit dem`Document` Konstruktor und Angabe des Pfads zur Dokumentdatei:

```csharp
using(Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
     // Der Code kommt hier hin...
}
```

#### F: Wie finde und ändere ich bestimmten Text im PDF-Dokument?

 A: In Schritt 5 verwenden Sie die`TextFragmentAbsorber`um den gewünschten Text im Dokument zu finden. Anschließend können Sie seine Eigenschaften ändern:

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
pdfDocument.Pages.Accept(absorber);
TextFragment textFragment = absorber.TextFragments[1];
```

#### F: Wie kann ich Schattierungsfarben für den Text festlegen?

 A: In Schritt 6 erstellen Sie eine neue`Color` Objekt mit einem Musterfarbraum und geben Sie die Schattierungsfarben des Farbverlaufs an. Weisen Sie diese Farbe dem`ForegroundColor` Eigentum der`TextState` der`TextFragment` Objekt:

```csharp
textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
{
     PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
};
```

#### F: Kann ich auf den geänderten Text zusätzliche Textformatierungen anwenden?

 A: Ja, in Schritt 7 können Sie zusätzliche Textformatierungen wie Unterstreichungen anwenden, indem Sie die Eigenschaften des`TextState` Objekt:

```csharp
textFragment.TextState.Underline = true;
```

#### F: Wie speichere ich das geänderte PDF-Dokument?

 A: In Schritt 8 speichern Sie das geänderte PDF-Dokument mit dem`Save` Methode der`Document` Objekt:

```csharp
pdfDocument.Save(dataDir + "text_out.pdf");
```

#### F: Was ist die wichtigste Erkenntnis aus diesem Tutorial?

A: In diesem Tutorial haben Sie erfolgreich gelernt, wie Sie Ihr PDF-Dokument verbessern können, indem Sie mit Aspose.PDF für .NET Text mit Schattierungsfarben hinzufügen. Dies kann besonders nützlich sein, um bestimmte Textinhalte in Ihren PDF-Dateien hervorzuheben und zu betonen.