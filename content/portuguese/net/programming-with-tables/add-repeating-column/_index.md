---
title: Adicionar coluna repetida em documento PDF
linktitle: Adicionar coluna repetida em documento PDF
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda como adicionar colunas repetidas a documentos PDF usando Aspose.PDF para .NET. Guia passo a passo com exemplos e código. Perfeito para desenvolvedores.
type: docs
weight: 20
url: /pt/net/programming-with-tables/add-repeating-column/
---
## Introdução

Se você estiver trabalhando com documentos PDF e precisar adicionar colunas repetidas, você está no lugar certo! Usando o Aspose.PDF para .NET, você pode gerenciar facilmente tabelas e conteúdo dentro de um PDF. Não importa se você está criando relatórios dinâmicos, faturas ou qualquer outro documento estruturado, as colunas repetidas podem ser um divisor de águas na organização de dados. Vamos mergulhar em um guia passo a passo sobre como adicionar colunas repetidas a um documento PDF.

## Pré-requisitos

Antes de começarmos o código, vamos garantir que você tenha tudo configurado:

- Aspose.PDF para .NET: você precisa ter a biblioteca Aspose.PDF para .NET instalada no seu projeto.
- [Baixe Aspose.PDF para .NET](https://releases.aspose.com/pdf/net/)
- [Teste grátis](https://releases.aspose.com/)
- Ambiente de desenvolvimento: certifique-se de ter um IDE compatível com .NET, como o Visual Studio, instalado.
- Noções básicas de C#: Embora vamos detalhar tudo, uma compreensão básica de C# ajudará você a acompanhar sem problemas.
  
 Se você ainda não tem o Aspose.PDF para .NET, você pode obter um[licença temporária](https://purchase.aspose.com/temporary-license/) para começar a explorar seus recursos.

## Pacotes de importação

Para começar, você precisa importar os namespaces necessários do Aspose.PDF para .NET. Veja como fazer isso:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

Esses pacotes fornecem as classes e os métodos essenciais necessários para trabalhar com documentos PDF e manipular tabelas.

Agora, vamos dividir o processo em várias etapas para adicionar colunas repetidas a um documento PDF. Acompanhe!

## Etapa 1: Defina o caminho para o diretório de documentos

Antes de criar ou manipular quaisquer arquivos, precisamos definir o caminho onde o PDF gerado será salvo. No seu projeto C#, defina o caminho do diretório onde seus arquivos serão localizados:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddRepeatingColumn_out.pdf";
```

 Este caminho aponta para o diretório onde o PDF de saída será salvo. Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real na sua máquina.

## Etapa 2: Crie um novo documento PDF

 Para começar, instancie um novo`Document` objeto. Isso servirá como contêiner para todas as páginas e conteúdo dentro do PDF.

```csharp
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

 Aqui, criamos um novo documento PDF e adicionamos uma página em branco a ele. O`doc.Pages.Add()` O método insere uma nova página no documento.

## Etapa 3: Instanciar a tabela externa

Em seguida, criamos uma tabela externa. Essa tabela abrangerá toda a largura da página e servirá como um contêiner para outras tabelas, incluindo a que conterá as colunas repetidas.

```csharp
Aspose.Pdf.Table outerTable = new Aspose.Pdf.Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;
```

 Nós definimos o`ColumnWidths` propriedade para "100%", o que significa que a tabela se estenderá por toda a largura da página.

## Etapa 4: Crie a tabela interna

 Agora, vamos criar a tabela interna, que terá colunas repetidas. As principais propriedades aqui são`Broken` , o que permite que a tabela continue na mesma página, e`ColumnAdjustment`, que ajusta automaticamente as larguras das colunas para caber no conteúdo.

```csharp
Aspose.Pdf.Table mytable = new Aspose.Pdf.Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;
```

Esta tabela interna será aninhada dentro da tabela externa.

## Etapa 5: Adicionar tabelas à página

Agora que temos as tabelas externa e interna prontas, vamos adicioná-las à página. Este passo garante que as tabelas sejam incluídas na estrutura do documento.

```csharp
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
```

 Aqui, adicionamos o`outerTable` para a página e, em seguida, dentro da tabela externa, aninhamos o`mytable` . Além disso, definimos`RepeatingColumnsCount`para 5, especificando quantas colunas devem ser repetidas quando os dados são adicionados.

## Etapa 6: Adicionar linha de cabeçalho

Agora é hora de adicionar os cabeçalhos à tabela. A linha de cabeçalho fornece contexto aos dados e ajuda a estruturar as colunas. 

```csharp
Aspose.Pdf.Row row = mytable.Rows.Add();
row.Cells.Add("header 1");
row.Cells.Add("header 2");
row.Cells.Add("header 3");
row.Cells.Add("header 4");
row.Cells.Add("header 5");
row.Cells.Add("header 6");
row.Cells.Add("header 7");
row.Cells.Add("header 11");
row.Cells.Add("header 12");
row.Cells.Add("header 13");
row.Cells.Add("header 14");
row.Cells.Add("header 15");
row.Cells.Add("header 16");
row.Cells.Add("header 17");
```

Este trecho de código adiciona a primeira linha (que usaremos como cabeçalhos) e a preenche com células contendo texto como “cabeçalho 1”, “cabeçalho 2” e assim por diante.

## Etapa 7: Adicionar linhas de dados

Finalmente, podemos adicionar alguns dados à tabela. Este loop cria linhas dinamicamente e preenche as células com conteúdo:

```csharp
for (int RowCounter = 0; RowCounter <= 5; RowCounter++)
{
    Aspose.Pdf.Row row1 = mytable.Rows.Add();
    row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 4");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 5");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 6");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 7");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 11");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 12");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 13");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 14");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 15");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 16");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 17");
}
```

O loop itera seis vezes, adicionando linhas e preenchendo cada célula com dados de coluna correspondentes (por exemplo, “col 1, 1”, “col 2, 2”, etc.).

## Etapa 8: Salve o documento

Depois que todas as linhas e colunas forem adicionadas, o último passo é salvar o documento no caminho de arquivo especificado.

```csharp
doc.Save(outFile);
```

Seu documento agora está salvo com colunas repetidas!

## Conclusão

Aí está! Com essas etapas simples, você pode criar um documento PDF com colunas repetidas usando o Aspose.PDF para .NET. Aproveitando a flexibilidade das tabelas aninhadas, você pode obter layouts complexos que fazem seus PDFs parecerem profissionais e organizados. Experimente isso em seu próximo projeto e explore todo o potencial do Aspose.PDF para lidar com suas necessidades de geração de PDF.

## Perguntas frequentes

### O que é Aspose.PDF para .NET?
Aspose.PDF para .NET é uma biblioteca poderosa que permite aos desenvolvedores criar, editar e gerenciar documentos PDF programaticamente.

### Posso ajustar o número de colunas repetidas dinamicamente?
 Sim, você pode alterar o número de colunas repetidas modificando o`RepeatingColumnsCount` propriedade.

### Como posso aplicar uma licença do Aspose.PDF para .NET?
 Você pode aplicar uma licença de um arquivo ou fluxo seguindo o[documentação](https://reference.aspose.com/pdf/net/).

### É possível adicionar imagens às células da tabela?
Sim, o Aspose.PDF para .NET suporta adicionar vários tipos de conteúdo, incluindo imagens, às células da tabela.

### Posso personalizar ainda mais o layout da tabela?
Absolutamente! O Aspose.PDF fornece recursos extensivos para personalizar estilos de tabela, incluindo bordas, preenchimento, alinhamento e muito mais.