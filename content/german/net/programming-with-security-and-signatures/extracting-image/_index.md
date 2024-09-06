---
title: Bild extrahieren
linktitle: Bild extrahieren
second_title: Aspose.PDF für .NET API-Referenz
description: Extrahieren Sie mit Aspose.PDF für .NET ganz einfach Bilder aus PDF-Dokumenten.
type: docs
weight: 70
url: /de/net/programming-with-security-and-signatures/extracting-image/
---
Das Extrahieren von Bildern aus einem PDF-Dokument kann in vielen Fällen nützlich sein. Mit Aspose.PDF für .NET können Sie Bilder mithilfe des folgenden Quellcodes ganz einfach extrahieren:

## Schritt 1: Erforderliche Bibliotheken importieren

Bevor Sie beginnen, müssen Sie die erforderlichen Bibliotheken für Ihr C#-Projekt importieren. Hier sind die erforderlichen Importanweisungen:

```csharp
using Aspose.Pdf;
using System.Drawing;
using System.Drawing.Imaging;
```

## Schritt 2: Pfad zum Dokumentenordner festlegen

 In diesem Schritt müssen Sie den Pfad zum Ordner angeben, der die PDF-Datei enthält, aus der Sie das Bild extrahieren möchten. Ersetzen Sie`"YOUR DOCUMENTS DIRECTORY"` ersetzen Sie den folgenden Code durch den tatsächlichen Pfad zu Ihrem Dokumentordner:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir + @"ExtractingImage.pdf";
```

## Schritt 3: Bild aus PDF-Dokument extrahieren

Nun extrahieren wir das Bild mit dem folgenden Code aus dem PDF-Dokument:

```csharp
using (Document pdfDocument = new Document(input))
{
foreach(Field field in pdfDocument.Form)
{
SignatureField sf = field as SignatureField;
if (sf != null)
{
string outFile = dataDir + @"output_out.jpg";
using (Stream imageStream = sf.ExtractImage())
{
if (imageStream != null)
{
using (Image image = Bitmap.FromStream(imageStream))
{
image.Save(outFile, ImageFormat.Jpeg);
}
}
}
}
}
}
```

In diesem Beispiel durchlaufen wir jedes Feld des Formulars im PDF-Dokument. Wenn ein Signaturfeld gefunden wird, extrahieren wir das zugehörige Bild und speichern es in einer JPEG-Datei.

### Beispiel-Quellcode zum Extrahieren von Bildern mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir+ @"ExtractingImage.pdf";
using (Document pdfDocument = new Document(input))
{
	foreach (Field field in pdfDocument.Form)
	{
		SignatureField sf = field as SignatureField;
		if (sf != null)
		{
			string outFile = dataDir+ @"output_out.jpg";
			using (Stream imageStream = sf.ExtractImage())
			{
				if (imageStream != null)
				{
					using (System.Drawing.Image image = Bitmap.FromStream(imageStream))
					{
						image.Save(outFile, System.Drawing.Imaging.ImageFormat.Jpeg);
					}
				}
			}
		}
	}
}
```

## Abschluss

Herzlichen Glückwunsch! Jetzt haben Sie eine Schritt-für-Schritt-Anleitung zum Extrahieren von Bildern aus einem PDF-Dokument mit Aspose.PDF für .NET. Sie können diesen Code in Ihre eigenen Projekte integrieren, um Bilder zu extrahieren und sie nach Bedarf zu verwenden.

Weitere Informationen zu erweiterten Funktionen zur Bildextraktion und PDF-Dokumentbearbeitung finden Sie in der offiziellen Aspose.PDF-Dokumentation.


### Häufig gestellte Fragen

#### F: Ist Aspose.PDF für .NET für Anfänger geeignet?

A: Zwar sind gewisse Kenntnisse der C#-Programmierung hilfreich, unser Tutorial ist jedoch anfängerfreundlich gestaltet und führt Sie durch jeden Schritt.

#### F: Kann ich mehrere Bilder gleichzeitig extrahieren?

A: Auf jeden Fall! Durch die Implementierung von Schleifen und die Anpassung des bereitgestellten Codes können Sie mehrere Bilder aus einem einzigen PDF-Dokument extrahieren.

#### F: Ist Aspose.PDF für .NET die einzige Lösung zur Bildextraktion?

A: Es sind zwar auch andere Tools verfügbar, aber Aspose.PDF für .NET ist für seine Effizienz und umfassenden Funktionen bekannt.

#### F: Kann ich die extrahierten Bilder für kommerzielle Zwecke verwenden?

A: Ja, nach der Extraktion können Sie die Bilder nach Bedarf verwenden, auch für kommerzielle Projekte.

#### F: Wo finde ich weitere Ressourcen zur PDF-Bearbeitung mit Aspose.PDF?

A: Besuchen Sie unsere offizielle Dokumentation für eine Fülle von Ressourcen und Einblicken in die erweiterte PDF-Bearbeitung mit Aspose.PDF für .NET.