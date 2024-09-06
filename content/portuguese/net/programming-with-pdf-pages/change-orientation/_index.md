---
title: Mudar Orientação
linktitle: Mudar Orientação
second_title: Referência da API do Aspose.PDF para .NET
description: Guia passo a passo para alterar a orientação da página de um PDF com Aspose.PDF para .NET. Fácil de seguir e implementar em seus projetos.
type: docs
weight: 10
url: /pt/net/programming-with-pdf-pages/change-orientation/
---
Neste tutorial, nós o guiaremos pelo processo passo a passo para alterar a orientação da página de um documento PDF usando o Aspose.PDF para .NET. Explicaremos o código-fonte C# incluído e forneceremos um guia abrangente para ajudar você a entender e implementar esse recurso em seus próprios projetos. No final deste tutorial, você saberá como alterar a orientação da página de seus documentos PDF usando o Aspose.PDF para .NET.

## Pré-requisitos
Antes de começar, certifique-se de ter o seguinte:

- Um conhecimento básico da linguagem de programação C#
- Aspose.PDF para .NET instalado em seu ambiente de desenvolvimento

## Etapa 1: Defina o diretório do documento
Primeiro, você precisa definir o caminho para o diretório dos seus documentos. Este é o local onde seu arquivo PDF de entrada está localizado e onde você deseja salvar seu arquivo PDF de saída modificado. Substitua "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho apropriado.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Etapa 2: Carregue o documento PDF
 Em seguida, você pode carregar o documento PDF do arquivo de entrada usando o`Document` classe de Aspose.PDF. Certifique-se de especificar o caminho correto para o arquivo PDF.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Etapa 3: Alterar a orientação da página
Agora, vamos percorrer cada página do documento e alterar sua orientação. Para cada página, modificamos as dimensões da caixa de mídia (`MediaBox`) trocando a largura e a altura, então ajustamos as coordenadas da caixa de mídia para manter a posição da página. Finalmente, definimos a rotação da página para 90 graus.

```csharp
foreach(Page page in doc.Pages)
{
Aspose.Pdf.Rectangle r = page.MediaBox;
double newHeight = r.Width;
double newWidth = r.Height;
double newLLX = r.LLX;
double newLLY = r.LLY + (r.Height - newHeight);
page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page. Rotate = Rotate. on90;
}
```

## Etapa 4: Salve o documento PDF modificado
 Por fim, você pode salvar o documento PDF modificado em um arquivo de saída usando o`Save()` método do`Document`classe. Certifique-se de especificar o caminho e o nome do arquivo corretos.

```csharp
dataDir = dataDir + "ChangeOrientation_out.pdf";
doc.Save(dataDir);
```

### Exemplo de código-fonte para Change Orientation usando Aspose.PDF para .NET 

```csharp

// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
foreach (Page page in doc.Pages)
{
	Aspose.Pdf.Rectangle r = page.MediaBox;
	double newHeight = r.Width;
	double newWidth = r.Height;
	double newLLX = r.LLX;
	// Devemos mover a página para cima para compensar a alteração do tamanho da página
	// (a borda inferior da página é 0,0 e as informações geralmente são colocadas a partir do
	// Topo da página. É por isso que movemos a borda do amante para cima na diferença entre
	// Altura antiga e nova.
	double newLLY = r.LLY + (r.Height - newHeight);
	page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
	// Às vezes também precisamos definir CropBox (se foi definido no arquivo original)
	page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
	// Definindo o ângulo de rotação da página
	page.Rotate = Rotation.on90;
}
dataDir = dataDir + "ChangeOrientation_out.pdf";
// Salvar arquivo de saída
doc.Save(dataDir);
System.Console.WriteLine("\nPage orientation changed successfully.\nFile saved at " + dataDir);

```

## Conclusão
Neste tutorial, aprendemos como alterar a orientação da página de um documento PDF usando o Aspose.PDF para .NET. Seguindo os passos descritos acima, você pode implementar facilmente essa funcionalidade em seus próprios projetos. Sinta-se à vontade para explorar mais a documentação do Aspose.PDF para descobrir outros recursos úteis para trabalhar com arquivos PDF.

### Perguntas frequentes

#### P: Qual é o propósito de alterar a orientação da página em um documento PDF?

R: Alterar a orientação da página em um documento PDF permite que você gire o conteúdo da página em 90 graus. Isso pode ser útil em cenários em que o conteúdo original precisa ser exibido ou impresso em uma orientação diferente, como alternar do modo retrato para o modo paisagem ou vice-versa.

#### P: Posso alterar a orientação de páginas específicas no documento PDF?

 R: Sim, você pode alterar a orientação de páginas específicas no documento PDF. No código-fonte C# fornecido, o`foreach` loop é usado para percorrer cada página do documento e alterar sua orientação. Se você quiser alterar apenas a orientação de páginas específicas, você pode modificar o loop para direcionar essas páginas com base em seus números de página ou outros critérios.

#### P: Alterar a orientação da página afeta o layout do conteúdo na página?

R: Sim, alterar a orientação da página afetará o layout do conteúdo na página. O conteúdo será girado em 90 graus, e a largura e a altura da página serão trocadas. Como resultado, o posicionamento e o alinhamento do conteúdo na página podem mudar.

#### P: Posso girar a página em um ângulo diferente de 90 graus?

 R: No código-fonte C# fornecido, a rotação da página é definida para 90 graus usando`page.Rotate = Rotate.on90;` . No entanto, você pode alterar o ângulo de rotação para outros valores, se necessário. Por exemplo, você pode usar`Rotate.on180` para girar a página em 180 graus ou`Rotate.on270` para girá-lo em 270 graus.

#### P: Como lidar com o conteúdo da página que transborda após alterar a orientação?

R: Ao alterar a orientação da página, as dimensões da página podem mudar, o que pode resultar em estouro de conteúdo. Para lidar com isso, pode ser necessário ajustar o layout e a formatação do conteúdo na página. Você pode usar recursos fornecidos pelo Aspose.PDF para .NET, como redimensionar elementos, ajustar margens ou reorganizar conteúdo, para garantir que o conteúdo da página se ajuste corretamente após a alteração da orientação.