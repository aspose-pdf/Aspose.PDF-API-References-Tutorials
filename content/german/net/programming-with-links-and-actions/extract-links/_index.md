---
title: Links in PDF-Datei extrahieren
linktitle: Links in PDF-Datei extrahieren
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie in diesem Schritt-für-Schritt-Tutorial, wie Sie mit Aspose.PDF für .NET ganz einfach Links aus PDF-Dateien extrahieren.
type: docs
weight: 50
url: /de/net/programming-with-links-and-actions/extract-links/
---
## Einführung

In unserer schnelllebigen digitalen Welt ist die effektive Verwaltung von Dokumenten von entscheidender Bedeutung. Wenn es um PDFs geht, besteht eine häufige Aufgabe darin, Links aus diesen Dateien zu extrahieren. Egal, ob Sie ein Entwickler sind, der PDF-Funktionen in seine Anwendung integriert, oder einfach jemand, der seine digitalen Dokumente besser verwalten möchte, die Verwendung einer robusten Bibliothek wie Aspose.PDF für .NET kann diese Aufgabe erheblich erleichtern. In diesem Tutorial werden wir uns eingehend damit befassen, wie man mit Aspose.PDF für .NET Links aus einem PDF-Dokument extrahiert, und dies in überschaubare Schritte unterteilen. Bereit, loszulegen? Los geht‘s!

## Voraussetzungen

Bevor wir uns in den Code vertiefen, müssen Sie sicherstellen, dass Sie einige Dinge eingerichtet haben:

1. .NET-Umgebung: Stellen Sie sicher, dass auf Ihrem Computer eine .NET-Entwicklungsumgebung bereitsteht. Dies kann Visual Studio oder eine andere IDE sein, die .NET unterstützt.
2. Aspose.PDF-Bibliothek: Sie müssen die Aspose.PDF-Bibliothek installiert haben. Sie können sie ganz einfach über den NuGet-Paketmanager in Visual Studio herunterladen. Führen Sie zur Installation einfach Folgendes aus:
```
Install-Package Aspose.PDF
```
    Oder Sie holen sich die neueste Version direkt von der[Downloadlink](https://releases.aspose.com/pdf/net/).
3. Grundkenntnisse in C#: Grundlegende Kenntnisse in C# helfen Ihnen, den Anweisungen zu folgen. Keine Sorge, wenn Sie kein Profi sind. Wir halten die Erklärungen klar und unkompliziert!
4. Beispiel-PDF-Dokument: Sie benötigen ein PDF-Dokument mit Links. Sie können eines zum Testen erstellen oder Beispiele online herunterladen.

Nachdem wir nun alles eingerichtet haben, können wir direkt loslegen!

## Pakete importieren

Nachdem Sie Ihre Umgebung eingerichtet haben, müssen Sie die erforderlichen Namespaces in Ihr Projekt importieren. So geht's:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using System.Collections;
using System;
using System.Collections.Generic;
```

Lassen Sie uns dies weiter in umsetzbare Schritte zum Extrahieren von Links aus einer PDF-Datei aufschlüsseln.

## Schritt 1: Datenverzeichnis festlegen

Als Erstes müssen Sie den Pfad zu Ihren Dokumenten angeben. Hier verweisen Sie auf die PDF-Datei, aus der Sie Links extrahieren möchten. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ersetzen Sie unbedingt`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Ordnerpfad, in dem sich Ihre PDF-Datei befindet. So weiß Ihre Anwendung, wo sie nach Ihren Dokumenten suchen muss.

## Schritt 2: Öffnen Sie das PDF-Dokument

Jetzt ist es an der Zeit, das PDF-Dokument tatsächlich mit Aspose.PDF zu öffnen. Hier ist die magische Codezeile:

```csharp
Document document = new Document(dataDir + "ExtractLinks.pdf");
```

 Ersetzen`"ExtractLinks.pdf"` mit dem Namen Ihrer PDF-Datei. Diese Zeile initialisiert ein Objekt Ihres PDF-Dokuments, das Sie bearbeiten können.

## Schritt 3: Zielseite auswählen

PDFs können mehrere Seiten haben, daher müssen Sie angeben, welche Seite Sie interessiert. Nehmen wir für dieses Beispiel an, dass wir Links von der ersten Seite extrahieren möchten:

```csharp
Page page = document.Pages[1];
```

 Denken Sie daran, dass Seiten in Aspose.PDF ab 1 indiziert werden. Wenn Sie also die erste Seite möchten, verwenden Sie`1` wie hier gezeigt.

## Schritt 4: Link-Annotation-Selektor einrichten

Jetzt wird es interessant! Sie müssen einen Selektor erstellen, der Ihnen hilft, alle Linkanmerkungen auf der Seite zu erfassen.

```csharp
AnnotationSelector selector = new AnnotationSelector(new LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
```

Diese Zeile teilt Aspose.PDF mit, dass Sie sich auf Linkanmerkungen innerhalb der angegebenen Seite konzentrieren möchten.

## Schritt 5: Akzeptieren Sie den Selektor

Nachdem Ihr Selektor nun eingerichtet ist, ist es an der Zeit, der Seite mitzuteilen, dass sie den Selektor akzeptieren und die relevanten Anmerkungen suchen soll:

```csharp
page.Accept(selector);
```

Dieser Befehl durchsucht die ausgewählte Seite und wendet den Selektor an, um alle Linkanmerkungen zu identifizieren und auszuwählen.

## Schritt 6: Abrufen der Liste der Anmerkungen

Hier können Sie alle extrahierten Links sammeln:

```csharp
IList<Annotation> list = selector.Selected;
```

Diese Zeile stellt eine Liste aller Linkanmerkungen zusammen, die auf Ihrer Zielseite gefunden wurden. Einfach, oder?

## Schritt 7: Extrahieren und Speichern der Links

Abschließend können Sie nun die Links extrahieren und das aktualisierte Dokument speichern. So geht's:

```csharp
if (list.Count > 0) // Stellen Sie sicher, dass Links vorhanden sind, bevor Sie versuchen, darauf zuzugreifen
{
    foreach (Annotation annotation in list)
    {
        // Führen Sie bei Bedarf Operationen an jeder Anmerkung durch
        Console.WriteLine("Extracted Link: " + annotation.Title);
    }
}

// Aktualisiertes Dokument speichern
dataDir = dataDir + "ExtractLinks_out.pdf";
document.Save(dataDir);
Console.WriteLine("\nLinks extracted successfully.\nFile saved at " + dataDir);
```

In diesem Snippet prüfen wir, ob Anmerkungen gefunden wurden. Wenn ja, durchlaufen wir die Liste und drucken ihre Titel aus. Schließlich speichern wir das Dokument und erstellen eine neue Datei, die Ihre extrahierten Daten enthält!

## Abschluss

 Und da haben Sie es! In nur wenigen einfachen Schritten können Sie jetzt mit Aspose.PDF für .NET Links aus jeder PDF-Datei extrahieren. Diese leistungsstarke Bibliothek eröffnet eine Welt voller Möglichkeiten für die Arbeit mit PDFs, von der einfachen Linkextraktion bis hin zu komplexen Dokumentmanipulationen. Wenn Sie sich mit Aspose vertraut machen möchten, sollten Sie sich deren[Dokumentation](https://reference.aspose.com/pdf/net/) oder erkunden Sie weitere Funktionen, die sie anbieten.

## Häufig gestellte Fragen

### Was ist Aspose.PDF für .NET?
Aspose.PDF für .NET ist eine leistungsstarke Bibliothek zum Erstellen, Bearbeiten und Konvertieren von PDF-Dokumenten in .NET-Anwendungen.

### Kann ich Links aus mehreren Seiten extrahieren?
Ja! Sie können mit einer einfachen For-Schleife alle Seiten Ihres Dokuments durchlaufen und denselben Link-Extraktionsprozess anwenden.

### Ist die Nutzung von Aspose.PDF kostenlos?
Aspose.PDF ist ein kommerzielles Produkt, aber Sie können eine kostenlose Testversion herunterladen[Hier](https://releases.aspose.com/).

### Wo erhalte ich Support für Aspose.PDF?
 Sie können Community-Unterstützung erhalten durch ihre[Support-Forum](https://forum.aspose.com/c/pdf/10).

### Wie kann ich eine temporäre Lizenz für Aspose.PDF erhalten?
 Wenn Sie eine temporäre Lizenz benötigen, können Sie diese hier anfordern.[Link](https://purchase.aspose.com/temporary-license/).