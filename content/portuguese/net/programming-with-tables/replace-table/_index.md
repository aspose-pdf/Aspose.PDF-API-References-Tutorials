---
title: Substituir tabela em documento PDF
linktitle: Substituir tabela em documento PDF
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como substituir uma tabela em um documento PDF usando Aspose.PDF for .NET.
type: docs
weight: 180
url: /pt/net/programming-with-tables/replace-table/
---
Neste tutorial, iremos guiá-lo passo a passo para substituir uma tabela em um documento PDF usando Aspose.PDF for .NET. Explicaremos o código-fonte C# fornecido e mostraremos como implementá-lo.

## Passo 1: Carregando o documento PDF existente
Primeiro, você precisa carregar o documento PDF existente usando o seguinte código:

```csharp
// Caminho para o diretório de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Carregue o documento PDF existente
Document pdfDocument = new Document(dataDir + @"Table_input.pdf");
```

## Etapa 2: Criando o objeto TableAbsorber para localizar as tabelas
A seguir, criaremos um objeto TableAbsorber para localizar as tabelas no documento PDF:

```csharp
// Crie um objeto TableAbsorber para encontrar as tabelas
TableAbsorber absorber = new TableAbsorber();
```

## Passo 3: Visite a primeira página com o absorvedor
Visitaremos agora a primeira página do documento PDF usando o absorvedor:

```csharp
// Visite a primeira página com o absorvente
absorb.Visit(pdfDocument.Pages[1]);
```

## Etapa 4: obter a primeira tabela da página
Para poder substituir a tabela, obteremos a primeira tabela da página:

```csharp
// Obtenha a primeira tabela da página
AbsorbedTable table = absorb.TableList[0];
```

## Etapa 5: Criando uma nova tabela
Agora criaremos uma nova tabela com as colunas e células desejadas:

```csharp
Table newTable = new Table();
newTable.ColumnWidths = "100 100 100";
newTable.DefaultCellBorder = new BorderInfo(BorderSide.All, 1F);

Row row = newTable.Rows.Add();
row. Cells. Add("Col 1");
row. Cells. Add("Col 2");
row. Cells. Add("Col 3");
```

## Etapa 6: Substituindo a tabela existente pela nova tabela
Iremos agora substituir a tabela existente pela nova tabela na primeira página do documento:

```csharp
// Substitua a tabela pela nova tabela
absorb.Replace(pdfDocument.Pages[1], table, newTable);
```

## Passo 7: Salvando o documento
Finalmente, salvamos o documento PDF modificado:

```csharp
pdfDocument.Save(dataDir + "TableReplaced_out.pdf");
```

### Exemplo de código-fonte para Substituir Tabela usando Aspose.PDF para .NET

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Carregar documento PDF existente
Document pdfDocument = new Document(dataDir + @"Table_input.pdf");

// Crie o objeto TableAbsorber para encontrar tabelas
TableAbsorber absorber = new TableAbsorber();

// Visite a primeira página com absorvedor
absorber.Visit(pdfDocument.Pages[1]);

// Obtenha a primeira tabela da página
AbsorbedTable table = absorber.TableList[0];

// Criar nova tabela
Table newTable = new Table();
newTable.ColumnWidths = "100 100 100";
newTable.DefaultCellBorder = new BorderInfo(BorderSide.All, 1F);

Row row = newTable.Rows.Add();
row.Cells.Add("Col 1");
row.Cells.Add("Col 2");
row.Cells.Add("Col 3");

// Substitua a mesa por uma nova
absorber.Replace(pdfDocument.Pages[1], table, newTable);

// Salvar documento
pdfDocument.Save(dataDir + "TableReplaced_out.pdf");
```

## Conclusão
Parabéns! Agora você aprendeu como substituir uma tabela em um documento PDF usando Aspose.PDF for .NET. Este guia passo a passo mostrou como carregar o documento, localizar a tabela existente, criar uma nova tabela e substituí-la. Agora você pode aplicar esse conhecimento em seus próprios projetos.

### Perguntas frequentes sobre substituição de tabela em documento PDF

#### P: Posso substituir várias tabelas no mesmo documento PDF usando esta abordagem?

 R: Sim, você pode substituir várias tabelas no mesmo documento PDF seguindo o mesmo processo para cada tabela que deseja substituir. Depois de obter o`AbsorbedTable` objeto para cada tabela usando o`TableAbsorber` , você pode criar novas tabelas correspondentes e então usar o`absorber.Replace()` método para substituir cada tabela existente pela respectiva nova tabela.

#### P: O que acontece se a nova tabela tiver um número de colunas diferente da tabela original?

R: Se a nova tabela tiver um número de colunas diferente da tabela original, isso poderá resultar em comportamento inesperado ou problemas de layout no documento PDF modificado. É essencial garantir que a estrutura da nova tabela (número de colunas e suas larguras) corresponda à estrutura da tabela original para uma substituição perfeita.

#### P: Posso substituir uma tabela em uma página específica que não seja a primeira página?

 R: Sim, você pode substituir uma tabela em uma página específica diferente da primeira página alterando o índice da página no campo`pdfDocument.Pages[]` chamada de método ao obter o`AbsorbedTable` objeto. Por exemplo, para substituir uma tabela na segunda página, você usaria`pdfDocument.Pages[2]`.

#### P: Posso personalizar a aparência da nova tabela, como adicionar cor de fundo ou bordas?

 R: Sim, você pode personalizar a aparência da nova tabela definindo diversas propriedades da tabela.`Table` e suas células. Por exemplo, você pode definir o`BackgroundColor` propriedade das células para adicionar cor de fundo. Você também pode definir o`DefaultCellBorder` propriedade da nova tabela ou células individuais para adicionar bordas.

#### P: A substituição de uma tabela afeta o layout do conteúdo do restante do documento PDF?

R: A substituição de uma tabela poderá afetar o layout do conteúdo se o tamanho ou a estrutura da nova tabela diferir significativamente da tabela original. O restante do conteúdo da página irá refluir para acomodar a nova tabela. É essencial projetar cuidadosamente a nova tabela para que ela se encaixe perfeitamente no layout existente para evitar problemas de layout.