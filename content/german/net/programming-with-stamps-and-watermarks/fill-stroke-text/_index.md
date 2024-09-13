---
title: Strichtext in PDF-Datei füllen
linktitle: Strichtext in PDF-Datei füllen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie in dieser Schritt-für-Schritt-Anleitung voller praktischer Beispiele, wie Sie mit Aspose.PDF für .NET mühelos Strichtext in PDF-Dateien füllen.
type: docs
weight: 90
url: /de/net/programming-with-stamps-and-watermarks/fill-stroke-text/
---
## Einführung

Wollten Sie schon einmal eine PDF-Datei ändern, um sie hervorzuheben? Vielleicht möchten Sie ein auffälliges Wasserzeichen oder einen auffälligen Stempel hinzufügen, der ein wichtiges Dokument unverkennbar von Ihnen abhebt. Mit Aspose.PDF für .NET können Sie Strichtext in einer PDF-Datei ganz einfach ausfüllen und so künstlerisches Flair hinzufügen, das ins Auge fällt. Im heutigen Tutorial führen wir Sie durch den Vorgang, genau das zu tun – das Ausfüllen von Strichtext in einer PDF-Datei mit C#. Am Ende haben Sie ein solides Verständnis dafür, wie Sie PDF-Dateien wie ein Profi bearbeiten.

## Voraussetzungen

Bevor wir uns in die Codierung stürzen, müssen Sie ein paar Dinge vorbereitet haben, damit dieses Tutorial ein Kinderspiel wird:

1. Visual Studio: Stellen Sie sicher, dass Visual Studio auf Ihrem Computer installiert ist, da wir C#-Code schreiben werden.
2.  Aspose.PDF-Bibliothek: Stellen Sie sicher, dass Sie die Aspose.PDF-Bibliothek für .NET heruntergeladen haben. Sie können sie herunterladen[Hier](https://releases.aspose.com/pdf/net/).
3. Grundkenntnisse in C#: Wenn Sie mit der C#-Programmierung vertraut sind, können Sie das Tutorial leichter verstehen.
4. Beispiel-PDF-Datei: Sie benötigen eine Beispiel-PDF-Datei (`input.pdf`zu Testzwecken. Sie können eine einfache erstellen oder eine vorhandene PDF-Datei verwenden.

Nachdem wir nun alles vorbereitet haben, können wir uns an die Details des Ausfüllens von Strichtext in Ihrer PDF-Datei machen.

## Pakete importieren

Zu Beginn müssen wir die erforderlichen Pakete importieren. Hier ist ein kurzer Überblick über die wesentlichen Importe für unser Projekt:

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Diese Pakete ermöglichen uns, die robusten Funktionen der Aspose.PDF-Bibliothek zu nutzen.

Lassen Sie uns die Hauptaufgabe in klare Schritte unterteilen. Wenn Sie diese Schritte befolgen, können Sie Strichtext ganz einfach in Ihre PDF-Dateien einfügen. 

## Schritt 1: Richten Sie Ihre Umgebung ein

Stellen Sie zunächst sicher, dass in Ihrem Visual Studio-Projekt alles richtig eingerichtet ist. Erstellen Sie ein neues Projekt oder wählen Sie ein vorhandenes aus. Wenn Sie Hilfe benötigen, gehen Sie wie folgt vor:

1. Öffnen Sie Visual Studio.
2. Erstellen Sie ein neues C#-Projekt (z. B. eine Konsolenanwendung).
3. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt und wählen Sie „NuGet-Pakete verwalten“ aus.
4.  Suchen nach`Aspose.PDF` und installieren Sie es.

## Schritt 2: Definieren Sie Ihr Dokumentverzeichnis

Jede Reise braucht einen Ausgangspunkt, und in unserem Fall ist das das Dokumentenverzeichnis, in dem die Eingabe- und Ausgabedateien gespeichert werden. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ersetzen`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad, in dem sich Ihre Eingabe-PDF-Datei befindet. 

## Schritt 3: Erstellen des TextState-Objekts

In diesem Schritt beginnen Sie, die Eigenschaften des Textes zu definieren, den Sie hinzufügen möchten. 

```csharp
TextState ts = new TextState();
```

 Der`TextState` Das Objekt enthält die Stiloptionen für Ihren Strichtext.

## Schritt 4: Farbe für Strich festlegen

Als Nächstes möchten Sie die Strichfarbe für Ihren Text definieren. 

```csharp
ts.StrokingColor = Color.Gray;
```

In diesem Code verwenden wir für den Strich eine graue Farbe. Sie können die Farbe gerne nach Bedarf ändern!

## Schritt 5: Rendering-Modus konfigurieren

Um sicherzustellen, dass Ihr Text wie gewünscht angezeigt wird, legen Sie den Rendering-Modus fest:

```csharp
ts.RenderingMode = TextRenderingMode.StrokeText;
```

Dies weist die Aspose-Bibliothek an, dass wir mit Strichtext arbeiten.

## Schritt 6: Laden Sie Ihr Eingabe-PDF-Dokument

Jetzt ist es an der Zeit, die PDF-Datei zu laden, die Sie ändern möchten. 

```csharp
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
```

Stellen Sie sicher, dass Ihr Eingabe-PDF (`input.pdf`befindet sich im Dokumentverzeichnis, das in früheren Schritten definiert wurde.

## Schritt 7: Erstellen Sie ein Stempelobjekt

Erstellen Sie als Nächstes einen Stempel, der Ihren Strichtext enthält. 

```csharp
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
```

Dieser Stempel wird verwendet, um Ihren Text auf das PDF zu legen.

## Schritt 8: Definieren Sie den zu stempelnden Text

Sie müssen angeben, welchen Text Sie der PDF-Datei hinzufügen möchten:

```csharp
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));
```

Hier fügen wir den Text „VOLLSTÄNDIG BEZAHLT“ zusammen mit seinen Stilattributen hinzu. Passen Sie ihn Ihren Anforderungen entsprechend an!

## Schritt 9: Den Textstatus binden

 Binden Sie nun die`TextState` den Sie zuvor für den Stempel definiert haben. 

```csharp
stamp.BindTextState(ts);
```

Dieser Schritt wendet alle Stile wie Farbe und Wiedergabemodus auf Ihren Text an.

## Schritt 10: Position des Stempels festlegen

Bestimmen Sie, wo Ihr Stempel in der PDF-Datei erscheinen soll:

```csharp
stamp.SetOrigin(100, 100);
```

 Die Argumente`(100, 100)` geben die X- und Y-Koordinaten (in Punkten) für den Ursprung des Textes an. Passen Sie diese Werte an, um Ihren Text perfekt zu positionieren!

## Schritt 11: Opazität und Rotation konfigurieren

Hier können Sie mit dem Erscheinungsbild Ihres Textes experimentieren:

```csharp
stamp.Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
```

In diesem Fall verleihen ein Deckkraftwert und ein Drehwinkel von 45 Grad Ihrem Text eine einzigartige Note. Sie können diese Einstellungen gerne ändern, um verschiedene Effekte zu erzielen.

## Schritt 12: Stempel zum PDF hinzufügen

Dies ist der entscheidende Schritt, bei dem wir abschließend unseren Stempel, der den Strichtext enthält, zum PDF hinzufügen:

```csharp
fileStamp.AddStamp(stamp);
```

Und schon ist Ihr Text bereit, eine Aussage zu machen!

## Schritt 13: Speichern und Schließen des Dokuments

Speichern Sie abschließend Ihre Änderungen und stellen Sie sicher, dass alles ordnungsgemäß bereinigt wurde. 

```csharp
fileStamp.Save(dataDir + "output_out.pdf");
fileStamp.Close();
```

 Ihre neu geänderte PDF-Datei mit dem Strichtext wird gespeichert als`output_out.pdf` in Ihrem Dokumentverzeichnis. 

## Abschluss

Und da haben Sie es! Indem Sie diese einfachen Schritte befolgen, können Sie mit Aspose.PDF für .NET ganz einfach Strichtext in eine PDF-Datei einfügen. Ob für Geschäftsdokumente oder persönliche Projekte, mit dieser Technik können Sie Ihren PDFs eine einzigartige Note verleihen, sodass sie in jedem Papierstapel hervorstechen.

## Häufig gestellte Fragen

### Was ist Aspose.PDF für .NET?
Aspose.PDF für .NET ist eine Bibliothek, mit der Entwickler PDF-Dateien programmgesteuert erstellen, bearbeiten und konvertieren können.

### Kann ich Aspose.PDF kostenlos nutzen?
Ja, Aspose bietet eine kostenlose Testversion an. Sie können es bekommen[Hier](https://releases.aspose.com/).

### Muss ich für eine Lizenz bezahlen?
 Während die Bibliothek eine kostenlose Testversion bietet, kann eine temporäre Lizenz auch erworben werden unter[dieser Link](https://purchase.aspose.com/temporary-license/).

### Wo finde ich die Dokumentation?
 Sie können auf die vollständige Dokumentation zugreifen[Hier](https://reference.aspose.com/pdf/net/).

### Gibt es Support, wenn ich auf Probleme stoße?
 Auf jeden Fall! Sie können Unterstützung im Aspose-Forum erhalten[Hier](https://forum.aspose.com/c/pdf/10).