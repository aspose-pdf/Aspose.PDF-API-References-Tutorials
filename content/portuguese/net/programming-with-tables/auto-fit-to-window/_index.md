---
title: Ajuste automático à janela
linktitle: Ajuste automático à janela
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda como ajustar automaticamente uma tabela à janela usando o Aspose.PDF para .NET neste guia detalhado passo a passo. Perfeito para criar tabelas polidas e bem ajustadas em PDFs.
type: docs
weight: 50
url: /pt/net/programming-with-tables/auto-fit-to-window/
---
## Introdução

Ao trabalhar com PDFs, é comum lidar com tabelas, e há momentos em que você precisa que essas tabelas se ajustem perfeitamente à largura de uma página. Neste tutorial, exploraremos como ajustar automaticamente uma tabela a uma janela usando o Aspose.PDF para .NET. Isso pode fazer com que suas tabelas pareçam polidas e organizadas, evitando problemas como colunas transbordando ou desiguais. Pronto para aprender? Vamos mergulhar!

## Pré-requisitos

Antes de começarmos o guia passo a passo, há algumas coisas que você precisará:

1. Aspose.PDF para .NET instalado em seu projeto. Se você ainda não o tem, você pode[baixe aqui](https://releases.aspose.com/pdf/net/) ou explorar seus[versão de teste gratuita](https://releases.aspose.com/).
2. Uma compreensão básica da programação .NET.
3. Visual Studio ou qualquer IDE compatível com .NET instalado no seu sistema.

>  PS Não se esqueça de que você precisará de uma licença para usar o Aspose.PDF sem limitações. Você pode comprar uma[aqui](https://purchase.aspose.com/buy) ou pegue um[licença temporária](https://purchase.aspose.com/temporary-license/) para experimentar todos os recursos.

## Pacotes de importação

Antes de mergulhar no código, você precisará importar os namespaces necessários:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Agora que estamos prontos, vamos dividir isso em etapas simples e fáceis de entender para entender como você pode ajustar automaticamente uma tabela a uma janela usando o Aspose.PDF para .NET.

## Etapa 1: inicializar o objeto de documento

Primeiro, você precisa criar um documento PDF. Pense neste documento como uma folha em branco onde você adicionará páginas e tabelas.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instanciar o objeto PDF chamando seu construtor vazio
Document doc = new Document();
```
  
 Aqui, criamos um novo documento usando o`Document` classe de Aspose.PDF. A`dataDir` é o local onde seu PDF será salvo depois que você terminar.

## Etapa 2: Adicionar uma página ao documento

Um documento PDF precisa de páginas, certo? Vamos adicionar uma.

```csharp
// Crie uma seção (página) no objeto PDF
Page sec1 = doc.Pages.Add();
```
  
 Adicionamos uma nova página ao documento usando o`Pages.Add()` método. Você pode pensar nisso como adicionar uma nova planilha ao seu documento onde você colocará a tabela.

## Etapa 3: Criar e configurar uma tabela

Agora é hora de criar uma tabela e ajustá-la para caber na janela.

```csharp
// Instanciar um objeto de tabela
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Adicione a tabela na coleção de parágrafos da seção desejada
sec1.Paragraphs.Add(tab1);
```
  
 Inicializamos um novo`Table` objeto e o adicionou à coleção de parágrafos da página. Cada página do PDF pode ter parágrafos diferentes, e aqui estamos tratando a tabela como um parágrafo.

## Etapa 4: Defina as larguras das colunas e ajuste automático à janela

Em seguida, definimos as larguras das colunas e garantimos que a tabela se ajuste para caber na janela.

```csharp
// Definir larguras de coluna para a tabela
tab1.ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
```
  
 Definimos larguras de coluna fixas para a tabela, mas também adicionamos`ColumnAdjustment.AutoFitToWindow`, o que garante que a tabela ajuste seu tamanho para caber na janela disponível.

## Etapa 5: Defina bordas e margens para a tabela e células

Tabelas sem bordas geralmente são ilegíveis. Vamos definir bordas e margens para que pareçam organizadas.

```csharp
// Definir borda de célula padrão usando objeto BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Definir borda da tabela usando outro objeto BorderInfo personalizado
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);

// Crie o objeto MarginInfo e defina suas margens esquerda, inferior, direita e superior
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;

// Defina o preenchimento de célula padrão para o objeto MarginInfo
tab1.DefaultCellPadding = margin;
```
  
 As bordas são adicionadas à tabela e às células usando o`BorderInfo` class, onde você define a espessura. Margens são definidas para dar às células algum espaço de preenchimento.

## Etapa 6: Adicionar linhas e células à tabela

Uma tabela sem conteúdo? Isso não é bom! Vamos adicionar algumas linhas e células.

```csharp
//Crie linhas na tabela e depois células nas linhas
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");

Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");
```
  
Estamos criando duas linhas e adicionando três células a cada linha. É aqui que você vai inserir seus dados reais (que podem ser qualquer coisa, de strings a elementos mais complexos).

## Etapa 7: Salve o documento

Depois que tudo estiver definido, você precisará salvar o documento PDF recém-criado.

```csharp
dataDir = dataDir + "AutoFitToWindow_out.pdf";
// Salvar documento atualizado contendo objeto de tabela
doc.Save(dataDir);
```
  
 O`doc.Save()` método salva o PDF no diretório especificado. Neste caso, o documento será salvo como`AutoFitToWindow_out.pdf` no seu diretório definido.

## Conclusão

aí está! Você acabou de criar uma tabela que se ajusta automaticamente à janela usando o Aspose.PDF para .NET. Isso não só garante que sua tabela tenha uma aparência profissional e bem ajustada, mas também lhe dá flexibilidade ao trabalhar com tamanhos de dados variados. Quer você esteja criando relatórios, faturas ou qualquer documento que exija tabelas, esse método é uma ótima maneira de manter layouts limpos e legíveis.

## Perguntas frequentes

### Posso adicionar mais linhas dinamicamente?  
 Sim, você pode continuar adicionando linhas usando o`tab1.Rows.Add()` método, dinamicamente baseado no conteúdo.

### Como ajusto a tabela se não quero que ela se ajuste automaticamente?  
 Você pode definir manualmente o`ColumnWidths` sem usar`ColumnAdjustment.AutoFitToWindow` para manter uma largura de tabela fixa.

### Posso adicionar imagens ou outro conteúdo dentro das células?  
Sim, o Aspose.PDF permite que você adicione imagens, texto e até outras tabelas dentro das células!

### E se eu precisar de estilos de tabela mais complexos?  
Você pode personalizar ainda mais os estilos de tabela e célula usando propriedades como cor de fundo, alinhamento de texto e configurações de fonte.

### É possível exportar esta tabela para outros formatos além de PDF?  
Com certeza! O Aspose.PDF suporta exportação para vários formatos como HTML, DOCX e mais.