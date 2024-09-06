---
title: Assinar com cartão inteligente usando assinatura de arquivo PDF
linktitle: Assinar com cartão inteligente usando assinatura de arquivo PDF
second_title: Referência da API do Aspose.PDF para .NET
description: Assine seus arquivos PDF com segurança com um cartão inteligente usando o Aspose.PDF para .NET.
type: docs
weight: 110
url: /pt/net/programming-with-security-and-signatures/sign-with-smart-card-using-pdf-file-signature/
---
A assinatura digital com um cartão inteligente é uma maneira segura de assinar arquivos PDF. Com o Aspose.PDF para .NET, você pode assinar facilmente um arquivo PDF usando um cartão inteligente seguindo o seguinte código-fonte:

## Etapa 1: Importar bibliotecas necessárias

Antes de começar, você precisa importar as bibliotecas necessárias para seu projeto C#. Aqui estão as diretivas de importação necessárias:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## Etapa 2: Defina o caminho para a pasta de documentos

 Nesta etapa, você precisa especificar o caminho para a pasta que contém o arquivo PDF que você deseja assinar. Substituir`"YOUR DOCUMENTS DIRECTORY"` no código a seguir com o caminho real para sua pasta de documentos:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Etapa 3: Carregue o documento PDF

Agora carregaremos o documento PDF a ser assinado usando o seguinte código:

```csharp
Document doc = new Document(dataDir + "blank.pdf");
```

## Etapa 4: Execute a assinatura com o cartão inteligente

 Nesta etapa, realizaremos a assinatura com o cartão inteligente utilizando o`PdfFileSignature` classe do`Facades`biblioteca. Selecionamos o certificado do cartão inteligente do armazenamento de certificados do Windows e especificamos as informações de assinatura necessárias. Aqui está o código correspondente:

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature())
{
     pdfSign.BindPdf(doc);

     // Selecione o certificado na loja
     X509Store store = new X509Store(StoreLocation.CurrentUser);
     store.Open(OpenFlags.ReadOnly);
     X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
     ExternalSignature externalSignature = new ExternalSignature(sel[0]);

     pdfSign.SignatureAppearance = dataDir + "demo.png";
     pdfSign.Sign(1, "Reason", "Contact", "Location", true, new System.Drawing.Rectangle(100, 100, 200, 200), externalSignature);
     pdfSign.Save(dataDir + "externalSignature2.pdf");
}
```

## Etapa 5: Verificar assinatura

 Por fim, verificamos a assinatura do arquivo PDF assinado usando o`PdfFileSignature` classe. Pegamos os nomes das assinaturas e os verificamos um por um. Se uma assinatura falhar na verificação, uma exceção é lançada. Aqui está o código correspondente:

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature(new Document(dataDir + "externalSignature2.pdf")))
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

### Código-fonte de exemplo para Assinar com cartão inteligente usando assinatura de arquivo PDF usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "blank.pdf");
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature())
{
	pdfSign.BindPdf(doc);
	// Assinar com seleção de certificado no armazenamento de certificados do Windows
	System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
	store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
	// Escolha manualmente o certificado na loja
	System.Security.Cryptography.X509Certificates.X509Certificate2Collection sel = System.Security.Cryptography.X509Certificates.X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, System.Security.Cryptography.X509Certificates.X509SelectionFlag.SingleSelection);
	Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0]);
	pdfSign.SignatureAppearance = dataDir + "demo.png";
	pdfSign.Sign(1, "Reason", "Contact", "Location", true, new System.Drawing.Rectangle(100, 100, 200, 200), externalSignature);
	pdfSign.Save(dataDir + "externalSignature2.pdf");
}
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature(new Document(dataDir + "externalSignature2.pdf")))
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

Parabéns! Agora você tem um guia passo a passo para assinar um arquivo PDF com um cartão inteligente usando o Aspose.PDF para .NET. Você pode usar este código para adicionar assinaturas digitais seguras aos seus documentos PDF.

Não deixe de conferir a documentação oficial do Aspose.PDF para obter mais informações sobre recursos avançados de gerenciamento de assinaturas digitais e certificados.

### Perguntas frequentes

#### P: Por que devo considerar assinar arquivos PDF com um cartão inteligente?

R: Assinar arquivos PDF com um cartão inteligente aumenta a segurança ao garantir a autenticidade e a integridade do documento. Assinaturas baseadas em cartão inteligente fornecem um nível mais alto de confiança e conformidade.

#### P: Como funciona a assinatura digital baseada em cartão inteligente?

R: A assinatura digital baseada em cartão inteligente envolve o uso de uma chave criptográfica armazenada em um cartão inteligente para criar uma assinatura digital exclusiva. Essa assinatura é anexada ao arquivo PDF, permitindo que os destinatários verifiquem a origem e a integridade do documento.

#### P: Qual é o papel do Aspose.PDF para .NET na assinatura baseada em cartão inteligente?

A: O Aspose.PDF para .NET fornece um conjunto abrangente de ferramentas e bibliotecas para facilitar a assinatura digital baseada em cartão inteligente de arquivos PDF. Ele simplifica o processo e garante a assinatura segura de documentos.

#### P: Posso escolher um certificado de cartão inteligente específico para assinatura?

R: Sim, você pode selecionar um certificado de smart card específico do Windows certificate store para assinatura. O Aspose.PDF for .NET permite que você integre perfeitamente a seleção de certificados ao seu aplicativo.

#### P: Como o código-fonte fornecido lida com assinatura baseada em cartão inteligente?

R: O código-fonte demonstra como vincular um documento PDF, selecionar um certificado de cartão inteligente, especificar informações de assinatura e criar uma assinatura digital. Ele também mostra como verificar a validade da assinatura.

#### P: Posso aplicar várias assinaturas usando cartões inteligentes em um único arquivo PDF?

R: Com certeza, você pode aplicar várias assinaturas baseadas em smart card a um único arquivo PDF. Cada assinatura é única e contribui para a segurança geral do documento.

#### P: O que acontece se uma assinatura falhar na verificação durante a etapa de verificação?

R: Se uma assinatura falhar na verificação, uma exceção será lançada, indicando que a assinatura não é válida. Isso garante que apenas assinaturas válidas e confiáveis sejam aceitas.

#### P: A assinatura baseada em cartão inteligente é compatível com todos os tipos de documentos PDF?

R: Sim, a assinatura baseada em cartão inteligente é compatível com todos os tipos de documentos PDF. Você pode aplicar assinaturas digitais a vários tipos de arquivos PDF, incluindo formulários, relatórios e muito mais.

#### P: Como posso aprender mais sobre gerenciamento avançado de assinaturas digitais e certificados?

R: Explore a documentação oficial do Aspose.PDF para obter informações detalhadas sobre recursos avançados de assinatura digital, gerenciamento de certificados e práticas recomendadas para garantir a segurança dos documentos.

#### P: Onde posso encontrar mais assistência ou suporte para implementar assinatura baseada em cartão inteligente?

R: Para obter orientação e suporte adicionais, entre em contato com os fóruns da comunidade Aspose.PDF ou consulte a documentação para obter informações abrangentes sobre assinatura baseada em cartão inteligente.