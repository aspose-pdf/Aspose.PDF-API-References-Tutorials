---
title: Bildinformationen in der PDF-Datei
linktitle: Bildinformationen in der PDF-Datei
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie mit unserer umfassenden Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.PDF für .NET Bildinformationen aus PDFs extrahieren.
type: docs
weight: 160
url: /de/net/programming-with-images/image-information/
---
## Einführung

PDF-Dateien sind heutzutage allgegenwärtig – praktisch jedes berufliche und private Dokument wird irgendwann in diesem Format verwendet. Ob es sich um einen Bericht, eine Broschüre oder ein E-Book handelt: Wenn Sie wissen, wie Sie programmgesteuert mit diesen Dateien interagieren können, eröffnen sich unzählige Möglichkeiten. Eine häufige Anforderung besteht darin, Bildinformationen aus PDF-Dateien zu extrahieren. In diesem Handbuch erfahren Sie, wie Sie mit der Aspose.PDF-Bibliothek für .NET wichtige Details zu Bildern extrahieren, die in ein PDF-Dokument eingebettet sind.

## Voraussetzungen

Bevor wir uns in die Einzelheiten der Codierung stürzen, müssen einige Voraussetzungen erfüllt sein:

1. Entwicklungsumgebung: Sie müssen eine .NET-Entwicklungsumgebung einrichten. Dies kann Visual Studio oder eine andere .NET-kompatible IDE sein.
2.  Aspose.PDF-Bibliothek: Stellen Sie sicher, dass Sie Zugriff auf die Aspose.PDF-Bibliothek haben. Sie können sie von der[Aspose-Website](https://releases.aspose.com/pdf/net/). 
3. Grundlegende C#-Kenntnisse: Wenn Sie mit C# und den Konzepten der objektorientierten Programmierung vertraut sind, können Sie dem Lernprogramm mühelos folgen.
4. PDF-Dokument: Halten Sie ein Beispiel-PDF-Dokument mit Bildern bereit, um Ihren Code zu testen. 

## Pakete importieren

Um mit der Verwendung der Aspose.PDF-Bibliothek zu beginnen, müssen Sie die erforderlichen Namespaces in Ihre C#-Datei importieren. Hier ist ein kurzer Überblick:

```csharp
using System.IO;
using Aspose.Pdf;
using System;
```

Diese Namespaces bieten Ihnen Zugriff auf die erforderlichen Klassen und Methoden zum Bearbeiten von PDF-Dateien und Extrahieren von Bilddaten.

Nachdem Sie nun alles eingerichtet haben, ist es an der Zeit, dies in überschaubare Schritte aufzuteilen. Wir werden ein C#-Programm schreiben, das ein PDF-Dokument lädt, jede Seite durchgeht und die Abmessungen und Auflösung jedes Bilds im Dokument extrahiert.

## Schritt 1: Initialisieren Sie das Dokument

 In diesem Schritt initialisieren wir das PDF-Dokument mit dem Pfad zu Ihrer PDF-Datei. Sie sollten ersetzen`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad, in dem sich Ihre PDF-Datei befindet.

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Laden Sie die PDF-Quelldatei
Document doc = new Document(dataDir + "ImageInformation.pdf");
```
 Wir schaffen eine`Document` Objekt, das die PDF-Datei aus dem angegebenen Verzeichnis lädt. Dadurch können wir mit dem Inhalt der Datei arbeiten.

## Schritt 2: Standardauflösung festlegen und Datenstrukturen initialisieren

Als nächstes legen wir eine Standardauflösung für die Bilder fest, die für Berechnungen nützlich ist. Wir bereiten auch ein Array zur Aufnahme der Bildnamen und einen Stapel zur Verwaltung grafischer Zustände vor.

```csharp
// Definieren Sie die Standardauflösung für Bilder
int defaultResolution = 72;
System.Collections.Stack graphicsState = new System.Collections.Stack();
// Definieren Sie ein Array-Listenobjekt, das Bildnamen enthalten wird
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
```
 Der`defaultResolution` Variable hilft uns, die Auflösung von Bildern richtig zu berechnen. Die`graphicsState`Der Stapel dient zum Speichern des aktuellen grafischen Status des Dokuments, wenn wir auf Transformationsoperatoren stoßen.

## Schritt 3: Verarbeiten Sie jeden Operator auf der Seite

Wir durchlaufen nun alle Operatoren auf der ersten Seite des Dokuments. Hier geschieht die Schwerstarbeit. 

```csharp
foreach (Operator op in doc.Pages[1].Contents)
{
    // Prozessoperatoren...
}
```
Jeder Operator in einer PDF-Datei ist ein Befehl, der dem Renderer mitteilt, wie grafische Elemente, einschließlich Bilder, zu verwalten sind.

## Schritt 4: GSave/GRestore-Operatoren handhaben

Innerhalb der Schleife verarbeiten wir Befehle zum Speichern und Wiederherstellen von Grafiken, um die am Grafikstatus vorgenommenen Änderungen zu verfolgen.

```csharp
if (opSaveState != null) 
{
    // Vorherigen Zustand speichern
    graphicsState.Push(((Matrix)graphicsState.Peek()).Clone());
} 
else if (opRestoreState != null) 
{
    // Vorherigen Zustand wiederherstellen
    graphicsState.Pop();
}
```
`GSave` speichert den aktuellen Grafikzustand, während`GRestore` stellt den zuletzt gespeicherten Zustand wieder her und ermöglicht es uns, alle Transformationen bei der Bildverarbeitung rückgängig zu machen.

## Schritt 5: Transformationsmatrizen verwalten

Als nächstes behandeln wir die Verkettung von Transformationsmatrizen beim Anwenden von Transformationen auf Bilder.

```csharp
else if (opCtm != null) 
{
    Matrix cm = new Matrix(
        (float)opCtm.Matrix.A,
        (float)opCtm.Matrix.B,
        (float)opCtm.Matrix.C,
        (float)opCtm.Matrix.D,
        (float)opCtm.Matrix.E,
        (float)opCtm.Matrix.F);
    
    ((Matrix)graphicsState.Peek()).Multiply(cm);
    continue;
}
```
Wenn eine Transformationsmatrix angewendet wird, multiplizieren wir sie mit der aktuellen Matrix, die im Grafikstatus gespeichert ist, sodass wir jede auf das Bild angewendete Skalierung oder Übersetzung verfolgen können.

## Schritt 6: Bildinformationen extrahieren

Abschließend verarbeiten wir den Zeichenoperator für Bilder und extrahieren die notwendigen Informationen wie Abmessungen und Auflösungen.

```csharp
else if (opDo != null) 
{
    // Handle Do-Operator, der Objekte zeichnet
    if (imageNames.Contains(opDo.Name)) 
    {
        Matrix lastCTM = (Matrix)graphicsState.Peek();
        XImage image = doc.Pages[1].Resources.Images[opDo.Name];
        double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
        double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
        double originalWidth = image.Width;
        double originalHeight = image.Height;
        
        double resHorizontal = originalWidth * defaultResolution / scaledWidth;
        double resVertical = originalHeight * defaultResolution / scaledHeight;
        
        // Informationen ausgeben
        Console.Out.WriteLine(string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
                         opDo.Name, scaledWidth, scaledHeight, resHorizontal, resVertical));
    }
}
```
Hier prüfen wir, ob der Operator für das Zeichnen eines Bildes zuständig ist. Wenn ja, holen wir uns das entsprechende XImage-Objekt, berechnen seine skalierten Abmessungen und Auflösung und drucken die erforderlichen Informationen.

## Abschluss

Herzlichen Glückwunsch! Sie haben gerade ein funktionierendes Beispiel für die Extraktion von Bildinformationen aus einer PDF-Datei mit Aspose.PDF für .NET erstellt. Diese Funktion kann für Entwickler, die PDF-Dokumente für verschiedene Anwendungen analysieren oder bearbeiten müssen, z. B. für Berichte, Datenextraktion oder sogar benutzerdefinierte PDF-Viewer, unglaublich nützlich sein. 


## Häufig gestellte Fragen

### Was ist die Aspose.PDF-Bibliothek?
Die Aspose.PDF-Bibliothek ist ein leistungsstarkes Tool zum Erstellen, Bearbeiten und Konvertieren von PDF-Dateien in .NET-Anwendungen.

### Kann ich die Bibliothek kostenlos nutzen?
 Ja, Aspose bietet eine kostenlose Testversion an. Sie können sie herunterladen[Hier](https://releases.aspose.com/).

### Welche Arten von Bildformaten können extrahiert werden?
Die Bibliothek unterstützt verschiedene Bildformate, darunter JPEG, PNG und TIFF, solange sie in das PDF eingebettet sind.

### Wird Aspose für kommerzielle Zwecke genutzt?
 Ja, Sie können Aspose-Produkte kommerziell nutzen. Informationen zur Lizenzierung finden Sie unter[Kaufseite](https://purchase.aspose.com/buy).

### Wie bekomme ich Support für Aspose?
 Sie können auf das Support-Forum zugreifen[Hier](https://forum.aspose.com/c/pdf/10).