---
title: Definir propriedade de chamada em arquivo PDF
linktitle: Definir propriedade de chamada em arquivo PDF
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda como definir a propriedade de chamada em um arquivo PDF usando o Aspose.PDF para .NET neste tutorial detalhado e passo a passo.
type: docs
weight: 130
url: /pt/net/annotations/setcalloutproperty/
---
## Introdução

Criar documentos PDF profissionais e visualmente atraentes geralmente requer a adição de anotações que chamem a atenção para um conteúdo específico. Uma dessas anotações é o callout, que é como aqueles balões de fala que você vê em quadrinhos. Eles ajudam a esclarecer ou enfatizar o texto dentro do seu PDF. O Aspose.PDF para .NET torna incrivelmente fácil adicionar essas anotações aos seus documentos e, neste tutorial, mostraremos como definir a propriedade callout em um arquivo PDF usando esta biblioteca poderosa. Seja você um desenvolvedor experiente ou apenas começando, ao final deste guia, você terá uma compreensão clara de como trabalhar com callouts em arquivos PDF.

## Pré-requisitos

Antes de mergulharmos no código, vamos abordar os conceitos essenciais que você precisa para começar.

1.  Aspose.PDF para .NET: Certifique-se de ter a biblioteca Aspose.PDF para .NET instalada. Você pode baixá-la em[aqui](https://releases.aspose.com/pdf/net/).
2. IDE: Um ambiente de desenvolvimento como o Visual Studio.
3. .NET Framework: certifique-se de ter o .NET instalado em sua máquina.
4. Licença temporária: se você quiser experimentar todos os recursos do Aspose.PDF sem limitações, obtenha uma[licença temporária](https://purchase.aspose.com/temporary-license/).

## Pacotes de importação

Antes de começar a escrever o código, você precisa importar os pacotes necessários que permitirão trabalhar com arquivos PDF e anotações.

```csharp
using Aspose.Pdf.Annotations;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

Essas importações fornecerão todas as classes e métodos necessários para manipular documentos PDF e criar anotações como o texto explicativo.

## Etapa 1: inicializar o documento PDF

O primeiro passo em nossa jornada é inicializar um novo documento PDF onde adicionaremos nossa anotação de chamada. Pense nisso como configurar uma tela em branco onde você pode começar a adicionar elementos.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Inicializar um novo documento PDF
Document doc = new Document();
```
 Aqui, estamos criando um novo`Document` objeto que servirá como nosso arquivo PDF. O`dataDir` A variável é definida como o diretório onde você deseja salvar seu arquivo PDF depois que terminarmos.

## Etapa 2: Adicionar uma nova página ao documento

Um documento PDF pode ter várias páginas e, nesta etapa, adicionaremos uma nova página ao nosso documento. Esta página será onde nossa anotação de chamada será colocada.

```csharp
//Adicionar uma nova página ao documento
Page page = doc.Pages.Add();
```
 O`Pages.Add()`método é usado para adicionar uma nova página ao`doc` objeto. A nova página é armazenada no`page` variável, que usaremos mais tarde ao adicionar a anotação.

## Etapa 3: Defina a aparência padrão

Anotações, como o callout, têm uma aparência visual que você pode personalizar. Nesta etapa, definiremos como o texto dentro do callout deve ficar.

```csharp
// Defina a aparência padrão para a anotação
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
```
 Nós criamos um`DefaultAppearance` objeto que define a cor do texto e o tamanho da fonte. Aqui, o texto será vermelho, e o tamanho da fonte será definido como 10. Essa aparência será aplicada à anotação de chamada.

## Etapa 4: Crie a anotação de texto livre

Agora é hora de criar a anotação real. A anotação de texto livre é o que nos permite adicionar um callout com texto e estilo específicos.

```csharp
// Crie um FreeTextAnnotation com um callout
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
```
 Nós criamos um`FreeTextAnnotation` objeto com coordenadas específicas, definindo sua posição na página. O`Intent` está definido para`FreeTextCallout` , indicando que esta é uma anotação de chamada. O`EndingStyle` está definido para`OpenArrow`o que significa que a linha de chamada terminará com uma seta aberta.

## Etapa 5: Defina os pontos da linha de chamada

Uma anotação de chamada tem uma linha que aponta para a área de interesse. Aqui, definiremos os pontos que compõem essa linha.

```csharp
// Defina os pontos para a linha de chamada
fta.Callout = new Point[]
{
    new Point(428.25, 651.75), 
    new Point(462.75, 681.375), 
    new Point(474, 681.375)
};
```
 O`Callout` propriedade é uma matriz de`Point` objetos, cada um representando uma coordenada na página. Esses pontos definem o caminho da linha de chamada, dando a ela a aparência clássica de balão de fala.

## Etapa 6: adicione a anotação à página

Depois de criar e configurar nossa anotação, o próximo passo é adicioná-la à página.

```csharp
// Adicione a anotação à página
page.Annotations.Add(fta);
```
 O`Annotations.Add()` O método é usado para colocar a anotação na página que criamos anteriormente. Esta etapa efetivamente "desenha" o callout na página PDF.

## Etapa 7: Defina o conteúdo de Rich Text

Anotações de chamada podem incluir rich text, permitindo conteúdo formatado dentro do balão. Vamos adicionar um texto de exemplo.

```csharp
// Defina o texto enriquecido para a anotação
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" style=\"color:#FF0000;font-weight:normal;font-style:normal;font-stretch:normal\"><p dir=\"ltr\"><span style=\"font-size:9.0pt;font-family:Helvetica\">Este é um exemplo</span></p></body>";
```
 O`RichText` property é definido com conteúdo HTML. Isso permite formatação detalhada dentro do callout, como especificar tamanho da fonte, cor e estilo.

## Etapa 8: Salve o documento PDF

Por fim, depois de configurar tudo, precisamos salvar o documento. Este passo finaliza a criação do PDF com a anotação de callout.

```csharp
// Salvar o documento
doc.Save(dataDir + "SetCalloutProperty.pdf");
```
 O`Save()` O método salva o documento no diretório especificado com o nome de arquivo "SetCalloutProperty.pdf". Esta etapa conclui nosso processo de criação de PDF.

## Conclusão

aí está! Você acabou de criar um documento PDF com uma anotação de chamada usando o Aspose.PDF para .NET. Essa anotação pode ser incrivelmente útil para destacar ou explicar partes específicas do seu documento. O Aspose.PDF oferece uma API poderosa que torna a manipulação de PDF direta e flexível. Não importa se você está adicionando anotações, convertendo documentos ou lidando com tarefas complexas de PDF, o Aspose.PDF tem tudo o que você precisa.

## Perguntas frequentes

### Posso personalizar ainda mais a aparência do texto explicativo?

Claro! Você pode personalizar vários aspectos como cor da linha, espessura e a família e estilo da fonte do texto.

### É possível adicionar vários textos explicativos em uma única página?

Sim, você pode adicionar quantos balões forem necessários repetindo as etapas para cada anotação.

### Como altero a posição do texto explicativo?

 Basta modificar as coordenadas no`Rectangle` e`Callout` propriedades para reposicionar a anotação.

### Posso adicionar outros tipos de anotações usando o Aspose.PDF?

Sim, o Aspose.PDF suporta vários tipos de anotações, incluindo destaques, carimbos e anexos de arquivo.

### O conteúdo de rich text é limitado a HTML?

 O`RichText` propriedade suporta um subconjunto de HTML, permitindo que você inclua texto estilizado e formatação básica.