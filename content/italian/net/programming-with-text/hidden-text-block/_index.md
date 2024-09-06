---
title: Blocco di testo nascosto nel file PDF
linktitle: Blocco di testo nascosto nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come creare blocchi di testo nascosti nei file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 230
url: /it/net/programming-with-text/hidden-text-block/
---
In questo tutorial, spiegheremo come creare un blocco di testo nascosto in un file PDF usando la libreria Aspose.PDF per .NET. Un blocco di testo nascosto è un testo mobile che diventa visibile quando il cursore del mouse passa sopra un'area specifica. Esamineremo passo dopo passo il processo di creazione del blocco di testo nascosto usando il codice sorgente C# fornito.

## Requisiti

Prima di iniziare, assicurati di avere quanto segue:

- È stata installata la libreria Aspose.PDF per .NET.
- Conoscenza di base della programmazione C#.

## Passaggio 1: impostare la directory dei documenti

 Per prima cosa, devi impostare il percorso della directory in cui vuoi salvare il file PDF generato. Sostituisci`"YOUR DOCUMENT DIRECTORY"` nel`dataDir` variabile con il percorso della directory desiderata.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: creare un documento di esempio

In questo passaggio, creiamo un documento PDF di esempio e vi aggiungiamo un frammento di testo. Il frammento di testo servirà come trigger per la visualizzazione del blocco di testo nascosto.

```csharp
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
```

## Passaggio 3: aprire il documento

 Ora apriamo il documento creato in precedenza utilizzando il`Document` classe.

```csharp
Document document = new Document(outputFile);
```

## Passaggio 4: trova il frammento di testo

 Noi utilizziamo un`TextFragmentAbsorber`object per trovare il frammento di testo che attiverà la visualizzazione del blocco di testo nascosto. In questo caso, stiamo cercando il testo esatto "Sposta il cursore del mouse qui per visualizzare il testo mobile".

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
TextFragment fragment = textFragments[1];
```

## Passaggio 5: creare il campo di testo nascosto

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

## Passaggio 6: aggiungere il campo di testo nascosto al documento

Aggiungiamo il campo di testo nascosto alla raccolta dei moduli del documento.

```csharp
document.Form.Add(floatingField);
```

## Passaggio 7: creare il pulsante invisibile

Creiamo un campo pulsante invisibile che verrà posizionato in cima al frammento di testo del trigger. Questo campo pulsante avrà azioni associate agli eventi di entrata e uscita del mouse.

```csharp
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
document.Form.Add(buttonField);
```

## Passaggio 8: Salvare il documento

Infine, salviamo il documento modificato con il blocco di testo nascosto.

```csharp
document. Save(outputFile);
```

### Esempio di codice sorgente per blocco di testo nascosto utilizzando Aspose.PDF per .NET 
```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
// Crea un documento di esempio con testo
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
//Crea un campo di testo nascosto per il testo mobile nel rettangolo specificato della pagina
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
// Imposta il testo da visualizzare come valore del campo
floatingField.Value = "This is the \"floating text field\".";
// Si consiglia di rendere il campo "di sola lettura" per questo scenario
floatingField.ReadOnly = true;
// Imposta il flag "nascosto" per rendere il campo invisibile all'apertura del documento
floatingField.Flags |= AnnotationFlags.Hidden;
// L'impostazione di un nome di campo univoco non è necessaria ma consentita
floatingField.PartialName = "FloatingField_1";
// L'impostazione delle caratteristiche dell'aspetto del campo non è necessaria, ma lo rende migliore
floatingField.DefaultAppearance = new DefaultAppearance("Helv", 10, System.Drawing.Color.Blue);
floatingField.Characteristics.Background = System.Drawing.Color.LightBlue;
floatingField.Characteristics.Border = System.Drawing.Color.DarkBlue;
floatingField.Border = new Border(floatingField);
floatingField.Border.Width = 1;
floatingField.Multiline = true;
// Aggiungi campo di testo al documento
document.Form.Add(floatingField);
// Crea un pulsante invisibile sulla posizione del frammento di testo
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
// Crea una nuova azione di nascondimento per il campo specificato (annotazione) e il flag di invisibilità.
// (È anche possibile fare riferimento al campo mobile tramite il nome, se lo si è specificato sopra.)
// Aggiungere azioni all'ingresso/uscita del mouse nel campo del pulsante invisibile
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
// Aggiungere il campo pulsante al documento
document.Form.Add(buttonField);
// Salvare il documento
document.Save(outputFile);
```

## Conclusione

In questo tutorial, hai imparato come creare un blocco di testo nascosto usando la libreria Aspose.PDF per .NET. Seguendo la guida passo passo, puoi generare un documento PDF con un campo di testo nascosto che diventa visibile quando il cursore del mouse passa sopra un'area specifica. Puoi personalizzare l'aspetto e il comportamento del blocco di testo nascosto in base alle tue esigenze.

### Domande frequenti

#### D: Qual è lo scopo del tutorial "Blocco di testo nascosto nel file PDF"?

A: Il tutorial "Hidden Text Block In PDF File" spiega come creare un blocco di testo nascosto in un file PDF utilizzando la libreria Aspose.PDF per .NET. Un blocco di testo nascosto è un testo mobile che diventa visibile quando il cursore del mouse passa sopra un'area specifica. Questo tutorial fornisce una guida passo-passo utilizzando il codice sorgente C#.

#### D: Perché dovrei voler creare un blocco di testo nascosto in un file PDF?

R: Creare un blocco di testo nascosto può essere utile per i documenti PDF interattivi in cui si desidera fornire informazioni aggiuntive o contesto che diventano visibili solo quando l'utente passa il cursore del mouse su un'area designata.

#### D: Come faccio a impostare la directory dei documenti?

A: Per impostare la directory dei documenti:

1.  Sostituire`"YOUR DOCUMENT DIRECTORY"` nel`dataDir` variabile con il percorso della directory in cui si desidera salvare il file PDF generato.

#### D: Come posso creare un documento di esempio e aggiungervi un frammento di testo?

 A: Nel tutorial, usi il`Document` classe per creare un documento PDF di esempio e aggiungere un frammento di testo. Questo frammento di testo serve come trigger per visualizzare il blocco di testo nascosto.

#### D: Come faccio a trovare il frammento di testo che attiva il blocco di testo nascosto?

 A: Il tutorial mostra come utilizzare un`TextFragmentAbsorber` oggetto per trovare il frammento di testo che attiva la visualizzazione del blocco di testo nascosto. Cerca una stringa di testo specifica all'interno del documento PDF.

#### D: Come posso creare e personalizzare il campo di testo nascosto?

 A: Crei un`TextBoxField`oggetto per rappresentare il campo di testo nascosto. Il tutorial fornisce codice per impostare varie proprietà come posizione, valore, aspetto e comportamento del campo di testo nascosto.

#### D: Come posso creare un pulsante invisibile associato al blocco di testo nascosto?

 A: Un campo pulsante invisibile viene creato utilizzando`ButtonField` classe. Questo campo pulsante è posizionato in cima al frammento di testo del trigger e ha azioni associate agli eventi di entrata e uscita del mouse. Queste azioni controllano la visibilità del blocco di testo nascosto.

#### D: Posso personalizzare l'aspetto del blocco di testo nascosto e dell'area di attivazione?

R: Sì, puoi personalizzare varie proprietà sia del campo di testo nascosto che del pulsante invisibile, tra cui carattere, colore, dimensione e posizionamento.

#### D: Come faccio a salvare il documento modificato con il blocco di testo nascosto?

 A: Il tutorial mostra come salvare il documento modificato utilizzando`Save` metodo del`Document` classe.