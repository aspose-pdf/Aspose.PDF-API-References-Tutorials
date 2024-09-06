---
title: Zeichen in PDF-Datei hervorheben
linktitle: Zeichen in PDF-Datei hervorheben
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Zeichen in PDF-Dateien hervorheben.
type: docs
weight: 240
url: /de/net/programming-with-text/highlight-character-in-pdf/
---
In diesem Tutorial erklären wir, wie man mit der Aspose.PDF-Bibliothek für .NET Zeichen in einer PDF-Datei hervorhebt. Wir gehen den Prozess zum Hervorheben von Zeichen in einer PDF-Datei mithilfe des bereitgestellten C#-Quellcodes Schritt für Schritt durch.

## Anforderungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Die Aspose.PDF-Bibliothek für .NET ist installiert.
- Grundlegende Kenntnisse der C#-Programmierung.

## Schritt 1: Einrichten des Dokumentverzeichnisses

 Zuerst müssen Sie den Pfad zum Verzeichnis festlegen, in dem sich Ihre PDF-Eingabedatei befindet. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` im`dataDir` Variable mit dem Pfad zu Ihrer PDF-Datei.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Laden Sie das PDF-Dokument

 Als nächstes laden wir das Eingabe-PDF-Dokument mit dem`Aspose.Pdf.Document` Klasse.

```csharp
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");
```

## Schritt 3: PDF in Bild konvertieren

 Um Zeichen hervorzuheben, konvertieren wir das PDF-Dokument in ein Bild mit dem`PdfConverter` Klasse. Wir legen die Auflösung für die Konvertierung fest und holen das Bild als`Bitmap` Objekt.

```csharp
int resolution = 150;
using (MemoryStream ms = new MemoryStream())
{
     PdfConverter conv = new PdfConverter(pdfDocument);
     conv. Resolution = new Resolution(resolution, resolution);
     conv. GetNextImage(ms, System.Drawing.Imaging.ImageFormat.Png);
     Bitmap bmp = (Bitmap)Bitmap.FromStream(ms);
```

## Schritt 4: Zeichen hervorheben

 Wir durchlaufen jede Seite des PDF-Dokuments und verwenden eine`TextFragmentAbsorber` Objekt, um alle Wörter auf der Seite zu finden. Anschließend iterieren wir über die Textfragmente, Segmente und Zeichen, um sie mithilfe von Rechtecken hervorzuheben.

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bmp))
{
     // Maßstab festlegen und transformieren
     float scale = resolution / 72f;
     gr.Transform = new System.Drawing.Drawing2D.Matrix(scale, 0, 0, -scale, 0, bmp.Height);

     // Seiten durchlaufen
     for (int i = 0; i < pdfDocument.Pages.Count; i++)
     {
         Page page = pdfDocument.Pages[1];

         //Alle Wörter auf der Seite finden
         TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
         textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
         page. Accept(textFragmentAbsorber);
         TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

         // Durchlaufen von Textfragmenten
         foreach(TextFragment textFragment in textFragmentCollection)
         {
             if (i == 0)
             {
                 // Zeichen hervorheben
                 gr.DrawRectangle(
                     Think.Yellow,
                     (float)textFragment.Position.XIndent,
                     (float)textFragment.Position.YIndent,
                     (float)textFragment.Rectangle.Width,
                     (float)textFragment.Rectangle.Height);

                 // Durch Segmente schleifen
                 foreach(TextSegment segment in textFragment.Segments)
                 {
                     // Highlight-Segment
                     gr.DrawRectangle(
                         Think Green,
                         (float)segment.Rectangle.LLX,
                         (float)segment.Rectangle.LLY,
                         (float)segment.Rectangle.Width,
                         (float)segment.Rectangle.Height);

                     // Durchlaufen von Zeichen
                     foreach(CharInfo characterInfo in segment.Characters)
                     {
                         // Highlightcharakter
                         gr.DrawRectangle(
                             Think.Black,
                             (float)characterInfo.Rectangle.LLx,
                             (float)characterInfo.Rectangle.LLY,
                             (float)characterInfo.Rectangle.Width,
                             (float)characterInfo.Rectangle.Height);
                     }
                 }
             }
         }
     }
}
```

## Schritt 5: Speichern Sie das Ausgabebild

Abschließend speichern wir das geänderte Bild mit den hervorgehobenen Zeichen in der angegebenen Ausgabedatei.

```csharp
dataDir = dataDir + "HighlightCharacterInPDF_out.png";
bmp.Save(dataDir, System.Drawing.Imaging.ImageFormat.Png);
```

### Beispielquellcode zum Hervorheben von Zeichen in PDF mit Aspose.PDF für .NET 
```csharp
try
{
	// Der Pfad zum Dokumentverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	int resolution = 150;
	Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");
	using (MemoryStream ms = new MemoryStream())
	{
		PdfConverter conv = new PdfConverter(pdfDocument);
		conv.Resolution = new Resolution(resolution, resolution);
		conv.GetNextImage(ms, System.Drawing.Imaging.ImageFormat.Png);
		Bitmap bmp = (Bitmap)Bitmap.FromStream(ms);
		using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bmp))
		{
			float scale = resolution / 72f;
			gr.Transform = new System.Drawing.Drawing2D.Matrix(scale, 0, 0, -scale, 0, bmp.Height);
			for (int i = 0; i < pdfDocument.Pages.Count; i++)
			{
				Page page = pdfDocument.Pages[1];
				// Erstellen Sie ein TextAbsorber-Objekt, um alle Wörter zu finden
				TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
				textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
				page.Accept(textFragmentAbsorber);
				// Holen Sie sich die extrahierten Textfragmente
				TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
				// Durchlaufen der Fragmente
				foreach (TextFragment textFragment in textFragmentCollection)
				{
					if (i == 0)
					{
						gr.DrawRectangle(
						Pens.Yellow,
						(float)textFragment.Position.XIndent,
						(float)textFragment.Position.YIndent,
						(float)textFragment.Rectangle.Width,
						(float)textFragment.Rectangle.Height);
						for (int segNum = 1; segNum <= textFragment.Segments.Count; segNum++)
						{
							TextSegment segment = textFragment.Segments[segNum];
							for (int charNum = 1; charNum <= segment.Characters.Count; charNum++)
							{
								CharInfo characterInfo = segment.Characters[charNum];
								Aspose.Pdf.Rectangle rect = page.GetPageRect(true);
								Console.WriteLine("TextFragment = " + textFragment.Text + "    Page URY = " + rect.URY +
												  "   TextFragment URY = " + textFragment.Rectangle.URY);
								gr.DrawRectangle(
								Pens.Black,
								(float)characterInfo.Rectangle.LLX,
								(float)characterInfo.Rectangle.LLY,
								(float)characterInfo.Rectangle.Width,
								(float)characterInfo.Rectangle.Height);
							}
							gr.DrawRectangle(
							Pens.Green,
							(float)segment.Rectangle.LLX,
							(float)segment.Rectangle.LLY,
							(float)segment.Rectangle.Width,
							(float)segment.Rectangle.Height);
						}
					}
				}
			}
		}
		dataDir = dataDir + "HighlightCharacterInPDF_out.png";
		bmp.Save(dataDir, System.Drawing.Imaging.ImageFormat.Png);
	}
	Console.WriteLine("\nCharacters highlighted successfully in pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx.");
}
```

## Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie mit der Aspose.PDF-Bibliothek für .NET Zeichen in einem PDF-Dokument hervorheben. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Code ausführen, können Sie Zeichen in einem PDF hervorheben und die Ausgabe als Bild speichern.

### Häufig gestellte Fragen

#### F: Was ist der Zweck des Tutorials „Zeichen in PDF-Datei hervorheben“?

A: Das Tutorial „Zeichen in PDF-Datei hervorheben“ erklärt, wie Sie mit der Aspose.PDF-Bibliothek für .NET Zeichen in einem PDF-Dokument hervorheben. Das Tutorial bietet eine Schritt-für-Schritt-Anleitung und C#-Quellcode, um dies zu erreichen.

#### F: Warum sollte ich Zeichen in einem PDF-Dokument hervorheben wollen?

A: Das Hervorheben von Zeichen in einem PDF-Dokument kann für verschiedene Zwecke nützlich sein, beispielsweise um bestimmte Inhalte hervorzuheben oder bestimmten Text besser sichtbar und unterscheidbar zu machen.

#### F: Wie richte ich das Dokumentverzeichnis ein?

A: So richten Sie das Dokumentverzeichnis ein:

1.  Ersetzen`"YOUR DOCUMENT DIRECTORY"` im`dataDir` Variable mit dem Pfad zum Verzeichnis, in dem sich Ihre Eingabe-PDF-Datei befindet.

#### F: Wie lade ich das PDF-Dokument und konvertiere es in ein Bild?

 A: Im Tutorial`Aspose.Pdf.Document` wird verwendet, um das PDF-Eingabedokument zu laden. Anschließend wird die`PdfConverter` Klasse wird verwendet, um das PDF-Dokument in ein Bild umzuwandeln. Die Auflösung des Bildes wird festgelegt und das Bild wird als`Bitmap` Objekt.

#### F: Wie hebe ich Zeichen im PDF-Dokumentbild hervor?

A: Das Tutorial führt Sie durch den Prozess des Durchlaufens jeder Seite des PDF-Dokuments und der Suche nach Wörtern mithilfe eines`TextFragmentAbsorber`, und durchläuft Textfragmente, -segmente und -zeichen, um sie mithilfe von Rechtecken hervorzuheben.

#### F: Kann ich das Erscheinungsbild der hervorgehobenen Zeichen und Segmente anpassen?

A: Ja, Sie können das Erscheinungsbild der hervorgehobenen Zeichen und Segmente anpassen, indem Sie die bei den Zeichenvorgängen verwendeten Farben und Stile ändern.

#### F: Wie speichere ich das geänderte Bild mit den hervorgehobenen Zeichen?

 A: Das Tutorial zeigt, wie Sie das geänderte Bild mit den hervorgehobenen Zeichen in der angegebenen Ausgabedatei speichern können. Dazu verwenden Sie den`Save` Methode der`Bitmap` Klasse.

#### F: Ist für dieses Tutorial eine gültige Aspose-Lizenz erforderlich?

A: Ja, damit dieses Tutorial richtig funktioniert, ist eine gültige Aspose-Lizenz erforderlich. Sie können eine Volllizenz oder eine 30-tägige temporäre Lizenz von der Aspose-Website erwerben.