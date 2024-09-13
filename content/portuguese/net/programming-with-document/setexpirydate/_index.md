---
title: Definir data de validade em arquivo PDF
linktitle: Definir data de validade em arquivo PDF
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda como definir uma data de expiração em arquivos PDF usando Aspose.PDF para .NET. Aumente a segurança do documento com este guia passo a passo.
type: docs
weight: 300
url: /pt/net/programming-with-document/setexpirydate/
---
## Introdução

Na era digital de hoje, gerenciar e proteger documentos é mais crucial do que nunca. Imagine enviar um PDF que se torna automaticamente inacessível após uma determinada data. Parece mágica, certo? Bem, com o Aspose.PDF para .NET, você pode facilmente definir uma data de expiração para seus arquivos PDF. Esse recurso é particularmente útil para documentos confidenciais que precisam ser restritos após um determinado período. Neste tutorial, mostraremos a você o processo de definição de uma data de expiração em um arquivo PDF passo a passo. Então, pegue seu chapéu de codificação e vamos mergulhar!

## Pré-requisitos

Antes de começar, há algumas coisas que você precisa ter em mãos:

1. Ambiente de desenvolvimento: Certifique-se de ter um ambiente de desenvolvimento .NET configurado. Pode ser o Visual Studio ou qualquer outro IDE que suporte .NET.
2.  Aspose.PDF para .NET: Você precisa ter a biblioteca Aspose.PDF instalada. Se você ainda não fez isso, você pode baixá-la em[aqui](https://releases.aspose.com/pdf/net/).
3. Conhecimento básico de C#: Este tutorial pressupõe que você tenha um entendimento básico de programação em C#. Se você é novo em C#, não se preocupe! Vamos manter tudo simples e direto.

## Pacotes de importação

Para começar com Aspose.PDF, você precisa importar os namespaces necessários no seu projeto C#. É assim que você pode fazer:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
```

Esses namespaces fornecem acesso às principais funcionalidades necessárias para trabalhar com documentos PDF no Aspose.PDF.

## Etapa 1: configure seu diretório de documentos

Primeiro, você precisa especificar o caminho para o diretório dos seus documentos. É aqui que seu PDF de saída será salvo. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real onde você quer salvar seu arquivo PDF. É como dizer ao seu programa, “Ei, é aqui que eu guardo meus arquivos!”

## Etapa 2: Instanciar o objeto Document

 Em seguida, você precisa criar uma nova instância do`Document` classe. Esta é sua tela onde você criará seu PDF.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

 Pense no`Document` objeto como uma folha de papel em branco. Você pode adicionar conteúdo a ele como quiser!

## Etapa 3: Adicionar uma página ao PDF

Agora que você configurou seu documento, é hora de adicionar uma página a ele. É aqui que seu conteúdo ficará.

```csharp
doc.Pages.Add();
```

Você acabou de criar uma nova página no seu PDF. É como adicionar uma nova página no seu caderno onde você pode anotar seus pensamentos.

## Etapa 4: adicione texto à página

Vamos tornar esta página um pouco mais interessante adicionando algum texto. Adicionaremos uma mensagem simples de “Hello World”.

```csharp
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
```

Esta linha de código adiciona um fragmento de texto à primeira página do seu PDF. É como escrever um título no topo da sua página!

## Etapa 5: Crie JavaScript para Data de Expiração

Agora vem a parte divertida! Você criará uma ação JavaScript que verificará a data de expiração do PDF. Se a data atual exceder a data de expiração, uma mensagem alertará o usuário.

```csharp
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");
```

Veja o que está acontecendo:
- Você define o ano e o mês de expiração.
- Você recebe a data de hoje.
- Você compara a data de hoje com a data de validade.
- Se a data de hoje estiver ultrapassada, uma mensagem aparecerá!

## Etapa 6: Defina JavaScript como ação de abertura de PDF

Agora, você precisa definir a ação JavaScript como a ação de abertura para seu documento PDF. Isso significa que o JavaScript será executado assim que o PDF for aberto.

```csharp
doc.OpenAction = javaScript;
```

Esta linha diz ao PDF para executar o JavaScript quando alguém o abrir. É como definir um lembrete que dispara assim que você abre seu calendário!

## Etapa 7: Salve o documento PDF

Por fim, é hora de salvar seu documento PDF com o recurso de data de validade. 

```csharp
dataDir = dataDir + "SetExpiryDate_out.pdf";
doc.Save(dataDir);
```

Esta linha salva seu PDF no diretório especificado com o nome "SetExpiryDate_out.pdf". É como colocar sua arte finalizada em uma moldura!

## Conclusão

E aí está! Você criou com sucesso um arquivo PDF com uma data de expiração usando o Aspose.PDF para .NET. Esse recurso não só aumenta a segurança, mas também garante que informações confidenciais sejam mantidas sob controle. Não importa se você está enviando contratos, relatórios ou quaisquer outros documentos importantes, definir uma data de expiração pode mudar o jogo.

## Perguntas frequentes

### O que é Aspose.PDF para .NET?
Aspose.PDF para .NET é uma biblioteca poderosa que permite aos desenvolvedores criar, manipular e converter documentos PDF em aplicativos .NET.

### Posso usar o Aspose.PDF gratuitamente?
 Sim, você pode usar uma versão de teste gratuita do Aspose.PDF. Você pode baixá-lo[aqui](https://releases.aspose.com/).

### Como faço para comprar o Aspose.PDF?
Você pode comprar Aspose.PDF visitando o[página de compra](https://purchase.aspose.com/buy).

### E se eu precisar de suporte?
Se você tiver alguma dúvida ou precisar de ajuda, você pode visitar o[Fórum de suporte Aspose](https://forum.aspose.com/c/pdf/10).

### Posso obter uma licença temporária para o Aspose.PDF?
 Sim, você pode solicitar uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/).