---
title: Assinar digitalmente com carimbo de data/hora em arquivo PDF
linktitle: Assinar digitalmente com carimbo de data/hora em arquivo PDF
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como realizar uma assinatura digital com carimbo de data/hora em arquivo PDF usando Aspose.PDF for .NET.
type: docs
weight: 50
url: /pt/net/programming-with-security-and-signatures/digitally-sign-with-time-stamp/
---
Neste tutorial, orientaremos você no processo de assinatura digital em arquivo PDF com carimbo de data e hora usando Aspose.PDF for .NET. A assinatura digital com carimbo temporal garante a autenticidade e integridade do documento, ao adicionar uma impressão digital eletrónica com carimbo temporal.

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
```

## Etapa 3: Assinatura digital com carimbo de data/hora

primeiro passo é realizar a assinatura digital com carimbo de data e hora no arquivo PDF. O código fornecido mostra como conseguir essa assinatura com Aspose.PDF for .NET.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pfxFile = "";
using (Document document = new Document(dataDir + @"DigitallySign.pdf"))
{
     using (PdfFileSignature signature = new PdfFileSignature(document))
     {
         PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
         TimestampSettings timestampSettings = new TimestampSettings("https:\\your_timestamp_settings", "user:password");
         pkcs. TimestampSettings = timestampSettings;
         System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
         signature.Sign(1, "Reason for signing", "Contact", "Location", true, rect, pkcs);
         signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
     }
}
```

Este código carrega um arquivo PDF, cria uma assinatura digital com carimbo de data/hora usando um arquivo PFX (chave privada) e os parâmetros de carimbo de data/hora especificados. A assinatura é então adicionada ao arquivo PDF e salva com o sufixo "_fora".

### Exemplo de código-fonte para assinatura digital com carimbo de data/hora usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pfxFile = "";
using (Document document = new Document(dataDir + @"DigitallySign.pdf"))
{
	using (PdfFileSignature signature = new PdfFileSignature(document))
	{
		PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
		TimestampSettings timestampSettings = new TimestampSettings("https:\\your_timestamp_settings", "user:password"); // Usuário/Senha pode ser omitido
		pkcs.TimestampSettings = timestampSettings;
		System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
		// Crie qualquer um dos três tipos de assinatura
		signature.Sign(1, "Signature Reason", "Contact", "Location", true, rect, pkcs);
		// Salvar arquivo PDF de saída
		signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
	}
}
```

## Conclusão

Parabéns! Você executou com sucesso uma assinatura digital com carimbo de data/hora em um arquivo PDF usando Aspose.PDF for .NET. Este tutorial abordou o processo passo a passo, desde a criação da assinatura até o salvamento do arquivo PDF atualizado. Agora você pode usar esse recurso para adicionar assinaturas digitais com carimbo de data/hora aos seus arquivos PDF.

### Perguntas frequentes sobre assinatura digital com carimbo de data/hora em arquivo PDF

#### P: Qual é o propósito da assinatura digital com carimbo de data/hora?

R: A assinatura digital com carimbo de data e hora adiciona uma impressão digital eletrônica com carimbo de data e hora a um arquivo PDF, garantindo a autenticidade e integridade do documento em um momento específico.

#### P: Quais pré-requisitos são necessários para iniciar este tutorial?

R: Antes de começar, certifique-se de ter um conhecimento básico da linguagem de programação C#, de ter o Visual Studio instalado e de ter a biblioteca Aspose.PDF para .NET instalada.

#### P: Como posso configurar meu ambiente de desenvolvimento?

R: Siga as etapas fornecidas para configurar seu ambiente de desenvolvimento, incluindo a criação de um novo projeto C# no Visual Studio e a importação dos namespaces necessários.

#### P: Como adiciono uma assinatura digital com carimbo de data/hora a um PDF?

R: O código de exemplo fornecido demonstra como carregar um arquivo PDF, criar uma assinatura digital com carimbo de data/hora usando um arquivo PFX (chave privada) e configurações de carimbo de data/hora especificadas, adicionar a assinatura ao arquivo PDF e salvar o arquivo atualizado.

#### P: O que é um arquivo PFX e por que ele é usado no exemplo?

R: Um arquivo PFX (Personal Exchange Format) contém uma chave privada e um certificado. É usado aqui para fornecer funcionalidade criptográfica para assinaturas digitais. Certifique-se de substituir o espaço reservado pelo seu arquivo PFX e senha.

#### P: O que são configurações de carimbo de data/hora?

R: TimestampSettings define as configurações do servidor de carimbo de data/hora usado para adicionar o carimbo de data/hora eletrônico à assinatura. Inclui o URL do servidor de carimbo de data/hora e credenciais de usuário opcionais.

#### P: Posso usar um servidor de carimbo de data/hora diferente do exemplo?
 R: Sim, você pode usar qualquer servidor de carimbo de data/hora compatível. Substitua o URL e, se necessário, forneça as credenciais de usuário apropriadas no campo`TimestampSettings` objeto.

#### P: Qual é o propósito de especificar o retângulo de assinatura?

R: O retângulo da assinatura define a posição e as dimensões da aparência da assinatura digital na página PDF. Ajuste esses valores para posicionar a assinatura conforme desejado.

#### P: O que acontece se o servidor de carimbo de data/hora estiver indisponível durante a assinatura?

R: Se o servidor de carimbo de data/hora não estiver disponível durante a assinatura, o processo poderá falhar ou demorar mais. Certifique-se de que seu servidor de carimbo de data/hora seja confiável e acessível.

#### P: Como posso verificar a presença de um carimbo de data/hora no PDF assinado?

 R: Você pode examinar o PDF assinado usando o código de exemplo fornecido. O`TimestampSettings` que você usou durante a assinatura deve estar disponível nos detalhes da assinatura.

#### P: As assinaturas digitais com carimbos de data e hora são juridicamente vinculativas?

R: As assinaturas digitais com carimbos de data e hora têm valor legal em muitas jurisdições e são frequentemente consideradas mais confiáveis do que simples assinaturas digitais. Consulte especialistas jurídicos em sua jurisdição para regulamentações específicas.

#### P: Posso adicionar várias assinaturas digitais com carimbos de data e hora a um PDF?

R: Sim, você pode adicionar várias assinaturas digitais com carimbos de data e hora a um arquivo PDF chamando o processo de criação de assinatura várias vezes. Cada assinatura terá seu próprio carimbo de data/hora.