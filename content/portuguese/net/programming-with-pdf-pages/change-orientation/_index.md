---
title: Mudança de orientação
linktitle: Mudança de orientação
second_title: Referência da API Aspose.PDF para .NET
description: Guia passo a passo para alterar a orientação da página de um PDF com Aspose.PDF para .NET. Fácil de seguir e implementar em seus projetos.
type: docs
weight: 10
url: /pt/net/programming-with-pdf-pages/change-orientation/
---
Neste tutorial, orientaremos você no processo passo a passo para alterar a orientação da página de um documento PDF usando Aspose.PDF for .NET. Explicaremos o código-fonte C# incluído e forneceremos um guia completo para ajudá-lo a entender e implementar esse recurso em seus próprios projetos. Ao final deste tutorial, você saberá como alterar a orientação da página de seus documentos PDF usando Aspose.PDF for .NET.

## Pré-requisitos
Antes de começar, certifique-se de ter o seguinte:

- Conhecimento básico da linguagem de programação C#
- Aspose.PDF for .NET instalado em seu ambiente de desenvolvimento

## Passo 1: Defina o diretório do documento
Primeiro, você precisa definir o caminho para o diretório de documentos. Este é o local onde seu arquivo PDF de entrada está localizado e onde você deseja salvar o arquivo PDF de saída modificado. Substitua "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho apropriado.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passo 2: Carregue o documento PDF
 Então você pode carregar o documento PDF do arquivo de entrada usando o`Document` classe de Aspose.PDF. Certifique-se de especificar o caminho correto para o arquivo PDF.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Etapa 3: alterar a orientação da página
Agora vamos percorrer cada página do documento e mudar sua orientação. Para cada página, modificamos as dimensões da caixa de mídia (`MediaBox`) trocando a largura e a altura, ajustamos as coordenadas da caixa de mídia para manter a posição da página. Finalmente, definimos a rotação da página para 90 graus.

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

## Passo 4: Salve o documento PDF modificado
 Finalmente, você pode salvar o documento PDF modificado em um arquivo de saída usando o`Save()` método do`Document`aula. Certifique-se de especificar o caminho e o nome do arquivo corretos.

```csharp
dataDir = dataDir + "ChangeOrientation_out.pdf";
doc.Save(dataDir);
```

### Exemplo de código-fonte para orientação de mudança usando Aspose.PDF para .NET 

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
	// Devemos mover a página para cima para compensar a mudança no tamanho da página
	// (a borda inferior da página é 0,0 e as informações geralmente são colocadas a partir do
	// Inicio da página. É por isso que movemos a vantagem do amante para cima na diferença entre
	// Altura antiga e nova.
	double newLLY = r.LLY + (r.Height - newHeight);
	page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
	// Às vezes também precisamos definir CropBox (se foi definido no arquivo original)
	page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
	// Configurando o ângulo de rotação da página
	page.Rotate = Rotation.on90;
}
dataDir = dataDir + "ChangeOrientation_out.pdf";
// Salvar arquivo de saída
doc.Save(dataDir);
System.Console.WriteLine("\nPage orientation changed successfully.\nFile saved at " + dataDir);

```

## Conclusão
Neste tutorial, aprendemos como alterar a orientação da página de um documento PDF usando Aspose.PDF for .NET. Seguindo as etapas descritas acima, você pode implementar facilmente essa funcionalidade em seus próprios projetos. Sinta-se à vontade para explorar mais a documentação do Aspose.PDF para descobrir outros recursos úteis para trabalhar com arquivos PDF.

### Perguntas frequentes

#### P: Qual é o propósito de alterar a orientação da página em um documento PDF?

R: Alterar a orientação da página em um documento PDF permite girar o conteúdo da página em 90 graus. Isto pode ser útil em cenários onde o conteúdo original precisa ser exibido ou impresso em uma orientação diferente, como alternar do modo retrato para paisagem ou vice-versa.

#### P: Posso alterar a orientação de páginas específicas no documento PDF?

 R: Sim, você pode alterar a orientação de páginas específicas no documento PDF. No código-fonte C# fornecido, o`foreach` loop é usado para percorrer cada página do documento e alterar sua orientação. Se desejar alterar apenas a orientação de páginas específicas, você poderá modificar o loop para direcionar essas páginas com base em seus números de página ou outros critérios.

#### P: A alteração da orientação da página afeta o layout do conteúdo da página?

R: Sim, alterar a orientação da página afetará o layout do conteúdo da página. O conteúdo será girado 90 graus e a largura e a altura da página serão trocadas. Como resultado, o posicionamento e o alinhamento do conteúdo da página podem mudar.

#### P: Posso girar a página em um ângulo diferente de 90 graus?

 R: No código-fonte C# fornecido, a rotação da página é definida para 90 graus usando`page.Rotate = Rotate.on90;` . No entanto, você pode alterar o ângulo de rotação para outros valores, se necessário. Por exemplo, você pode usar`Rotate.on180` para girar a página em 180 graus ou`Rotate.on270` para girá-lo em 270 graus.

#### P: Como faço para lidar com o conteúdo da página que transborda após alterar a orientação?

R: Ao alterar a orientação da página, as dimensões da página podem mudar, o que pode resultar em excesso de conteúdo. Para lidar com isso, pode ser necessário ajustar o layout e a formatação do conteúdo da página. Você pode usar recursos fornecidos pelo Aspose.PDF for .NET, como redimensionar elementos, ajustar margens ou reorganizar conteúdo, para garantir que o conteúdo da página se ajuste corretamente após a mudança de orientação.