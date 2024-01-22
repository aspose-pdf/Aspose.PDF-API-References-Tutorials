---
title: Preencher o texto do traço no arquivo PDF
linktitle: Preencher o texto do traço no arquivo PDF
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como preencher e delinear facilmente texto em arquivo PDF com Aspose.PDF para .NET.
type: docs
weight: 90
url: /pt/net/programming-with-stamps-and-watermarks/fill-stroke-text/
---
Neste tutorial, mostraremos passo a passo como preencher e delinear texto em arquivo PDF usando Aspose.PDF for .NET. Mostraremos como usar o código-fonte C# fornecido para aplicar cores de preenchimento e contorno ao texto no arquivo PDF.

## Passo 1: Configurando o ambiente

Antes de começar, certifique-se de ter o seguinte:

- Um ambiente de desenvolvimento .NET instalado.
- A biblioteca Aspose.PDF para .NET baixada e referenciada em seu projeto.

## Etapa 2: Criando o objeto TextState

O primeiro passo é criar um objeto TextState para passar as propriedades avançadas. Veja como:

```csharp
// Crie o objeto TextState para transferir propriedades avançadas
TextState ts = new TextState();

// Definir cor do contorno
ts.StrokingColor = Color.Gray;

// Defina o modo de renderização de texto
ts.RenderingMode = TextRenderingMode.StrokeText;
```

O código acima cria um novo objeto TextState e define a cor do contorno, bem como a forma como o texto é renderizado.

## Passo 3: Carregando o documento PDF

Agora que o objeto TextState está pronto, podemos carregar o documento PDF onde queremos aplicar o preenchimento e contorno do texto. Veja como:

```csharp
// Carregue o documento PDF como entrada
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
```

O código acima carrega o documento PDF existente usando a classe PdfFileStamp da biblioteca Aspose.PDF.Facades.

## Etapa 4: adicionar preenchimento e traço ao texto

Agora que o documento PDF foi carregado, podemos adicionar preenchimento e contorno ao texto. Veja como:

```csharp
// Crie um carimbo (Stamp) com o texto e propriedades definidas
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

// Vincule o objeto TextState
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

O código acima cria um Carimbo com o texto especificado e propriedades de Preenchimento e Traço definidas.

## Etapa 5: salve o documento de saída

Assim que o carimbo de texto for adicionado, podemos salvar o documento PDF modificado. Veja como:

```csharp
// Salve o documento modificado
fileStamp.Save(dataDir + "output_out.pdf");
fileStamp.Close();
```

O código acima salva o documento PDF editado no diretório especificado.

### Exemplo de código-fonte para Fill Stroke Text usando Aspose.PDF para .NET 
```csharp

// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crie o objeto TextState para transferir propriedades avançadas
TextState ts = new TextState();

// Definir cor para traço
ts.StrokingColor = Color.Gray;

// Definir modo de renderização de texto
ts.RenderingMode = TextRenderingMode.StrokeText;

// Carregar um documento PDF de entrada
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

// Vincular TextState
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

Parabéns! Você aprendeu como preencher e delinear texto em um documento PDF usando Aspose.PDF for .NET. Agora você pode aplicar esse conhecimento para personalizar cores de preenchimento e contorno em seus documentos PDF.

### Perguntas frequentes sobre preenchimento de texto de traço em arquivo PDF

#### P: O que significa preencher e delinear o texto em um documento PDF e quando posso precisar fazer isso?

R: O preenchimento e o contorno do texto em um documento PDF envolvem a aplicação de cores no interior dos caracteres do texto (preenchimento) e nas bordas ao redor do texto (contorno). Isso pode ser usado para melhorar a aparência visual do texto, dar ênfase ou destacar conteúdo específico no PDF.

#### P: Como o código-fonte C# fornecido preenche e delineia o texto em um arquivo PDF?

 R: O código-fonte fornecido demonstra como criar um`TextState` objeto para definir propriedades avançadas de texto, como cor de contorno e modo de renderização. Em seguida, ele usa Aspose.PDF.Facades para carregar um documento PDF existente, criar um carimbo contendo o texto com propriedades de preenchimento e traçado especificadas e adicionar o carimbo ao documento.

####  P: Qual é o propósito do`TextState` object in the code?

 R: O`TextState` objeto é usado para definir propriedades avançadas de texto, incluindo a cor do contorno do texto (traço) e o modo de renderização. Ele permite que você personalize a aparência do texto em termos de traço e preenchimento.

#### P: Posso aplicar diferentes cores de preenchimento e contorno a diferentes partes do mesmo texto?

 R: Sim, você pode modificar o código para criar diferentes`TextState` objetos com cores distintas de preenchimento e contorno e aplique-os a partes específicas do texto usando cores separadas`Stamp` objetos.

#### P: Posso aplicar cores de preenchimento e contorno ao texto que já está presente no documento PDF?

 R: Sim, você pode usar princípios semelhantes para aplicar cores de preenchimento e contorno ao texto existente no documento PDF selecionando os objetos de texto apropriados e adicionando-os como carimbos com a cor desejada.`TextState` propriedades.

#### P: Como posso ajustar a opacidade e a mesclagem do texto preenchido e contornado?

 R: O código fornecido permite definir as propriedades de opacidade e mesclagem do carimbo usando o`Opacity` e`BlendingSpace`propriedades, respectivamente. Você pode ajustar esses valores para obter o efeito visual desejado.

#### P: Como posso aplicar diferentes cores de preenchimento e contorno a vários carimbos no mesmo documento PDF?

 R: Você pode criar vários`TextState` objetos com diferentes cores de preenchimento e contorno e, em seguida, crie objetos separados`Stamp` objetos para cada conjunto de texto com cores distintas. Adicione esses carimbos ao mesmo documento PDF usando o`PdfFileStamp` aula.

#### P: Posso usar outras fontes além da Arial para o texto contornado e preenchido?

 R: Sim, você pode alterar a fonte modificando o parâmetro do nome da fonte no campo`FormattedText` construtor ao criar o carimbo. Você pode usar qualquer fonte disponível em seu sistema.

#### P: Como posso modificar o ângulo de rotação do texto contornado e preenchido?

 R: O código fornecido permite definir o ângulo de rotação do carimbo usando o`Rotation` propriedade. Você pode ajustar esta propriedade para especificar o ângulo de rotação desejado para o texto.

#### P: Como posso controlar a posição e o tamanho do texto contornado e preenchido na página?

R: Você pode usar o`SetOrigin` método do`Stamp` objeto para definir as coordenadas X e Y da posição do carimbo na página. Além disso, você pode ajustar o tamanho da fonte no`FormattedText` construtor para controlar o tamanho do texto.