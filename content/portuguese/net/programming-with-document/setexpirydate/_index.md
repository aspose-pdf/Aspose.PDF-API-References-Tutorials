---
title: Definir data de expiração em arquivo PDF
linktitle: Definir data de expiração em arquivo PDF
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como definir a data de validade em um arquivo PDF usando Aspose.PDF for .NET com este guia passo a passo.
type: docs
weight: 300
url: /pt/net/programming-with-document/setexpirydate/
---
Aspose.PDF for .NET é uma biblioteca poderosa que oferece vários recursos para trabalhar com arquivos PDF. Um desses recursos é a capacidade de definir uma data de validade para um documento PDF. Neste tutorial, orientaremos você no processo de definição de uma data de expiração para um documento PDF usando Aspose.PDF for .NET. 

## Passo 1: Defina o caminho para o diretório do documento

Antes de começarmos, precisamos definir o caminho para o diretório onde nosso documento PDF está localizado. Armazenaremos esse caminho em uma variável chamada “dataDir”.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passo 2: Criando um novo documento PDF

 Para criar um novo documento PDF, precisamos instanciar um novo`Aspose.Pdf.Document` objeto. Podemos fazer isso usando o seguinte código:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## Passo 3: Adicionar uma nova página ao documento PDF

Depois de criar o documento PDF, podemos adicionar uma nova página a ele. Podemos fazer isso usando o seguinte código:

```csharp
doc.Pages.Add();
```

## Passo 4: Adicionando Texto ao Documento PDF

Depois de adicionar uma página ao documento PDF, podemos adicionar texto a ela usando o`Paragraphs` coleção. Podemos fazer isso usando o seguinte código:

```csharp
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
```

## Etapa 5: definir a data de expiração do PDF usando JavaScript

Para definir a data de expiração do PDF, precisamos criar um objeto JavaScript. Podemos fazer isso usando o seguinte código:

```csharp
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");

// Definir JavaScript como ação de abertura de PDF
doc.OpenAction = javaScript;
```

Neste código, estamos definindo a data de validade para maio de 2017.

## Etapa 6: salve o arquivo PDF

 Depois de definir a data de validade, você precisa salvar o arquivo PDF. Para fazer isso, você pode usar o`Save` método do`Document` objeto e passe o caminho onde deseja salvar o arquivo PDF atualizado.

```csharp
dataDir = dataDir + "SetExpiryDate_out.pdf";
// Salvar documento PDF
doc.Save(dataDir);
```

### Exemplo de código-fonte para definir data de expiração usando Aspose.PDF para .NET

Aqui está o exemplo completo de código-fonte para definir a data de expiração usando Aspose.PDF para .NET:

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instanciar objeto Document
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// Adicionar página à coleção de páginas do arquivo PDF
doc.Pages.Add();
// Adicionar fragmento de texto à coleção de parágrafos do objeto de página
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
// Crie um objeto JavaScript para definir a data de expiração do PDF
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");
// Definir JavaScript como ação de abertura de PDF
doc.OpenAction = javaScript;

dataDir = dataDir + "SetExpiryDate_out.pdf";
// Salvar documento PDF
doc.Save(dataDir);
```

## Conclusão

Definir uma data de validade para um documento PDF usando Aspose.PDF for .NET é um recurso útil para garantir que o documento seja válido apenas por um período especificado. Seguindo o guia passo a passo e usando o código-fonte C# fornecido, os desenvolvedores podem facilmente definir a data de validade e criar PDFs com validade limitada no tempo. Este recurso pode ser particularmente útil para documentos que precisam ser acessados ou distribuídos por um período limitado.

### Perguntas frequentes sobre como definir a data de validade em arquivo PDF

#### P: Posso definir uma data de validade diferente para o documento PDF?

 R: Sim, você pode definir uma data de expiração diferente para o documento PDF modificando o código JavaScript na Etapa 5. No exemplo fornecido, a data de expiração é definida para maio de 2017. Para definir uma data de expiração diferente, você precisa modificar o`year` e`month` variáveis no código JavaScript para o ano e mês desejados.

#### P: O que acontece quando o documento PDF expira?

R: Quando o documento PDF expirar, conforme especificado no código JavaScript, o visualizador exibirá uma mensagem de alerta indicando que o arquivo expirou e que o usuário precisa de um novo. Esta mensagem de alerta será mostrada quando o PDF for aberto.

#### P: Posso usar um horário específico para a data de vencimento em vez de apenas a data?

 R: Sim, você pode definir um horário específico para a data de expiração no código JavaScript. Ao modificar o`expiry` variável no código JavaScript para incluir o horário desejado, você pode definir um horário específico para a data de expiração.