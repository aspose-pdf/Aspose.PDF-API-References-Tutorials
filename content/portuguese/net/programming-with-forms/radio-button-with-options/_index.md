---
title: Botão de rádio com opções
linktitle: Botão de rádio com opções
second_title: Referência da API do Aspose.PDF para .NET
description: Desbloqueie o potencial dos PDFs interativos adicionando botões de opção usando o Aspose.PDF para .NET. Crie formulários envolventes com facilidade e melhore a experiência do usuário.
type: docs
weight: 230
url: /pt/net/programming-with-forms/radio-button-with-options/
---
## Introdução

Criar documentos PDF interativos pode aumentar significativamente o engajamento do usuário e agilizar a coleta de dados. Entre os vários elementos que você pode incorporar, os botões de opção se destacam como um método amigável de apresentar opções de múltipla escolha. Usando o Aspose.PDF para .NET, você pode adicionar botões de opção sem esforço em seus formulários PDF, facilitando para os usuários selecionarem suas preferências. Esteja você trabalhando em pesquisas, formulários de feedback ou aplicativos, este guia ajudará você a aproveitar o poder do Aspose.PDF para implementar botões de opção de forma eficaz.

## Pré-requisitos

Antes de começar, há algumas coisas que você precisa configurar para garantir uma jornada tranquila enquanto criamos nosso PDF com botões de opção:

1.  Aspose.PDF para .NET: Certifique-se de ter a biblioteca Aspose.PDF instalada em seu projeto. Se você ainda não a tem, você pode baixá-la facilmente do[página de lançamento](https://releases.aspose.com/pdf/net/).
2. .NET Framework: Uma compreensão básica do .NET Framework ajudará você a lidar com quaisquer problemas que encontrar ao longo do caminho.
3. Ambiente de desenvolvimento: você precisará de um IDE adequado para .NET (como o Visual Studio), onde poderá escrever e testar seu código.
4. Familiaridade com C#: Embora você não precise ser um profissional, ter conhecimento de programação em C# certamente tornará esse processo mais fácil e agradável.
5. Conhecimento básico da estrutura de PDF: entender como os PDFs são estruturados pode ajudar na solução de problemas ou na personalização adicional de seus formulários.

Depois de resolver tudo isso, você estará pronto para liberar sua criatividade no mundo dos PDFs!

## Pacotes de importação

Para começar a usar botões de opção no Aspose.PDF, primeiro você precisa importar os pacotes essenciais para seu projeto C#. Veja como fazer isso:

### Abra seu editor de código

Abra seu ambiente de desenvolvimento (como o Visual Studio) e crie um novo projeto C#, caso ainda não tenha feito isso. 

### Adicione a referência Aspose.PDF

Clique com o botão direito do mouse no seu projeto no Solution Explorer, selecione Add > Reference e, na seção Assemblies, procure por Aspose.PDF. Se você instalou a biblioteca corretamente, ela deve aparecer na lista. Basta desmarcá-la e clicar em OK.

```csharp
using System;
using System.IO;
using Aspose.Pdf.Forms;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
```

Agora, seu projeto está pronto para aproveitar o poder do Aspose!

Com tudo configurado, vamos criar um documento PDF cheio de botões de opção passo a passo!

## Etapa 1: Configurar o documento

Primeiro, vamos criar um novo documento PDF e adicionar uma página a ele. Esta será a tela onde pintaremos nossas opções de botões de rádio.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
```

 Neste trecho, estamos estabelecendo um novo`Document` objeto e adicionando um`Page` para o nosso conteúdo. Certifique-se de substituir`YOUR DOCUMENT DIRECTORY` com o caminho onde você deseja salvar seu PDF.

## Etapa 2: Crie uma tabela para layout

Em seguida, precisamos de um layout para nossos botões de rádio. Usar uma tabela torna mais fácil posicioná-los bem.

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table.ColumnWidths = "120 120 120"; // Defina as larguras das colunas
page.Paragraphs.Add(table);
```

 Aqui, criamos um`Table`object e especificamos as larguras para nossas três colunas. Isso cria um layout organizado para nossas opções.

## Etapa 3: Adicionar linhas à tabela

Agora adicionaremos uma linha à nossa tabela e células que conterão os botões de opção.

```csharp
Row r1 = table.Rows.Add();
Cell c1 = r1.Cells.Add();
Cell c2 = r1.Cells.Add();
Cell c3 = r1.Cells.Add();
```

Criamos uma nova linha e três células na linha. Cada célula abrigará uma opção de botão de rádio.

## Etapa 4: Adicionar um campo de botão de opção

É aqui que a diversão começa: vamos adicionar o campo de botão de opção ao nosso PDF!

```csharp
RadioButtonField rf = new RadioButtonField(page);
rf.PartialName = "radio";
doc.Form.Add(rf, 1);
```

 Nós instanciamos um`RadioButtonField`, defina seu nome e adicione-o ao formulário do documento. Este campo permitirá que os usuários façam sua seleção.

## Etapa 5: Configurar opções de botão de opção

Hora de criar as opções para os botões de rádio! Adicionaremos três opções que os usuários podem escolher.

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField();
RadioButtonOptionField opt2 = new RadioButtonOptionField();
RadioButtonOptionField opt3 = new RadioButtonOptionField();
opt1.OptionName = "Item1";
opt2.OptionName = "Item2";
opt3.OptionName = "Item3";
```

 Aqui, criamos três`RadioButtonOptionField` instâncias para cada uma de nossas escolhas e atribuir nomes a elas. Ser criativo com esses nomes pode ajudar a orientar melhor os usuários sobre o que escolher.

## Etapa 6: Definir dimensões para opções

Em seguida, vamos definir o tamanho das opções dos botões de opção para torná-los visualmente atraentes.

```csharp
opt1.Width = 15;
opt1.Height = 15;
opt2.Width = 15;
opt2.Height = 15;
opt3.Width = 15;
opt3.Height = 15;
```

Com esse código, estamos definindo as dimensões de cada botão de opção. Você pode ajustar esses valores se quiser opções maiores ou menores.

## Etapa 7: Adicionar opções ao campo do botão de opção

Agora que as opções foram criadas, precisamos adicioná-las ao campo do botão de opção.

```csharp
rf.Add(opt1);
rf.Add(opt2);
rf.Add(opt3);
```

Este código não apenas adiciona as opções, mas também as vincula ao nosso campo de botão de opção, dando aos usuários a capacidade de selecionar uma das opções.

## Etapa 8: Estilize as opções

Para fazer nossas opções se destacarem, vamos estilizá-las. Podemos adicionar bordas e definir cores.

```csharp
opt1.Border = new Border(opt1);
opt1.Border.Width = 1;
opt1.Border.Style = BorderStyle.Solid;
opt1.Characteristics.Border = System.Drawing.Color.Black;
opt1.DefaultAppearance.TextColor = System.Drawing.Color.Red;
opt1.Caption = new TextFragment("Item1");
```

 Repita esse estilo para`opt2` e`opt3`, ajustando as legendas de acordo. Isso garante que cada opção pareça profissional e envolvente.

## Etapa 9: Adicionar opções às células

Em seguida, precisamos colocar esses botões de opção nas células correspondentes da nossa tabela.

```csharp
c1.Paragraphs.Add(opt1);
c2.Paragraphs.Add(opt2);
c3.Paragraphs.Add(opt3);
```

Esta linha adiciona as opções estilizadas às células que criamos anteriormente, organizando-as cuidadosamente em nossa tabela.

## Etapa 10: Salve o documento PDF

Finalmente, é hora de salvar seu trabalho! Este passo confirma tudo o que fizemos em um arquivo PDF.

```csharp
dataDir = dataDir + "RadioButtonWithOptions_out.pdf";
// Salvar o arquivo PDF
doc.Save(dataDir);
Console.WriteLine("\nRadio button field with three options added successfully.\nFile saved at " + dataDir);
```

Com este código, seu documento será salvo no diretório especificado. Agora você pode abrir este arquivo PDF para ver seus botões de opção em ação. Parabéns por implementar seu primeiro PDF interativo!

## Conclusão

Dominar como criar elementos interativos como botões de opção com o Aspose.PDF para .NET abre um novo reino de possibilidades para seus documentos PDF. Ao seguir este guia, você agora deve estar equipado para incorporar botões de opção em seus projetos sem esforço, aprimorando a experiência do usuário e os processos de coleta de dados. Seja para uma pesquisa simples ou um formulário complexo, o poder de criar PDFs interativos personalizados está ao seu alcance.

## Perguntas frequentes

### O que é Aspose.PDF para .NET?
Aspose.PDF para .NET é uma biblioteca que permite aos desenvolvedores criar e manipular documentos PDF programaticamente.

### Como instalo o Aspose.PDF para .NET?
 Você pode baixar a biblioteca do[Página de lançamento do Aspose](https://releases.aspose.com/pdf/net/) e adicione-o ao seu projeto.

### Posso criar botões de opção em PDFs usando outras linguagens de programação?
Sim, o Aspose.PDF também está disponível para Java e outras linguagens para funcionalidades semelhantes.

### Existe uma versão de avaliação gratuita do Aspose.PDF?
 Sim, você pode explorar as funcionalidades do Aspose.PDF baixando um[versão de teste gratuita](https://releases.aspose.com/).

### Onde posso obter suporte para o Aspose.PDF?
 Para obter suporte, você pode visitar o[Fórum de suporte Aspose](https://forum.aspose.com/c/pdf/10) para obter assistência de especialistas e membros da comunidade.