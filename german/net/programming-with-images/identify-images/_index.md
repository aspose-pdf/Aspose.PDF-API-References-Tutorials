---
title: Bilder identifizieren
linktitle: Bilder identifizieren
second_title: Aspose.PDF für .NET API-Referenz
description: Identifizieren Sie Bilder in einer PDF-Datei ganz einfach und bestimmen Sie ihren Farbtyp mit Aspose.PDF für .NET.
type: docs
weight: 150
url: /de/net/programming-with-images/identify-images/
---

Diese Anleitung führt Sie Schritt für Schritt durch die Identifizierung von Bildern in einer PDF-Datei mit Aspose.PDF für .NET. Stellen Sie sicher, dass Sie Ihre Umgebung bereits eingerichtet haben, und führen Sie die folgenden Schritte aus:

## Schritt 1: Definieren Sie das Dokumentenverzeichnis

 Stellen Sie sicher, dass Sie das richtige Dokumentverzeichnis festlegen. Ersetzen`"YOUR DOCUMENT DIRECTORY"` Geben Sie im Code den Pfad zu dem Verzeichnis ein, in dem sich Ihr PDF-Dokument befindet.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Initialisieren Sie die Zähler

In diesem Schritt initialisieren wir die Zähler für Graustufenbilder und RGB-Bilder.

```csharp
int grayscaled = 0; // Zähler für Graustufenbilder
int rdg = 0; // Zähler für RGB-Bilder
```

## Schritt 3: Öffnen Sie das PDF-Dokument

 In diesem Schritt öffnen wir das PDF-Dokument mit`Document` Klasse von Aspose.PDF. Benutzen Sie die`Document` Konstruktor und übergeben Sie den Pfad zum PDF-Dokument.

```csharp
using (Document document = new Document(dataDir + "ExtractImages.pdf"))
{
```

## Schritt 4: Dokumentseiten durchsuchen

In diesem Schritt gehen wir alle Seiten des PDF-Dokuments durch und identifizieren die Bilder auf jeder Seite.

```csharp
foreach(Page page in document.Pages)
{
```

## Schritt 5: Bildplatzierungen abrufen

 In diesem Schritt verwenden wir`ImagePlacementAbsorber` um Bildplatzierungen auf jeder Seite abzurufen.

```csharp
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
page. Accept(abs);
```

## Schritt 6: Zählen Sie die Bilder und identifizieren Sie ihren Farbtyp

In diesem Schritt zählen wir die Anzahl der Bilder auf jeder Seite und identifizieren ihren Farbtyp (Graustufen oder RGB).

```csharp
Console.WriteLine("Total Images = {0} on page number {1}", abs.ImagePlacements.Count, page.Number);
int image_counter = 1;
foreach(ImagePlacement ia in abs.ImagePlacements)
{
     ColorType colorType = ia.Image.GetColorType();
     switch (colorType)
     {
         ColorType.Grayscale box:
             ++grayscaled;
             Console.WriteLine("Image {0} is grayscale...", image_counter);
             break;
         box ColorType.Rgb:
             ++rgd;
             Console.WriteLine("Image {0} is RGB...", image_counter);
             break;
     }
     image_counter += 1;
}
```

### Beispielquellcode für „Bilder identifizieren“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Zähler für Graustufenbilder
int grayscaled = 0;
// Zähler für RGB-Bilder
int rgd = 0;
using (Document document = new Document(dataDir + "ExtractImages.pdf"))
{
	foreach (Page page in document.Pages)
	{
		Console.WriteLine("--------------------------------");
		ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
		page.Accept(abs);
		// Ermitteln Sie die Anzahl der Bilder auf einer bestimmten Seite
		Console.WriteLine("Total Images = {0} over page number {1}", abs.ImagePlacements.Count, page.Number);
		// Document.Pages[29].Accept(abs);
		int image_counter = 1;
		foreach (ImagePlacement ia in abs.ImagePlacements)
		{
			ColorType colorType = ia.Image.GetColorType();
			switch (colorType)
			{
				case ColorType.Grayscale:
					++grayscaled;
					Console.WriteLine("Image {0} is GrayScale...", image_counter);
					break;
				case ColorType.Rgb:
					++rgd;
					Console.WriteLine("Image {0} is RGB...", image_counter);
					break;
			}
			image_counter += 1;
		}
	}
}
```

## Abschluss

Herzlichen Glückwunsch! Sie haben mit Aspose.PDF für .NET erfolgreich Bilder in einer PDF-Datei identifiziert. Die Bilder wurden gezählt und ihr Farbtyp (Graustufen oder RGB) identifiziert. Sie können diese Informationen nun für Ihre spezifischen Bedürfnisse nutzen.