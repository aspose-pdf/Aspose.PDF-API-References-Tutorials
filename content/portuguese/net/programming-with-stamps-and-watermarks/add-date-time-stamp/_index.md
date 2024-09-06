---
title: Adicionar carimbo de data e hora em arquivo PDF
linktitle: Adicionar carimbo de data e hora em arquivo PDF
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda como adicionar facilmente um carimbo de data e hora em um arquivo PDF com o Aspose.PDF para .NET.
type: docs
weight: 10
url: /pt/net/programming-with-stamps-and-watermarks/add-date-time-stamp/
---
Neste artigo, mostraremos passo a passo como adicionar um carimbo de data e hora em um arquivo PDF usando o Aspose.PDF para .NET. Mostraremos como usar o código-fonte C# fornecido para adicionar um carimbo de data e hora a um arquivo PDF existente.

## Requisitos

Antes de começar, certifique-se de ter o seguinte:

- Um ambiente de desenvolvimento .NET instalado.
- A biblioteca Aspose.PDF para .NET baixada e referenciada em seu projeto.

## Etapa 1: Configurando o ambiente

Antes de poder adicionar um carimbo de data e hora a um documento PDF, você precisa configurar seu ambiente de desenvolvimento. Aqui estão as etapas a seguir:

1. Abra seu IDE (Ambiente de Desenvolvimento Integrado) favorito.
2. Crie um novo projeto C#.
3. Certifique-se de ter adicionado uma referência à biblioteca Aspose.PDF para .NET.

## Etapa 2: Adicionando a biblioteca Aspose.PDF

A biblioteca Aspose.PDF para .NET é necessária para trabalhar com documentos PDF em seu projeto.

## Etapa 3: Carregando o documento PDF

O primeiro passo para adicionar um carimbo de data e hora é carregar o documento PDF existente no seu projeto. Veja como:

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Abra o documento
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

Certifique-se de substituir "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho real para o diretório onde seu documento PDF está localizado.

## Etapa 4: Criando o carimbo de data e hora

Agora que você carregou o documento

  PDF, você pode criar o carimbo de data e hora para adicionar. Veja como fazer isso:

```csharp
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt");

// Crie um buffer de texto
TextStamp textStamp = new TextStamp(annotationText);
```

O código acima cria um novo buffer de texto contendo a data e a hora atuais.

## Etapa 5: Configurando as propriedades do carimbo

Antes de adicionar o carimbo ao documento PDF, você pode configurar várias propriedades do carimbo, como margem, alinhamento horizontal e vertical, etc. Veja como:

```csharp
// Definir propriedades do buffer
textStamp.BottomMargin = 10;
textStamp. RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;
```

Você pode ajustar essas propriedades de acordo com suas necessidades.

## Etapa 6: Adicionar carimbo ao PDF

Agora que o carimbo de data e hora está pronto, você pode adicioná-lo a uma página específica do documento PDF. Veja como:

```csharp
// Adicione o selo à coleção de selos da página
pdfDocument.Pages[1].AddStamp(textStamp);
```

código acima adiciona o carimbo à primeira página do documento PDF. Você pode especificar outra página, se necessário.

## Etapa 7: Salve o documento de saída

Depois de adicionar o carimbo de data e hora, você pode salvar o documento PDF modificado. Veja como:

```csharp
// Salvar o documento de saída
pdfDocument.Save(dataDir);
```

O código acima salva o documento PDF editado no diretório especificado.

### Código-fonte de exemplo para Adicionar carimbo de data e hora usando Aspose.PDF para .NET 
```csharp

// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Abrir documento
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt ");

// Criar carimbo de texto
TextStamp textStamp = new TextStamp(annotationText);

// Definir propriedades do carimbo
textStamp.BottomMargin = 10;
textStamp.RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;

// Adicionar selo na coleção de selos
pdfDocument.Pages[1].AddStamp(textStamp);
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 6, System.Drawing.Color.Black);
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(0, 0, 0, 0), default_appearance);
textAnnotation.Name = "Stamp";
textAnnotation.Accept(new AnnotationSelector(textAnnotation));
textAnnotation.Contents = textStamp.Value;

Border border = new Border(textAnnotation);
border.Width = 0;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(0, 0, 0, 0);
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
dataDir = dataDir + "AddDateTimeStamp_out.pdf";

// Salvar documento de saída
pdfDocument.Save(dataDir);
Console.WriteLine("\nDate time stamp added successfully.\nFile saved at " + dataDir);  
          
```

## Conclusão

Parabéns! Você aprendeu como adicionar um carimbo de data e hora usando o Aspose.PDF para .NET. Agora você pode aplicar esse conhecimento aos seus próprios projetos para adicionar carimbos de data e hora a documentos PDF.

### Perguntas frequentes sobre como adicionar carimbo de data e hora em arquivo PDF

#### P: Qual é o propósito de adicionar um registro de data e hora a um documento PDF usando o Aspose.PDF para .NET?

A: Adicionar um carimbo de data e hora a um documento PDF aumenta seu valor informativo ao indicar quando o documento foi modificado ou criado. Esse recurso é útil para rastrear alterações em documentos e fornecer um ponto de referência para o histórico do documento.

#### P: Posso personalizar o formato do carimbo de data e hora para atender a requisitos específicos?

 R: Sim, você pode personalizar o formato do carimbo de data e hora de acordo com suas preferências. O código-fonte C# fornecido usa o`DateTime.Now.ToString()` método para gerar o timestamp em um formato específico. Você pode modificar este código para formatar o timestamp conforme necessário.

#### P: É possível adicionar o carimbo de data e hora a um local específico em uma página PDF?

 R: Claro, você pode ajustar o posicionamento do carimbo de data e hora na página PDF modificando as propriedades do`TextStamp` objeto. O código fornecido no tutorial demonstra como definir propriedades como margem, alinhamento e posicionamento vertical.

#### P: Posso adicionar vários carimbos de data e hora a páginas diferentes do mesmo documento PDF?

 R: Sim, você pode adicionar vários carimbos de data e hora a diferentes páginas do mesmo documento PDF. Basta repetir o processo de criação de um`TextStamp` objeto e configurando suas propriedades para cada página desejada.

#### P: Como posso alterar a fonte, o tamanho ou a cor do texto do carimbo de data e hora?

 R: Para modificar a fonte, o tamanho ou a cor do texto do carimbo de data e hora, você pode personalizar as propriedades do`DefaultAppearance` objeto usado para criar o`TextStamp`. Ajuste o nome da fonte, o tamanho e os valores de cor para obter a aparência desejada.

#### P: É possível adicionar outros tipos de anotações ou carimbos a um documento PDF usando o Aspose.PDF para .NET?

R: Sim, o Aspose.PDF para .NET fornece uma ampla variedade de tipos de anotações que você pode adicionar a documentos PDF, incluindo anotações de texto, carimbos, linhas, formas e muito mais. Você pode explorar a documentação do Aspose.PDF para obter mais detalhes sobre como trabalhar com anotações.

#### P: Há alguma limitação ou consideração ao adicionar um carimbo de data e hora a um documento PDF?

R: Embora adicionar um carimbo de data e hora seja simples, considere fatores como o layout do documento e o conteúdo existente. Certifique-se de que o posicionamento do carimbo não obscureça informações importantes ou afete a legibilidade do documento.

#### P: Como posso integrar esse método em meus próprios projetos para adicionar carimbos de data e hora a documentos PDF?

R: Para integrar esse método, siga as etapas fornecidas e ajuste o código para se adequar à estrutura do seu projeto. Você pode adicionar carimbos de data e hora a documentos PDF existentes para aumentar sua utilidade e fornecer um cronograma claro de alterações.

#### P: Posso automatizar o processo de adição de carimbos de data e hora a vários documentos PDF?

R: Sim, você pode automatizar o processo de adição de carimbos de data e hora a vários documentos PDF criando um script ou programa que itera por uma lista de documentos e aplica o mesmo processo de carimbo a cada um.