---
title: Símbolos substituíveis no cabeçalho e rodapé
linktitle: Símbolos substituíveis no cabeçalho e rodapé
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda a usar símbolos substituíveis no cabeçalho e rodapé de um documento PDF usando o Aspose.PDF para .NET.
type: docs
weight: 320
url: /pt/net/programming-with-text/replaceable-symbols-in-header-footer/
---
## Introdução

Ao trabalhar com arquivos PDF, há momentos em que você precisa personalizar cabeçalhos e rodapés com conteúdo dinâmico, como números de página, nomes de relatórios ou datas geradas. Felizmente, o Aspose.PDF para .NET simplifica esse processo, permitindo que você crie PDFs com símbolos atualizados automaticamente em cabeçalhos e rodapés, como números de página ou detalhes de geração de relatórios. Este artigo o guiará pelo processo passo a passo de substituição de símbolos em cabeçalhos e rodapés usando o Aspose.PDF para .NET, de uma forma que não é apenas simples, mas também incrivelmente eficiente.

## Pré-requisitos

Antes de mergulhar no guia passo a passo, certifique-se de ter o seguinte:

-  Biblioteca Aspose.PDF para .NET –[Download](https://releases.aspose.com/pdf/net/) ou pegue um[teste gratuito](https://releases.aspose.com/).
- Visual Studio ou qualquer IDE C# instalado no seu sistema.
- Conhecimento básico de desenvolvimento em C# e .NET.
-  Um válido[licença](https://purchase.aspose.com/temporary-license/) para Aspose.PDF, ou você pode usar a versão de teste.

## Pacotes de importação

Para começar, você precisa importar os namespaces necessários que habilitarão a funcionalidade do Aspose.PDF para .NET. Abaixo está a importação necessária:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

Eles são essenciais para lidar com a criação de PDF, manipulação de texto e gerenciamento de cabeçalho/rodapé.

Vamos dividir o código de exemplo em etapas fáceis de entender.

## Etapa 1: Configurar o documento e a página

Primeiro, precisamos inicializar o documento e adicionar uma página a ele. Isso define a base para adicionar cabeçalhos e rodapés.

```csharp
// Configurar diretório de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Inicializar o objeto do documento
Document doc = new Document();

// Adicionar uma página ao documento
Page page = doc.Pages.Add();
```

 Aqui, estamos configurando um documento PDF usando o`Document` classe e adicionando uma página com`doc.Pages.Add()`Esta página conterá o cabeçalho, o rodapé e outros conteúdos.

## Etapa 2: Configurar margens da página

Em seguida, definiremos as margens da página para garantir que nosso conteúdo não chegue até a borda.

```csharp
// Configurar margens
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
page.PageInfo.Margin = marginInfo;
```

 Aqui, definimos as margens superior, inferior, esquerda e direita usando o`MarginInfo` classe e aplicou-a à página usando`page.PageInfo.Margin`.

## Etapa 3: Crie e configure o cabeçalho

Agora, vamos criar um cabeçalho e adicioná-lo à página. O cabeçalho incluirá o título e o nome do relatório.

```csharp
// Criar cabeçalho
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;

// Definir margens do cabeçalho
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;

// Adicionar título ao cabeçalho
TextFragment t1 = new TextFragment("report title");
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
hfFirst.Paragraphs.Add(t1);

// Adicionar nome do relatório ao cabeçalho
TextFragment t2 = new TextFragment("Report_Name");
t2.TextState.Font = FontRepository.FindFont("Arial");
t2.TextState.FontSize = 12;
t2.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
hfFirst.Paragraphs.Add(t2);
```

 Adicionamos dois`TextFragment` objetos para o cabeçalho: um para o título do relatório e outro para o nome do relatório. O texto é estilizado usando`TextState` propriedades como fonte, tamanho e alinhamento.

## Etapa 4: Crie e configure o rodapé

Agora é hora de configurar o rodapé, que conterá conteúdo dinâmico, como números de página e a data de geração.

```csharp
// Criar rodapé
HeaderFooter hfFoot = new HeaderFooter();
page.Footer = hfFoot;

// Definir margens de rodapé
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;

// Adicionar conteúdo de rodapé
TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("Report Name");
TextFragment t5 = new TextFragment("Page $p of $P");
```

No rodapé, incluímos fragmentos para a data de geração, nome do relatório e números de página dinâmicos (`$p` e`$P` representam o número da página atual e o número total de páginas, respectivamente).

## Etapa 5: Crie uma tabela no rodapé

Você também pode adicionar elementos mais complexos, como tabelas no rodapé, para organizar melhor seus dados.

```csharp
// Criar tabela para rodapé
Table tab2 = new Table();
hfFoot.Paragraphs.Add(tab2);
tab2.ColumnWidths = "165 172 165";

// Crie linhas e células para a tabela
Row row3 = tab2.Rows.Add();
row3.Cells.Add();
row3.Cells.Add();
row3.Cells.Add();

// Definir alinhamento para cada célula
row3.Cells[0].Alignment = Aspose.Pdf.HorizontalAlignment.Left;
row3.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
row3.Cells[2].Alignment = Aspose.Pdf.HorizontalAlignment.Right;

// Adicionar conteúdo às células da tabela
row3.Cells[0].Paragraphs.Add(t3);
row3.Cells[1].Paragraphs.Add(t4);
row3.Cells[2].Paragraphs.Add(t5);
```

Este bloco de código cria uma tabela de 3 colunas no rodapé, com cada coluna contendo diferentes informações, como data de geração, nome do relatório e números de página.

## Etapa 6: Adicionar conteúdo à página

Além de cabeçalhos e rodapés, você pode adicionar conteúdo ao corpo da página PDF. Aqui, adicionamos uma tabela com algum texto de espaço reservado.

```csharp
Table table = new Table();
table.ColumnWidths = "33% 33% 34%";
page.Paragraphs.Add(table);

// Adicionar conteúdo da tabela
for (int i = 0; i <= 10; i++)
{
    Row row = table.Rows.Add();
    for (int c = 0; c <= 2; c++)
    {
        Cell cell = row.Cells.Add("Content " + c);
        cell.Margin = new MarginInfo { Left = 30, Top = 10, Bottom = 10 };
    }
}
```

Este código adiciona uma tabela simples com três colunas à página. Você pode modificá-la para atender às suas necessidades específicas.

## Etapa 7: Salve o PDF

Depois que tudo estiver configurado, o último passo é salvar o documento PDF no local desejado.

```csharp
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("Symbols replaced successfully in header and footer. File saved at " + dataDir);
```

 Você especifica o caminho do arquivo e salva o documento usando`doc.Save()`. Pronto! Você criou com sucesso um PDF com cabeçalhos e rodapés personalizados.

## Conclusão

Substituir símbolos em cabeçalhos e rodapés usando o Aspose.PDF para .NET não é apenas simples, mas também poderoso. Seguindo o guia passo a passo acima, você pode personalizar facilmente seus PDFs com conteúdo dinâmico, como números de página, nomes de relatórios e datas. Este método é altamente flexível, permitindo que você insira tabelas, ajuste a formatação e controle o layout para atender às suas necessidades específicas.

## Perguntas frequentes

### Posso personalizar fontes para cabeçalhos e rodapés?  
Sim, você pode personalizar totalmente fontes, tamanhos, cores e estilos de texto em cabeçalhos e rodapés.

### Como adiciono imagens aos cabeçalhos e rodapés?  
 Você pode usar`ImageStamp` para inserir imagens em seus cabeçalhos e rodapés.

### É possível adicionar hiperlinks em cabeçalhos ou rodapés?  
 Sim, você pode usar`TextFragment` com um hiperlink definindo o`Hyperlink` propriedade.

### Posso usar cabeçalhos diferentes para páginas pares e ímpares?  
Sim, o Aspose.PDF permite que você especifique diferentes cabeçalhos e rodapés para páginas pares e ímpares.

### Como ajusto as posições do cabeçalho e do rodapé?  
Você pode ajustar as margens e as propriedades de alinhamento para controlar a posição dos seus cabeçalhos e rodapés.