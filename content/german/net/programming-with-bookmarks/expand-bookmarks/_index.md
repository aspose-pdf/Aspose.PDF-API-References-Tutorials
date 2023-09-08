---
title: Erweitern Sie Lesezeichen in der PDF-Datei
linktitle: Erweitern Sie Lesezeichen in der PDF-Datei
second_title: Aspose.PDF für .NET API-Referenz
description: Erweitern Sie Lesezeichen in PDF-Dateien ganz einfach, um die Navigation mit Aspose.PDF für .NET zu verbessern.
type: docs
weight: 50
url: /de/net/programming-with-bookmarks/expand-bookmarks/
---
Durch Erweitern der Lesezeichen in einer PDF-Datei werden standardmäßig alle geöffneten Lesezeichen angezeigt. Mit Aspose.PDF für .NET können Sie Lesezeichen ganz einfach erweitern, indem Sie dem folgenden Quellcode folgen:

## Schritt 1: Erforderliche Bibliotheken importieren

Bevor Sie beginnen, müssen Sie die erforderlichen Bibliotheken für Ihr C#-Projekt importieren. Hier ist die notwendige Importanweisung:

```csharp
using Aspose.Pdf;
```

## Schritt 2: Legen Sie den Pfad zum Dokumentenordner fest

 In diesem Schritt müssen Sie den Pfad zu dem Ordner angeben, der die PDF-Datei enthält, deren Lesezeichen Sie erweitern möchten. Ersetzen`"YOUR DOCUMENT DIRECTORY"`Geben Sie im folgenden Code den tatsächlichen Pfad zu Ihrem Dokumentenordner ein:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 3: Öffnen Sie das PDF-Dokument

Nun öffnen wir das PDF-Dokument, dessen Lesezeichen wir erweitern möchten, mit folgendem Code:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Schritt 4: Stellen Sie den Seitenanzeigemodus ein

In diesem Schritt stellen wir den Seitenanzeigemodus so ein, dass standardmäßig Lesezeichen angezeigt werden. Wir benutzen das`PageMode` Eigentum der`doc` Objekt, um den gewünschten Seitenmodus festzulegen. Hier ist der entsprechende Code:

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

### FAQs zum Erweitern von Lesezeichen in PDF-Dateien

#### F: Was sind Lesezeichen in einer PDF-Datei?

A: Lesezeichen in einer PDF-Datei sind Navigationshilfen, die es Benutzern ermöglichen, schnell zu bestimmten Abschnitten oder Seiten innerhalb des Dokuments zu springen. Sie bieten eine bequeme Möglichkeit, auf verschiedene Teile eines Dokuments zuzugreifen.

#### F: Warum sollte ich Lesezeichen in einer PDF-Datei erweitern?

A: Das Erweitern von Lesezeichen kann die Benutzererfahrung verbessern, indem alle Lesezeichen standardmäßig im erweiterten Zustand angezeigt werden. Dadurch erhalten Benutzer einen klaren Überblick über die Struktur des Dokuments und können problemlos zu verschiedenen Abschnitten navigieren.

#### F: Wie importiere ich die erforderlichen Bibliotheken für mein C#-Projekt?

A: Um die erforderliche Bibliothek für Ihr C#-Projekt zu importieren, verwenden Sie die folgende Importanweisung:

```csharp
using Aspose.Pdf;
```

Mit dieser Direktive können Sie die von Aspose.PDF für .NET bereitgestellten Klassen und Methoden verwenden.

#### F: Wie lege ich den Pfad zum Dokumentenordner fest?

 A: Ersetzen Sie im bereitgestellten Quellcode`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu dem Ordner, der die PDF-Datei enthält, mit der Sie arbeiten möchten. Dadurch wird sichergestellt, dass der Code die Ziel-PDF-Datei finden kann.

#### F: Wie öffne ich ein PDF-Dokument, um seine Lesezeichen zu erweitern?

A: Um ein PDF-Dokument zum Erweitern von Lesezeichen zu öffnen, verwenden Sie den folgenden Code:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

 Ersetzen`"input.pdf"` mit dem tatsächlichen Dateinamen.

#### F: Wie stelle ich den Seitenanzeigemodus so ein, dass standardmäßig Lesezeichen angezeigt werden?

A: Um den Seitenanzeigemodus so einzustellen, dass standardmäßig Lesezeichen angezeigt werden, verwenden Sie die`PageMode` Eigentum der`doc` Objekt:

```csharp
doc.PageMode = PageMode.UseOutlines;
```

#### F: Wie erweitere ich alle Lesezeichen im PDF-Dokument?

 A: Um alle Lesezeichen zu erweitern, durchlaufen Sie jedes Lesezeichenelement in der Gliederungssammlung des Dokuments und legen Sie fest`Open` Eigentum zu`true`:

```csharp
foreach (OutlineItemCollection item in doc.Outlines)
{
    item.Open = true;
}
```

#### F: Was passiert, wenn ein Lesezeichen verschachtelte untergeordnete Lesezeichen hat?

A: Wenn ein Lesezeichen über verschachtelte untergeordnete Lesezeichen verfügt, werden beim Erweitern des übergeordneten Lesezeichens auch die untergeordneten Lesezeichen erweitert, sodass eine umfassende Ansicht der Struktur des Dokuments angezeigt wird.

#### F: Wie speichere ich die aktualisierte PDF-Datei, nachdem ich die Lesezeichen erweitert habe?

A: Um die aktualisierte PDF-Datei nach dem Erweitern der Lesezeichen zu speichern, verwenden Sie den folgenden Code:

```csharp
dataDir = dataDir + "ExpandBookmarks_out.pdf";
doc.Save(dataDir);
```

#### F: Kann ich das Erscheinungsbild erweiterter Lesezeichen anpassen?

A: Während sich dieses Tutorial auf das standardmäßige Erweitern von Lesezeichen konzentriert, können Sie das Erscheinungsbild von Lesezeichen mithilfe der anderen Funktionen und Eigenschaften von Aspose.PDF anpassen.