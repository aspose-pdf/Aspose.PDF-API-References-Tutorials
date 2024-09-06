---
title: Preencher texto de traço em arquivo PDF
linktitle: Preencher texto de traço em arquivo PDF
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda a preencher e contornar facilmente o texto em um arquivo PDF com o Aspose.PDF para .NET.
type: docs
weight: 90
url: /pt/net/programming-with-stamps-and-watermarks/fill-stroke-text/
---
Neste tutorial, mostraremos passo a passo como preencher e contornar texto em arquivo PDF usando Aspose.PDF para .NET. Mostraremos como usar o código-fonte C# fornecido para aplicar cores de preenchimento e contorno ao texto no arquivo PDF.

## Etapa 1: Configurando o ambiente

Antes de começar, certifique-se de ter o seguinte:

- Um ambiente de desenvolvimento .NET instalado.
- A biblioteca Aspose.PDF para .NET baixada e referenciada em seu projeto.

## Etapa 2: Criando o objeto TextState

O primeiro passo é criar um objeto TextState para passar as propriedades avançadas. Veja como:

```csharp
// Crie um objeto TextState para transferir propriedades avançadas
TextState ts = new TextState();

// Definir cor do contorno
ts.StrokingColor = Color.Gray;

// Defina o modo de renderização de texto
ts.RenderingMode = TextRenderingMode.StrokeText;
```

O código acima cria um novo objeto TextState e define a cor do contorno e também como o texto é renderizado.

## Etapa 3: Carregando o documento PDF

Agora que o objeto TextState está pronto, podemos carregar o documento PDF onde queremos aplicar o preenchimento de texto e o contorno. Veja como:

```csharp
// Carregue o documento PDF como entrada
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
```

O código acima carrega o documento PDF existente usando a classe PdfFileStamp da biblioteca Aspose.PDF.Facades.

## Etapa 4: adicione preenchimento e traçado ao texto

Agora que o documento PDF está carregado, podemos adicionar o preenchimento e o contorno ao texto. Veja como:

```csharp
// Crie um carimbo (Stamp) com o texto e as propriedades definidas
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

// Vincular o objeto TextState
stamp.BindTextState(ts);

// Definir origem X, Y
stamp.SetOrigin(100, 100);
stamp. Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp. IsBackground = false;

// Adicione o carimbo ao documento
fileStamp.AddStamp(stamp);
```

O código acima cria um carimbo com o texto especificado e as propriedades de preenchimento e traçado definidas.

## Etapa 5: Salve o documento de saída

Depois que o carimbo de texto for adicionado, podemos salvar o documento PDF modificado. Veja como:

```csharp
// Salvar o documento modificado
fileStamp.Save(dataDir + "output_out.pdf");
fileStamp.Close();
```

O código acima salva o documento PDF editado no diretório especificado.

### Exemplo de código-fonte para preencher texto de traço usando Aspose.PDF para .NET 
```csharp

// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crie um objeto TextState para transferir propriedades avançadas
TextState ts = new TextState();

// Definir cor para traço
ts.StrokingColor = Color.Gray;

// Definir modo de renderização de texto
ts.RenderingMode = TextRenderingMode.StrokeText;

// Carregar um documento PDF de entrada
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

// Vincular estado do texto
stamp.BindTextState(ts);

// Definir origem X,Y
stamp.SetOrigin(100, 100);
stamp.Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp.IsBackground = false;

// Adicionar carimbo
fileStamp.AddStamp(stamp);
fileStamp.Save(dataDir + "ouput_out.pdf");
fileStamp.Close();

```

## Conclusão

Parabéns! Você aprendeu como preencher e contornar texto em um documento PDF usando Aspose.PDF para .NET. Agora você pode aplicar esse conhecimento para personalizar cores de preenchimento e contorno em seus documentos PDF.

### Perguntas frequentes sobre preenchimento de texto de traço em arquivo PDF

#### P: O que significa preencher e contornar o texto em um documento PDF e quando posso precisar fazer isso?

R: Preencher e delinear texto em um documento PDF envolve aplicar cores ao interior dos caracteres do texto (preenchimento) e às bordas ao redor do texto (contorno). Isso pode ser usado para melhorar a aparência visual do texto, criar ênfase ou destacar conteúdo específico dentro do PDF.

#### P: Como o código-fonte C# fornecido preenche e descreve o texto em um arquivo PDF?

 R: O código-fonte fornecido demonstra como criar um`TextState` objeto para definir propriedades de texto avançadas, como cor de contorno e modo de renderização. Ele então usa Aspose.PDF.Facades para carregar um documento PDF existente, criar um carimbo contendo o texto com propriedades de preenchimento e traço especificadas e adicionar o carimbo ao documento.

####  P: Qual é o propósito do`TextState` object in the code?

 A: O`TextState`objeto é usado para definir propriedades avançadas de texto, incluindo a cor do contorno do texto (traço) e o modo de renderização. Ele permite que você personalize como o texto aparece em termos de traço e preenchimento.

#### P: Posso aplicar cores diferentes de preenchimento e contorno a diferentes partes do mesmo texto?

 R: Sim, você pode modificar o código para criar diferentes`TextState` objetos com cores distintas de preenchimento e contorno e aplicá-los a partes específicas do texto usando`Stamp` objetos.

#### P: Posso aplicar cores de preenchimento e contorno ao texto que já está presente no documento PDF?

 R: Sim, você pode usar princípios semelhantes para aplicar cores de preenchimento e contorno ao texto existente no documento PDF selecionando os objetos de texto apropriados e adicionando-os como carimbos com o desejado`TextState` propriedades.

#### P: Como posso ajustar a opacidade e a mesclagem do texto preenchido e contornado?

 R: O código fornecido permite que você defina as propriedades de opacidade e mesclagem do carimbo usando o`Opacity` e`BlendingSpace`propriedades, respectivamente. Você pode ajustar esses valores para atingir o efeito visual desejado.

#### P: Como posso aplicar diferentes cores de preenchimento e contorno a vários carimbos no mesmo documento PDF?

 A: Você pode criar vários`TextState` objetos com diferentes cores de preenchimento e contorno e, em seguida, crie`Stamp` objetos para cada conjunto de texto com cores distintas. Adicione esses carimbos ao mesmo documento PDF usando o`PdfFileStamp` aula.

#### P: Posso usar fontes diferentes de Arial para o texto contornado e preenchido?

 R: Sim, você pode alterar a fonte modificando o parâmetro do nome da fonte no`FormattedText` construtor ao criar o carimbo. Você pode usar qualquer fonte disponível no seu sistema.

#### P: Como posso modificar o ângulo de rotação do texto contornado e preenchido?

 R: O código fornecido permite que você defina o ângulo de rotação do carimbo usando o`Rotation` propriedade. Você pode ajustar esta propriedade para especificar o ângulo de rotação desejado para o texto.

#### P: Como posso controlar a posição e o tamanho do texto contornado e preenchido na página?

 A: Você pode usar o`SetOrigin` método do`Stamp` objeto para definir as coordenadas X e Y da posição do carimbo na página. Além disso, você pode ajustar o tamanho da fonte no`FormattedText` construtor para controlar o tamanho do texto.