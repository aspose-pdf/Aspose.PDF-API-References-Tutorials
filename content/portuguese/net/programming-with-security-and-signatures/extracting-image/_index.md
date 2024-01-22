---
title: Extraindo imagem
linktitle: Extraindo imagem
second_title: Referência da API Aspose.PDF para .NET
description: Extraia facilmente imagens de documentos PDF com Aspose.PDF for .NET.
type: docs
weight: 70
url: /pt/net/programming-with-security-and-signatures/extracting-image/
---
Extrair imagens de um documento PDF pode ser útil em muitos casos. Com Aspose.PDF for .NET, você pode extrair imagens facilmente usando o seguinte código-fonte:

## Etapa 1: importar as bibliotecas necessárias

Antes de começar, você precisa importar as bibliotecas necessárias para seu projeto C#. Aqui estão as diretivas de importação necessárias:

```csharp
using Aspose.Pdf;
using System.Drawing;
using System.Drawing.Imaging;
```

## Etapa 2: definir o caminho para a pasta de documentos

 Nesta etapa, você precisa especificar o caminho para a pasta que contém o arquivo PDF do qual deseja extrair a imagem. Substituir`"YOUR DOCUMENTS DIRECTORY"`no código a seguir com o caminho real para sua pasta de documentos:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir + @"ExtractingImage.pdf";
```

## Passo 3: Extraia a imagem do documento PDF

Agora iremos extrair a imagem do documento PDF usando o seguinte código:

```csharp
using (Document pdfDocument = new Document(input))
{
foreach(Field field in pdfDocument.Form)
{
SignatureField sf = field as SignatureField;
if (sf != null)
{
string outFile = dataDir + @"output_out.jpg";
using (Stream imageStream = sf.ExtractImage())
{
if (imageStream != null)
{
using (Image image = Bitmap.FromStream(imageStream))
{
image.Save(outFile, ImageFormat.Jpeg);
}
}
}
}
}
}
```

Neste exemplo, percorremos cada campo do formulário no documento PDF. Se for encontrado um campo de assinatura, extraímos a imagem associada e salvamos em um arquivo JPEG.

### Exemplo de código-fonte para extração de imagem usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir+ @"ExtractingImage.pdf";
using (Document pdfDocument = new Document(input))
{
	foreach (Field field in pdfDocument.Form)
	{
		SignatureField sf = field as SignatureField;
		if (sf != null)
		{
			string outFile = dataDir+ @"output_out.jpg";
			using (Stream imageStream = sf.ExtractImage())
			{
				if (imageStream != null)
				{
					using (System.Drawing.Image image = Bitmap.FromStream(imageStream))
					{
						image.Save(outFile, System.Drawing.Imaging.ImageFormat.Jpeg);
					}
				}
			}
		}
	}
}
```

## Conclusão

Parabéns! Agora você tem um guia passo a passo para extrair imagens de um documento PDF usando Aspose.PDF for .NET. Você pode integrar esse código em seus próprios projetos para extrair imagens e usá-las conforme necessário.

Certifique-se de verificar a documentação oficial do Aspose.PDF para obter mais informações sobre extração avançada de imagens e recursos de manipulação de documentos PDF.


### Perguntas frequentes

#### P: O Aspose.PDF for .NET é adequado para iniciantes?

R: Embora alguma familiaridade com a programação C# seja útil, nosso tutorial foi projetado para ser amigável para iniciantes, orientando você em cada etapa.

#### P: Posso extrair várias imagens de uma vez?

R: Absolutamente! Ao implementar loops e adaptar o código fornecido, você pode extrair várias imagens de um único documento PDF.

#### P: O Aspose.PDF for .NET é a única solução para extração de imagens?

R: Embora existam outras ferramentas disponíveis, o Aspose.PDF for .NET é conhecido por sua eficiência e recursos abrangentes.

#### P: Posso usar as imagens extraídas para fins comerciais?

R: Sim, uma vez extraídas, as imagens são suas para uso conforme necessário, inclusive para projetos comerciais.

#### P: Onde posso encontrar mais recursos sobre manipulação de PDF com Aspose.PDF?

R: Visite nossa documentação oficial para obter diversos recursos e insights sobre manipulação avançada de PDF com Aspose.PDF para .NET.