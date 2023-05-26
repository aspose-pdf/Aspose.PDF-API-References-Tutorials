---
title: Freitextanmerkung aktualisieren
linktitle: Freitextanmerkung aktualisieren
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie die Freitextanmerkungsfunktion von Aspose.PDF für .NET mithilfe von C#-Quellcode aktualisieren.
type: docs
weight: 160
url: /de/net/annotations/updatefreetextannotation/
---
In diesem Artikel stellen wir eine Schritt-für-Schritt-Anleitung bereit, um den folgenden C#-Quellcode der Funktion „Freitextanmerkungen aktualisieren“ von Aspose.PDF für .NET zu erklären. Wir gehen jede Codezeile durch und erklären, was sie bewirkt, damit auch Anfänger sie verstehen können.

Lassen Sie uns nun jede Zeile des obigen Codes Schritt für Schritt erklären:

## Schritt 1: Dokumentverzeichnis festlegen

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

In dieser Zeile legen wir den Pfad zu dem Verzeichnis fest, das das PDF-Dokument enthält, das wir aktualisieren möchten.

## Schritt 2: Öffnen des PDF-Dokuments

```csharp
Document doc1 = new Document(dataDir + "input.pdf");
```

 Hier öffnen wir das PDF-Dokument mit Aspose.PDFs`Document` Klasse und Angabe des Pfads zur Eingabe-PDF-Datei.

## Schritt 3: Aktualisieren der Schriftgröße und -farbe der Freitextanmerkung

```csharp
(doc1.Pages[1].Annotations[0] as FreeTextAnnotation).TextStyle.FontSize = 18;
(doc1.Pages[1].Annotations[0] as FreeTextAnnotation).TextStyle.Color = System.Drawing.Color.Green;
```

 In diesem Schritt aktualisieren wir die Schriftgröße und Farbe der ersten Freitextanmerkung auf der zweiten Seite des PDF-Dokuments. Wir tun dies, indem wir auf die zugreifen`TextStyle` Eigentum der`FreeTextAnnotation` Objekt und dessen Einstellung`FontSize` Und`Color` Eigenschaften auf 18 bzw. Grün.

## Schritt 4: Ausnahmen behandeln

```csharp
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```

 Dies ist ein Standard`try-catch` Block, der alle Ausnahmen abfängt, die während der Ausführung des Codes auftreten können, und die Fehlermeldung an die Konsole ausgibt.

## Abschluss

In diesem Artikel haben wir eine Schritt-für-Schritt-Anleitung zur Erläuterung des C#-Quellcodes der Funktion „Freitextanmerkungen aktualisieren“ von Aspose.PDF für .NET bereitgestellt. Wenn Sie diese Schritte befolgen, können Sie mit Aspose.PDF für .NET ganz einfach die Schriftgröße und Farbe von Freitextanmerkungen in Ihren PDF-Dokumenten aktualisieren.

### Beispielquellcode für die Aktualisierung der Freitextanmerkung mit Aspose.PDF für .NET

Bevor wir uns mit der Erklärung des Codes befassen, werfen wir zunächst einen Blick auf den Code selbst. Dieses Codebeispiel zeigt, wie Sie die Eigenschaften einer Freitextanmerkung in einem PDF-Dokument mit Aspose.PDF für .NET aktualisieren.

```csharp
try
{
    // Der Pfad zum Dokumentenverzeichnis.
    string dataDir = "YOUR DOCUMENT DIRECTORY";

    // Dokument öffnen
    Document doc1 = new Document(dataDir + "input.pdf");

    // Schriftgröße und Farbe der Anmerkung festlegen:
    (doc1.Pages[1].Annotations[0] as FreeTextAnnotation).TextStyle.FontSize = 18;
    (doc1.Pages[1].Annotations[0] as FreeTextAnnotation).TextStyle.Color = System.Drawing.Color.Green;
                
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```