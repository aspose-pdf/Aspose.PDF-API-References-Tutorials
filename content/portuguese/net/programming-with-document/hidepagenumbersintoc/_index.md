---
title: Ocultar números de página no TOC
linktitle: Ocultar números de página no TOC
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda como ocultar números de página no Índice usando Aspose.PDF para .NET. Siga este guia detalhado com exemplos de código para criar PDFs profissionais.
type: docs
weight: 220
url: /pt/net/programming-with-document/hidepagenumbersintoc/
---
## Introdução

Ao trabalhar com PDFs, às vezes você pode querer gerar um Índice (TOC), mas manter as coisas elegantes ocultando os números de página. Talvez o documento flua melhor sem eles, ou talvez seja uma escolha estética. Seja qual for o motivo, se você estiver trabalhando com o Aspose.PDF para .NET, este tutorial mostrará exatamente como ocultar números de página no seu TOC.

## Pré-requisitos

Antes de começarmos, há algumas coisas que você precisa ter em mãos. Aqui vai uma lista de verificação rápida:

- Visual Studio instalado: você precisará de uma versão funcional do Visual Studio para codificar.
- Biblioteca Aspose.PDF para .NET: certifique-se de ter instalado a biblioteca Aspose.PDF para .NET.
  -  Link para download:[Aspose.PDF para .NET](https://releases.aspose.com/pdf/net/)
- Licença temporária: se você estiver testando os recursos, é útil ter uma licença temporária.
  -  Licença temporária:[Pegue aqui](https://purchase.aspose.com/temporary-license/)

## Pacotes de importação

Antes de pular para o código, certifique-se de importar os seguintes namespaces no seu projeto C#. Eles fornecerão as classes e métodos necessários para trabalhar com documentos PDF e criar seu Índice (TOC).

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

Agora que seu ambiente está pronto e os pacotes foram importados, vamos dividir cada etapa do processo. Cobriremos cada parte do código para garantir clareza, para que você possa acompanhar facilmente.

## Etapa 1: inicialize seu documento PDF

A primeira coisa que precisamos fazer é criar um novo documento PDF e adicionar uma página para o Índice (TOC).


```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
Page tocPage = doc.Pages.Add();
```

- dataDir: Este é o diretório onde seu arquivo de saída será salvo.
- Document(): Inicializa um novo documento PDF.
- Pages.Add(): Adiciona uma nova página em branco ao documento, que mais tarde conterá seu TOC.

## Etapa 2: Configurar informações e título do TOC

Em seguida, definiremos as informações do TOC, incluindo a definição do título que aparecerá na parte superior do TOC.

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocPage.TocInfo = tocInfo;
```

- TocInfo: Este objeto contém todas as informações sobre o TOC.
- TextFragment: representa o texto do título do TOC, aqui o definimos como "Índice".
- FontStyle: estilizamos o título do TOC definindo seu tamanho como 20 e deixando-o em negrito.
- tocPage.TocInfo: Atribuímos as informações do TOC à página que exibirá o TOC.

## Etapa 3: Ocultar números de página no TOC

Agora a parte divertida! É aqui que configuramos o TOC para ocultar os números de página.

```csharp
tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
```

-  IsShowPageNumbers: Este é o interruptor mágico que oculta os números das páginas. Defina-o como`false`, e os números das páginas não aparecerão no TOC.
- FormatArrayLength: definimos como 4, indicando que queremos definir a formatação para quatro níveis de títulos do TOC.

## Etapa 4: personalizar a formatação do TOC

Para adicionar mais estilo ao seu índice, agora definiremos a formatação para diferentes níveis de títulos.

```csharp
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
```

- FormatArray: Este array controla a formatação das entradas do TOC. Cada índice representa um nível de título diferente.
- Margem e estilo do texto: definimos margens e aplicamos estilos de fonte, como negrito, itálico e sublinhado, para cada nível de título.

## Etapa 5: Adicionar títulos ao documento

Por fim, vamos adicionar os títulos reais que farão parte do índice.

```csharp
Page page = doc.Pages.Add();
for (int Level = 1; Level != 5; Level++)
{ 
    Heading heading2 = new Heading(Level); 
    TextSegment segment2 = new TextSegment(); 
    heading2.TocPage = tocPage; 
    heading2.Segments.Add(segment2); 
    heading2.IsAutoSequence = true; 
    segment2.Text = "this is heading of level " + Level; 
    heading2.IsInList = true; 
    page.Paragraphs.Add(heading2); 
}
```

- Heading e TextSegment: Representam os títulos que aparecerão no seu TOC. Cada nível tem seu próprio título.
- IsAutoSequence: numera automaticamente os títulos.
- IsInList: garante que cada título apareça no TOC.

## Etapa 6: Salve o documento

Depois que tudo estiver definido, salve o documento PDF no arquivo de saída especificado.

```csharp
doc.Save(outFile);
```

E é isso! Você criou com sucesso um PDF com um Índice, e os números das páginas estão ocultos!

## Conclusão

Criar um Índice em um PDF e ocultar números de página pode parecer complicado, mas com o Aspose.PDF para .NET, é moleza. Seguindo este guia passo a passo, você aprendeu a personalizar o formato do TOC, ocultar números de página e aplicar estilos diferentes aos seus títulos. Agora você pode criar PDFs profissionais adaptados às suas necessidades exatas.

## Perguntas frequentes

### Posso mostrar números de página para títulos específicos no índice?
Não, o Aspose.PDF oculta ou mostra números de página para todo o TOC. Você não pode ocultá-los seletivamente para entradas específicas.

### É possível adicionar mais níveis ao TOC?
 Sim, você pode aumentar o`FormatArrayLength` para definir mais níveis de títulos do TOC.

### Como posso alterar a fonte de todas as entradas do sumário?
 Você pode alterar a fonte modificando o`TextState.Font` propriedade para cada nível no`FormatArray`.

### Posso inserir hiperlinks no TOC?
 Sim, você pode vincular cada entrada do TOC a uma seção específica do documento usando o`Heading.TocPage` propriedade.

### Preciso de uma licença para o Aspose.PDF?
Sim, uma licença válida é necessária para uso em produção. Você pode obter uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/) para testar os recursos.