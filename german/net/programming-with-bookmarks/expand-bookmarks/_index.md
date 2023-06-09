---
title: Erweitern Sie Lesezeichen
linktitle: Erweitern Sie Lesezeichen
second_title: Aspose.PDF für .NET API-Referenz
description: Erweitern Sie ganz einfach die Lesezeichen Ihrer PDF-Dateien für eine verbesserte Navigation mit Aspose.PDF für .NET.
type: docs
weight: 50
url: /de/net/programming-with-bookmarks/expand-bookmarks/
---

Wenn Sie Lesezeichen in einem PDF-Dokument erweitern, werden standardmäßig alle geöffneten Lesezeichen angezeigt. Mit Aspose.PDF für .NET können Sie Lesezeichen ganz einfach erweitern, indem Sie dem folgenden Quellcode folgen:

## Schritt 1: Erforderliche Bibliotheken importieren

Bevor Sie beginnen, müssen Sie die erforderlichen Bibliotheken für Ihr C#-Projekt importieren. Hier ist die notwendige Importanweisung:

```csharp
using Aspose.Pdf;
```

## Schritt 2: Legen Sie den Pfad zum Dokumentenordner fest

 In diesem Schritt müssen Sie den Pfad zu dem Ordner angeben, der die PDF-Datei enthält, deren Lesezeichen Sie erweitern möchten. Ersetzen`"YOUR DOCUMENT DIRECTORY"` Geben Sie im folgenden Code den tatsächlichen Pfad zu Ihrem Dokumentenordner ein:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 3: Öffnen Sie das PDF-Dokument

Nun öffnen wir das PDF-Dokument, dessen Lesezeichen wir erweitern möchten, mit folgendem Code:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Schritt 4: Stellen Sie den Seitenanzeigemodus ein

 In diesem Schritt stellen wir den Seitenanzeigemodus so ein, dass standardmäßig Lesezeichen angezeigt werden. Wir benutzen das`PageMode` Eigentum der`doc`Objekt, um den gewünschten Seitenmodus festzulegen. Hier ist der entsprechende Code:

```csharp
doc.PageMode = PageMode.UseOutlines;
```

## Schritt 5: Durchsuchen Sie die Lesezeichen und erweitern Sie sie

 Jetzt durchlaufen wir jedes Lesezeichenelement in der Lesezeichensammlung des Dokuments und setzen den geöffneten Status jedes Elements auf`true` um sie standardmäßig zu erweitern. Hier ist der entsprechende Code:

```csharp
foreach(OutlineItemCollection item in doc.Outlines)
{
     item. Open = true;
}
```

## Schritt 6: Speichern Sie die aktualisierte Datei

 Abschließend speichern wir die aktualisierte PDF-Datei mit`Save` Methode der`doc` Objekt. Hier ist der entsprechende Code:

```csharp
dataDir = dataDir + "ExpandBookmarks_out.pdf";
doc.Save(dataDir);
```

### Beispielquellcode für „Lesezeichen erweitern“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document doc = new Document(dataDir + "input.pdf");
// Stellen Sie den Seitenansichtsmodus ein, z. B. Miniaturansichten anzeigen, Vollbild anzeigen, Anhangsbereich anzeigen
doc.PageMode = PageMode.UseOutlines;
// Durchsuchen Sie jedes Ouline-Element in der Gliederungssammlung der PDF-Datei
foreach (OutlineItemCollection item in doc.Outlines)
{
	// Offenen Status für Gliederungselement festlegen
	item.Open = true;
}
dataDir = dataDir + "ExpandBookmarks_out.pdf";
// Ausgabe speichern
doc.Save(dataDir);
Console.WriteLine("\nBookmarks expanded successfully.\nFile saved at " + dataDir);
```

## Abschluss

Herzlichen Glückwunsch! Sie haben jetzt eine Schritt-für-Schritt-Anleitung zum Entwickeln von Lesezeichen mit Aspose.PDF für .NET. Mit diesem Code können Sie alle Standardlesezeichen in Ihren PDF-Dokumenten anzeigen.

Weitere Informationen zu erweiterten Funktionen zur Lesezeichenmanipulation finden Sie unbedingt in der offiziellen Aspose.PDF-Dokumentation.