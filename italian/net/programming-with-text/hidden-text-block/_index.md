---
title: Blocco di testo nascosto
linktitle: Blocco di testo nascosto
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come creare blocchi di testo nascosti in PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 230
url: /it/net/programming-with-text/hidden-text-block/
---

In questo tutorial, spiegheremo come creare un blocco di testo nascosto utilizzando la libreria Aspose.PDF per .NET. Un blocco di testo nascosto è un testo fluttuante che diventa visibile quando il cursore del mouse passa sopra un'area specifica. Passeremo attraverso il processo passo-passo di creazione del blocco di testo nascosto utilizzando il codice sorgente C# fornito.

## Requisiti

Prima di iniziare, assicurati di disporre di quanto segue:

- La libreria Aspose.PDF per .NET installata.
- Una conoscenza di base della programmazione C#.

## Passaggio 1: impostare la directory dei documenti

 Innanzitutto, devi impostare il percorso della directory in cui desideri salvare il file PDF generato. Sostituire`"YOUR DOCUMENT DIRECTORY"` nel`dataDir` variabile con il percorso della directory desiderata.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: creare un documento di esempio

In questo passaggio, creiamo un documento PDF di esempio e vi aggiungiamo un frammento di testo. Il frammento di testo fungerà da trigger per la visualizzazione del blocco di testo nascosto.

```csharp
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
```

## Passaggio 3: apri il documento

 Ora apriamo il documento creato in precedenza utilizzando il file`Document` classe.

```csharp
Document document = new Document(outputFile);
```

## Passaggio 4: trova il frammento di testo

 Usiamo un`TextFragmentAbsorber` oggetto per trovare il frammento di testo che attiverà la visualizzazione del blocco di testo nascosto. In questo caso, stiamo cercando il testo esatto "Sposta qui il cursore del mouse per visualizzare il testo mobile".

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
TextFragment fragment = textFragments[1];
```

## Passaggio 5: crea il campo di testo nascosto

 Creiamo un`TextBoxField` oggetto per rappresentare il campo di testo nascosto. Questo campo conterrà il testo che diventa visibile quando il cursore del mouse passa sopra il testo del trigger.

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

## Passaggio 6: aggiungi il campo di testo nascosto al documento

Aggiungiamo il campo di testo nascosto alla raccolta di moduli del documento.

```csharp
document.Form.Add(floatingField);
```

## Passaggio 7: crea il pulsante invisibile

Creiamo un campo pulsante invisibile che verrà posizionato sopra il frammento di testo del trigger. Questo campo pulsante avrà azioni associate agli eventi di entrata e uscita del mouse.

```csharp
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
document.Form.Add(buttonField);
```

## Passaggio 8: salvare il documento

Infine, salviamo il documento modificato con il blocco di testo nascosto.

```csharp
document. Save(outputFile);
```

### Esempio di codice sorgente per Hidden Text Block utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
// Crea un documento di esempio con il testo
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
// Apri documento con testo
Document document = new Document(outputFile);
// Crea un oggetto TextAbsorber per trovare tutte le frasi che corrispondono all'espressione regolare
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
// Accetta l'assorbitore per le pagine del documento
document.Pages.Accept(absorber);
// Ottieni il primo frammento di testo estratto
TextFragmentCollection textFragments = absorber.TextFragments;
TextFragment fragment = textFragments[1];
// Crea un campo di testo nascosto per il testo mobile nel rettangolo specificato della pagina
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
// Imposta il testo da visualizzare come valore del campo
floatingField.Value = "This is the \"floating text field\".";
// Si consiglia di rendere il campo "sola lettura" per questo scenario
floatingField.ReadOnly = true;
// Imposta il flag 'nascosto' per rendere invisibile il campo all'apertura del documento
floatingField.Flags |= AnnotationFlags.Hidden;
// L'impostazione di un nome di campo univoco non è necessaria ma consentita
floatingField.PartialName = "FloatingField_1";
// L'impostazione delle caratteristiche dell'aspetto del campo non è necessaria ma lo rende migliore
floatingField.DefaultAppearance = new DefaultAppearance("Helv", 10, System.Drawing.Color.Blue);
floatingField.Characteristics.Background = System.Drawing.Color.LightBlue;
floatingField.Characteristics.Border = System.Drawing.Color.DarkBlue;
floatingField.Border = new Border(floatingField);
floatingField.Border.Width = 1;
floatingField.Multiline = true;
// Aggiungi campo di testo al documento
document.Form.Add(floatingField);
// Crea pulsante invisibile sulla posizione del frammento di testo
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
// Crea una nuova azione nascondi per il campo specificato (annotazione) e il flag di invisibilità.
//(Puoi anche fare riferimento al campo mobile con il nome se lo hai specificato sopra.)
// Aggiungi azioni all'entrata/uscita del mouse nel campo del pulsante invisibile
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
// Aggiungi campo pulsante al documento
document.Form.Add(buttonField);
// Salva documento
document.Save(outputFile);
```

## Conclusione

In questo tutorial, hai imparato come creare un blocco di testo nascosto utilizzando la libreria Aspose.PDF per .NET. Seguendo la guida passo passo, puoi generare un documento PDF con un campo di testo nascosto che diventa visibile quando il cursore del mouse passa sopra un'area specifica. È possibile personalizzare l'aspetto e il comportamento del blocco di testo nascosto in base alle proprie esigenze.