---
title: Versteckter Textblock in der PDF-Datei
linktitle: Versteckter Textblock in der PDF-Datei
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET versteckte Textblöcke in PDF-Dateien erstellen.
type: docs
weight: 230
url: /de/net/programming-with-text/hidden-text-block/
---
In diesem Tutorial erklären wir, wie man mit der Aspose.PDF-Bibliothek für .NET einen versteckten Textblock in einer PDF-Datei erstellt. Ein versteckter Textblock ist ein schwebender Text, der sichtbar wird, wenn der Mauszeiger über einen bestimmten Bereich fährt. Wir werden den Prozess der Erstellung des versteckten Textblocks mit dem bereitgestellten C#-Quellcode Schritt für Schritt durchgehen.

## Anforderungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Die Aspose.PDF-Bibliothek für .NET ist installiert.
- Grundlegende Kenntnisse der C#-Programmierung.

## Schritt 1: Einrichten des Dokumentverzeichnisses

 Zunächst müssen Sie den Pfad zum Verzeichnis festlegen, in dem Sie die generierte PDF-Datei speichern möchten. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` im`dataDir` Variable durch den Pfad zu Ihrem gewünschten Verzeichnis.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Erstellen Sie ein Beispieldokument

In diesem Schritt erstellen wir ein Beispiel-PDF-Dokument und fügen ihm ein Textfragment hinzu. Das Textfragment dient als Auslöser für die Anzeige des ausgeblendeten Textblocks.

```csharp
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
```

## Schritt 3: Öffnen Sie das Dokument

 Nun öffnen wir das zuvor erstellte Dokument mit dem`Document` Klasse.

```csharp
Document document = new Document(outputFile);
```

## Schritt 4: Suchen Sie das Textfragment

 Wir verwenden ein`TextFragmentAbsorber`Objekt, um das Textfragment zu finden, das die Anzeige des ausgeblendeten Textblocks auslöst. In diesem Fall suchen wir nach dem genauen Text „Bewegen Sie den Mauszeiger hierher, um schwebenden Text anzuzeigen“.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
TextFragment fragment = textFragments[1];
```

## Schritt 5: Erstellen Sie das versteckte Textfeld

 Wir schaffen eine`TextBoxField` Objekt zur Darstellung des ausgeblendeten Textfelds. Dieses Feld enthält den Text, der sichtbar wird, wenn der Mauszeiger über den Triggertext schwebt.

```csharp
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
floatingField.Value = "This is the \"floating text field\".";
floatingField. ReadOnly = true;
floatingField.Flags |= AnnotationFlags.Hidden;
floatingField.PartialName = "FloatingField_1";
floatingField.DefaultAppearance = new DefaultAppearance("Helv", 10, System.Drawing.Color.Blue);
floatingField.Characteristics.Background = System.Drawing.Color.LightBlue;
floatingField.Characteristics.Border = System.Drawing.Color.DarkBlue;
floatingField.Border = new Border(floatingField);
floatingField.Border.Width = 1;
floatingField. Multiline = true;
```

## Schritt 6: Das versteckte Textfeld zum Dokument hinzufügen

Wir fügen das versteckte Textfeld der Formularsammlung des Dokuments hinzu.

```csharp
document.Form.Add(floatingField);
```

## Schritt 7: Erstellen Sie den unsichtbaren Button

Wir erstellen ein unsichtbares Schaltflächenfeld, das über dem Trigger-Textfragment positioniert wird. Dieses Schaltflächenfeld enthält Aktionen, die mit Mauseingabe- und -ausgabeereignissen verknüpft sind.

```csharp
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
document.Form.Add(buttonField);
```

## Schritt 8: Speichern Sie das Dokument

Abschließend speichern wir das geänderte Dokument mit dem ausgeblendeten Textblock.

```csharp
document. Save(outputFile);
```

### Beispiel-Quellcode für versteckten Textblock mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
// Beispieldokument mit Text erstellen
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
// Dokument mit Text öffnen
Document document = new Document(outputFile);
//Erstellen Sie ein TextAbsorber-Objekt, um alle Phrasen zu finden, die dem regulären Ausdruck entsprechen
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
// Akzeptieren Sie den Absorber für die Dokumentseiten
document.Pages.Accept(absorber);
// Holen Sie sich das erste extrahierte Textfragment
TextFragmentCollection textFragments = absorber.TextFragments;
TextFragment fragment = textFragments[1];
//Erstellen Sie ein verstecktes Textfeld für schwebenden Text im angegebenen Rechteck der Seite
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
// Legen Sie den Text fest, der als Feldwert angezeigt werden soll
floatingField.Value = "This is the \"floating text field\".";
// Wir empfehlen, das Feld für dieses Szenario auf „schreibgeschützt“ zu setzen.
floatingField.ReadOnly = true;
// Setzen Sie die Markierung „Versteckt“, um das Feld beim Öffnen des Dokuments unsichtbar zu machen
floatingField.Flags |= AnnotationFlags.Hidden;
// Das Festlegen eines eindeutigen Feldnamens ist nicht erforderlich, aber zulässig
floatingField.PartialName = "FloatingField_1";
// Das Festlegen von Eigenschaften des Feldaussehens ist nicht notwendig, verbessert es aber
floatingField.DefaultAppearance = new DefaultAppearance("Helv", 10, System.Drawing.Color.Blue);
floatingField.Characteristics.Background = System.Drawing.Color.LightBlue;
floatingField.Characteristics.Border = System.Drawing.Color.DarkBlue;
floatingField.Border = new Border(floatingField);
floatingField.Border.Width = 1;
floatingField.Multiline = true;
// Dem Dokument ein Textfeld hinzufügen
document.Form.Add(floatingField);
// Unsichtbare Schaltfläche an der Textfragmentposition erstellen
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
// Erstellen Sie eine neue Ausblendaktion für das angegebene Feld (Anmerkung) und das Unsichtbarkeitskennzeichen.
// (Sie können sich auch auf das Floating-Feld mit dem Namen beziehen, wenn Sie ihn oben angegeben haben.)
// Aktionen beim Ein- und Aussteigen mit der Maus im unsichtbaren Schaltflächenfeld hinzufügen
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
// Schaltflächenfeld zum Dokument hinzufügen
document.Form.Add(buttonField);
// Dokument speichern
document.Save(outputFile);
```

## Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie mit der Aspose.PDF-Bibliothek für .NET einen versteckten Textblock erstellen. Indem Sie der Schritt-für-Schritt-Anleitung folgen, können Sie ein PDF-Dokument mit einem versteckten Textfeld erstellen, das sichtbar wird, wenn der Mauszeiger über einen bestimmten Bereich fährt. Sie können das Erscheinungsbild und Verhalten des versteckten Textblocks Ihren Anforderungen entsprechend anpassen.

### Häufig gestellte Fragen

#### F: Was ist der Zweck des Tutorials „Versteckter Textblock in PDF-Datei“?

A: Das Tutorial „Versteckter Textblock in PDF-Datei“ erklärt, wie man mit der Aspose.PDF-Bibliothek für .NET einen versteckten Textblock in einer PDF-Datei erstellt. Ein versteckter Textblock ist ein schwebender Text, der sichtbar wird, wenn der Mauszeiger über einen bestimmten Bereich fährt. Dieses Tutorial bietet eine Schritt-für-Schritt-Anleitung mit C#-Quellcode.

#### F: Warum sollte ich in einer PDF-Datei einen versteckten Textblock erstellen wollen?

A: Das Erstellen eines versteckten Textblocks kann für interaktive PDF-Dokumente nützlich sein, in denen Sie zusätzliche Informationen oder Kontext bereitstellen möchten, die nur sichtbar werden, wenn ein Benutzer den Mauszeiger über einen bestimmten Bereich bewegt.

#### F: Wie richte ich das Dokumentverzeichnis ein?

A: So richten Sie das Dokumentverzeichnis ein:

1.  Ersetzen`"YOUR DOCUMENT DIRECTORY"` im`dataDir` Variable mit dem Pfad zum Verzeichnis, in dem Sie die generierte PDF-Datei speichern möchten.

#### F: Wie erstelle ich ein Beispieldokument und füge ihm ein Textfragment hinzu?

 A: Im Tutorial verwenden Sie die`Document` Klasse, um ein Beispiel-PDF-Dokument zu erstellen und ein Textfragment hinzuzufügen. Dieses Textfragment dient als Auslöser für die Anzeige des ausgeblendeten Textblocks.

#### F: Wie finde ich das Textfragment, das den versteckten Textblock auslöst?

 A: Das Tutorial zeigt die Verwendung eines`TextFragmentAbsorber` Objekt, um das Textfragment zu finden, das die Anzeige des ausgeblendeten Textblocks auslöst. Es sucht nach einer bestimmten Textzeichenfolge im PDF-Dokument.

#### F: Wie erstelle und passe ich das versteckte Textfeld an?

 A: Sie erstellen eine`TextBoxField`Objekt zur Darstellung des ausgeblendeten Textfelds. Das Tutorial bietet Code zum Festlegen verschiedener Eigenschaften wie Position, Wert, Aussehen und Verhalten des ausgeblendeten Textfelds.

#### F: Wie erstelle ich eine unsichtbare Schaltfläche, die mit dem ausgeblendeten Textblock verknüpft ist?

 A: Ein unsichtbares Schaltflächenfeld wird mit dem`ButtonField` Klasse. Dieses Schaltflächenfeld wird über dem Trigger-Textfragment positioniert und verfügt über Aktionen, die mit Mauseingabe- und -ausgabeereignissen verknüpft sind. Diese Aktionen steuern die Sichtbarkeit des ausgeblendeten Textblocks.

#### F: Kann ich das Erscheinungsbild des ausgeblendeten Textblocks und des Triggerbereichs anpassen?

A: Ja, Sie können verschiedene Eigenschaften sowohl des ausgeblendeten Textfelds als auch der unsichtbaren Schaltfläche anpassen, einschließlich Schriftart, Farbe, Größe und Positionierung.

#### F: Wie speichere ich das geänderte Dokument mit dem ausgeblendeten Textblock?

 A: Das Tutorial zeigt, wie Sie das geänderte Dokument speichern können mit dem`Save` Methode der`Document` Klasse.