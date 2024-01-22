---
title: Substitua fontes ausentes
linktitle: Substitua fontes ausentes
second_title: Referência da API Aspose.PDF para .NET
description: Guia passo a passo para substituir fontes ausentes em um arquivo PDF usando Aspose.PDF for .NET.
type: docs
weight: 260
url: /pt/net/document-conversion/replace-missing-fonts/
---
Neste tutorial, orientaremos você no processo de substituição de fontes ausentes em um arquivo PDF usando Aspose.PDF for .NET. Quando você abre um arquivo PDF em uma máquina onde está faltando uma fonte específica, pode haver problemas de exibição da fonte. Nesses casos, é possível substituir a fonte faltante por outra disponível na máquina. Seguindo as etapas abaixo, você poderá substituir fontes ausentes em um arquivo PDF.

## Pré-requisitos
Antes de começar, certifique-se de atender aos seguintes pré-requisitos:

- Conhecimento básico da linguagem de programação C#.
- Biblioteca Aspose.PDF para .NET instalada em seu sistema.
- Um ambiente de desenvolvimento como o Visual Studio.

## Etapa 1: encontrar a fonte que falta
primeiro passo é encontrar a fonte que falta no arquivo PDF. Use o seguinte código:

```csharp
// Caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Aspose.Pdf.Text.Font originalFont = null;
try
{
     // Encontre a fonte original
     originalFont = FontRepository.FindFont("AgencyFB");
}
catch(Exception)
{
     // A fonte está faltando na máquina de destino
     // Adicionar substituição de fonte simples
     FontRepository.Substitutions.Add(new SimpleFontSubstitution("AgencyFB", "Arial"));
}
```

 Certifique-se de substituir`"YOUR DOCUMENTS DIRECTORY"` com o diretório real onde seu arquivo PDF está localizado.

## Etapa 2: Substitua a fonte ausente
A seguir, substituiremos a fonte ausente por outra fonte disponível. Use o seguinte código:

```csharp
var fileNew = new FileInfo(dataDir + "newfile_out.pdf");
var pdf = new Document(dataDir + "input.pdf");

// Converta o arquivo PDF para o formato PDF/A com remoção de erros
pdf.Convert(dataDir + "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);

// Salve o arquivo PDF resultante
pdf.Save(fileNew.FullName);
```

 Certifique-se de substituir`"input.pdf"` com o caminho real para o seu arquivo PDF original e`"newfile_out.pdf"` com o nome desejado para o arquivo PDF resultante.

## Passo 3: Salvando o arquivo PDF resultante
Finalmente, salvaremos o arquivo PDF resultante com a fonte substituída. Use o seguinte código:

```csharp
// Salve o arquivo PDF resultante
pdf.Save(fileNew.FullName);
```

Garante que você definiu o caminho de destino correto para o arquivo PDF resultante.

### Exemplo de código-fonte para substituir fontes ausentes usando Aspose.PDF para .NET

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Pdf.Text.Font originalFont = null;
try
{
	originalFont = FontRepository.FindFont("AgencyFB");
}
catch (Exception)
{
	// A fonte está faltando na máquina de destino
	FontRepository.Substitutions.Add(new SimpleFontSubstitution("AgencyFB", "Arial"));
}
var fileNew = new FileInfo(dataDir + "newfile_out.pdf");
var pdf = new Document(dataDir + "input.pdf");
pdf.Convert( dataDir +  "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);
pdf.Save(fileNew.FullName);
```

## Conclusão
Neste tutorial, cobrimos o processo passo a passo de substituição de fontes ausentes em um arquivo PDF usando Aspose.PDF for .NET. Seguindo as instruções descritas acima, você poderá substituir com êxito as fontes ausentes em seu arquivo PDF.

### Perguntas frequentes

#### P: O que é Aspose.PDF para .NET?

R: Aspose.PDF for .NET é uma biblioteca poderosa que permite aos desenvolvedores trabalhar com documentos PDF em aplicativos C#. Oferece várias funcionalidades, incluindo a capacidade de substituir fontes ausentes em arquivos PDF.

#### P: Por que eu encontraria fontes ausentes em um arquivo PDF?

R: A falta de fontes em um arquivo PDF pode ocorrer quando o arquivo é aberto em uma máquina que não possui as fontes necessárias instaladas. Isto pode levar à substituição de fontes, afetando a aparência visual do documento.

#### P: Como posso encontrar e substituir fontes ausentes em um arquivo PDF usando Aspose.PDF for .NET?

 R: Para localizar e substituir fontes ausentes, você pode usar o`FontRepository.FindFont` método para verificar a presença da fonte necessária. Se a fonte estiver faltando, você poderá adicionar uma substituição de fonte usando o`FontRepository.Substitutions` propriedade.

#### P: Posso personalizar o processo de substituição de fontes?

R: Sim, você pode personalizar o processo de substituição de fonte especificando uma fonte diferente para a substituição. No código fornecido, usamos Arial como substituto para a fonte “AgencyFB” ausente, mas você pode escolher uma fonte diferente de acordo com suas preferências.

#### P: Como posso garantir a precisão da renderização da fonte após a substituição?

R: Aspose.PDF for .NET fornece recursos robustos de manipulação de fontes, garantindo uma renderização precisa da fonte após a substituição. Você pode visualizar o arquivo PDF resultante para verificar a substituição da fonte.