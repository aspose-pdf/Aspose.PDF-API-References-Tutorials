---
title: Adicionar carimbo de data e hora em arquivo PDF
linktitle: Adicionar carimbo de data e hora em arquivo PDF
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda como adicionar um carimbo de data e hora aos seus arquivos PDF usando o Aspose.PDF para .NET com este guia passo a passo. Perfeito para melhorar a autenticidade do documento.
type: docs
weight: 10
url: /pt/net/programming-with-stamps-and-watermarks/add-date-time-stamp/
---
## Introdução

Quando se trata de gerenciar documentos, especialmente PDFs, adicionar um carimbo de data e hora pode ser uma virada de jogo. Não importa se você está trabalhando em documentos legais, relatórios de projeto ou faturas, um carimbo de data e hora não só adiciona autenticidade, mas também fornece um registro claro de quando o documento foi criado ou modificado. Neste guia, nós o guiaremos pelo processo de adicionar um carimbo de data e hora a um arquivo PDF usando a biblioteca Aspose.PDF para .NET. 

Este artigo foi criado para ser direto e fácil de seguir, então, mesmo que você seja novo em programação ou na biblioteca Aspose.PDF, você conseguirá implementar esse recurso com confiança. Vamos lá!

## Pré-requisitos

Antes de começar, há alguns pré-requisitos que você precisa ter em mente:

1. Visual Studio: Certifique-se de ter o Visual Studio instalado na sua máquina. É aqui que você escreverá e executará seu código.
2. Aspose.PDF para .NET: Você precisa baixar e instalar a biblioteca Aspose.PDF. Você pode encontrar a versão mais recente[aqui](https://releases.aspose.com/pdf/net/).
3. Conhecimento básico de C#: A familiaridade com a programação em C# ajudará você a entender melhor os exemplos, mas não se preocupe se você estiver apenas começando; explicaremos tudo passo a passo.
4.  Um arquivo PDF: Tenha um arquivo PDF de exemplo pronto. Para nosso exemplo, usaremos um arquivo chamado`AddTextStamp.pdf`.

Depois de atender a esses pré-requisitos, você estará pronto para começar a adicionar carimbos de data e hora aos seus arquivos PDF!

## Pacotes de importação

Para começar, você precisa importar os namespaces necessários no seu projeto C#. Veja como fazer isso:

### Criar um novo projeto

1. Abra o Visual Studio: inicie seu aplicativo Visual Studio.
2. Criar um novo projeto: Selecione “Criar um novo projeto” na tela inicial.
3. Escolha o aplicativo de console: Selecione “Aplicativo de console (.NET Framework)” na lista de modelos de projeto.
4.  Dê um nome ao seu projeto: Dê um nome ao seu projeto, por exemplo,`PDFDateTimeStamp`.

### Adicionar referência Aspose.PDF

1. Clique com o botão direito do mouse em Referências: No Solution Explorer, clique com o botão direito do mouse na pasta “Referências” do seu projeto.
2. Selecione “Adicionar referência”: Escolha “Adicionar referência” no menu de contexto.
3. Procure por Aspose.PDF: Navegue até o local onde você baixou Aspose.PDF e selecione-o. Clique em “OK” para adicioná-lo ao seu projeto.

### Importar namespaces necessários

 No topo do seu`Program.cs` arquivo, você precisa importar os seguintes namespaces:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
using Aspose.Pdf.Annotations;
```

Agora que configuramos tudo, vamos dividir o processo de adicionar um carimbo de data e hora a um arquivo PDF em etapas claras e gerenciáveis.

## Etapa 1: Defina o diretório de documentos

Primeiro, você precisa especificar o diretório onde seu arquivo PDF está localizado. Isso é crucial porque o código procurará o PDF nesse diretório.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Substitua pelo seu caminho atual
```

 Certifique-se de substituir`YOUR DOCUMENT DIRECTORY` com o caminho real para seu arquivo PDF.

## Etapa 2: Abra o documento PDF

Em seguida, você abrirá o documento PDF onde deseja adicionar o carimbo de data/hora. 

```csharp
// Abrir documento
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

 Esta linha de código inicializa o`Document` classe e carrega seu arquivo PDF no`pdfDocument` objeto.

## Etapa 3: Crie o carimbo de data e hora

Agora é hora de gerar o carimbo de data e hora. Você vai formatá-lo para exibir de uma forma específica. 

```csharp
string annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt ");
```

 Aqui,`DateTime.Now` obtém a data e hora atuais e`ToString` formata-o no formato desejado.

## Etapa 4: Crie um carimbo de texto

Com a data e a hora prontas, agora você pode criar um carimbo de texto que será adicionado ao seu PDF.

```csharp
// Criar carimbo de texto
TextStamp textStamp = new TextStamp(annotationText);
```

 Esta linha cria uma nova instância de`TextStamp` usando a sequência de data e hora formatada.

## Etapa 5: Defina as propriedades do carimbo

Você pode personalizar a aparência e a posição do carimbo. Veja como definir suas propriedades:

```csharp
// Definir propriedades do carimbo
textStamp.BottomMargin = 10;
textStamp.RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;
```

Nesta etapa, definimos as margens e alinhamos o carimbo no canto inferior direito da página do PDF.

## Etapa 6: Adicione o carimbo ao PDF

Agora é hora de adicionar o carimbo de texto ao seu documento PDF. 

```csharp
// Adicionar selo na coleção de selos
pdfDocument.Pages[1].AddStamp(textStamp);
```

Esta linha adiciona o carimbo à primeira página do PDF. Você pode alterar o número da página se quiser colocá-lo em uma página diferente.

## Etapa 7: Crie uma anotação de texto livre (opcional)

Se você quiser adicionar uma anotação ao carimbo, você pode criar uma`FreeTextAnnotation` do seguinte modo:

```csharp
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 6, System.Drawing.Color.Black);
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(0, 0, 0, 0), default_appearance);
textAnnotation.Name = "Stamp";
textAnnotation.Accept(new AnnotationSelector(textAnnotation));
textAnnotation.Contents = textStamp.Value;
```

Esta etapa opcional cria uma anotação de texto livre que pode fornecer contexto ou informações adicionais sobre o selo.

## Etapa 8: Configurar a Borda de Anotação

Se você quiser personalizar a borda da sua anotação, você também pode fazer isso:

```csharp
Border border = new Border(textAnnotation);
border.Width = 0;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(0, 0, 0, 0);
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
```

Este trecho de código define a largura da borda como 0, tornando-a invisível, e adiciona a anotação ao PDF.

## Etapa 9: Salve o documento PDF

Por fim, você precisa salvar o documento PDF modificado. 

```csharp
dataDir = dataDir + "AddDateTimeStamp_out.pdf"; // Especifique o nome do arquivo de saída
pdfDocument.Save(dataDir);
Console.WriteLine("\nDate time stamp added successfully.\nFile saved at " + dataDir);
```

Esta linha salva o PDF com o timestamp adicionado em um novo arquivo. Você pode verificar seu diretório especificado para ver a saída.

## Conclusão

Parabéns! Você adicionou com sucesso um carimbo de data e hora a um arquivo PDF usando o Aspose.PDF para .NET. Esse recurso simples, mas eficaz, pode aprimorar seus documentos, tornando-os mais profissionais e fornecendo um registro claro de quando eles foram criados ou modificados. 

## Perguntas frequentes

### Posso personalizar o formato da data no registro de data e hora?
 Sim, você pode modificar o`ToString`método para alterar o formato da data de acordo com sua preferência.

### O Aspose.PDF é gratuito?
 O Aspose.PDF oferece um teste gratuito, mas para recursos completos, você precisa comprar uma licença. Você pode obter uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/).

### Posso adicionar vários carimbos de data/hora a um PDF?
 Absolutamente! Você pode criar vários`TextStamp` instâncias e adicioná-las a diferentes páginas ou posições no PDF.

### E se eu não tiver o Visual Studio?
Você pode usar qualquer IDE C# ou editor de texto, mas para executar e depurar seu projeto, o Visual Studio é recomendado.

### Onde posso encontrar mais exemplos de uso do Aspose.PDF?
 Você pode explorar mais exemplos e tutoriais no[Documentação Aspose.PDF](https://reference.aspose.com/pdf/net/).