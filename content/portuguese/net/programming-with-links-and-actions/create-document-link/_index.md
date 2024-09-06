---
title: Criar link de documento
linktitle: Criar link de documento
second_title: Referência da API do Aspose.PDF para .NET
description: Crie facilmente links para outros documentos PDF com Aspose.PDF para .NET.
type: docs
weight: 30
url: /pt/net/programming-with-links-and-actions/create-document-link/
---
Vincular a outro documento em um arquivo PDF permite que você crie links clicáveis que redirecionam os usuários para outros documentos PDF. Com o Aspose.PDF para .NET, você pode criar facilmente esses links seguindo o seguinte código-fonte:

## Etapa 1: Importar bibliotecas necessárias

Antes de começar, você precisa importar as bibliotecas necessárias para seu projeto C#. Aqui está a diretiva import necessária:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.InteractiveFeatures;
```

## Etapa 2: Defina o caminho para a pasta de documentos

 Nesta etapa, você precisa especificar o caminho para a pasta que contém o arquivo PDF ao qual você deseja adicionar um link para outro documento. Substituir`"YOUR DOCUMENT DIRECTORY"` no código a seguir com o caminho real para sua pasta de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Etapa 3: Abra o documento PDF

Agora abriremos o documento PDF ao qual queremos adicionar o link para outro documento usando o seguinte código:

```csharp
Document document = new Document(dataDir + "CreateDocumentLink.pdf");
```

## Etapa 4: Crie o link para outro documento

 Nesta etapa, criaremos o link para outro documento usando o`LinkAnnotation` anotação. Especificaremos as coordenadas e a área do link, bem como a ação de navegação para um documento externo. Aqui está o código correspondente:

```csharp
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link. Action = new GoToRemoteAction(dataDir + "RemoveOpenAction.pdf", 1);
page.Annotations.Add(link);
```

## Etapa 5: Salve o arquivo atualizado

Agora vamos salvar o arquivo PDF atualizado usando o`Save` método do`document` objeto. Aqui está o código correspondente:

```csharp
dataDir = dataDir + "CreateDocumentLink_out.pdf";
document. Save(dataDir);
```

### Código-fonte de exemplo para criar link de documento usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document document = new Document(dataDir+ "CreateDocumentLink.pdf");
// Criar link
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link.Action = new GoToRemoteAction(dataDir + "RemoveOpenAction.pdf", 1);
page.Annotations.Add(link);
dataDir = dataDir + "CreateDocumentLink_out.pdf";
// Salvar documento atualizado
document.Save(dataDir);
Console.WriteLine("\nDocument link created successfully.\nFile saved at " + dataDir);            
```

## Conclusão

Parabéns! Agora você tem um guia passo a passo para vincular a outros documentos com o Aspose.PDF para .NET. Você pode usar este código para criar links clicáveis em seus arquivos PDF, redirecionando usuários para outros documentos.

Não deixe de conferir a documentação oficial do Aspose.PDF para obter mais informações sobre os recursos avançados dos links interativos.

### Perguntas frequentes sobre como criar link de documento

#### P: O que são links de documentos em arquivos PDF?

A: Os links de documentos em arquivos PDF são links clicáveis que direcionam os usuários para outros documentos PDF. Esses links melhoram a navegação ao fornecer uma maneira eficiente de conectar conteúdo relacionado e facilitar uma experiência de leitura perfeita.

#### P: Como posso me beneficiar da criação de links de documentos?

A: Criar links de documentos permite que você estabeleça conexões entre diferentes seções ou tópicos dentro de seus documentos PDF. Esse recurso permite que os usuários acessem informações suplementares ou materiais relacionados com facilidade.

#### P: Como o Aspose.PDF para .NET oferece suporte à criação de links de documentos?

A: O Aspose.PDF para .NET simplifica o processo de criação de links de documentos ao fornecer um conjunto abrangente de APIs. O tutorial passo a passo descrito neste guia demonstra como adicionar links de documentos aos seus arquivos PDF.

#### P: Posso personalizar a aparência dos links de documentos?

R: Com certeza! O Aspose.PDF para .NET oferece opções de personalização para a aparência do link do documento, incluindo cor, estilo e efeitos de foco. Você pode personalizar a aparência para combinar com o design do seu documento.

#### P: É possível criar links para seções ou páginas específicas dentro de outro documento?

R: Sim, você pode criar links que navegam os usuários para páginas ou seções específicas dentro de outro documento PDF. O Aspose.PDF for .NET fornece a flexibilidade para definir o local de destino dentro do documento vinculado.

#### P: Como posso garantir que meus links de documentos estejam funcionais?

R: Seguindo o tutorial fornecido e o código de exemplo, você pode criar links de documentos funcionais com confiança. Você pode testar os links abrindo o documento PDF gerado e clicando nos links.

#### P: Posso criar vários links de documentos em um único arquivo PDF?

 R: Certamente! Você pode criar vários links de documentos dentro de um único documento PDF usando o`LinkAnnotation` anotação. Isso permite que você forneça aos usuários acesso a vários documentos relacionados de diferentes seções.

#### P: Há alguma limitação ao criar links para documentos externos?

R: Ao vincular a documentos externos, garanta que os documentos vinculados sejam acessíveis e estejam localizados nos caminhos especificados. Também é importante considerar as permissões do usuário e a compatibilidade dos documentos vinculados.

#### P: Posso criar links para documentos armazenados na web ou em repositórios on-line?

R: Embora este tutorial se concentre em vincular a documentos locais, o Aspose.PDF para .NET também oferece suporte a vincular a URLs da Web ou repositórios on-line. Você pode adaptar o código fornecido para criar links de documentos baseados na Web.