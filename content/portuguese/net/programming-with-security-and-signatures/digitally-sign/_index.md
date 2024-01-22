---
title: Arquivo PDF de login digital
linktitle: Arquivo PDF de login digital
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como assinar digitalmente um arquivo PDF com Aspose.PDF para .NET.
type: docs
weight: 40
url: /pt/net/programming-with-security-and-signatures/digitally-sign/
---
Neste tutorial, orientaremos você no processo de assinatura digital em arquivo PDF usando Aspose.PDF for .NET. A assinatura digital garante a autenticidade e integridade do documento, ao adicionar uma impressão digital eletrónica única.

## Etapa 1: Pré-requisitos

Antes de começar, certifique-se de ter os seguintes pré-requisitos:

- Conhecimento básico da linguagem de programação C#
- Instalando o Visual Studio em sua máquina
- Biblioteca Aspose.PDF para .NET instalada

## Etapa 2: configuração do ambiente

Para começar, siga estas etapas para configurar seu ambiente de desenvolvimento:

1. Abra o Visual Studio e crie um novo projeto C#.
2. Importe os namespaces necessários para o seu arquivo de código:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Collections.Generic;
```

## Etapa 3: assinatura digital

O primeiro passo é assinar digitalmente o arquivo PDF. O código fornecido mostra como fazer uma assinatura digital com Aspose.PDF for .NET.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pbxFile = "";
string inFile = dataDir + @"DigitallySign.pdf";
string outFile = dataDir + @"DigitallySign_out.pdf";
using (Document document = new Document(inFile))
{
     using (PdfFileSignature signature = new PdfFileSignature(document))
     {
         PKCS7 pkcs = new PKCS7(pbxFile, "WebSales");
         DocMDPSignature docMdpSignature = new DocMDPSignature(pkcs, DocMDPAccessPermissions.FillingInForms);
         System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
         signature.SignatureAppearance = dataDir + @"aspose-logo.jpg";
         signature.Certify(1, "Reason for signing", "Contact", "Location", true, rect, docMdpSignature);
         signature.Save(outFile);
     }
}
```

Este código carrega um arquivo PDF, cria uma assinatura digital com uma aparência especificada e salva o arquivo PDF com a assinatura adicionada.

## Etapa 4: verificação de assinatura

Após adicionar a assinatura digital, você pode verificar se o arquivo PDF contém uma assinatura válida.

```csharp
using(Document document = new Document(outFile))
{
     using (PdfFileSignature signature = new PdfFileSignature(document))
     {
         IList<string> sigNames = signature. GetSignNames();
         if (sigNames.Count > 0)
         {
             if (signature.VerifySigned(sigNames[0] as string))
             {
                 if (signature.IsCertified)
                 {
                     if (signature.GetAccessPermissions() == DocMDPAccessPermissions.FillingInForms)
                     {
                         // Faça alguma coisa
                     }
                 }
             }
         }
     }
}
```

Este código verifica a primeira assinatura do arquivo PDF e executa ações adicionais se a assinatura for certificada e tiver permissões específicas.

### Exemplo de código-fonte para assinatura digital usando Aspose.PDF para .NET 
```csharp
try
{
	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENTS DIRECTORY";
	string pbxFile = "";
	string inFile = dataDir + @"DigitallySign.pdf";
	string outFile = dataDir + @"DigitallySign_out.pdf";
	using (Document document = new Document(inFile))
	{
		using (PdfFileSignature signature = new PdfFileSignature(document))
		{
			PKCS7 pkcs = new PKCS7(pbxFile, "WebSales"); // Usar objetos PKCS7/PKCS7Detached
			DocMDPSignature docMdpSignature = new DocMDPSignature(pkcs, DocMDPAccessPermissions.FillingInForms);
			System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
			// Definir aparência de assinatura
			signature.SignatureAppearance = dataDir + @"aspose-logo.jpg";
			// Crie qualquer um dos três tipos de assinatura
			signature.Certify(1, "Signature Reason", "Contact", "Location", true, rect, docMdpSignature);
			// Salvar arquivo PDF de saída
			signature.Save(outFile);
		}
	}
	using (Document document = new Document(outFile))
	{
		using (PdfFileSignature signature = new PdfFileSignature(document))
		{
			IList<string> sigNames = signature.GetSignNames();
			if (sigNames.Count > 0) // Alguma assinatura?
			{
				if (signature.VerifySigned(sigNames[0] as string)) // Verifique o primeiro
				{
					if (signature.IsCertified) // Certificado?
					{
						if (signature.GetAccessPermissions() == DocMDPAccessPermissions.FillingInForms) // Obtenha permissão de acesso
						{
							// Faça alguma coisa
						}
					}
				}
			}
		}
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusão

Parabéns! Você executou com sucesso uma assinatura digital em um arquivo PDF usando Aspose.PDF for .NET. Este tutorial abordou o processo passo a passo, desde a adição da assinatura digital até a verificação de sua validade. Agora você pode usar esse recurso para proteger seus arquivos PDF com assinaturas digitais.

### Perguntas frequentes

#### P: Qual é o objetivo deste tutorial?

R: Este tutorial orienta você no processo de assinatura digital de um arquivo PDF usando Aspose.PDF for .NET. As assinaturas digitais adicionam uma impressão digital eletrônica para garantir a autenticidade e integridade do documento.

#### P: Quais pré-requisitos são necessários antes de começar?

R: Antes de começar, certifique-se de ter um conhecimento básico da linguagem de programação C#, de ter o Visual Studio instalado e de ter a biblioteca Aspose.PDF para .NET instalada.

#### P: Como configuro o ambiente de desenvolvimento?

R: Siga as etapas fornecidas para configurar seu ambiente de desenvolvimento, incluindo a criação de um novo projeto C# no Visual Studio e a importação dos namespaces necessários.

#### P: Como adiciono uma assinatura digital a um arquivo PDF?

 R: O código de exemplo fornecido demonstra como carregar um arquivo PDF, criar uma assinatura digital, especificar a aparência e salvar o arquivo PDF assinado. A assinatura digital é adicionada usando o`Certify` método do`PdfFileSignature` objeto.

#### P: Como posso verificar a validade de uma assinatura digital?

R: Depois de adicionar a assinatura digital, você pode usar o código de exemplo para verificar a validade da assinatura. Verifica se a assinatura está certificada e possui permissões de acesso específicas.

####  P: O que o`PKCS7` object represent?

 R: O`PKCS7` objeto é usado para fornecer a funcionalidade criptográfica para assinaturas digitais. É usado para criar a assinatura digital no código de exemplo fornecido.

#### P: Posso personalizar a aparência da assinatura digital?

 R: Sim, você pode personalizar a aparência da assinatura digital especificando o caminho para uma imagem no campo`SignatureAppearance` propriedade do`PdfFileSignature` objeto.

#### P: O que acontece se a assinatura não for válida?

R: Se a assinatura não for válida, o processo de verificação falhará e as ações correspondentes dentro do bloco de código de verificação não serão executadas.

#### P: Como posso garantir a segurança das minhas assinaturas digitais?

R: As assinaturas digitais são seguras por design e usam técnicas criptográficas para garantir autenticidade e integridade. Certifique-se de manter sua chave privada segura e seguir as práticas recomendadas para lidar com assinaturas digitais.

#### P: Posso adicionar várias assinaturas digitais a um PDF?

 R: Sim, você pode adicionar várias assinaturas digitais a um arquivo PDF usando o`PdfFileSignature` objeto`Sign` ou`Certify` métodos. Cada assinatura terá sua própria aparência e configuração.