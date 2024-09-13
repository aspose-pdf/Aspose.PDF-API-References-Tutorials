---
title: Gruppierte Kontrollkästchen im PDF-Dokument
linktitle: Gruppierte Kontrollkästchen im PDF-Dokument
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie in diesem Schritt-für-Schritt-Tutorial, wie Sie mit Aspose.PDF für .NET gruppierte Kontrollkästchen (Optionsfelder) in einem PDF-Dokument erstellen.
type: docs
weight: 170
url: /de/net/programming-with-forms/grouped-check-boxes/
---
## Einführung

Das Erstellen interaktiver PDFs ist nicht so schwierig, wie es sich anhört, insbesondere wenn Ihnen leistungsstarke Tools wie Aspose.PDF für .NET zur Verfügung stehen. Eines der interaktiven Elemente, die Sie möglicherweise zu Ihren PDF-Dokumenten hinzufügen müssen, sind gruppierte Kontrollkästchen oder genauer gesagt Optionsfelder, mit denen Benutzer eine Option aus einer Gruppe auswählen können. Dieses Tutorial führt Sie durch den Vorgang des Hinzufügens gruppierter Kontrollkästchen (Optionsfelder) zu einem PDF-Dokument mit Aspose.PDF für .NET. Egal, ob Sie Anfänger oder erfahrener Entwickler sind, Sie werden diese Anleitung interessant, detailliert und leicht verständlich finden.

## Voraussetzungen

Bevor wir uns in die Schritt-für-Schritt-Anleitung vertiefen, wollen wir einige wesentliche Voraussetzungen klären:

1.  Aspose.PDF für .NET: Stellen Sie sicher, dass Sie die Aspose.PDF-Bibliothek installiert haben. Wenn nicht, können Sie[Laden Sie es hier herunter](https://releases.aspose.com/pdf/net/).
2. IDE: Sie sollten eine Entwicklungsumgebung wie Visual Studio eingerichtet haben.
3. .NET Framework: Das Projekt sollte auf eine Version des .NET Frameworks abzielen, die mit Aspose.PDF kompatibel ist.
4. Grundlegende C#-Kenntnisse: Um problemlos mitarbeiten zu können, sind Kenntnisse in C# und der PDF-Bearbeitung erforderlich.
5.  Lizenz: Für die volle Funktionalität von Aspose.PDF ist eine Lizenz erforderlich. Sie können[eine vorübergehende Lizenz erhalten](https://purchase.aspose.com/temporary-license/) falls erforderlich.

## Pakete importieren

Stellen Sie vor dem Start sicher, dass Sie die erforderlichen Namespaces in Ihr Projekt importiert haben:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Forms;
```

Diese Pakete geben Ihnen Zugriff auf alle Klassen und Methoden, die zum Bearbeiten von PDF-Dokumenten erforderlich sind, einschließlich der Erstellung von Optionsfeldern und der Definition ihrer Eigenschaften.

In diesem Abschnitt unterteilen wir den Vorgang zum Erstellen gruppierter Kontrollkästchen (Optionsfelder) in klare, leicht verständliche Schritte.

## Schritt 1: Ein neues PDF-Dokument erstellen

 Der erste Schritt besteht in der Erstellung einer Instanz des`Document` Objekt, das Ihre PDF-Datei darstellt. Fügen Sie dann Ihrem Dokument eine leere Seite hinzu, auf der Sie Ihre gruppierten Kontrollkästchen platzieren.

```csharp
// Document-Objekt instanziieren
Document pdfDocument = new Document();

// Fügen Sie der PDF-Datei eine Seite hinzu
Page page = pdfDocument.Pages.Add();
```

Dadurch wird die Grundlage für das Hinzufügen beliebiger Elemente, beispielsweise Optionsfelder, zur PDF-Datei geschaffen.

## Schritt 2: Radiobutton-Feld initialisieren

Als nächstes müssen wir ein`RadioButtonField` Objekt, das die gruppierten Kontrollkästchen (Optionsfelder) enthält. Dieses Feld wird der jeweiligen Seite hinzugefügt, auf der die Kontrollkästchen angezeigt werden.

```csharp
// RadioButtonField-Objekt instantiieren und der ersten Seite zuweisen
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

Stellen Sie sich dies als einen Container vor, der die einzelnen Optionsfeldoptionen zusammenfasst.

## Schritt 3: Optionsfeldoptionen hinzufügen

 Fügen wir nun die einzelnen Optionsfelder zum Feld hinzu. In diesem Beispiel fügen wir zwei Optionsfelder hinzu und geben ihre Positionen mit dem`Rectangle` Objekt.

```csharp
// Fügen Sie die erste Optionsfeldoption hinzu und geben Sie ihre Position mit Rechteck an
RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));

// Festlegen von Optionsnamen zur Identifizierung
opt1.OptionName = "Option1";
opt2.OptionName = "Option2";
```

 Hier die`Rectangle` Das Objekt definiert die Koordinaten und die Größe jedes Optionsfelds auf der Seite.

## Schritt 4: Passen Sie den Stil der Optionsfelder an

 Sie können das Erscheinungsbild der Optionsfelder anpassen, indem Sie deren`Style` Eigenschaft. Sie möchten vielleicht quadratische oder kreuzförmige Kontrollkästchen.

```csharp
// Legen Sie den Stil der Optionsfelder fest
opt1.Style = BoxStyle.Square;
opt2.Style = BoxStyle.Cross;
```

Dadurch können Sie das Erscheinungsbild der Kontrollkästchen steuern und sie benutzerfreundlicher und optisch ansprechender gestalten.

## Schritt 5: Rahmeneigenschaften konfigurieren

Rahmen spielen eine wichtige Rolle, um die Kontrollkästchen leicht erkennbar zu machen. Hier fügen wir um jede Optionsfeldoption durchgehende Rahmen hinzu und definieren deren Breite und Farbe.

```csharp
// Konfigurieren Sie den Rahmen des ersten Optionsfelds
opt1.Border = new Border(opt1);
opt1.Border.Style = BorderStyle.Solid;
opt1.Border.Width = 1;
opt1.Characteristics.Border = Color.Black;

// Konfigurieren Sie den Rahmen des zweiten Optionsfelds
opt2.Border = new Border(opt2);
opt2.Border.Style = BorderStyle.Solid;
opt2.Border.Width = 1;
opt2.Characteristics.Border = Color.Black;
```

Dieser Schritt stellt sicher, dass jedes Optionsfeld einen klar definierten Rahmen hat, was die Lesbarkeit des Dokuments verbessert.

## Schritt 6: Optionsfeldoptionen zum Formular hinzufügen

Jetzt fügen wir die Optionsfelder zum Formular des Dokuments hinzu. Dies ist der letzte Schritt beim Gruppieren der Kontrollkästchen in einem einzigen Feld.

```csharp
// Radiobutton-Feld zum Formularobjekt des Dokuments hinzufügen
pdfDocument.Form.Add(radio);
```

Das Formularobjekt fungiert als Container für alle interaktiven Elemente, einschließlich unserer gruppierten Kontrollkästchen.

## Schritt 7: Speichern Sie das PDF-Dokument

Wenn alles eingerichtet ist, können Sie das PDF-Dokument am gewünschten Speicherort speichern.

```csharp
// Definieren Sie den Ausgabedateipfad
string dataDir = "YOUR DOCUMENT DIRECTORY" + "GroupedCheckBoxes_out.pdf";

// Speichern des PDF-Dokuments
pdfDocument.Save(dataDir);

// Erfolgreiche Erstellung bestätigen
Console.WriteLine("Grouped checkboxes added successfully. File saved at " + dataDir);
```

Und das war’s! Sie haben erfolgreich ein PDF mit gruppierten Kontrollkästchen mit Aspose.PDF für .NET erstellt.

## Abschluss

Das Hinzufügen interaktiver Elemente wie gruppierter Kontrollkästchen zu PDF-Dokumenten kann zunächst schwierig erscheinen, aber mit Aspose.PDF für .NET wird es zum Kinderspiel. In dieser Schritt-für-Schritt-Anleitung haben Sie gelernt, wie Sie ein einfaches PDF-Dokument einrichten, gruppierte Optionsfelder hinzufügen, deren Erscheinungsbild anpassen und das Endergebnis speichern. Egal, ob Sie Formulare, Umfragen oder andere Arten interaktiver PDFs erstellen, diese Anleitung bietet Ihnen eine solide Grundlage für den Anfang.

## Häufig gestellte Fragen

### Kann ich einer Gruppe mehr als zwei Optionsfelder hinzufügen?
 Absolut! Instanziieren Sie einfach weitere`RadioButtonOptionField` Objekte und fügen Sie sie dem`RadioButtonField` wie im Tutorial gezeigt.

### Wie gehe ich mit mehreren Gruppen von Kontrollkästchen in einem Dokument um?
Um mehrere Gruppen zu erstellen, instanziieren Sie separate`RadioButtonField` Objekte für jede Gruppe.

### Gibt es eine Begrenzung für die Anzahl der Kontrollkästchen, die ich hinzufügen kann?
Nein, Aspose.PDF für .NET legt keine Beschränkungen hinsichtlich der Anzahl der Kontrollkästchen fest, die Sie einem PDF hinzufügen können.

### Kann ich das Erscheinungsbild von Kontrollkästchen nach dem Hinzufügen ändern?
Ja, Sie können die Eigenschaften wie Rahmenstil, Breite und Farbe ändern, nachdem die Kontrollkästchen hinzugefügt wurden.

### Ist es möglich, Bilder als Optionsfelder zu verwenden?
 Ja, Aspose.PDF ermöglicht Ihnen die Verwendung von benutzerdefinierten Bildern als Optionsfelder durch die Einstellung der`Appearance` Eigenschaft jeder Optionsfeldoption.