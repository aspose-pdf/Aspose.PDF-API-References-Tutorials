---
title: Caixas de seleção agrupadas em documento PDF
linktitle: Caixas de seleção agrupadas em documento PDF
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda a criar caixas de seleção agrupadas (botões de opção) em um documento PDF usando o Aspose.PDF para .NET com este tutorial passo a passo.
type: docs
weight: 170
url: /pt/net/programming-with-forms/grouped-check-boxes/
---
## Introdução

Criar PDFs interativos não é tão difícil quanto parece, especialmente quando você tem ferramentas poderosas como o Aspose.PDF para .NET à sua disposição. Um dos elementos interativos que você pode precisar adicionar aos seus documentos PDF são caixas de seleção agrupadas ou, mais especificamente, botões de opção que permitem que os usuários selecionem uma opção de um conjunto. Este tutorial o guiará pelo processo de adicionar caixas de seleção agrupadas (botões de opção) a um documento PDF usando o Aspose.PDF para .NET. Seja você um iniciante ou um desenvolvedor experiente, você achará este guia envolvente, detalhado e fácil de seguir.

## Pré-requisitos

Antes de mergulharmos no guia passo a passo, vamos abordar alguns pré-requisitos essenciais:

1.  Aspose.PDF para .NET: Certifique-se de ter a biblioteca Aspose.PDF instalada. Se não, você pode[baixe aqui](https://releases.aspose.com/pdf/net/).
2. IDE: Você deve ter um ambiente de desenvolvimento configurado, como o Visual Studio.
3. .NET Framework: O projeto deve ter como alvo uma versão do .NET Framework compatível com Aspose.PDF.
4. Conhecimento básico de C#: É necessário ter familiaridade com C# e manipulação de PDF para acompanhar sem problemas.
5.  Licença: Aspose.PDF requer uma licença para funcionalidade completa. Você pode[obter uma licença temporária](https://purchase.aspose.com/temporary-license/) se necessário.

## Pacotes de importação

Antes de começar, certifique-se de ter importado os namespaces necessários para o seu projeto:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Forms;
```

Esses pacotes darão acesso a todas as classes e métodos necessários para manipular documentos PDF, incluindo a criação de botões de opção e a definição de suas propriedades.

Nesta seção, dividiremos o processo de criação de caixas de seleção agrupadas (botões de opção) em etapas claras e fáceis de seguir.

## Etapa 1: Crie um novo documento PDF

 O primeiro passo é criar uma instância do`Document` objeto, que representará seu arquivo PDF. Em seguida, adicione uma página em branco ao seu documento onde você colocará suas caixas de seleção agrupadas.

```csharp
// Instanciar objeto Document
Document pdfDocument = new Document();

// Adicionar uma página ao arquivo PDF
Page page = pdfDocument.Pages.Add();
```

Isso configura a base para adicionar quaisquer elementos, como botões de opção, ao PDF.

## Etapa 2: Inicializar o campo do botão de opção

Em seguida, precisamos criar um`RadioButtonField` objeto, que manterá as caixas de seleção agrupadas (botões de opção). Este campo é adicionado à página específica onde as caixas de seleção aparecerão.

```csharp
// Instanciar o objeto RadioButtonField e atribuí-lo à primeira página
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

Pense nisso como o contêiner que agrupará as opções individuais dos botões de opção.

## Etapa 3: Adicionar opções de botão de opção

 Agora, vamos adicionar as opções individuais de botões de rádio ao campo. Neste exemplo, adicionaremos dois botões de rádio e especificaremos suas posições usando o`Rectangle` objeto.

```csharp
// Adicione a primeira opção de botão de opção e especifique sua posição usando Retângulo
RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));

// Definir nomes de opções para identificação
opt1.OptionName = "Option1";
opt2.OptionName = "Option2";
```

 Aqui, o`Rectangle` objeto define as coordenadas e o tamanho de cada botão de opção na página.

## Etapa 4: personalize o estilo dos botões de opção

 Você pode personalizar a aparência dos botões de opção definindo-os`Style` propriedade. Por exemplo, você pode querer caixas de seleção quadradas ou em forma de cruz.

```csharp
// Defina o estilo dos botões de opção
opt1.Style = BoxStyle.Square;
opt2.Style = BoxStyle.Cross;
```

Isso permite que você controle a aparência das caixas de seleção, tornando-as mais fáceis de usar e visualmente atraentes.

## Etapa 5: Configurar propriedades de borda

As bordas desempenham um papel vital em tornar as caixas de seleção facilmente identificáveis. Aqui, adicionaremos bordas sólidas ao redor de cada opção de botão de rádio e definiremos sua largura e cor.

```csharp
// Configurar a borda do primeiro botão de opção
opt1.Border = new Border(opt1);
opt1.Border.Style = BorderStyle.Solid;
opt1.Border.Width = 1;
opt1.Characteristics.Border = Color.Black;

// Configurar a borda do segundo botão de opção
opt2.Border = new Border(opt2);
opt2.Border.Style = BorderStyle.Solid;
opt2.Border.Width = 1;
opt2.Characteristics.Border = Color.Black;
```

Esta etapa garante que cada botão de opção tenha uma borda bem definida, melhorando a legibilidade do documento.

## Etapa 6: Adicionar opções de botão de opção ao formulário

Agora, adicionaremos os botões de opção ao formulário do documento. Este é o passo final para agrupar as caixas de seleção em um único campo.

```csharp
// Adicionar campo de botão de opção ao objeto de formulário do documento
pdfDocument.Form.Add(radio);
```

O objeto de formulário atua como um contêiner para todos os elementos interativos, incluindo nossas caixas de seleção agrupadas.

## Etapa 7: Salve o documento PDF

Por fim, quando tudo estiver configurado, você pode salvar o documento PDF no local desejado.

```csharp
// Defina o caminho do arquivo de saída
string dataDir = "YOUR DOCUMENT DIRECTORY" + "GroupedCheckBoxes_out.pdf";

// Salvar o documento PDF
pdfDocument.Save(dataDir);

// Confirmar criação bem-sucedida
Console.WriteLine("Grouped checkboxes added successfully. File saved at " + dataDir);
```

E é isso! Você criou com sucesso um PDF com caixas de seleção agrupadas usando Aspose.PDF para .NET.

## Conclusão

Adicionar elementos interativos como caixas de seleção agrupadas a documentos PDF pode parecer complicado no começo, mas com o Aspose.PDF para .NET, isso se torna moleza. Seguindo este guia passo a passo, você aprendeu a configurar um documento PDF básico, adicionar botões de opção agrupados, personalizar sua aparência e salvar o resultado final. Não importa se você está criando formulários, pesquisas ou qualquer outro tipo de PDF interativo, este guia oferece uma base sólida para começar.

## Perguntas frequentes

### Posso adicionar mais de dois botões de opção a um grupo?
 Absolutamente! Basta instanciar adicional`RadioButtonOptionField` objetos e adicioná-los ao`RadioButtonField` conforme mostrado no tutorial.

### Como lidar com vários grupos de caixas de seleção em um documento?
Para criar vários grupos, instancie separadamente`RadioButtonField` objetos para cada grupo.

### Existe um limite para o número de caixas de seleção que posso adicionar?
Não, o Aspose.PDF para .NET não impõe nenhum limite ao número de caixas de seleção que você pode adicionar a um PDF.

### Posso alterar a aparência das caixas de seleção depois que elas forem adicionadas?
Sim, você pode modificar propriedades como estilo, largura e cor da borda depois que as caixas de seleção forem adicionadas.

### É possível usar imagens como botões de opção?
 Sim, o Aspose.PDF permite que você use imagens personalizadas como botões de opção, definindo o`Appearance` propriedade de cada opção de botão de rádio.