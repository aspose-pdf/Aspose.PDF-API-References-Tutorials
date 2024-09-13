---
title: Ausrichtung ändern
linktitle: Ausrichtung ändern
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Ändern der Seitenausrichtung einer PDF-Datei mit Aspose.PDF für .NET. Einfach zu befolgen und in Ihren Projekten zu implementieren.
type: docs
weight: 10
url: /de/net/programming-with-pdf-pages/change-orientation/
---
## Einführung

Haben Sie schon einmal mit einer PDF-Datei gekämpft, bei der die Seitenausrichtung einfach... falsch ist? Vielleicht haben Sie es mit einem Dokument zu tun, das falsch gescannt oder erstellt wurde, und die Seiten müssen gedreht werden, damit sie Sinn ergeben. Zum Glück bietet Aspose.PDF für .NET eine einfache und leistungsstarke Möglichkeit, PDF-Dateien auf nahezu jede erdenkliche Weise zu bearbeiten – einschließlich der Änderung der Seitenausrichtung. Egal, ob Sie von Hochformat auf Querformat oder umgekehrt wechseln möchten, diese Anleitung führt Sie Schritt für Schritt durch den Vorgang.

Wenn Sie also bereit sind, loszulegen und diese PDF-Seiten mühelos zu drehen, dann legen wir los!

## Voraussetzungen

Bevor wir uns mit den Details der Änderung der Seitenausrichtung in Ihrem PDF befassen, wollen wir kurz besprechen, was Sie dafür benötigen:

-  Aspose.PDF für .NET: Stellen Sie sicher, dass Sie die Aspose.PDF-Bibliothek für .NET installiert haben. Wenn nicht, können Sie[Laden Sie es hier herunter](https://releases.aspose.com/pdf/net/).
- Eine .NET-Entwicklungsumgebung: Sie können Visual Studio, JetBrains Rider oder eine beliebige bevorzugte IDE für die Arbeit mit .NET verwenden.
- Grundkenntnisse in C#: Diese Anleitung ist zwar unkompliziert, aber mit ein paar Grundkenntnissen in C# ist sie noch einfacher zu befolgen.
- Eine PDF-Datei: Das folgende Beispiel geht davon aus, dass Sie eine PDF-Datei mit mehreren Seiten haben. Wenn Sie keine zur Hand haben, erstellen oder laden Sie eine Beispiel-PDF herunter, mit der Sie arbeiten können.

 Wenn Sie gerade erst anfangen, können Sie Aspose.PDF auch mit einem[kostenlose temporäre Lizenz](https://purchase.aspose.com/temporary-license/) bevor Sie sich entscheiden,[Vollversion kaufen](https://purchase.aspose.com/buy).

## Namespaces importieren

Bevor Sie die Seitenausrichtung in Ihrer PDF-Datei ändern können, müssen Sie die erforderlichen Namespaces in Ihr C#-Projekt importieren. Stellen Sie sicher, dass Sie über Folgendes verfügen:

```csharp
using System.IO;
using Aspose.Pdf;
```

Nachdem wir dies importiert haben, springen wir zum Hauptteil des Tutorials.

## Schritt 1: Laden Sie das PDF-Dokument

 Als erstes müssen wir die PDF-Datei laden, die Sie ändern möchten. Sie können den`Document` Klasse aus dem Aspose.PDF-Namespace, um Ihr PDF zu öffnen.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
```

 Diese Zeile lädt das PDF aus dem angegebenen Verzeichnis. Achten Sie darauf, zu ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu Ihrer Datei. Die`"input.pdf"` ist die PDF-Datei, deren Ausrichtung Sie ändern möchten.

## Schritt 2: Jede Seite durchlaufen

 Nachdem wir das Dokument geladen haben, können wir nun jede Seite im PDF durchgehen. Wir verwenden eine`foreach` Schleife, um alle Seiten zu durchlaufen, sodass wir die Ausrichtungsänderung auf alle anwenden können.

```csharp
foreach (Page page in doc.Pages)
{
    // Bearbeiten Sie jede Seite
}
```

Diese Schleife durchläuft alle Seiten im Dokument.

## Schritt 3: Holen Sie sich die MediaBox der Seite

 Jede Seite in einer PDF hat eine`MediaBox` das die Grenzen der Seite definiert. Wir müssen darauf zugreifen, um die aktuelle Ausrichtung zu bestimmen und sie zu ändern.

```csharp
Aspose.Pdf.Rectangle r = page.MediaBox;
```

 Der`MediaBox` gibt uns die Abmessungen der Seite, wie etwa Breite, Höhe und Positionierung.

## Schritt 4: Breite und Höhe vertauschen

Um die Seitenausrichtung von Hochformat auf Querformat oder von Querformat auf Hochformat zu ändern, vertauschen wir einfach die Werte für Breite und Höhe. Mit diesem Schritt werden die Abmessungen der Seite angepasst.

```csharp
double newHeight = r.Width;
double newWidth = r.Height;
double newLLX = r.LLX;
double newLLY = r.LLY + (r.Height - newHeight);
```

Dieser Code vertauscht Höhe und Breite und positioniert die untere linke Ecke neu (`LLY`), damit der Inhalt nach der Drehung gut passt.

## Schritt 5: Aktualisieren Sie die MediaBox und CropBox

Nachdem wir nun die neue Höhe und Breite haben, wenden wir die Änderungen auf die Seite an.`MediaBox` Und`CropBox` . Der`CropBox` ist wichtig, wenn das Originaldokument einen Satz hatte, um sicherzustellen, dass die gesamte Seite korrekt angezeigt wird.

```csharp
page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
```

Dieser Schritt ändert die Größe der Seite basierend auf den neuen Abmessungen, die wir gerade berechnet haben.

## Schritt 6: Seite drehen

Zum Schluss legen wir den Drehwinkel der Seite fest. Aspose.PDF macht das super einfach. Wir können die Seite um 90 Grad drehen, um vom Hoch- ins Querformat oder umgekehrt zu wechseln.

```csharp
page.Rotate = Rotation.on90;
```

Dieser Code dreht die Seite um 90 Grad und bringt sie in die gewünschte Ausrichtung.

## Schritt 7: Speichern Sie das Ausgabe-PDF

Nachdem wir die Ausrichtungsänderungen auf alle Seiten angewendet haben, speichern wir das geänderte Dokument in einer neuen Datei. 

```csharp
dataDir = dataDir + "ChangeOrientation_out.pdf";
doc.Save(dataDir);
System.Console.WriteLine("\nPage orientation changed successfully.\nFile saved at " + dataDir);
```

 Stellen Sie sicher, dass Sie einen neuen Dateinamen angeben (in diesem Fall`ChangeOrientation_out.pdf`), um die Ausgabe zu speichern. Auf diese Weise überschreiben Sie Ihre Originaldatei nicht.

### Abschluss

Und da haben Sie es! Das Ändern der Seitenausrichtung einer PDF-Datei mit Aspose.PDF für .NET ist so einfach wie das Laden des Dokuments, das Durchlaufen der Seiten, das Anpassen der MediaBox und das Speichern der aktualisierten Datei. Egal, ob Sie es mit einem schlecht gescannten Dokument zu tun haben oder Seiten drehen müssen, um Ihren Formatierungsanforderungen zu entsprechen, diese Schritt-für-Schritt-Anleitung sollte Ihnen dabei helfen.

## Häufig gestellte Fragen

### Kann ich im PDF statt aller Seiten nur bestimmte Seiten drehen?  
Ja, Sie können die Schleife so ändern, dass sie bestimmte Seiten anhand ihres Indexes anspricht, anstatt alle Seiten zu durchlaufen.

###  Was ist der`MediaBox`?  
 Der`MediaBox` definiert die Größe und Form der Seite in einer PDF-Datei. Hier wird der Inhalt der Seite platziert.

### Funktioniert Aspose.PDF für .NET mit anderen Dateiformaten?  
Ja, Aspose.PDF kann eine Vielzahl von Dateiformaten wie HTML, XML, XPS und mehr verarbeiten.

### Gibt es eine kostenlose Version von Aspose.PDF für .NET?  
 Ja, Sie können beginnen mit einem[Kostenlose Testversion](https://releases.aspose.com/) oder fordern Sie ein[vorläufige Lizenz](https://purchase.aspose.com/temporary-license/).

### Kann ich die Änderungen nach dem Speichern rückgängig machen?  
Sobald Sie das Dokument speichern, sind die Änderungen dauerhaft. Arbeiten Sie unbedingt an einer Kopie oder bewahren Sie eine Sicherungskopie der Originaldatei auf.