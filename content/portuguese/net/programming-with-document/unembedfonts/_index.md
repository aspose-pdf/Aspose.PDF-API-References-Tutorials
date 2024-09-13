---
title: Desincorpore fontes e otimize arquivos PDF
linktitle: Desincorpore fontes e otimize arquivos PDF
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda como desincorporar fontes e otimizar arquivos PDF usando o Aspose.PDF para .NET neste tutorial passo a passo.
type: docs
weight: 370
url: /pt/net/programming-with-document/unembedfonts/
---
## Introdução

Na era digital, os PDFs são onipresentes. Não importa se você está compartilhando relatórios, apresentações ou eBooks, o Portable Document Format (PDF) é a escolha certa para manter a integridade dos seus documentos. No entanto, à medida que criamos e compartilhamos mais PDFs, os tamanhos dos arquivos podem aumentar, tornando-os difíceis de enviar ou armazenar. É aqui que o Aspose.PDF para .NET entra em cena, oferecendo ferramentas poderosas para otimizar seus arquivos PDF. Neste tutorial, vamos nos aprofundar em como desincorporar fontes e otimizar arquivos PDF usando o Aspose.PDF para .NET.

## Pré-requisitos

Antes de começarmos, vamos garantir que você tenha tudo o que precisa para começar:

1. Visual Studio: Certifique-se de ter o Visual Studio instalado em sua máquina. É o IDE que usaremos para escrever e executar nosso código .NET.
2.  Aspose.PDF para .NET: Você precisará baixar e instalar a biblioteca Aspose.PDF. Você pode obtê-la do[link para download](https://releases.aspose.com/pdf/net/).
3. Conhecimento básico de C#: A familiaridade com a programação em C# ajudará você a entender os trechos de código que usaremos.
4.  Um arquivo PDF: Tenha um arquivo PDF pronto que você deseja otimizar. Você pode usar qualquer PDF, mas para demonstração, vamos nos referir a ele como`OptimizeDocument.pdf`.

## Pacotes de importação

Para começar, você precisa importar os pacotes necessários no seu projeto C#. Veja como você pode fazer isso:

1. Abra seu projeto no Visual Studio.
2. Adicione uma referência ao Aspose.PDF: clique com o botão direito do mouse no seu projeto no Solution Explorer, selecione "Gerenciar pacotes NuGet" e pesquise por`Aspose.PDF`. Instale o pacote.

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Agora que configuramos tudo, vamos dividir o processo de otimização em etapas gerenciáveis.

## Etapa 1: configure seu diretório de documentos

Primeiro, você precisa definir o caminho para o diretório dos seus documentos. É aqui que seus arquivos PDF serão armazenados. Veja como fazer isso:

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real onde seu arquivo PDF está localizado. Isso é crucial porque o programa precisa saber onde encontrar o PDF que você quer otimizar.

## Etapa 2: Abra o documento PDF

Agora que configuramos nosso diretório, é hora de abrir o documento PDF que queremos otimizar. Aqui está o código para fazer isso:

```csharp
// Abrir documento
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

 Esta linha de código cria um novo`Document` objeto, que representa seu arquivo PDF. Certifique-se de que o nome do arquivo corresponde ao que você tem em seu diretório.

## Etapa 3: Defina as opções de otimização

Em seguida, precisamos especificar as opções de otimização. Neste caso, queremos desincorporar fontes. Veja como configurar isso:

```csharp
// Definir opção UnembedFonts
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    UnembedFonts = true
};
```

 Ao definir`UnembedFonts` para`true`, estamos instruindo o Aspose.PDF a otimizar o PDF desincorporando as fontes. Isso pode reduzir significativamente o tamanho do arquivo, especialmente se o PDF contiver muitas fontes incorporadas.

## Etapa 4: Otimize o documento PDF

Com nossas opções definidas, é hora de otimizar o documento PDF. Aqui está o código para fazer isso:

```csharp
Console.WriteLine("Start");
// Otimizar documento PDF usando OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
```

Este trecho de código chama o`OptimizeResources` método sobre o`pdfDocument` objeto, aplicando as opções de otimização que definimos anteriormente. Você verá uma mensagem no console indicando que o processo de otimização foi iniciado.

## Etapa 5: Salve o documento atualizado

Após otimizar o PDF, precisamos salvar o documento atualizado. Veja como fazer isso:

```csharp
// Salvar documento atualizado
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Finished");
```

 Este código salva o PDF otimizado como`OptimizeDocument_out.pdf` no mesmo diretório. Você pode escolher um nome diferente se preferir, mas mantê-lo similar ajuda a identificar as versões original e otimizada.

## Etapa 6: Compare os tamanhos dos arquivos

Por fim, é sempre bom verificar quanto espaço você economizou. Veja como comparar os tamanhos de arquivo original e otimizado:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

Este código recupera os tamanhos de arquivo dos PDFs originais e otimizados e os imprime no console. É um momento gratificante ver o quanto você reduziu o tamanho do arquivo!

## Conclusão

aí está! Você desincorporou fontes com sucesso e otimizou um arquivo PDF usando o Aspose.PDF para .NET. Esse processo não só ajuda a reduzir o tamanho dos arquivos, mas também melhora o desempenho dos seus documentos PDF. Não importa se você está compartilhando arquivos por e-mail ou armazenando-os na nuvem, um tamanho de arquivo menor pode fazer uma grande diferença.

## Perguntas frequentes

### O que é Aspose.PDF para .NET?
Aspose.PDF para .NET é uma biblioteca poderosa que permite aos desenvolvedores criar, manipular e otimizar documentos PDF programaticamente.

### Posso usar o Aspose.PDF gratuitamente?
 Sim, o Aspose oferece uma versão de teste gratuita. Você pode baixá-lo em[aqui](https://releases.aspose.com/).

### Como obtenho suporte para o Aspose.PDF?
 Você pode obter suporte através do[Fórum Aspose](https://forum.aspose.com/c/pdf/10).

### Que tipos de otimizações posso realizar em PDFs?
Você pode desincorporar fontes, compactar imagens, remover objetos não utilizados e muito mais para otimizar seus arquivos PDF.

### Onde posso comprar o Aspose.PDF para .NET?
 Você pode comprar uma licença do[Aspose página de compra](https://purchase.aspose.com/buy).