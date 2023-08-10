---
title: Firma con smart card utilizzando il campo firma
linktitle: Firma con smart card utilizzando il campo firma
second_title: Aspose.PDF per riferimento API .NET
description: Firma i tuoi file PDF in modo sicuro con una smart card utilizzando Aspose.PDF per .NET.
type: docs
weight: 120
url: /it/net/programming-with-security-and-signatures/sign-with-smart-card-using-signature-field/
---
La firma digitale con una smart card è un modo sicuro per firmare i file PDF. Con Aspose.PDF per .NET, puoi facilmente firmare un file PDF utilizzando un campo firma e una smart card seguendo il seguente codice sorgente:

## Passaggio 1: importa le librerie richieste

Prima di iniziare, devi importare le librerie necessarie per il tuo progetto C#. Ecco le direttive di importazione necessarie:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## Passaggio 2: imposta il percorso della cartella dei documenti

 In questo passaggio, è necessario specificare il percorso della cartella contenente il file PDF che si desidera firmare. Sostituire`"YOUR DOCUMENTS DIRECTORY"`nel seguente codice con il percorso effettivo della cartella dei documenti:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 3: copia e apri il documento PDF

Ora copieremo e apriremo il documento PDF da firmare utilizzando il seguente codice:

```csharp
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);

using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
     using (Document doc = new Document(fs))
     {
         // Crea un campo firma
         SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));

         // Seleziona il certificato nello store
         X509Store store = new X509Store(StoreLocation.CurrentUser);
         store.Open(OpenFlags.ReadOnly);
         X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
        
         // Crea una firma esterna con le informazioni necessarie
         ExternalSignature externalSignature = new ExternalSignature(sel[0])
         {
             Authority = "Me",
             Reason = "Reason",
             ContactInfo = "Contact"
         };

         field1.PartialName = "sig1";
         doc.Form.Add(field1, 1);
         field1.Sign(externalSignature);
         doc.Save();
     }
}
```

## Passaggio 4: verifica la firma

 Infine, verifichiamo la firma del file PDF firmato utilizzando l'estensione`PdfFileSignature` classe. Otteniamo i nomi delle firme e li controlliamo uno per uno. Se una firma non supera la verifica, viene generata un'eccezione. Ecco il codice corrispondente:

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature(new Document(dataDir + "externalSignature1.pdf")))
{
     IList<string> sigNames = pdfSign. GetSignNames();
     for (int index = 0; index <= sigNames.Count - 1; index++)
     {
         if (!pdfSign.VerifySigned(sigNames[index]) || !pdfSign.VerifySignature(sigNames[index]))
         {
             throw new ApplicationException("Unverified");
         }
     }
}
```

### Esempio di codice sorgente per Firma con smart card utilizzando il campo firma utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);
using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
	using (Document doc = new Document(fs))
	{
		SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));
		// Firma con la selezione del certificato nell'archivio certificati di Windows
		System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
		store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
		// Scegli manualmente il certificato nello store
		System.Security.Cryptography.X509Certificates.X509Certificate2Collection sel = System.Security.Cryptography.X509Certificates.X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, System.Security.Cryptography.X509Certificates.X509SelectionFlag.SingleSelection);
		Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0])
		{
			Authority = "Me",
			Reason = "Reason",
			ContactInfo = "Contact"
		};
		field1.PartialName = "sig1";
		doc.Form.Add(field1, 1);
		field1.Sign(externalSignature);
		doc.Save();
	}
}
using (PdfFileSignature pdfSign = new PdfFileSignature(new Document(dataDir + "externalSignature1.pdf")))
{
	IList<string> sigNames = pdfSign.GetSignNames();
	for (int index = 0; index <= sigNames.Count - 1; index++)
	{
		if (!pdfSign.VerifySigned(sigNames[index]) || !pdfSign.VerifySignature(sigNames[index]))
		{
			throw new ApplicationException("Not verified");
		}
	}
}
```

## Conclusione

Congratulazioni! Ora hai una guida passo-passo per firmare un file PDF con una smart card utilizzando un campo firma con Aspose.PDF per .NET. Puoi utilizzare questo codice per aggiungere firme digitali sicure ai tuoi documenti PDF.

Assicurati di controllare la documentazione ufficiale di Aspose.PDF per ulteriori informazioni sulla firma digitale avanzata e sulle funzionalità di gestione dei certificati.

### FAQ

#### D: Qual è il vantaggio dell'utilizzo di un campo firma per la firma digitale con una smart card?

R: L'utilizzo di un campo firma per la firma digitale con una smart card fornisce un'area designata all'interno del PDF in cui viene applicata la firma. Ciò migliora la chiarezza del documento e garantisce l'autenticità della firma.

#### D: In che modo la libreria Aspose.PDF per .NET facilita la firma digitale basata su smart card con un campo firma?

R: Aspose.PDF per .NET semplifica il processo di creazione di un campo firma, selezione di un certificato smart card e applicazione di una firma digitale a un'area specifica all'interno del documento PDF.

#### D: Perché la selezione di un certificato specifico è importante per la firma basata su smart card?

R: La selezione di un certificato specifico consente di identificare in modo univoco il firmatario e garantire l'integrità della firma. Questo aiuta a stabilire la fiducia e la conformità con gli standard di firma digitale.

#### D: In che modo il codice sorgente fornito gestisce il processo di firma basato su smart card con un campo firma?

R: Il codice sorgente mostra come creare un campo firma, selezionare un certificato smart card e applicare una firma digitale con informazioni di firma specifiche. Mostra anche come verificare la validità della firma.

#### D: Posso personalizzare l'aspetto del campo della firma?

R: Sì, puoi personalizzare l'aspetto del campo della firma, ad esempio dimensioni, posizione e rappresentazione visiva, per allinearlo al layout del documento.

#### D: Cosa succede se una firma non supera la verifica durante la fase di verifica?

R: Se una firma non supera la verifica, viene generata un'eccezione che indica che la firma non è valida. Ciò garantisce che vengano accettate solo firme valide e attendibili.

#### D: Posso applicare più campi firma e firme basate su smart card a un singolo documento PDF?

R: Assolutamente, puoi applicare più campi firma e firme basate su smart card a diverse aree dello stesso documento PDF, fornendo più livelli di sicurezza.

#### D: In che modo l'utilizzo di un campo firma migliora il processo complessivo di firma del documento?

R: L'uso di un campo firma semplifica il processo di firma del documento, in quanto guida il firmatario ad apporre la propria firma in un'area designata, rendendo il processo di firma più organizzato e intuitivo.

#### D: Esistono limitazioni all'utilizzo dei campi firma con la firma basata su smart card?

R: Non ci sono limiti intrinseci all'utilizzo dei campi firma con la firma basata su smart card. Tuttavia, è importante assicurarsi che la posizione del campo della firma scelta non oscuri il contenuto importante del documento.

#### D: Dove posso trovare ulteriore assistenza o supporto per l'implementazione della firma basata su smart card con un campo firma?

R: Per ulteriori indicazioni e supporto, è possibile fare riferimento alla documentazione ufficiale di Aspose.PDF e ai forum della community, che offrono preziose informazioni e soluzioni per l'implementazione di firme digitali sicure.