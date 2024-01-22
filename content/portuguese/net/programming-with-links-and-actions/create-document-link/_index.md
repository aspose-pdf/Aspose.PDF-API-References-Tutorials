---
title: Criar link de documento
linktitle: Criar link de documento
second_title: Referência da API Aspose.PDF para .NET
description: Crie facilmente links para outros documentos PDF com Aspose.PDF for .NET.
type: docs
weight: 30
url: /pt/net/programming-with-links-and-actions/create-document-link/
---
Vincular a outro documento em um arquivo PDF permite criar links clicáveis que redirecionam os usuários para outros documentos PDF. Com Aspose.PDF for .NET, você pode criar facilmente esses links seguindo o seguinte código-fonte:

## Etapa 1: importar as bibliotecas necessárias

Antes de começar, você precisa importar as bibliotecas necessárias para seu projeto C#. Aqui está a diretiva de importação necessária:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.InteractiveFeatures;
```

## Etapa 2: definir o caminho para a pasta de documentos

Nesta etapa, você precisa especificar o caminho para a pasta que contém o arquivo PDF ao qual deseja adicionar um link para outro documento. Substituir`"YOUR DOCUMENT DIRECTORY"`no código a seguir com o caminho real para sua pasta de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passo 3: Abra o documento PDF

Agora abriremos o documento PDF ao qual queremos adicionar o link para outro documento usando o seguinte código:

```csharp
Document document = new Document(dataDir + "CreateDocumentLink.pdf");
```

## Etapa 4: crie o link para outro documento

 Nesta etapa, criaremos o link para outro documento usando o`LinkAnnotation` anotação. Especificaremos as coordenadas e a área do link, bem como a ação de navegação para um documento externo. Aqui está o código correspondente:

```csharp
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link. Action = new GoToRemoteAction(dataDir + "RemoveOpenAction.pdf", 1);
page.Annotations.Add(link);
```

## Etapa 5: salve o arquivo atualizado

 Agora vamos salvar o arquivo PDF atualizado usando o`Save` método do`document` objeto. Aqui está o código correspondente:

```csharp
dataDir = dataDir + "CreateDocumentLink_out.pdf";
document. Save(dataDir);
```

### Exemplo de código-fonte para criar link de documento usando Aspose.PDF para .NET 
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

Parabéns! Agora você tem um guia passo a passo para vincular a outros documentos com Aspose.PDF for .NET. Você pode usar esse código para criar links clicáveis em seus arquivos PDF, redirecionando os usuários para outros documentos.

Certifique-se de verificar a documentação oficial do Aspose.PDF para obter mais informações sobre os recursos avançados de links interativos.

### Perguntas frequentes sobre como criar link de documento

#### P: O que são links de documentos em arquivos PDF?

R: Os links de documentos em arquivos PDF são links clicáveis que direcionam os usuários para outros documentos PDF. Esses links melhoram a navegação, fornecendo uma maneira eficiente de conectar conteúdo relacionado e facilitando uma experiência de leitura perfeita.

#### P: Como posso me beneficiar da criação de links de documentos?

R: A criação de links de documentos permite estabelecer conexões entre diferentes seções ou tópicos em seus documentos PDF. Este recurso permite que os usuários acessem informações complementares ou materiais relacionados com facilidade.

#### P: Como o Aspose.PDF for .NET oferece suporte à criação de links de documentos?

R: Aspose.PDF for .NET simplifica o processo de criação de links de documentos, fornecendo um conjunto abrangente de APIs. O tutorial passo a passo descrito neste guia demonstra como adicionar links de documentos aos seus arquivos PDF.

#### P: Posso personalizar a aparência dos links de documentos?

R: Absolutamente! Aspose.PDF for .NET oferece opções de personalização para a aparência do link do documento, incluindo cor, estilo e efeitos de foco. Você pode personalizar a aparência para combinar com o design do seu documento.

#### P: É possível vincular seções ou páginas específicas em outro documento?

R: Sim, você pode criar links que conduzam os usuários a páginas ou seções específicas de outro documento PDF. Aspose.PDF for .NET oferece flexibilidade para definir o local de destino no documento vinculado.

#### P: Como posso garantir que os links dos meus documentos estejam funcionais?

R: Seguindo o tutorial fornecido e o código de exemplo, você pode criar links de documentos funcionais com segurança. Você pode testar os links abrindo o documento PDF gerado e clicando nos links.

#### P: Posso criar vários links de documentos em um único arquivo PDF?

 R: Certamente! Você pode criar vários links de documentos em um único documento PDF usando o`LinkAnnotation`anotação. Isso permite que você forneça aos usuários acesso a vários documentos relacionados em diferentes seções.

#### P: Há alguma limitação ao vincular documentos externos?

R: Ao vincular documentos externos, certifique-se de que os documentos vinculados estejam acessíveis e localizados nos caminhos especificados. Também é importante considerar as permissões do usuário e a compatibilidade dos documentos vinculados.

#### P: Posso vincular documentos armazenados na Web ou em repositórios on-line?

R: Embora este tutorial se concentre na vinculação a documentos locais, o Aspose.PDF for .NET também oferece suporte à vinculação a URLs da web ou repositórios online. Você pode adaptar o código fornecido para criar links de documentos baseados na web.