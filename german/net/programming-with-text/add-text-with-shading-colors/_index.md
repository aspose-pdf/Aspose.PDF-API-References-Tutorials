---
title: Fügen Sie Text mit Schattierungsfarben hinzu
linktitle: Fügen Sie Text mit Schattierungsfarben hinzu
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Text mit Schattierungsfarben zu einem PDF-Dokument hinzufügen.
type: docs
weight: 80
url: /de/net/programming-with-text/add-text-with-shading-colors/
---

Dieses Tutorial führt Sie durch den Prozess des Hinzufügens von Text mit Schattierungsfarben mithilfe von Aspose.PDF für .NET. Der bereitgestellte C#-Quellcode demonstriert die notwendigen Schritte.

## Anforderungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Visual Studio oder ein anderer auf Ihrem Computer installierter C#-Compiler.
- Aspose.PDF für .NET-Bibliothek. Sie können es von der offiziellen Aspose-Website herunterladen oder einen Paketmanager wie NuGet verwenden, um es zu installieren.

## Schritt 1: Richten Sie das Projekt ein
1. Erstellen Sie ein neues C#-Projekt in Ihrer bevorzugten Entwicklungsumgebung.
2. Fügen Sie einen Verweis auf die Aspose.PDF für .NET-Bibliothek hinzu.

## Schritt 2: Erforderliche Namespaces importieren
Fügen Sie in der Codedatei, in der Sie Text mit Schattierungsfarben hinzufügen möchten, die folgende using-Anweisung oben in der Datei hinzu:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

## Schritt 3: Legen Sie das Dokumentverzeichnis fest
 Suchen Sie im Code die Zeile mit der Aufschrift`string dataDir = "YOUR DOCUMENT DIRECTORY";` und ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem Pfad zu dem Verzeichnis, in dem Ihre Dokumente gespeichert sind.

## Schritt 4: Laden Sie das PDF-Dokument
 Laden Sie das vorhandene PDF-Dokument mit`Document` Konstruktor und geben Sie den Pfad zur Dokumentdatei an.

```csharp
using(Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
     // Code kommt hier...
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
 Erstelle eine neue`Color`Objekt mit einem Musterfarbraum und geben Sie die Verlaufsschattierungsfarben an. Weisen Sie dem diese Farbe zu`ForegroundColor` Eigentum der`TextState` des`TextFragment` Objekt.

```csharp
textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
{
     PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
};
```

## Schritt 7: Zusätzliche Textformatierung anwenden (optional)
 Sie können dem Textfragment zusätzliche Formatierungen hinzufügen, z. B. Unterstreichungen, indem Sie die Eigenschaften des Textfragments ändern`TextState` Objekt.

```csharp
textFragment.TextState.Underline = true;
```

## Schritt 8: Speichern Sie das geänderte PDF-Dokument
 Speichern Sie das geänderte PDF-Dokument mit`Save` Methode der`Document` Objekt.

```csharp
pdfDocument.Save(dataDir + "text_out.pdf");
```

### Beispielquellcode für das Hinzufügen von Text mit Schattierungsfarben mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
using (Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
	TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
	pdfDocument.Pages.Accept(absorber);
	TextFragment textFragment = absorber.TextFragments[1];
	// Erstellen Sie eine neue Farbe mit dem Musterfarbraum
	textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
	{
		PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
	};
	textFragment.TextState.Underline = true;
	pdfDocument.Save(dataDir + "text_out.pdf");
}
```

## Abschluss
Sie haben mit Aspose.PDF für .NET erfolgreich Text mit Schattierungsfarben zu Ihrem PDF-Dokument hinzugefügt. Die resultierende PDF-Datei befindet sich nun im angegebenen Ausgabedateipfad.