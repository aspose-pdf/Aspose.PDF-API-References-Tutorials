---
title: Estilo Tabela Linha
linktitle: Estilo Tabela Linha
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda a estilizar linhas de tabela em um PDF usando o Aspose.PDF para .NET com um guia passo a passo para melhorar a formatação do seu documento com facilidade.
type: docs
weight: 180
url: /pt/net/programming-with-tagged-pdf/style-table-row/
---
## Introdução

Quando se trata de criar documentos PDF bem estruturados e lindamente formatados, o Aspose.PDF para .NET é uma solução ideal. Não importa se você está automatizando relatórios, faturas ou criando tabelas dinâmicas, formatar tabelas com vários estilos é a chave para um documento polido. Neste tutorial, vamos nos aprofundar na estilização de uma linha de tabela usando o Aspose.PDF para .NET. E não se preocupe, eu o guiarei passo a passo, assim como uma boa conversa durante o café!

## Pré-requisitos

Antes de pularmos para o âmago da questão, vamos garantir que você tenha tudo em ordem. Você vai precisar de:

1. Biblioteca Aspose.PDF para .NET  
    Se você ainda não o tem, você pode obtê-lo em[aqui](https://releases.aspose.com/pdf/net/) . Você também pode obter um[teste gratuito](https://releases.aspose.com/) para começar.
2. Ambiente de Desenvolvimento  
   Configure o Visual Studio ou qualquer IDE C# de sua escolha. Você também precisará do .NET instalado, mas imagino que já esteja familiarizado com ele.
3. Conhecimento básico de C# e .NET  
   Um bom entendimento de C# tornará este tutorial muito fácil. Mas não se preocupe, explicarei cada passo em detalhes!

## Pacotes de importação

Antes de começarmos a trabalhar com Aspose.PDF, precisamos importar os namespaces necessários. No seu projeto C#, certifique-se de incluir o seguinte:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Elas são essenciais para criar e estilizar a tabela e, claro, para trabalhar com conteúdo marcado para conformidade.

Agora vamos dividir a tarefa passo a passo, para que você possa estilizar as linhas da sua tabela como um profissional!

## Etapa 1: Crie um novo documento PDF

Primeiro as coisas mais importantes: vamos criar um documento PDF novinho em folha. Este documento conterá todas as linhas de tabela estilizadas.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Criar documento
Document document = new Document();
```

 Aqui, estamos simplesmente inicializando um novo`Document` objeto que representará nosso arquivo PDF. Certifique-se de definir o caminho do diretório onde você salvará seus arquivos de saída.

## Etapa 2: trabalhe com conteúdo marcado

Para estruturar seu PDF para acessibilidade, trabalharemos com conteúdo marcado. Isso ajuda a criar elementos estruturados como tabelas, garantindo que eles estejam em conformidade com os padrões de acessibilidade, como PDF/UA.

```csharp
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table row style");
taggedContent.SetLanguage("en-US");
```

Aqui, estamos definindo o título e o idioma para o conteúdo marcado do PDF. É como dar um nome ao seu PDF e dizer a ele qual idioma ele deve falar!

## Etapa 3: Defina a estrutura da tabela

Em seguida, vamos definir a estrutura da tabela que estamos prestes a criar. Cada tabela precisa de um cabeçalho, corpo e rodapé – muito parecido com um post de blog bem organizado!

```csharp
// Obter elemento de estrutura raiz
StructureElement rootElement = taggedContent.RootElement;

// Criar elemento de estrutura de tabela
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

O que estamos fazendo aqui é criar uma tabela com um cabeçalho (`THead`), corpo (`TBody`) e rodapé (`TFoot`). Esses elementos vão segurar nossas linhas.

## Etapa 4: adicione a linha de cabeçalho da tabela

Tabelas sem cabeçalhos são como livros sem títulos. Vamos criar a linha de cabeçalho primeiro para fornecer contexto para os dados.

```csharp
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (int colIndex = 0; colIndex < 3; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText(String.Format("Head {0}", colIndex));
}
```

Aqui, fazemos um loop e adicionamos três células de cabeçalho (`TableTHElement`), dando a cada um um texto descritivo. Simples, certo?

## Etapa 5: Adicionar linhas de corpo estilizadas

Agora vem a parte divertida – estilizar as linhas! Vamos criar sete linhas com estilos personalizados. Definiremos cores de fundo, bordas, preenchimento e alinhamento de texto.

```csharp
for (int rowIndex = 0; rowIndex < 7; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    trElement.AlternativeText = String.Format("Row {0}", rowIndex);
    trElement.BackgroundColor = Color.LightGoldenrodYellow;
    trElement.Border = new BorderInfo(BorderSide.All, 0.75F, Color.DarkGray);
    trElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.Blue);
    trElement.MinRowHeight = 100.0;
    trElement.FixedRowHeight = 120.0;
    trElement.IsInNewPage = (rowIndex % 3 == 1);
    trElement.IsRowBroken = true;

    for (int colIndex = 0; colIndex < 3; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
    }
}
```

- Cor de fundo: Usamos um amarelo dourado claro para dar um toque profissional e ao mesmo tempo acolhedor.
- Bordas: Cada linha recebe uma borda externa cinza escuro e bordas de células azuis para uma aparência mais nítida.
- Altura e preenchimento: as alturas das linhas são definidas e o preenchimento é adicionado para uma aparência limpa.
- Quebras de página: para tornar a tabela mais legível, cada segunda linha começa em uma nova página.

## Etapa 6: adicione a linha de rodapé

Assim como o cabeçalho, o rodapé ancora a tabela. Vamos criar um.

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
for (int colIndex = 0; colIndex < 3; colIndex++)
{
    TableTDElement tdElement = footTrElement.CreateTD();
    tdElement.SetText(String.Format("Foot {0}", colIndex));
}
```

Simplesmente fazemos um loop por três células de rodapé e adicionamos um pouco de texto. O texto alternativo para o rodapé é “Foot Row” para torná-lo acessível.

## Etapa 7: Salve o documento PDF

Agora que a mesa está toda arrumada, é hora de salvar sua obra-prima!

```csharp
document.Save(dataDir + "StyleTableRow.pdf");
```

assim, seu PDF será salvo com todas as lindas linhas de tabela que acabamos de estilizar.

## Etapa 8: Validar a conformidade com PDF/UA

Para garantir que nosso PDF esteja de acordo com os padrões de acessibilidade, nós o validaremos quanto à conformidade com PDF/UA.

```csharp
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));
```

Isso garante que seu PDF atenda ao padrão PDF/UA, tornando-o acessível a todos. Acessibilidade é o nome do jogo!

## Conclusão

E aí está! Com apenas algumas linhas de código, você criou uma tabela totalmente estilizada em um PDF usando o Aspose.PDF para .NET. De cabeçalhos a rodapés, estilizamos cada linha, adicionamos elementos de acessibilidade e até validamos o documento para conformidade. Não importa se você está trabalhando em relatórios corporativos, apresentações ou apenas se divertindo com PDFs, este guia tem tudo o que você precisa. Agora, vá em frente e comece a estilizar suas tabelas como um profissional!

## Perguntas frequentes

### Posso alterar também o estilo da fonte da tabela?  
 Sim! Você pode modificar o estilo da fonte usando o`TextState` objeto para cada célula, permitindo personalização completa.

### Como adiciono mais colunas à minha tabela?  
 Basta ajustar o`colCount`variável e adicione mais células nos loops para cabeçalhos, corpo e rodapés.

### O que acontece se eu não definir a altura da linha?  
Se você não definir a altura da linha, a tabela será ajustada automaticamente com base no conteúdo.

### Posso usar isso para um número dinâmico de linhas?  
Absolutamente! Você pode buscar dados de um banco de dados ou qualquer outra fonte e ajustar dinamicamente as contagens de linhas e colunas.

### O Aspose.PDF para .NET é gratuito?  
 Aspose.PDF para .NET é um produto licenciado, mas você pode experimentá-lo com um[teste gratuito](https://releases.aspose.com/) ou pegue um[licença temporária](https://purchase.aspose.com/temporary-license/).