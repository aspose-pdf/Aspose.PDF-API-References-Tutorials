---
title: Incorpora i caratteri utilizzando la strategia dei sottoinsiemi
linktitle: Incorpora i caratteri utilizzando la strategia dei sottoinsiemi
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come incorporare i caratteri in un file PDF con Subset Strategy utilizzando Aspose.PDF per .NET. Ottimizza le dimensioni del tuo PDF incorporando solo i caratteri necessari.
type: docs
weight: 130
url: /it/net/programming-with-document/embedfontsusingsubsetstrategy/
---

In questo tutorial, discuteremo come incorporare i caratteri in un file PDF con una strategia di sottoinsieme utilizzando Aspose.PDF per .NET. Aspose.PDF per .NET è una potente libreria che consente agli sviluppatori di creare, modificare e manipolare documenti PDF in modo programmatico. L'incorporamento dei caratteri in un file PDF è un passaggio importante per garantire che il documento venga visualizzato correttamente su dispositivi diversi, indipendentemente dal fatto che i caratteri richiesti siano installati o meno su tali dispositivi.

## Passaggio 1: creare una nuova applicazione console C#
Per iniziare, crea una nuova applicazione console C# in Visual Studio. Puoi chiamarlo come preferisci. Una volta creato il progetto, è necessario aggiungere un riferimento alla libreria Aspose.PDF per .NET.

## Passaggio 2: importa lo spazio dei nomi Aspose.PDF
Aggiungi la seguente riga di codice nella parte superiore del file C# per importare lo spazio dei nomi Aspose.PDF:

```csharp
using Aspose.Pdf;
```

## Passaggio 3: caricare un file PDF esistente
Per incorporare i font in un file PDF esistente, è necessario caricare quel file utilizzando la classe Document. Il codice seguente mostra come caricare un file PDF esistente:

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Carica un file PDF esistente
Document doc = new Document(dataDir + "input.pdf");
```

## Passaggio 4: incorpora i caratteri con la strategia dei sottoinsiemi
Aspose.PDF per .NET fornisce due strategie per l'incorporamento dei caratteri: SubsetAllFonts e SubsetEmbeddedFontsOnly.

La strategia SubsetAllFonts incorporerà tutti i caratteri nel documento come sottoinsieme. Un sottoinsieme è una parte del carattere che contiene solo i caratteri utilizzati nel documento. Questa strategia è utile per ridurre le dimensioni del file del documento PDF.

La strategia SubsetEmbeddedFontsOnly incorporerà solo il sottoinsieme di caratteri che sono già incorporati nel documento. Se un carattere non è incorporato, non sarà influenzato da questa strategia.

Il codice seguente mostra come incorporare i caratteri in un file PDF con una strategia di sottoinsieme:

```csharp
// Tutti i caratteri verranno incorporati come sottoinsieme nel documento in caso di SubsetAllFonts.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetAllFonts);

// Il sottoinsieme di caratteri verrà incorporato per i caratteri completamente incorporati, ma i caratteri che non sono incorporati nel documento non saranno interessati.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetEmbeddedFontsOnly);
```

## Passaggio 5: salvare il documento PDF
Dopo aver incorporato tutti i caratteri nel file PDF con una strategia di sottoinsieme, è necessario salvare il documento. Il codice seguente mostra come salvare il file PDF:

```csharp
doc.Save(dataDir + "Output_out.pdf");
```

### Codice sorgente di esempio per l'incorporamento di caratteri con strategia di sottoinsieme utilizzando Aspose.PDF per .NET. 

```csharp

            
            // Il percorso della directory dei documenti.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            Document doc = new Document(dataDir + "input.pdf");
            // Tutti i caratteri verranno incorporati come sottoinsieme nel documento in caso di SubsetAllFonts.
            doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetAllFonts);
            // Il sottoinsieme di caratteri verrà incorporato per i caratteri completamente incorporati, ma i caratteri che non sono incorporati nel documento non saranno interessati.
            doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetEmbeddedFontsOnly);
            doc.Save(dataDir + "Output_out.pdf");
            

        
```

## Conclusione
In questo articolo, abbiamo discusso su come incorporare i caratteri in un file PDF con una strategia di sottoinsieme utilizzando Aspose.PDF per .NET. Aspose.PDF per .NET fornisce un'API semplice e facile da usare per lavorare con documenti PDF, inclusa l'aggiunta e l'incorporamento di caratteri con diverse strategie. L'incorporamento dei caratteri in un file PDF è un passaggio importante per garantire che il documento venga visualizzato correttamente su dispositivi diversi e la strategia dei sottoinsiemi è una funzione utile per ridurre le dimensioni del file del documento PDF.

