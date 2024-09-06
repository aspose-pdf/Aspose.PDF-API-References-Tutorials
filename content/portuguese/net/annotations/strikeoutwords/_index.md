---
title: Riscar palavras
linktitle: Riscar palavras
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda como riscar palavras em um PDF usando o Aspose.PDF para .NET com este guia passo a passo abrangente. Melhore suas habilidades de edição de documentos.
type: docs
weight: 150
url: /pt/net/annotations/strikeoutwords/
---
## Introdução

Você já se viu precisando enfatizar um texto específico em um PDF riscando-o? Não importa se você está revisando documentos, marcando texto ou simplesmente precisa destacar certas seções, riscar palavras pode ser uma ferramenta valiosa. Neste tutorial, exploraremos como fazer exatamente isso usando o Aspose.PDF para .NET. Este guia abrangente o guiará por cada etapa, garantindo que você tenha todas as informações necessárias para implementar efetivamente esse recurso em seus aplicativos .NET. 

## Pré-requisitos

Antes de começarmos a usar o código, há alguns pré-requisitos que você precisa atender para acompanhar este tutorial:

1.  Biblioteca Aspose.PDF para .NET: Certifique-se de ter a biblioteca Aspose.PDF para .NET instalada. Você pode[baixe aqui](https://releases.aspose.com/pdf/net/).

2. .NET Framework: Certifique-se de ter o .NET Framework instalado em sua máquina. Este tutorial é projetado para aplicativos .NET.

3. Ambiente de desenvolvimento: você precisará de um IDE como o Visual Studio para escrever e executar seu código.

4. Documento PDF: Tenha um arquivo PDF de amostra pronto com o qual você queira trabalhar. Este será o documento onde riscaremos o texto.

5. Conhecimento básico de C#: É necessária familiaridade com programação em C# para entender e implementar as etapas deste tutorial.

## Pacotes de importação

Antes de começarmos a codificar, precisamos importar os namespaces necessários em nosso projeto .NET. Isso nos dará acesso às classes e métodos necessários para manipular arquivos PDF usando Aspose.PDF.

```csharp
using System;
using System.IO;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
```

Esses namespaces são essenciais para trabalhar com documentos PDF, manipular texto e adicionar anotações, como tachados.

Nesta seção, dividiremos o processo de riscar palavras em um documento PDF em etapas simples e gerenciáveis. Cada etapa será acompanhada por uma explicação detalhada para garantir que você entenda como tudo funciona.

## Etapa 1: Carregue o documento PDF

O primeiro passo é carregar o documento PDF que você quer editar. Este documento será aquele em que você vai riscar palavras ou frases específicas.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Abra o documento PDF
Document document = new Document(dataDir + "input.pdf");
```

- `dataDir` : Esta variável contém o caminho para o diretório do seu documento. Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real onde seu arquivo PDF está localizado.
- `Document` : O`Document` class representa um documento PDF. Ao passar o caminho do arquivo para seu construtor, abrimos o arquivo PDF para processamento.

## Etapa 2: Crie um absorvedor de TextFragment para encontrar texto específico

 Em seguida, criaremos uma instância de`TextFragmentAbsorber` para procurar um fragmento de texto específico no documento PDF. Isso nos permite localizar o texto que queremos riscar.

```csharp
// Crie uma instância do TextFragment Absorber para pesquisar um fragmento de texto específico
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
```

- `TextFragmentAbsorber`Esta classe é usada para encontrar e trabalhar com fragmentos de texto específicos dentro do documento PDF. Neste exemplo, estamos procurando pela palavra "Estoque". Substitua "Estoque" pela palavra ou frase que você deseja encontrar no seu documento.

## Etapa 3: iterar pelas páginas do documento PDF

 Agora que temos nosso`TextFragmentAbsorber`, precisamos iterar por cada página do documento PDF para encontrar o texto especificado.

```csharp
// Iterar pelas páginas do documento PDF
for (int i = 1; i <= document.Pages.Count; i++)
{
    // Obter a página atual do documento PDF
    Page page = document.Pages[i];
    page.Accept(textFragmentAbsorber);
}
```

- `for (int i = 1; i <= document.Pages.Count; i++)`: Este loop itera por cada página do documento PDF.
- `document.Pages[i]`: Recupera a página atual que está sendo processada.
- `page.Accept(textFragmentAbsorber)` :Este método aplica o`TextFragmentAbsorber` para a página atual, procurando o texto especificado.

## Etapa 4: coletar e processar os fragmentos de texto

Depois de iterar pelas páginas, coletaremos os fragmentos de texto encontrados e os prepararemos para processamento posterior.

```csharp
// Crie uma coleção de fragmentos de texto absorvidos
Aspose.Pdf.Text.TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

- `TextFragmentCollection`Esta coleção armazena todos os fragmentos de texto que foram encontrados no documento. Usaremos esta coleção na próxima etapa para riscar o texto.

## Etapa 5: itere pelos fragmentos de texto e risque-os

Nesta etapa, percorreremos cada fragmento de texto em nossa coleção e aplicaremos uma anotação de tachado a ele.

```csharp
// Iterar sobre a coleção de fragmentos de texto
for (int j = 1; j <= textFragmentCollection.Count; j++)
{
	Aspose.Pdf.Text.TextFragment textFragment = textFragmentCollection[j];

    // Obter as dimensões retangulares do objeto TextFragment
    Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle(
        (float)textFragment.Position.XIndent,
        (float)textFragment.Position.YIndent,
        (float)textFragment.Position.XIndent + (float)textFragment.Rectangle.Width,
        (float)textFragment.Position.YIndent + (float)textFragment.Rectangle.Height);

    // Instanciar instância de anotação StrikeOut
    StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);

    // Definir propriedades da anotação de strikeout
    strikeOut.Opacity = .80f;
    strikeOut.Border = new Border(strikeOut);
    strikeOut.Color = Aspose.Pdf.Color.Red;

    // Adicione a anotação à coleção de anotações da página do fragmento de texto
    textFragment.Page.Annotations.Add(strikeOut);
}
```

- `TextFragment textFragment = textFragmentCollection[j]`: Esta linha recupera o fragmento de texto atual.
- `Aspose.Pdf.Rectangle`: Calculamos as dimensões retangulares do fragmento de texto para determinar onde aplicar o tachado.
- `StrikeOutAnnotation`: Esta classe representa a anotação strikeout. Nós a instanciamos com o retângulo calculado e a página atual.
- `strikeOut.Opacity`: Esta propriedade define a opacidade do tachado, tornando-o 80% visível.
- `strikeOut.Color`Definimos a cor do strikeout para vermelho. Você pode mudar isso para qualquer cor que preferir.
- `textFragment.Page.Annotations.Add(strikeOut)`: Isso adiciona a anotação de tachado à página.

## Etapa 6: Salve o documento PDF modificado

A etapa final é salvar o documento PDF modificado com os tachados aplicados.

```csharp
// Salvar o documento PDF atualizado
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

- `dataDir + "StrikeOutWords_out.pdf"`: Isso cria um novo nome de arquivo para o documento modificado. O arquivo original permanece inalterado.
- `document.Save(dataDir)`: Salva o documento PDF com os tachados no local especificado.

## Conclusão

Parabéns! Você riscou com sucesso palavras específicas em um documento PDF usando o Aspose.PDF para .NET. Seguindo este guia passo a passo, agora você pode personalizar documentos PDF destacando ou riscando texto, tornando-os mais dinâmicos e adaptados às suas necessidades. Quer você esteja anotando documentos legais, preparando relatórios ou apenas marcando texto para revisão, este tutorial equipou você com as habilidades para fazer isso de forma eficiente.

## Perguntas frequentes

### Posso mudar a cor do strikeout?

 Sim, você pode alterar a cor modificando o`strikeOut.Color`propriedade. Por exemplo, você pode defini-lo como`Aspose.Pdf.Color.Blue` para um strikeout azul.

### É possível riscar várias palavras de uma só vez?

 Absolutamente! O`TextFragmentAbsorber` pode ser usado para procurar qualquer palavra ou frase no documento. Você pode aplicar o strikeout a várias instâncias iterando por meio do`TextFragmentCollection`.

### E se eu quiser riscar texto apenas em páginas específicas?

 Você pode modificar o loop que itera pelas páginas para incluir somente as páginas que você deseja modificar. Por exemplo,`for (int i = 1; i <= 3; i++)` aplicaria o tachado somente às três primeiras páginas.

### Como posso ajustar a espessura da linha de tachado?

 Você pode ajustar a espessura da linha de tachado modificando o`Border` propriedade do`StrikeOutAnnotation`. Isso permite a personalização da aparência do strikeout.

### Existe uma maneira de desfazer o tachado depois de salvar o documento?

Uma vez que o documento é salvo, o strikeout é permanente. Se você precisa manter o texto original sem o strikeout, considere salvar um backup do documento original antes de aplicar quaisquer modificações.