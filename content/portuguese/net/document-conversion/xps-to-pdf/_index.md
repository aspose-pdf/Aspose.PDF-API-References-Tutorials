---
title: XPS para PDF
linktitle: XPS para PDF
second_title: Referência da API Aspose.PDF para .NET
description: Guia passo a passo para converter arquivo XPS em PDF com Aspose.PDF para .NET.
type: docs
weight: 350
url: /pt/net/document-conversion/xps-to-pdf/
---
Neste tutorial, orientaremos você sobre como converter arquivo XPS em PDF usando a biblioteca Aspose.PDF para .NET, passo a passo. Detalharemos o código-fonte C# fornecido e mostraremos como implementá-lo em seus próprios projetos. Ao final deste tutorial, você poderá converter facilmente arquivos XPS em documentos PDF.

## Etapa 1: definir diretório de documentos
```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```
 Substituir`"YOUR DOCUMENTS DIRECTORY"` com o caminho onde você salvou seus arquivos.

## Etapa 2: instanciar o objeto LoadOptions usando opções de carregamento XPS
```csharp
Aspose.Pdf.LoadOptions options = new XpsLoadOptions();
```
Crie uma instância do objeto LoadOptions usando opções de carregamento XPS.

## Etapa 3: crie o objeto de documento
```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "XPSToPDF.xps", options);
```
Crie um objeto Document especificando o arquivo XPS de entrada e as opções de carregamento.

## Etapa 4: salve o documento PDF resultante
```csharp
document.Save(dataDir + "XPSToPDF_out.pdf");
```
Salve o documento PDF resultante no diretório especificado.

### Exemplo de código-fonte de XPS para PDF usando Aspose.PDF para .NET

```csharp
try
{
	
	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	//Instancie o objeto LoadOption usando a opção de carregamento XPS
	Aspose.Pdf.LoadOptions options = new XpsLoadOptions();

	// Criar objeto de documento
	Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "XPSToPDF.xps", options);

	// Salve o documento PDF resultante
	document.Save(dataDir + "XPSToPDF_out.pdf");
	
}
catch(Exception ex)
   
{
	Console.WriteLine(ex.Message);
}
```

## Conclusão
Neste tutorial, aprendemos como converter arquivo XPS em PDF usando a biblioteca Aspose.PDF para .NET. Seguindo as etapas fornecidas, você pode realizar essa conversão facilmente em seus próprios aplicativos. Obtenha resultados precisos e profissionais ao converter arquivos XPS em PDF.

### Perguntas frequentes

#### P: O que é XPS e por que devo convertê-lo para PDF?

R: XPS (XML Paper Specification) é um formato de documento de layout fixo desenvolvido pela Microsoft. A conversão de XPS em PDF permite tornar o documento mais acessível e amplamente compatível, já que PDF é um formato universalmente suportado em diferentes plataformas e dispositivos.

#### P: A biblioteca Aspose.PDF oferece suporte a outros formatos de arquivo além do XPS?

R: Sim, Aspose.PDF for .NET suporta vários outros formatos de arquivo para conversão, como HTML, EPUB, SVG, XML e muito mais. Também permite criar e manipular documentos PDF de forma programática.

#### P: Posso personalizar o processo de conversão de PDF, como definir o tamanho da página, margens ou outras opções?

R: Sim, você pode personalizar o processo de conversão de PDF usando Aspose.PDF para .NET. A biblioteca oferece uma ampla gama de opções para controlar o tamanho da página, margens, compactação de imagem, incorporação de fontes e outras configurações relacionadas ao PDF para atender aos seus requisitos específicos.

#### P: Existe uma versão de teste do Aspose.PDF for .NET disponível para teste?

R: Sim, você pode baixar e experimentar a versão de teste do Aspose.PDF for .NET no site oficial do Aspose. A versão de teste permite explorar os recursos da biblioteca antes de fazer uma compra.

#### P: Posso converter vários arquivos XPS em PDF em um processo em lote?

R: Sim, você pode converter vários arquivos XPS em PDF em um processo em lote, implementando um loop ou iterando a lista de arquivos XPS e convertendo cada arquivo em PDF usando o código fornecido.