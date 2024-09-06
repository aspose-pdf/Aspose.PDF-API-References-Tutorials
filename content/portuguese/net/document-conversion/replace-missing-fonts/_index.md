---
title: Substituir fontes ausentes
linktitle: Substituir fontes ausentes
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda como substituir fontes ausentes em documentos PDF usando o Aspose.PDF para .NET com este guia passo a passo.
type: docs
weight: 260
url: /pt/net/document-conversion/replace-missing-fonts/
---
## Introdução

Você já abriu um documento PDF apenas para descobrir que algumas fontes estavam faltando? Pode ser frustrante, certo? Fontes faltantes podem levar a um documento que parece completamente diferente do que o criador pretendia. Felizmente, com o Aspose.PDF para .NET, você pode facilmente substituir fontes faltantes e garantir que seus documentos PDF mantenham a aparência pretendida. Neste tutorial, nós o guiaremos pelo processo passo a passo, tornando-o simples e direto.

## Pré-requisitos

Antes de começar, há algumas coisas que você precisa ter em mãos:

1.  Aspose.PDF para .NET: Certifique-se de ter a biblioteca Aspose.PDF instalada. Você pode baixá-la de[aqui](https://releases.aspose.com/pdf/net/).
2. Visual Studio: um ambiente de desenvolvimento onde você pode escrever e testar seu código.
3. Conhecimento básico de C#: A familiaridade com a programação em C# ajudará você a entender melhor os trechos de código.

## Pacotes de importação

Para começar, você precisará importar os pacotes necessários no seu projeto C#. Veja como você pode fazer isso:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Etapa 1: configure seu diretório de documentos

Primeiro, você precisa especificar o caminho para o diretório dos seus documentos. É aqui que seu arquivo PDF de entrada está localizado e onde o arquivo de saída será salvo.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Etapa 2: inicializar a fonte original

Em seguida, você vai querer tentar encontrar a fonte original que pode estar faltando. Neste caso, estamos procurando por "AgencyFB".

```csharp
Aspose.Pdf.Text.Font originalFont = null;
try
{
    originalFont = FontRepository.FindFont("AgencyFB");
}
catch (Exception)
{
    // fonte está faltando na máquina de destino
    FontRepository.Substitutions.Add(new SimpleFontSubstitution("AgencyFB", "Arial"));
}
```

Aqui, tentamos encontrar a fonte. Se não for encontrada, capturamos a exceção e a substituímos por uma fonte mais comum, "Arial". Isso garante que seu documento ainda tenha uma boa aparência, mesmo que a fonte original não esteja disponível.

## Etapa 3: Carregue o documento PDF

Agora, vamos carregar o documento PDF que você quer processar. Você precisará especificar o caminho do arquivo de entrada.

```csharp
var fileNew = new FileInfo(dataDir + "newfile_out.pdf");
var pdf = new Document(dataDir + "input.pdf");
```

 Nesta etapa, criamos um novo`FileInfo` objeto para o arquivo de saída e carregar o documento PDF de entrada em um novo`Document` objeto.

## Etapa 4: converter o documento PDF

Antes de salvar o documento, é uma boa ideia convertê-lo para um formato PDF específico. Neste caso, nós o converteremos para o formato PDF/A-1B, que é um padrão para arquivamento de longo prazo de documentos eletrônicos.

```csharp
pdf.Convert(dataDir + "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);
```

Esta linha converte o PDF e registra quaisquer erros em um arquivo XML especificado. Se houver algum problema durante a conversão, eles serão registrados em "log.xml".

## Etapa 5: Salve o documento PDF atualizado

Por fim, é hora de salvar o documento PDF atualizado com as fontes substituídas.

```csharp
pdf.Save(fileNew.FullName);
```

Esta linha salva o PDF modificado no caminho de arquivo de saída especificado. E assim, você substituiu com sucesso as fontes ausentes no seu documento PDF!

## Conclusão

Substituir fontes ausentes em documentos PDF não precisa ser uma tarefa assustadora. Com o Aspose.PDF para .NET, você pode gerenciar facilmente as substituições de fontes e garantir que seus documentos tenham a aparência que deveriam. Seguindo as etapas descritas neste tutorial, você pode manter a integridade dos seus arquivos PDF, mesmo quando certas fontes não estiverem disponíveis. Então, da próxima vez que você encontrar um problema de fonte ausente, você saberá exatamente o que fazer!

## Perguntas frequentes

### O que é Aspose.PDF para .NET?
Aspose.PDF para .NET é uma biblioteca poderosa que permite aos desenvolvedores criar, manipular e converter documentos PDF programaticamente.

### Posso usar o Aspose.PDF gratuitamente?
 Sim, o Aspose oferece uma versão de teste gratuita que você pode usar para avaliar a biblioteca. Você pode baixá-la[aqui](https://releases.aspose.com/).

### O que devo fazer se a fonte que preciso não estiver disponível?
Você pode substituir a fonte ausente por uma mais comum usando o recurso de substituição de fonte no Aspose.PDF.

### É possível converter PDFs para outros formatos?
Absolutamente! O Aspose.PDF suporta conversão para vários formatos, incluindo PDF/A, DOCX e mais.

### Onde posso encontrar suporte para o Aspose.PDF?
 Você pode encontrar suporte e fazer perguntas no fórum Aspose[aqui](https://forum.aspose.com/c/pdf/10).