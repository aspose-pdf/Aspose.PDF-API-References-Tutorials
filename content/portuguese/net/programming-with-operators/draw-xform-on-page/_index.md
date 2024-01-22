---
title: Desenhar XForm na página
linktitle: Desenhar XForm na página
second_title: Referência da API Aspose.PDF para .NET
description: Guia passo a passo para desenhar um formulário XForm em uma página PDF usando Aspose.PDF for .NET. Adicione e posicione o formulário na página.
type: docs
weight: 10
url: /pt/net/programming-with-operators/draw-xform-on-page/
---
Neste tutorial, forneceremos um guia passo a passo sobre como desenhar um XForm em uma página usando Aspose.PDF for .NET. Aspose.PDF é uma biblioteca poderosa que permite criar, manipular e converter documentos PDF de forma programática. Usando os operadores fornecidos pelo Aspose.PDF, você pode adicionar e posicionar um formulário XForm em uma página PDF existente.

## Pré-requisitos

Antes de começar, certifique-se de ter os seguintes pré-requisitos em vigor:

1. Visual Studio instalado com estrutura .NET.
2. A biblioteca Aspose.PDF para .NET.

## Etapa 1: configuração do projeto

Para começar, crie um novo projeto no Visual Studio e adicione uma referência à biblioteca Aspose.PDF para .NET. Você pode baixar a biblioteca do site oficial do Aspose e instalá-la em sua máquina.

## Etapa 2: importe os namespaces necessários

Em seu arquivo de código C#, importe os namespaces necessários para acessar as classes e métodos fornecidos por Aspose.PDF:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

## Etapa 3: definir caminhos de arquivo

Defina os caminhos dos arquivos para a imagem de fundo, o arquivo PDF de entrada e o arquivo PDF de saída:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string imageFile = dataDir + "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
```

Certifique-se de especificar os caminhos de arquivo reais em sua máquina.

## Passo 4: Carregando o arquivo PDF de entrada

Use o seguinte código para carregar o arquivo PDF de entrada:

```csharp
using (Document doc = new Document(inFile))
{
OperatorCollection pageContents = doc.Pages[1].Contents;
// O código a seguir usa os operadores GSave/GRestore
// O código usa o operador ContatonateMatrix para posicionar o XForm
// O código usa o operador Do para desenhar o XForm na página
// Operadores GSave/GRestore encapsulam conteúdo existente
// isso é feito para obter o estado gráfico inicial no final do conteúdo existente
// caso contrário, poderão existir transformações indesejadas no final da cadeia de operadores existentes
pageContents. Insert(1, new GSave());
pageContents. Add(new GRestore());
// Adicione o operador GSave para redefinir corretamente o estado dos gráficos após novos comandos
pageContents. Add(new GSave());

// Crie o XForm
XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
doc.Pages[1].Resources.Forms.Add(form);
form.Contents.Add(new GSave());
// Defina a largura e a altura da imagem
form.Contents.Add(new ConcatenateMatrix(200, 0, 0, 200, 0, 0));
// Carregar a imagem em um stream
Stream imageStream = new FileStream(imageFile, FileMode.Open);
// Adicione a imagem à coleção de imagens de recursos do XForm
form.Resources.Images.Add(imageStream);
XImage ximage = form.Resources.Images[form.Resources.Images.Count];
// Usando o operador Do: este operador desenha a imagem
form.Contents.Add(new Do(ximage.Name));
form.Contents.Add(new GRestore());

pageContents. Add(new GSave());
//Posicione o XForm nas coordenadas x=100 e y=500
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 500));
// Desenhe o XForm com o operador Do
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

pageContents. Add(new GSave());
// Posicione o XForm nas coordenadas x=100 e y=300
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 300));
// Desenhe o XForm com o operador Do
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

// Restaure o estado gráfico com GRestore após GSave
pageContents. Add(new GRestore());
doc.Save(outFile);
}
```

Certifique-se de especificar os caminhos reais dos arquivos e ajustar o número da página e as posições do XForm conforme necessário.

### Exemplo de código-fonte para Draw XForm On Page usando Aspose.PDF para .NET
 
```csharp

// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string imageFile = dataDir+ "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
using (Document doc = new Document(inFile))
{
	OperatorCollection pageContents = doc.Pages[1].Contents;
	// A amostra demonstra
	// Uso de operadores GSave/GRestore
	// Uso do operador ContatonateMatrix para posicionar o xForm
	// Faça uso do operador para desenhar xForm na página
	// Envolva o conteúdo existente com o par de operadores GSave/GRestore
	// isto é para obter o estado gráfico inicial no e do conteúdo existente
	// caso contrário, poderão permanecer algumas transformações indesejáveis no final da cadeia de operadores existentes
	pageContents.Insert(1, new Aspose.Pdf.Operators.GSave());
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// Adicione o operador salvar estado gráfico para limpar adequadamente o estado gráfico após novos comandos
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	#region create xForm
	// Criar xForm
	XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
	doc.Pages[1].Resources.Forms.Add(form);
	form.Contents.Add(new Aspose.Pdf.Operators.GSave());
	// Definir largura e altura da imagem
	form.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(200, 0, 0, 200, 0, 0));
	// Carregar imagem no stream
	Stream imageStream = new FileStream(imageFile, FileMode.Open);
	//Adicionar imagem à coleção de imagens dos recursos XForm
	form.Resources.Images.Add(imageStream);
	XImage ximage = form.Resources.Images[form.Resources.Images.Count];
	// Usando o operador Do: este operador desenha a imagem
	form.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
	form.Contents.Add(new Aspose.Pdf.Operators.GRestore());
	#endregion
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// Coloque o formulário nas coordenadas x=100 y=500
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 500));
	// Desenhar formulário com operador Do
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// Coloque o formulário nas coordenadas x=100 y=300
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 300));
	// Desenhar formulário com operador Do
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// Restaure o estado gráfico com GRestore após o GSave
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	doc.Save(outFile);                
}

```

## Conclusão

Neste tutorial, você aprendeu como desenhar um formulário XForm em uma página PDF usando Aspose.PDF for .NET. Seguindo os passos descritos, você poderá adicionar e posicionar um formulário XForm em uma página existente, dando assim mais flexibilidade aos seus documentos PDF.

### Perguntas frequentes para desenhar XForm na página

#### P: O que é um XForm no Aspose.PDF?

R: Um XForm é um objeto gráfico reutilizável em um documento PDF. Ele permite definir e desenhar gráficos, imagens ou textos complexos que podem ser reutilizados várias vezes em páginas diferentes.

#### P: Como importo os namespaces necessários para Aspose.PDF?

 R: Em seu arquivo de código C#, use o`using` diretiva para importar os namespaces necessários para acessar as classes e métodos fornecidos por Aspose.PDF:
```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

#### P: Qual é o propósito dos operadores GSave e GRestore?

 R: O`GSave` e`GRestore`operadores em Aspose.PDF são usados para salvar e restaurar o estado gráfico. Eles ajudam a garantir que as transformações e configurações aplicadas a uma seção do conteúdo não afetem as seções subsequentes.

#### P: Como defino um XForm usando Aspose.PDF?

 R: Para criar um XForm, use o`XForm.CreateNewForm` método e adicione-o ao`Resources.Forms` coleção de uma página específica. Você pode então adicionar conteúdo ao XForm`Contents` propriedade.

#### P: Como posso desenhar uma imagem dentro de um XForm?

 R: Carregue a imagem em um stream e adicione-a ao`Resources.Images` coleção do XForm. Use o`Do` operador dentro do XForm`Contents` para desenhar a imagem.

#### P: Como posiciono um XForm em uma página PDF?

 R: Para posicionar um XForm em uma página, use o`ConcatenateMatrix` operador dentro da página`Contents`. Ajuste os parâmetros da matriz para especificar a tradução (posição) e escala do XForm.

#### P: Posso desenhar vários XForms na mesma página?

 R: Sim, você pode desenhar vários XForms na mesma página ajustando o`ConcatenateMatrix`parâmetros para posicionar cada XForm em coordenadas diferentes.

#### P: Posso modificar o conteúdo de um XForm depois de criado?

 R: Sim, você pode modificar o conteúdo de um XForm após a criação adicionando operadores adicionais ao seu`Contents` propriedade.

#### P: O que acontece se eu omitir os operadores GSave e GRestore?

R: A omissão dos operadores GSave e GRestore pode levar à aplicação de transformações ou configurações indesejadas ao conteúdo subsequente. Usá-los ajuda a manter um estado gráfico limpo.

#### P: Posso reutilizar XForms em diferentes páginas do documento PDF?

 R: Sim, você pode reutilizar XForms em múltiplas páginas adicionando o mesmo XForm ao`Resources.Forms` coleção de páginas diferentes.

#### P: Existe um limite para o número de XForms que posso criar?

R: Embora não haja um limite estrito para o número de XForms que você pode criar, lembre-se de que muitos XForms podem afetar o desempenho e o uso de memória. Use-os criteriosamente.

#### P: Posso girar um XForm ou aplicar outras transformações?

 R: Sim, você pode usar o`ConcatenateMatrix`operador para aplicar transformações como rotação, dimensionamento e tradução a um XForm.
