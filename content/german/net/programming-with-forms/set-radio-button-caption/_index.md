---
title: Beschriftung für Optionsfeld festlegen
linktitle: Beschriftung für Optionsfeld festlegen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Optionsfeldbeschriftungen in PDFs festlegen. Diese Schritt-für-Schritt-Anleitung führt Sie durch das Laden, Ändern und Speichern Ihrer PDF-Formulare.
type: docs
weight: 280
url: /de/net/programming-with-forms/set-radio-button-caption/
---
## Einführung

Wenn Sie sich mit der PDF-Bearbeitung mit Aspose.PDF für .NET beschäftigen, erwartet Sie ein Leckerbissen! Heute konzentrieren wir uns auf eine praktische Funktion: das Festlegen von Optionsfeldbeschriftungen in Ihren PDF-Formularen. Optionsfelder sind für Benutzerformulare unerlässlich, bei denen Sie aus einer Reihe von Optionen auswählen müssen. Stellen Sie sie sich als Multiple-Choice-Fragen vor, bei denen nur eine Antwort zulässig ist. Dieses Tutorial führt Sie durch den Prozess der Aktualisierung von Optionsfeldbeschriftungen in einem PDF-Formular, damit Ihre Dokumente sowohl interaktiv als auch benutzerfreundlich sind. 

## Voraussetzungen

Bevor Sie sich in den Code vertiefen, müssen Sie Folgendes sicherstellen:

1. Aspose.PDF für .NET: Stellen Sie sicher, dass Sie die Aspose.PDF-Bibliothek installiert haben. Mit dieser Bibliothek können Sie PDF-Dateien programmgesteuert bearbeiten.
2. Entwicklungsumgebung: Sie sollten eine .NET-Entwicklungsumgebung wie Visual Studio eingerichtet haben.
3. Beispiel-PDF-Formular: Für dieses Tutorial benötigen Sie ein Beispiel-PDF-Formular mit Optionsfeldern. Sie können ein vorhandenes PDF-Formular verwenden oder ein neues mit Optionsfeldern erstellen.
4. Grundkenntnisse in C#: Dieses Handbuch setzt voraus, dass Sie über grundlegende Kenntnisse der Programmierkonzepte von C# und .NET verfügen.

 Wenn Sie Aspose.PDF für .NET noch nicht installiert haben oder eine temporäre Lizenz benötigen, können Sie[Laden Sie es hier herunter](https://releases.aspose.com/pdf/net/) oder[eine temporäre Lizenz erhalten](https://purchase.aspose.com/temporary-license/).

## Pakete importieren

Um zu beginnen, müssen Sie die erforderlichen Pakete in Ihr C#-Projekt importieren. So binden Sie die Aspose.PDF-Bibliothek ein:

```csharp
using System;
using Aspose.Pdf.Forms;
using System.Collections.Generic;
using Aspose.Pdf.Text;
```

Stellen Sie sicher, dass Sie diese Pakete über NuGet oder Ihre bevorzugte Methode zu Ihrem Projekt hinzugefügt haben.

## Schritt 1: Laden Sie das PDF-Formular

 Zuerst müssen Sie das PDF-Formular laden, das die Optionsfelder enthält.`Aspose.Pdf.Facades.Form`Klasse wird für diesen Zweck verwendet. So geht's:

```csharp
// Definieren Sie den Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Laden Sie das Quell-PDF-Formular
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
Document PDF_Template_PDF_HTML = new Document(dataDir + "RadioButtonField.pdf");
```

In diesem Codeausschnitt:
- `dataDir` gibt den Pfad an, in dem sich Ihr PDF befindet.
- `Form` Klasse wird zur Interaktion mit den Formularfeldern im PDF verwendet.
- `Document` Klasse bietet Zugriff auf die Seiten des PDF-Dokuments.

## Schritt 2: Durch Radiobutton-Felder iterieren

Als Nächstes müssen Sie die Felder in Ihrem Formular durchlaufen, um die Optionsfeldfelder zu identifizieren und zu bearbeiten:

```csharp
foreach (var item in form1.FieldNames)
{
    Console.WriteLine(item.ToString());
    Dictionary<string, string> radioOptions = form1.GetButtonOptionValues(item);
```

In dieser Schleife:
- `FieldNames` bietet eine Liste aller Feldnamen im PDF.
- `GetButtonOptionValues(item)` ruft die für jedes Optionsfeld verfügbaren Optionen ab.

## Schritt 3: Optionsfeldoptionen ändern

 Sobald Sie die Optionsfelder identifiziert haben, können Sie deren Optionen ändern. Dazu müssen Sie das Feld in`RadioButtonField` und aktualisieren Sie die Optionen:

```csharp
    if (item.Contains("radio1"))
    {
        Aspose.Pdf.Forms.RadioButtonField field0 = PDF_Template_PDF_HTML.Form[item] as Aspose.Pdf.Forms.RadioButtonField;
        Aspose.Pdf.Forms.RadioButtonOptionField fieldoption = new Aspose.Pdf.Forms.RadioButtonOptionField();
        fieldoption.OptionName = "Yes";
        fieldoption.PartialName = "Yesname";
```

Hier:
- Wir prüfen, ob der Feldname „radio1“ enthält, um das spezifische Optionsfeld zu identifizieren, das wir ändern möchten.
- `RadioButtonField`wird aus den Formularfeldern gegossen, um bestimmte Änderungen vorzunehmen.

## Schritt 4: Festlegen der Beschriftung für das Optionsfeld

 Um die Beschriftung für das Optionsfeld festzulegen oder zu aktualisieren, müssen Sie eine`TextFragment` und Verwendung`TextBuilder` um es an der gewünschten Stelle zu platzieren:

```csharp
        var updatedFragment = new Aspose.Pdf.Text.TextFragment("test123");
        updatedFragment.TextState.Font = FontRepository.FindFont("Arial");
        updatedFragment.TextState.FontSize = 10;
        updatedFragment.TextState.LineSpacing = 6.32f;

        // TextParagraph-Objekt erstellen
        TextParagraph par = new TextParagraph();
        // Absatzposition festlegen
        par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
        // Festlegen des Zeilenumbruchmodus
        par.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
        // Neues TextFragment zum Absatz hinzufügen
        par.AppendLine(updatedFragment);
        // Fügen Sie den TextParagraph mit TextBuilder hinzu
        TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
        textBuilder.AppendParagraph(par);
```

In diesem Teil:
- `TextFragment` wird verwendet, um den Text und sein Erscheinungsbild zu definieren.
- `TextParagraph` hilft beim Positionieren und Formatieren des Textes.
- `TextBuilder` fügt den Text der angegebenen Seite des PDFs hinzu.

## Schritt 5: Speichern Sie die aktualisierte PDF-Datei

Speichern Sie abschließend die aktualisierte PDF-Datei in einer neuen Datei:

```csharp
        field0.DeleteOption("item1");
    }
}
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

Dadurch wird Folgendes sichergestellt:
- Die Änderungen werden in das PDF übernommen.
- Die ursprüngliche Optionsfeldoption wird wie angegeben entfernt.

## Abschluss

Das Ändern von Optionsfeldbeschriftungen in einem PDF-Formular mit Aspose.PDF für .NET kann die Interaktivität und Benutzerfreundlichkeit Ihrer Dokumente erheblich verbessern. Mit den in diesem Tutorial beschriebenen Schritten können Sie ganz einfach ein PDF laden, Optionsfeldoptionen aktualisieren und Ihre Änderungen speichern. Dieser Ansatz ist praktisch für die Formularverwaltung und stellt sicher, dass Ihre PDFs genau den Anforderungen Ihrer Benutzer entsprechen. Tauchen Sie ein in Aspose.PDF und erkunden Sie seine Möglichkeiten für andere PDF-Manipulationen!

## Häufig gestellte Fragen

### Kann ich mehrere Optionsfeldfelder gleichzeitig aktualisieren?
Ja, Sie können alle Optionsfeldfelder durchlaufen und nach Bedarf Änderungen vornehmen.

### Benötige ich eine Lizenz, um Aspose.PDF zu verwenden?
 Sie können mit einer kostenlosen Testversion beginnen, für die erweiterte Nutzung ist jedoch eine Lizenz erforderlich.[Holen Sie sich hier eine Lizenz](https://purchase.aspose.com/buy).

### Wie kann ich die Änderungen testen, bevor ich das PDF speichere?
Sie können eine Vorschau der PDF-Datei in Ihrer Entwicklungsumgebung anzeigen oder einen PDF-Viewer verwenden, um die Änderungen zu überprüfen.

### Ist Aspose.PDF mit allen Versionen von .NET kompatibel?
Aspose.PDF unterstützt verschiedene Versionen von .NET. Stellen Sie sicher, dass Sie die Kompatibilität mit Ihrer spezifischen .NET-Version überprüfen.

### Kann ich andere Formularfelder auf ähnliche Weise bearbeiten?
Ja, ähnliche Techniken können auf andere Arten von Formularfeldern in PDF-Dokumenten angewendet werden.