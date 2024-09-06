---
title: Alinhamento de texto para conteúdo de linha de tabela
linktitle: Alinhamento de texto para conteúdo de linha de tabela
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda a alinhar o conteúdo da linha em uma tabela PDF usando o Aspose.PDF para .NET.
type: docs
weight: 210
url: /pt/net/programming-with-tables/text-alignment-for-table-row-content/
---
Neste tutorial, nós o guiaremos passo a passo para alinhar o conteúdo de uma linha em uma tabela de um documento PDF usando Aspose.PDF para .NET. Explicaremos o código-fonte C# fornecido e mostraremos como implementá-lo.

## Etapa 1: Criando o documento PDF
Primeiro, criaremos o documento PDF:

```csharp
var dataDir = "YOUR DOCUMENTS DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## Etapa 2: Inicialização da tabela
Em seguida, inicializaremos a tabela:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

## Etapa 3: Definindo a cor da borda da tabela
Vamos configurar a cor da borda da tabela:

```csharp
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## Etapa 4: Configurando a borda da célula da tabela
Vamos configurar a borda da célula da tabela:

```csharp
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## Etapa 5: Loop para adicionar 10 linhas à tabela
Agora usaremos um loop para adicionar 10 linhas à tabela:

```csharp
for (int row_count = 0; row_count < 10; row_count++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row.VerticalAlignment = VerticalAlignment.Center;

     row.Cells.Add("Column("+row_count+",1)"+DateTime.Now.Ticks);
     row.Cells.Add("Column("+row_count+",2)");
     row.Cells.Add("Column("+row_count+",3)");
}
```

## Etapa 6: Configurando o alinhamento da linha vertical
Vamos configurar o alinhamento vertical das linhas da tabela:

```csharp
row.VerticalAlignment = VerticalAlignment.Center;
```

## Etapa 7: Adicionar conteúdo às células da linha
Vamos adicionar conteúdo às células da linha:

```csharp
row.Cells.Add("Column("+row_count+",1)"+DateTime.Now.Ticks);
row.Cells.Add("Column("+row_count+",2)");
row.Cells.Add("Column("+row_count+",3)");
```

## Etapa 8: Adicionando a tabela à página do documento
Agora vamos adicionar a tabela à página do documento:

```csharp
Page tocPage = doc.Pages.Add();
tocPage.Paragraphs.Add(table);
```

## Etapa 9: Salvando o documento PDF
Por fim, salvaremos o documento PDF:

```csharp
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

### Exemplo de código-fonte para alinhamento de texto para conteúdo de linha de tabela usando Aspose.PDF para .NET

```csharp
var dataDir = "YOUR DOCUMENT DIRECTORY";

// Criar documento PDF
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// Inicializa uma nova instância da Tabela
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Defina a cor da borda da tabela como LightGray
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// definir a borda para as células da tabela
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// crie um loop para adicionar 10 linhas
for (int row_count = 0; row_count < 10; row_count++)
{
	// adicionar linha à tabela
	Aspose.Pdf.Row row = table.Rows.Add();
	row.VerticalAlignment = VerticalAlignment.Center;

	row.Cells.Add("Column (" + row_count + ", 1)" + DateTime.Now.Ticks);
	row.Cells.Add("Column (" + row_count + ", 2)");
	row.Cells.Add("Column (" + row_count + ", 3)");
}
Page tocPage = doc.Pages.Add();
// Adicionar objeto de tabela à primeira página do documento de entrada
tocPage.Paragraphs.Add(table);
// Salvar documento atualizado contendo objeto de tabela
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

## Conclusão
Parabéns! Agora você aprendeu como alinhar o conteúdo de uma linha em uma tabela em um documento PDF usando o Aspose.PDF para .NET. Este guia passo a passo mostrou como criar um documento, inicializar uma tabela, configurar borda e alinhamento, adicionar conteúdo e salvar o documento PDF. Agora você pode aplicar esse conhecimento aos seus próprios projetos.

### Perguntas frequentes

#### P: Como posso alinhar o conteúdo das células da tabela horizontalmente?

 R: Você pode alinhar o conteúdo das células da tabela horizontalmente, definindo o`HorizontalAlign` propriedade da célula`TextState` objeto. Por exemplo, para centralizar o texto, use`cell.TextState.HorizontalAlignment = HorizontalAlignment.Center` . Você também pode configurá-lo para`HorizontalAlignment.Left` ou`HorizontalAlignment.Right` para alinhamento à esquerda e à direita, respectivamente.

#### P: Posso aplicar diferentes estilos e cores de borda a células individuais dentro da tabela?

 R: Sim, você pode aplicar diferentes estilos e cores de borda a células individuais dentro da tabela. Para personalizar a borda de uma célula específica, defina o`cell.Border` propriedade para um novo`BorderInfo`objeto com as configurações desejadas, como bordas laterais, largura e cor.

#### P: Como posso ajustar o alinhamento vertical do conteúdo da tabela dentro das células?

 R: Você pode ajustar o alinhamento vertical do conteúdo da tabela dentro das células definindo o`VerticalAlignment` propriedade da linha para`VerticalAlignment.Center`, `VerticalAlignment.Top` , ou`VerticalAlignment.Bottom`. Esta propriedade controla o alinhamento vertical de todas as células naquela linha.

#### P: É possível adicionar mais colunas ou linhas à tabela dinamicamente?

 R: Sim, você pode adicionar mais colunas e linhas à tabela dinamicamente usando o`table.Rows.Add()` método para adicionar novas linhas e o`row.Cells.Add()` método para adicionar novas células às linhas. Você pode fazer isso dentro de loops ou com base em seus requisitos específicos.

#### P: Como posso definir uma cor de fundo para células específicas ou para a tabela inteira?

 R: Para definir uma cor de fundo para células específicas ou para toda a tabela, use o`BackgroundColor` propriedade do`Cell` ou`Table` objeto. Por exemplo, para definir a cor de fundo de uma célula, use`cell.BackgroundColor = Aspose.Pdf.Color.LightBlue`.