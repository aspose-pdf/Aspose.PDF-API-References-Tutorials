---
title: Von RGB in Graustufen konvertieren
linktitle: Von RGB in Graustufen konvertieren
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET PDFs von RGB in Graustufen konvertieren. Verbessern Sie die Druckqualität und reduzieren Sie die Dateigröße.
type: docs
weight: 60
url: /de/net/programming-with-document/convertfromrgbtograyscale/
---

In diesem Tutorial führen wir Sie durch den Prozess der Konvertierung eines PDF-Dokuments vom RGB-Farbraum in Graustufen mit Aspose.PDF für .NET. Diese Konvertierung kann für verschiedene Zwecke nützlich sein, beispielsweise zum Reduzieren der Dateigröße oder zum Vorbereiten von Dokumenten für den Druck. Befolgen Sie die nachstehende Schritt-für-Schritt-Anleitung:

## Schritt 1: Laden Sie die Quell-PDF-Datei

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
using (Document document = new Document(dataDir + "input.pdf"))
{
    // Ihr Code hier...
}
```

## Schritt 2: Legen Sie die Konvertierungsstrategie fest

```csharp
Aspose.Pdf.RgbToDeviceGrayConversionStrategy strategy = new Aspose.Pdf.RgbToDeviceGrayConversionStrategy();
```

## Schritt 3: Konvertieren Sie jede Seite in Graustufen

```csharp
for (int idxPage = 1; idxPage <= document.Pages.Count; idxPage++)
{
    Page page = document.Pages[idxPage];
    strategy.Convert(page);
}
```

## Schritt 4: Speichern Sie die resultierende Datei

```csharp
document.Save(dataDir + "Test-gray_out.pdf");
```

Glückwunsch! Sie haben das PDF-Dokument mit Aspose.PDF für .NET erfolgreich von RGB in Graustufen konvertiert.

### Beispielquellcode für die Konvertierung von RGB in Graustufen mit Aspose.PDF für .NET:

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Laden Sie die PDF-Quelldatei
using (Document document = new Document(dataDir + "input.pdf"))
{
    Aspose.Pdf.RgbToDeviceGrayConversionStrategy strategy = new Aspose.Pdf.RgbToDeviceGrayConversionStrategy();

    for (int idxPage = 1; idxPage <= document.Pages.Count; idxPage++)
    {
        Page page = document.Pages[idxPage];
        strategy.Convert(page);
    }

    document.Save(dataDir + "Test-gray_out.pdf");
}
```

Jetzt können Sie Ihre PDF-Dokumente mit Aspose.PDF für .NET ganz einfach von RGB in Graustufen konvertieren.

