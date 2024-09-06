---
title: Assinar com cartão inteligente usando o campo de assinatura
linktitle: Assinar com cartão inteligente usando o campo de assinatura
second_title: Referência da API do Aspose.PDF para .NET
description: Assine seus arquivos PDF com segurança com um cartão inteligente usando o Aspose.PDF para .NET.
type: docs
weight: 120
url: /pt/net/programming-with-security-and-signatures/sign-with-smart-card-using-signature-field/
---
A assinatura digital com um cartão inteligente é uma maneira segura de assinar arquivos PDF. Com o Aspose.PDF para .NET, você pode assinar facilmente um arquivo PDF usando um campo de assinatura e um cartão inteligente seguindo o seguinte código-fonte:

## Etapa 1: Importar bibliotecas necessárias

Antes de começar, você precisa importar as bibliotecas necessárias para seu projeto C#. Aqui estão as diretivas de importação necessárias:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## Etapa 2: Defina o caminho para a pasta de documentos

 Nesta etapa, você precisa especificar o caminho para a pasta que contém o arquivo PDF que você deseja assinar. Substituir`"YOUR DOCUMENTS DIRECTORY"` no código a seguir com o caminho real para sua pasta de documentos:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Etapa 3: Copie e abra o documento PDF

Agora copiaremos e abriremos o documento PDF a ser assinado usando o seguinte código:

```csharp
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);

using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
     using (Document doc = new Document(fs))
     {
         // Crie um campo de assinatura
         SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));

         // Selecione o certificado na loja
         X509Store store = new X509Store(StoreLocation.CurrentUser);
         store.Open(OpenFlags.ReadOnly);
         X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
        
         // Crie uma assinatura externa com as informações necessárias
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

## Etapa 4: Verificar assinatura

 Por fim, verificamos a assinatura do arquivo PDF assinado usando o`PdfFileSignature` classe. Pegamos os nomes das assinaturas e os verificamos um por um. Se uma assinatura falhar na verificação, uma exceção é lançada. Aqui está o código correspondente:

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

### Código-fonte de exemplo para Sign With Smart Card Using Signature Field usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);
using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
	using (Document doc = new Document(fs))
	{
		SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));
		// Assinar com seleção de certificado no armazenamento de certificados do Windows
		System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
		store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
		// Escolha manualmente o certificado na loja
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

## Conclusão

Parabéns! Agora você tem um guia passo a passo para assinar um arquivo PDF com um cartão inteligente usando um campo de assinatura com Aspose.PDF para .NET. Você pode usar este código para adicionar assinaturas digitais seguras aos seus documentos PDF.

Não deixe de conferir a documentação oficial do Aspose.PDF para obter mais informações sobre recursos avançados de gerenciamento de assinaturas digitais e certificados.

### Perguntas frequentes

#### P: Qual é o benefício de usar um campo de assinatura para assinatura digital com um cartão inteligente?

R: Usar um campo de assinatura para assinatura digital com um cartão inteligente fornece uma área designada dentro do PDF onde a assinatura é aplicada. Isso melhora a clareza do documento e garante a autenticidade da assinatura.

#### P: Como a biblioteca Aspose.PDF para .NET facilita a assinatura digital baseada em cartão inteligente com um campo de assinatura?

R: O Aspose.PDF para .NET simplifica o processo de criação de um campo de assinatura, seleção de um certificado de cartão inteligente e aplicação de uma assinatura digital a uma área específica dentro do documento PDF.

#### P: Por que selecionar um certificado específico é importante para assinatura baseada em cartão inteligente?

R: Selecionar um certificado específico permite que você identifique exclusivamente o signatário e garanta a integridade da assinatura. Isso ajuda a estabelecer confiança e conformidade com os padrões de assinatura digital.

#### P: Como o código-fonte fornecido lida com o processo de assinatura baseado em cartão inteligente com um campo de assinatura?

R: O código-fonte demonstra como criar um campo de assinatura, selecionar um certificado de cartão inteligente e aplicar uma assinatura digital com informações de assinatura específicas. Ele também mostra como verificar a validade da assinatura.

#### P: Posso personalizar a aparência do campo de assinatura?

R: Sim, você pode personalizar a aparência do campo de assinatura, como tamanho, posição e representação visual, para alinhá-lo ao layout do seu documento.

#### P: O que acontece se uma assinatura falhar na verificação durante a etapa de verificação?

R: Se uma assinatura falhar na verificação, uma exceção será lançada, indicando que a assinatura não é válida. Isso garante que apenas assinaturas válidas e confiáveis sejam aceitas.

#### P: Posso aplicar vários campos de assinatura e assinaturas baseadas em cartão inteligente a um único documento PDF?

R: Claro, você pode aplicar vários campos de assinatura e assinaturas baseadas em cartão inteligente a diferentes áreas do mesmo documento PDF, fornecendo várias camadas de segurança.

#### P: Como o uso de um campo de assinatura melhora o processo geral de assinatura de documentos?

R: Usar um campo de assinatura simplifica o processo de assinatura do documento, pois orienta o signatário a colocar sua assinatura em uma área designada, tornando o processo de assinatura mais organizado e fácil de usar.

#### P: Há alguma limitação no uso de campos de assinatura com assinatura baseada em cartão inteligente?

R: Não há limitações inerentes ao uso de campos de assinatura com assinatura baseada em cartão inteligente. No entanto, é importante garantir que o local do campo de assinatura escolhido não obscureça conteúdo importante do documento.

#### P: Onde posso encontrar mais assistência ou suporte para implementar assinatura baseada em cartão inteligente com um campo de assinatura?

R: Para obter orientação e suporte adicionais, você pode consultar a documentação oficial do Aspose.PDF e os fóruns da comunidade, que oferecem insights e soluções valiosas para implementar assinaturas digitais seguras.