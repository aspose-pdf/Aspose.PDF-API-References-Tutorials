---
title: Versteckter Textblock
linktitle: Versteckter Textblock
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET versteckte Textblöcke in PDF erstellen.
type: docs
weight: 230
url: /de/net/programming-with-text/hidden-text-block/
---

In diesem Tutorial erklären wir, wie Sie mit der Aspose.PDF-Bibliothek für .NET einen versteckten Textblock erstellen. Ein ausgeblendeter Textblock ist ein schwebender Text, der sichtbar wird, wenn der Mauszeiger über einen bestimmten Bereich schwebt. Wir werden den Prozess der Erstellung des versteckten Textblocks mithilfe des bereitgestellten C#-Quellcodes Schritt für Schritt durchgehen.

## Anforderungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Die Aspose.PDF für .NET-Bibliothek installiert.
- Ein grundlegendes Verständnis der C#-Programmierung.

## Schritt 1: Richten Sie das Dokumentenverzeichnis ein

 Zunächst müssen Sie den Pfad zu dem Verzeichnis festlegen, in dem Sie die generierte PDF-Datei speichern möchten. Ersetzen`"YOUR DOCUMENT DIRECTORY"` im`dataDir` Variable mit dem Pfad zu Ihrem gewünschten Verzeichnis.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Erstellen Sie ein Beispieldokument

In diesem Schritt erstellen wir ein Beispiel-PDF-Dokument und fügen ein Textfragment hinzu. Das Textfragment dient als Auslöser für die Anzeige des ausgeblendeten Textblocks.

```csharp
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
```

## Schritt 3: Öffnen Sie das Dokument

 Jetzt öffnen wir das zuvor erstellte Dokument mit`Document` Klasse.

```csharp
Document document = new Document(outputFile);
```

## Schritt 4: Finden Sie das Textfragment

 Wir benutzen ein`TextFragmentAbsorber` Objekt, um das Textfragment zu finden, das die Anzeige des ausgeblendeten Textblocks auslöst. In diesem Fall suchen wir nach dem genauen Text „Bewegen Sie den Mauszeiger hierher, um schwebenden Text anzuzeigen“.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
TextFragment fragment = textFragments[1];
```

## Schritt 5: Erstellen Sie das ausgeblendete Textfeld

 Wir erstellen ein`TextBoxField` Objekt zur Darstellung des ausgeblendeten Textfelds. Dieses Feld enthält den Text, der sichtbar wird, wenn sich der Mauszeiger über dem Auslösetext befindet.

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

## Schritt 6: Fügen Sie das ausgeblendete Textfeld zum Dokument hinzu

Wir fügen das ausgeblendete Textfeld zur Formularsammlung des Dokuments hinzu.

```csharp
document.Form.Add(floatingField);
```

## Schritt 7: Erstellen Sie die unsichtbare Schaltfläche

Wir erstellen ein unsichtbares Schaltflächenfeld, das über dem Triggertextfragment positioniert wird. Dieses Schaltflächenfeld verfügt über Aktionen, die mit Ein- und Ausstiegsereignissen der Maus verknüpft sind.

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

### Beispielquellcode für Hidden Text Block mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
// Erstellen Sie ein Beispieldokument mit Text
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
// Dokument mit Text öffnen
Document document = new Document(outputFile);
// Erstellen Sie ein TextAbsorber-Objekt, um alle Phrasen zu finden, die dem regulären Ausdruck entsprechen
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
// Akzeptieren Sie den Absorber für die Dokumentseiten
document.Pages.Accept(absorber);
// Holen Sie sich das erste extrahierte Textfragment
TextFragmentCollection textFragments = absorber.TextFragments;
TextFragment fragment = textFragments[1];
// Erstellen Sie ein verstecktes Textfeld für schwebenden Text im angegebenen Rechteck der Seite
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
// Legen Sie den Text fest, der als Feldwert angezeigt werden soll
floatingField.Value = "This is the \"floating text field\".";
// Wir empfehlen, das Feld für dieses Szenario auf „schreibgeschützt“ zu setzen
floatingField.ReadOnly = true;
// Setzen Sie die Markierung „versteckt“, um das Feld beim Öffnen des Dokuments unsichtbar zu machen
floatingField.Flags |= AnnotationFlags.Hidden;
// Das Festlegen eines eindeutigen Feldnamens ist nicht erforderlich, aber zulässig
floatingField.PartialName = "FloatingField_1";
// Das Festlegen von Eigenschaften der Felddarstellung ist nicht notwendig, macht es aber besser
floatingField.DefaultAppearance = new DefaultAppearance("Helv", 10, System.Drawing.Color.Blue);
floatingField.Characteristics.Background = System.Drawing.Color.LightBlue;
floatingField.Characteristics.Border = System.Drawing.Color.DarkBlue;
floatingField.Border = new Border(floatingField);
floatingField.Border.Width = 1;
floatingField.Multiline = true;
// Fügen Sie dem Dokument ein Textfeld hinzu
document.Form.Add(floatingField);
// Erstellen Sie eine unsichtbare Schaltfläche an der Position des Textfragments
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
// Erstellen Sie eine neue Ausblenden-Aktion für das angegebene Feld (Anmerkung) und die Unsichtbarkeitsmarkierung.
//(Sie können das Floating-Feld auch anhand des Namens referenzieren, wenn Sie ihn oben angegeben haben.)
// Fügen Sie Aktionen beim Betreten/Verlassen der Maus im unsichtbaren Schaltflächenfeld hinzu
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
// Fügen Sie dem Dokument ein Schaltflächenfeld hinzu
document.Form.Add(buttonField);
// Dokument speichern
document.Save(outputFile);
```

## Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie mit der Bibliothek Aspose.PDF für .NET einen versteckten Textblock erstellen. Wenn Sie der Schritt-für-Schritt-Anleitung folgen, können Sie ein PDF-Dokument mit einem ausgeblendeten Textfeld erstellen, das sichtbar wird, wenn der Mauszeiger über einen bestimmten Bereich fährt. Sie können das Aussehen und Verhalten des ausgeblendeten Textblocks Ihren Anforderungen entsprechend anpassen.