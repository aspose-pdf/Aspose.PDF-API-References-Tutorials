---
title: Especificar página ao visualizar
linktitle: Especificar página ao visualizar
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda como especificar uma página ao visualizar um PDF usando o Aspose.PDF para .NET.
type: docs
weight: 110
url: /pt/net/programming-with-links-and-actions/specify-page-when-viewing/
---
Aprenda como especificar uma página ao visualizar um arquivo PDF usando o Aspose.PDF para .NET com este guia passo a passo.

## Etapa 1: Configurando o ambiente

Certifique-se de ter configurado seu ambiente de desenvolvimento com um projeto C# e as referências Aspose.PDF apropriadas.

## Etapa 2: Carregando o arquivo PDF

Defina o caminho do diretório dos seus documentos e carregue o arquivo PDF usando o seguinte código:

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Carregue o arquivo PDF
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
```

## Etapa 3: Especificando a página de destino

Obtenha a instância da página de destino usando o seguinte código:

```csharp
Page page2 = doc.Pages[2];
```

 Você pode ajustar o índice`[2]` para selecionar a página desejada.

## Etapa 4: Configurando a configuração de zoom

Crie uma variável para definir o fator de zoom da página de destino:

```csharp
double zoom = 1;
```

Você pode ajustar o valor do zoom de acordo com suas necessidades.

## Etapa 5: Crie a ação de navegação

Crie uma instância da ação de navegação usando a página de destino especificada:

```csharp
GoToAction action = new GoToAction(doc.Pages[2]);
```

## Etapa 6: Definir o destino

Defina o destino para ir para a página de destino usando coordenadas e zoom:

```csharp
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
```

## Etapa 7: Configurando a ação de abertura de documento

Defina a ação de abertura do documento com a ação de navegação criada:

```csharp
doc. OpenAction = action;
```

## Etapa 8: Salve o documento atualizado

 Salve o documento atualizado usando o`Save` método:

```csharp
doc.Save(dataDir + "goto2page_out.pdf");
```

### Código-fonte de exemplo para Especificar página ao visualizar usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Carregue o arquivo PDF
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
// Obter a instância da segunda página do documento
Page page2 = doc.Pages[2];
// Crie a variável para definir o fator de zoom da página de destino
double zoom = 1;
// Criar instância GoToAction
GoToAction action = new GoToAction(doc.Pages[2]);
// Ir para a página 2
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
// Defina a ação de abertura do documento
doc.OpenAction = action;
// Salvar documento atualizado
doc.Save(dataDir + "goto2page_out.pdf");
```

## Conclusão

Parabéns! Agora você sabe como especificar uma página ao visualizar um PDF usando o Aspose.PDF for .NET. Use esse conhecimento para personalizar a experiência de visualização do usuário em seus documentos PDF.

Agora que você concluiu este guia, pode aplicar esses conceitos aos seus próprios projetos e explorar ainda mais os recursos oferecidos pelo Aspose.PDF para .NET.

### Perguntas frequentes 

#### P: Qual é o propósito de especificar uma página de destino ao visualizar um arquivo PDF?

R: Especificar uma página de destino permite que você controle qual página de um documento PDF é exibida quando o arquivo é aberto. Isso pode melhorar a experiência do usuário, direcionando-o para uma página específica de interesse.

#### P: Como especificar uma página de destino pode ser útil em documentos PDF?

R: Especificar uma página de destino é benéfico quando você deseja guiar os usuários para uma seção ou conteúdo específico em um documento PDF sem exigir que eles naveguem manualmente pelas páginas.

#### P: Como o Aspose.PDF para .NET facilita a especificação de uma página de destino para visualização?

R: O Aspose.PDF para .NET fornece APIs que permitem definir a visualização inicial de um documento PDF, incluindo a página de destino, o nível de zoom e outras propriedades de exibição.

#### P: Posso especificar qualquer página para ser a página de destino?

R: Sim, você pode especificar qualquer página dentro do documento PDF como a página de destino para visualização. Basta usar o índice apropriado para selecionar a página desejada.

#### P: Qual é a importância do fator de zoom ao especificar uma página de destino?

A: O fator de zoom determina o nível de ampliação aplicado à página de destino quando o documento PDF é aberto. Ele controla quanto conteúdo é exibido dentro da viewport.

#### P: Posso definir diferentes fatores de zoom para diferentes páginas de destino?

R: Sim, você pode definir diferentes fatores de zoom para diferentes páginas de destino criando páginas separadas`GoToAction` instâncias e configurando seus destinos adequadamente.

#### P: Há alguma limitação para especificar uma página de destino?

R: Especificar uma página de destino é limitado a controlar a visualização inicial quando o PDF é aberto. Não afeta as interações do usuário ou a navegação depois que o PDF é exibido.

#### P: Posso usar esse recurso para criar apresentações em um documento PDF?

R: Sim, você pode usar esse recurso para criar experiências semelhantes a apresentações em um documento PDF, guiando os usuários por diferentes seções ou tópicos.

#### P: Posso personalizar outros aspectos da visualização inicial, como o layout da página?

R: Sim, o Aspose.PDF para .NET fornece propriedades para personalizar outros aspectos da visualização inicial, incluindo layout de página, modo de página e muito mais.

#### P: Como posso testar se a página de destino e o fator de zoom especificados estão funcionando conforme o esperado?

R: Depois de aplicar o código fornecido para especificar a página de destino e o fator de zoom, abra o arquivo PDF modificado e verifique se ele abre com a página e o nível de zoom corretos.