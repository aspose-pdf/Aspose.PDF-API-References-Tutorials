---
title: Textausrichtung für schwebende Boxinhalte in PDF-Datei
linktitle: Textausrichtung für schwebende Boxinhalte in PDF-Datei
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET schwebende Boxinhalte in PDF-Dateien ausrichten. Erstellen Sie beeindruckende Dokumente mit professionellen Layouts.
type: docs
weight: 520
url: /de/net/programming-with-text/text-alignment-for-floating-box-contents/
---
## Einführung

Das Erstellen optisch ansprechender PDFs ist eine entscheidende Fähigkeit in der heutigen digitalen Welt, in der jeder um Aufmerksamkeit buhlt. Aspose.PDF für .NET macht diese Aufgabe unglaublich unkompliziert und flexibel, insbesondere wenn es darum geht, das Layout Ihrer Dokumente anzupassen. In diesem Tutorial erfahren Sie, wie Sie den Inhalt schwebender Boxen in Ihren PDF-Dateien ausrichten. Dieser Ansatz verleiht Ihren Dokumenten einen eleganten und professionellen Touch, der sich von der Masse abhebt.

## Voraussetzungen

Bevor Sie mit dem Lernprogramm beginnen, benötigen Sie einige wichtige Dinge:

1. .NET Framework: Stellen Sie sicher, dass auf Ihrem Computer ein kompatibles .NET Framework installiert ist, da Sie Ihren Code hier ausführen werden.
2.  Aspose.PDF-Bibliothek: Sie benötigen die Aspose.PDF-Bibliothek. Wenn Sie sie noch nicht heruntergeladen haben, können Sie dies tun[Hier](https://releases.aspose.com/pdf/net/).
3. IDE: Eine integrierte Entwicklungsumgebung (IDE) wie Visual Studio ist beim Codieren und Debuggen hilfreich.
4. Grundkenntnisse in C#: Wenn Sie mit der C#-Programmierung vertraut sind, können Sie den Codeausschnitten leichter folgen und sie verstehen.

## Pakete importieren

Um zu beginnen, müssen Sie die erforderlichen Pakete in Ihr C#-Projekt importieren. So geht's:

1. Öffnen Sie Ihr Projekt: Starten Sie Ihre IDE und öffnen Sie das Projekt, in dem Sie die Floating-Box-Funktionalität implementieren möchten.
2. Installieren Sie Aspose.PDF für .NET: Verwenden Sie den NuGet Package Manager, um das Aspose.PDF-Paket zu installieren. Gehen Sie dazu wie folgt vor:
   - Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf Ihr Projekt und wählen Sie „NuGet-Pakete verwalten“.
   - Suchen Sie nach „Aspose.PDF“ und klicken Sie auf „Installieren“.
   
```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Nachdem Sie die Pakete eingerichtet haben, können Sie mit dem Erstellen und Ausrichten schwebender Boxen in Ihrer PDF-Datei beginnen.

Lassen Sie uns nun den Vorgang des Hinzufügens und Ausrichtens schwebender Boxen in einem PDF-Dokument genauer betrachten. Wir werden mehrere schwebende Boxen erstellen und deren Inhalt zur Veranschaulichung unterschiedlich ausrichten.

## Schritt 1: Einrichten des Dokuments

Der erste Schritt besteht darin, ein neues PDF-Dokument zu initialisieren und ihm eine Seite hinzuzufügen. Diese dient als Leinwand für unsere schwebenden Boxen.

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document doc = new Document();
doc.Pages.Add();
```

 Ersetzen Sie in diesem Codeausschnitt`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad, in dem Sie Ihre PDF-Datei speichern möchten.

## Schritt 2: Erstellen Sie die erste schwebende Box

Als nächstes erstellen wir unsere erste schwebende Box und legen ihre Ausrichtung fest. Hier wird der Inhalt unten rechts in der Box ausgerichtet.

```csharp
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox(100, 100);
floatBox.VerticalAlignment = VerticalAlignment.Bottom;
floatBox.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox.Paragraphs.Add(new TextFragment("FloatingBox_bottom"));
floatBox.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox);
```

- FloatingBox(100, 100): Dies initialisiert eine schwebende Box mit einer Breite und Höhe von jeweils 100 Einheiten.
- Vertikale und horizontale Ausrichtung: Wir geben an, dass der Text unten und rechts ausgerichtet werden soll.
- TextFragment: Dies stellt den Text dar, den Sie innerhalb des schwebenden Felds anzeigen möchten.
- BorderInfo: Dadurch wird ein Rahmen um die schwebende Box gelegt, der sie optisch hervorhebt.

## Schritt 3: Fügen Sie die zweite schwebende Box hinzu

Lassen Sie uns nun eine zweite schwebende Box erstellen, die ihren Inhalt zentriert.

```csharp
Aspose.Pdf.FloatingBox floatBox1 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox1.VerticalAlignment = VerticalAlignment.Center;
floatBox1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox1.Paragraphs.Add(new TextFragment("FloatingBox_center"));
floatBox1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox1);
```

Genau wie bei der ersten Box haben wir die vertikale Ausrichtung auf die Mitte und die horizontale Ausrichtung auf rechts eingestellt. Diese Methode ermöglicht dynamische Inhaltsanpassungen und eine bessere visuelle Attraktivität.

## Schritt 4: Erstellen Sie die dritte schwebende Box

Nun richten wir den Inhalt unserer dritten und letzten schwebenden Box oben rechts aus.

```csharp
Aspose.Pdf.FloatingBox floatBox2 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox2.VerticalAlignment = VerticalAlignment.Top;
floatBox2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox2.Paragraphs.Add(new TextFragment("FloatingBox_top"));
floatBox2.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox2);
```

Dieses Feld richtet den Inhalt oben rechts aus und zeigt die Flexibilität, die Sie mit der Aspose.PDF-Bibliothek haben. Jedes schwebende Feld kann einen bestimmten Zweck erfüllen, je nachdem, wie Sie Informationen visuell kommunizieren möchten.

## Schritt 5: Speichern Sie das Dokument

Zum Schluss ist es an der Zeit, Ihr Dokument zu speichern. Sie speichern es an dem zuvor angegebenen Speicherort.

```csharp
doc.Save(dataDir + "FloatingBox_alignment_review_out.pdf");
```

 Die Datei wird unter dem Namen gespeichert`FloatingBox_alignment_review_out.pdf` im angegebenen Verzeichnis. Überprüfen Sie unbedingt diesen Speicherort, um Ihr erstelltes PDF anzuzeigen.

## Abschluss

Mit Aspose.PDF für .NET können Sie PDF-Layouts bearbeiten und auf effiziente Weise professionelle und optisch ansprechende Dokumente erstellen. Wenn Sie wissen, wie Sie den Inhalt schwebender Boxen ausrichten, können Sie die Benutzerfreundlichkeit Ihrer PDF-Dateien deutlich verbessern. Wie wir gesehen haben, ist es einfach und dennoch leistungsstark genug, um Ihre PDFs hervorzuheben.

## Häufig gestellte Fragen

### Was ist eine schwebende Box in Aspose.PDF?  
Mithilfe einer schwebenden Box können Sie Inhalte flexibel innerhalb eines PDF-Layouts positionieren.

### Kann ich die Farbe des schwebenden Boxrahmens ändern?  
Ja, Sie können beim Erstellen einer schwebenden Box verschiedene Farben für den Rahmen angeben.

### Ist die Nutzung von Aspose.PDF für .NET kostenlos?  
Aspose.PDF bietet eine kostenlose Testversion, für die volle Funktionalität ist jedoch eine kostenpflichtige Lizenz erforderlich.

### Kann ich schwebenden Boxen Bilder hinzufügen?  
Auf jeden Fall! Sie können schwebenden Boxen verschiedene Arten von Inhalten hinzufügen, darunter auch Bilder.

### Wo finde ich weitere Informationen zu Aspose.PDF?  
 Detaillierte Dokumentation finden Sie[Hier](https://reference.aspose.com/pdf/net/).