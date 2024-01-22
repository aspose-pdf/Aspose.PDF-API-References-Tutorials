---
title: Carimbos de número de página em arquivo PDF
linktitle: Carimbos de número de página em arquivo PDF
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como adicionar carimbos de número de página em arquivo PDF com Aspose.PDF para .NET.
type: docs
weight: 160
url: /pt/net/programming-with-stamps-and-watermarks/page-number-stamps/
---
Neste tutorial, iremos guiá-lo passo a passo sobre como adicionar carimbos de número de página em arquivo PDF usando Aspose.PDF for .NET. Usaremos o código-fonte C# fornecido para abrir um documento PDF existente, criar um carimbo de número de página, definir suas propriedades e adicioná-lo a uma página específica no arquivo PDF.

## Passo 1: Configurando o ambiente

Antes de começar, certifique-se de ter o seguinte:

- Um ambiente de desenvolvimento .NET instalado.
- A biblioteca Aspose.PDF para .NET baixada e referenciada em seu projeto.

## Passo 2: Carregando o documento PDF existente

O primeiro passo é carregar o documento PDF existente em seu projeto. Veja como:

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Abra o documento PDF existente
Document pdfDocument = new Document(dataDir + "PageNumberStamp.pdf");
```

Certifique-se de substituir "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho real para o diretório onde seu documento PDF está localizado.

## Etapa 3: Criando e configurando o carimbo de numeração de página

Agora que o documento PDF foi carregado, podemos criar um buffer de numeração de páginas e configurá-lo de acordo com nossas necessidades. Veja como:

```csharp
// Crie um buffer de número de página
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// Defina se o buffer está em segundo plano ou não
pageNumberStamp.Background = false;

// Formato do buffer de numeração de páginas
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;

// Margem inferior do buffer de numeração de páginas
pageNumberStamp.BottomMargin = 10;

// Alinhamento horizontal do buffer de numeração de páginas
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;

// Número inicial da numeração de páginas
pageNumberStamp.StartingNumber = 1;

// Definir propriedades de texto do buffer de número de página
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;
```

código acima cria um carimbo de número de página com propriedades como formato de número de página, margem inferior, alinhamento horizontal, número inicial e propriedades de texto.

## Etapa 4: adicionar o carimbo do número da página a uma página específica

Depois que o carimbo do número da página estiver configurado, podemos adicioná-lo a uma página específica do documento PDF. Veja como:

```csharp
// Adicione o buffer de número de página a uma página específica
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
```

O código acima adiciona o carimbo do número da página à primeira página do documento PDF. Você pode alterar o número da página conforme necessário.

## Passo 5: Salvando o documento PDF modificado

Depois que o carimbo do número da página for adicionado ao documento PDF, podemos salvar o documento PDF modificado. Veja como:

```csharp
// Salve o documento PDF modificado
pdfDocument.Save(dataDir + "PageNumberStamp_out.pdf");
```

Certifique-se de substituir "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho real para o diretório onde deseja salvar o documento PDF editado.

### Exemplo de código-fonte para carimbos de número de página usando Aspose.PDF para .NET 
```csharp

// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Abrir documento
Document pdfDocument = new Document(dataDir+ "PageNumberStamp.pdf");

// Criar carimbo de número de página
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// Se o carimbo é de fundo
pageNumberStamp.Background = false;
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;
pageNumberStamp.BottomMargin = 10;
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;
pageNumberStamp.StartingNumber = 1;

// Definir propriedades de texto
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;

// Adicionar carimbo a uma página específica
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
dataDir = dataDir + "PageNumberStamp_out.pdf";

// Salvar documento de saída
pdfDocument.Save(dataDir);
Console.WriteLine("\nPage number stamp added successfully.\nFile saved at " + dataDir);

```

## Conclusão

Parabéns! Você aprendeu como adicionar carimbos de número de página a um documento PDF usando Aspose.PDF for .NET. Agora você pode personalizar seus documentos PDF adicionando números de página claros e informativos.

### Perguntas frequentes sobre carimbos de número de página em arquivo PDF

#### P: O que é um carimbo de número de página e como ele é usado para adicionar números de página a um arquivo PDF?

R: Um carimbo de número de página é um recurso do Aspose.PDF que permite adicionar números de página dinâmicos a páginas específicas de um documento PDF. Neste tutorial, isso é feito criando um objeto PageNumberStamp, configurando suas propriedades e adicionando-o a uma página designada.

#### P: Como o código-fonte C# fornecido consegue adicionar carimbos de número de página a um arquivo PDF?

R: O código demonstra como carregar um documento PDF existente, criar um PageNumberStamp, definir várias propriedades (como formato, fonte, alinhamento, etc.) e, em seguida, adicionar o carimbo a uma página específica. O carimbo calcula automaticamente a contagem total de páginas e insere os números de páginas corretos.

#### P: Posso personalizar a aparência do número da página, como estilo, cor e tamanho da fonte?

R: Com certeza, você pode personalizar a aparência do carimbo do número da página ajustando propriedades como fonte, tamanho da fonte, estilo da fonte (negrito, itálico, etc.) e cor do texto.

#### P: É possível adicionar carimbos de número de página a várias páginas de um documento PDF?

R: Sim, você pode adicionar carimbos de número de página a várias páginas criando vários objetos PageNumberStamp e adicionando cada um deles às páginas desejadas.

#### P: Posso escolher se o carimbo do número da página aparece como parte do conteúdo da página ou como elemento de fundo?

 R: Sim, você pode controlar se o carimbo do número da página aparece como parte do conteúdo da página ou como elemento de fundo definindo a opção`Background` propriedade do PageNumberStamp.

#### P: Como especifico o formato do número da página, incluindo a contagem total de páginas?

 R: O código usa o`Format`propriedade do PageNumberStamp para especificar o formato do número da página. A macro "# of" é usada para representar a contagem total de páginas.

#### P: O que acontece se eu adicionar o mesmo carimbo de número de página a várias páginas?

R: Adicionar a mesma instância PageNumberStamp a várias páginas exibirá os números de página corretos para cada página. O carimbo ajusta automaticamente o número da página e a contagem total de páginas.

#### P: Posso adicionar carimbos de número de página às seções de cabeçalho ou rodapé de um documento PDF?

R: Embora PageNumberStamps normalmente sejam adicionados diretamente ao conteúdo da página, você pode usar FloatingBox ou outras técnicas para posicioná-los nas seções de cabeçalho ou rodapé.

#### P: Como especifico a posição do carimbo do número da página na página?

 R: O`BottomMargin` e`HorizontalAlignment` As propriedades do PageNumberStamp permitem controlar a posição do carimbo na página.

#### P: E se eu quiser iniciar a numeração de páginas com um número diferente em vez de 1?

 R: Você pode definir o`StartingNumber`propriedade do PageNumberStamp para especificar o número da página inicial.