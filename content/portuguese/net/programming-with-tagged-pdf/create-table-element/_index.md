---
title: Criar elemento de tabela
linktitle: Criar elemento de tabela
second_title: Referência da API do Aspose.PDF para .NET
description: Guia passo a passo para criar um elemento de array com Aspose.PDF para .NET. Gere PDFs dinâmicos com tabelas facilmente.
type: docs
weight: 80
url: /pt/net/programming-with-tagged-pdf/create-table-element/
---
## Introdução

Você já se perguntou como pode criar e personalizar elementos de tabela sem esforço em um PDF usando .NET? Bem, o Aspose.PDF para .NET é a sua solução ideal! Quer você esteja automatizando a geração de relatórios ou criando tabelas dinamicamente para vários documentos, o Aspose.PDF fornece uma API avançada para trabalhar com elementos de tabela. Este guia o guiará passo a passo sobre como criar uma tabela, estilizá-la e até mesmo garantir que ela atenda aos padrões de conformidade do PDF/UA. Parece emocionante, certo? Vamos direto ao assunto!

## Pré-requisitos

Antes de começar, você precisará de algumas coisas:
1.  Aspose.PDF para .NET: Baixe a versão mais recente em[Aspose.PDF para .NET Baixar](https://releases.aspose.com/pdf/net/).
2. Ambiente de desenvolvimento: qualquer IDE compatível com .NET (por exemplo, Visual Studio).
3. Conhecimento básico de C#: Recomenda-se familiaridade com programação em C#.

 Por último, não se esqueça da sua licença Aspose.PDF. Se você não tiver uma, você pode usar a[teste gratuito](https://releases.aspose.com/) ou solicite um[licença temporária](https://purchase.aspose.com/temporary-license/) para testar tudo.

## Pacotes de importação

Primeiro as coisas mais importantes — vamos importar os pacotes necessários. Isso nos permitirá trabalhar com todas as classes relevantes para criar tabelas em documentos PDF.

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Nesta seção, dividiremos o processo de criação de uma tabela em várias etapas. Cada etapa foca em diferentes partes do processo de criação e personalização da tabela.

## Etapa 1: Crie um novo documento PDF

A primeira coisa que precisamos fazer é criar um novo documento PDF. Ele servirá como contêiner para nossa tabela.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Criar um novo documento PDF
Document document = new Document();
```

 Aqui, estamos inicializando uma nova instância do`Document` class, que será nosso arquivo PDF em branco. Não esqueça de definir o caminho do seu arquivo!

## Etapa 2: Configurar conteúdo marcado

Em seguida, precisamos habilitar o conteúdo marcado, o que garante acessibilidade para a tabela. PDFs marcados são necessários para conformidade com PDF/UA (Acessibilidade Universal).

```csharp
// Habilitar conteúdo marcado
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Table");
taggedContent.SetLanguage("en-US");
```

Esta etapa define o título e o idioma do documento, garantindo que a tabela esteja em conformidade com os padrões de acessibilidade. Ter documentos acessíveis é crucial para a experiência do usuário e requisitos legais em alguns setores.

## Etapa 3: Crie o elemento de tabela

Agora vem a parte divertida: criar a mesa em si!

```csharp
// Obter o elemento de estrutura raiz
StructureElement rootElement = taggedContent.RootElement;
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
```

 Aqui, estamos usando o`RootElement` do conteúdo marcado para anexar nossa tabela. Isso é essencialmente adicionar uma tabela como um nó filho à estrutura do documento.

## Etapa 4: personalizar bordas e cabeçalhos de tabela

Você não quer que sua mesa pareça sem graça, certo? Vamos adicionar um pouco de estilo!

```csharp
tableElement.Border = new BorderInfo(BorderSide.All, 1.2F, Color.DarkBlue);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

 Estamos definindo bordas e adicionando cabeçalhos, corpo e rodapés à tabela. Observe o uso de`BorderInfo` para estilizar as bordas da mesa com uma cor azul escura.

## Etapa 5: Adicionar linhas e células à tabela

Agora, vamos preencher nossa tabela com linhas e células. Esta parte do processo é onde definimos o layout da nossa tabela.

### Etapa 5.1: Criar linha de cabeçalho

```csharp
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
headTrElement.BackgroundColor = Color.LightGray;

for (int colIndex = 0; colIndex < 4; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText($"Head {colIndex}");
    thElement.BackgroundColor = Color.GreenYellow;
    thElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
    thElement.Alignment = HorizontalAlignment.Right;
}
```

 Estamos criando uma linha de cabeçalho com 4 colunas, e cada célula de cabeçalho é estilizada com uma cor de fundo de`GreenYellow`. Também definimos uma borda e alinhamento para os cabeçalhos.

### Etapa 5.2: Adicionar linhas do corpo

```csharp
for (int rowIndex = 0; rowIndex < 50; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    trElement.AlternativeText = $"Row {rowIndex}";

    for (int colIndex = 0; colIndex < 4; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText($"Cell [{rowIndex}, {colIndex}]");
        tdElement.BackgroundColor = Color.Yellow;
        tdElement.Alignment = HorizontalAlignment.Center;
    }
}
```

Aqui, estamos criando dinamicamente 50 linhas e 4 colunas, preenchendo-as com texto e estilizando as células. A cor de fundo é definida como amarela, com o texto centralizado.

### Etapa 5.3: Adicionar linha de rodapé

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
footTrElement.BackgroundColor = Color.LightSeaGreen;

for (int colIndex = 0; colIndex < 4; colIndex++)
{
    TableTDElement tdElement = footTrElement.CreateTD();
    tdElement.SetText($"Foot {colIndex}");
    tdElement.Alignment = HorizontalAlignment.Center;
}
```

 Para completar a tabela, adicionamos um rodapé com texto centralizado e uma`LightSeaGreen` fundo.

## Etapa 6: Validar a conformidade com PDF/UA

Depois que a tabela for criada, é crucial garantir que o PDF seja compatível com PDF/UA.

```csharp
document.Save(dataDir + "CreateTableElement.pdf");

// Validar a conformidade com PDF/UA
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```

Este snippet salva o arquivo PDF e verifica se ele atende aos padrões de conformidade do PDF/UA. Se o documento estiver em conformidade, ele será acessível a usuários com deficiências.

## Conclusão

Parabéns! Você criou com sucesso uma tabela totalmente personalizada em um PDF usando o Aspose.PDF para .NET. Desde estilizar a tabela até garantir a conformidade com PDF/UA, agora você tem uma base sólida para gerar tabelas dinâmicas em seus documentos PDF. Não se esqueça de explorar os recursos abrangentes do Aspose.PDF para aprimorar ainda mais seus documentos!

## Perguntas frequentes

### Posso personalizar a fonte e o estilo do texto da tabela?
Sim, o Aspose.PDF permite que você personalize totalmente fontes, estilos de texto e alinhamento usando o`TextState` aula.

### Como adiciono mais colunas ou linhas dinamicamente?
 Você pode ajustar o número de colunas ou linhas modificando o`rowIndex` e`colIndex` nos laços.

### É possível mesclar células na tabela?
 Sim, você pode usar o`ColSpan` e`RowSpan` propriedades para mesclar células em colunas ou linhas.

### O que é conformidade com PDF/UA?
A conformidade com PDF/UA garante que o documento seja acessível a usuários com deficiências, aderindo aos padrões internacionais de acessibilidade.

### Como faço para testar a conformidade com PDF/UA no Aspose.PDF?
 Você pode usar o`Validate` método para verificar se o documento está em conformidade com os padrões PDF/UA.