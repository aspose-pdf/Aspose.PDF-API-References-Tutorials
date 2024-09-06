---
title: Adicionar Java Script ao arquivo PDF
linktitle: Adicionar arquivo PDF Java Script
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda como adicionar JavaScript a um arquivo PDF usando Aspose.PDF para .NET. Guia passo a passo com tutoriais de código para scripts em nível de documento e página.
type: docs
weight: 10
url: /pt/net/programming-with-document/addjavascripttopage/
---
## Introdução

Você já se perguntou como aprimorar seus PDFs com elementos interativos, como alertas pop-up ou funções de impressão automática? Bem, boas notícias: você pode! Ao usar o Aspose.PDF para .NET, você pode adicionar JavaScript aos seus documentos PDF sem problemas. Não importa se você está automatizando tarefas ou criando experiências dinâmicas para o usuário, incorporar JavaScript em PDFs dá aos seus arquivos aquele nível extra de funcionalidade.

## Pré-requisitos

Antes de começarmos a codificação, há algumas coisas que você precisa configurar:

-  Aspose.PDF para .NET: Baixe a biblioteca em[Lançamentos Aspose](https://releases.aspose.com/pdf/net/) ou pegue um[teste gratuito](https://releases.aspose.com/).
- Ambiente de desenvolvimento: qualquer IDE compatível com .NET, como o Visual Studio.
- Conhecimento básico de C#: Este guia pressupõe que você esteja familiarizado com a sintaxe básica do C#.
-  Licença temporária (opcional): você pode obter uma[licença temporária](https://purchase.aspose.com/temporary-license/) se você quiser evitar limitações durante seu desenvolvimento.

## Pacotes de importação

Antes de começar a escrever código, você precisará importar os namespaces necessários da biblioteca Aspose.PDF. Esses namespaces permitirão que você manipule PDFs e adicione ações JavaScript facilmente.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
```

Agora que você importou os namespaces corretos, está tudo pronto para começar a codificar.

## Etapa 1: Carregue um PDF existente

Primeiro, o mais importante: você precisa carregar o documento PDF ao qual deseja adicionar JavaScript. Esta etapa prepara o cenário para todas as modificações posteriores. Imagine que você tem um PDF que deseja aprimorar com funcionalidade dinâmica, como imprimir o documento automaticamente quando aberto.

Veja como você pode carregar esse arquivo PDF:

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Carregar um arquivo PDF existente
Document doc = new Document(dataDir + "input.pdf");
```

 Neste trecho de código, estamos usando o`Document` classe para carregar um arquivo PDF existente do diretório especificado. Certifique-se de substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para seu arquivo PDF.

## Etapa 2: adicione JavaScript no nível do documento

Agora, vamos adicionar um pouco de JavaScript que será acionado quando o documento for aberto. Neste exemplo, escreveremos um script que abre o diálogo de impressão assim que o usuário abrir o PDF.

O JavaScript em nível de documento é perfeito para ações que você deseja aplicar ao PDF inteiro. Pense nisso como configurar uma regra global para seu documento.

Aqui está o código:

```csharp
// Adicionando JavaScript no nível do documento
// Instanciar JavascriptAction com a declaração JavaScript desejada
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

// Atribuir objeto JavascriptAction ao OpenAction do Documento
doc.OpenAction = javaScript;
```

 Nesta etapa, criamos um`JavascriptAction` objeto que define uma função JavaScript para abrir o diálogo de impressão quando o documento é aberto. O`doc.OpenAction` propriedade é então atribuída a esta ação JavaScript.

## Etapa 3: adicione JavaScript no nível da página

Nem toda ação precisa afetar o documento inteiro. Às vezes, você quer que ações específicas ocorram quando certas páginas são abertas ou fechadas. Aqui, configuraremos ações JavaScript para quando uma página específica (digamos, a página 2) for aberta e fechada.

O JavaScript de nível de página é útil para interações direcionadas. Pode ser qualquer coisa, desde exibir uma mensagem quando um usuário navega para uma página, até ações personalizadas, como preenchimento automático de campos de formulário.

Veja como fazer:

```csharp
// Adicionando JavaScript no nível da página
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('Page 2 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('Page 2 closed')");
```

Neste trecho de código, adicionamos duas ações JavaScript:
1. Ação OnOpen: Exibe um alerta dizendo “Página 2 aberta” quando o usuário abre a página 2.
2. Ação OnClose: exibe um alerta dizendo “Página 2 fechada” quando o usuário sai da página 2.

Isso adiciona uma camada de interatividade ao seu PDF. Imagine guiar o usuário por uma série de etapas em páginas diferentes, com alertas que aparecem quando ele entra ou sai de uma página.

## Etapa 4: Salve o documento PDF

Agora você adicionou JavaScript ao documento e às páginas específicas. O passo final é salvar o PDF modificado no local desejado. Esta parte é simples, mas crucial — não se esqueça de salvar seu trabalho!

Aqui está o código:

```csharp
// Especifique o caminho do arquivo de saída
dataDir = dataDir + "JavaScript-Added_out.pdf";

// Salvar o documento PDF atualizado
doc.Save(dataDir);

Console.WriteLine("\nJavaScript added successfully to the PDF.\nFile saved at " + dataDir);
```

 Neste snippet, salvamos o documento atualizado com o JavaScript adicionado em um novo arquivo chamado`"JavaScript-Added_out.pdf"`. Isso garante que você não sobrescreva seu arquivo original e lhe dá um backup para trabalhar.

## Conclusão

Adicionar JavaScript a arquivos PDF usando Aspose.PDF para .NET é uma maneira poderosa de criar PDFs interativos e dinâmicos. Não importa se você está automatizando tarefas como impressão ou criando alertas personalizados, a capacidade de incorporar JavaScript ao seu PDF torna seus documentos mais envolventes e funcionais.

## Perguntas frequentes

### Posso adicionar várias ações JavaScript a diferentes páginas de um PDF?
Sim, você pode atribuir diferentes ações JavaScript a páginas individuais ou ao documento inteiro.

### É possível remover JavaScript de um PDF depois de adicioná-lo?
Sim, você pode remover ou modificar ações JavaScript existentes limpando o`Actions` propriedades do documento ou página.

### Que tipo de funções JavaScript posso usar em um PDF?
Você pode usar qualquer JavaScript suportado pelo mecanismo JavaScript do Adobe Acrobat, como impressão, alertas e manipulações de formulários.

### O JavaScript funciona em todos os visualizadores de PDF?
A maioria das ações JavaScript funcionará em visualizadores de PDF que suportam PDFs interativos, como o Adobe Acrobat. No entanto, alguns leitores básicos de PDF podem não suportar JavaScript.

### Posso acionar ações JavaScript com base na entrada do usuário no PDF?
Sim, você pode vincular JavaScript aos campos do formulário para acionar ações com base na entrada do usuário.