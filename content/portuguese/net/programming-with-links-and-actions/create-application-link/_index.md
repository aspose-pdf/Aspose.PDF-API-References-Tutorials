---
title: Criar link de aplicativo em arquivo PDF
linktitle: Criar link de aplicativo em arquivo PDF
second_title: Referência da API Aspose.PDF para .NET
description: Crie facilmente links de aplicativos em arquivo PDF com Aspose.PDF para .NET.
type: docs
weight: 20
url: /pt/net/programming-with-links-and-actions/create-application-link/
---
Criar um link de aplicativo em arquivo PDF permite criar links para aplicativos externos, como arquivos executáveis ou URLs. Com Aspose.PDF for .NET, você pode criar links de aplicativos facilmente seguindo o seguinte código-fonte:

## Etapa 1: importar as bibliotecas necessárias

Antes de começar, você precisa importar as bibliotecas necessárias para seu projeto C#. Aqui está a diretiva de importação necessária:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.InteractiveFeatures;
```

## Etapa 2: definir o caminho para a pasta de documentos

 Nesta etapa, você precisa especificar o caminho para a pasta que contém o arquivo PDF ao qual deseja adicionar um link de aplicativo. Substituir`"YOUR DOCUMENT DIRECTORY"`no código a seguir com o caminho real para sua pasta de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passo 3: Abra o documento PDF

Agora abriremos o documento PDF ao qual queremos adicionar um link de aplicativo usando o seguinte código:

```csharp
Document document = new Document(dataDir + "CreateApplicationLink.pdf");
```

## Etapa 4: crie o link do aplicativo

 Nesta etapa, criaremos o link do aplicativo usando o`LinkAnnotation`anotação. Especificaremos as coordenadas e a área do link, bem como a ação de lançamento do aplicativo. Aqui está o código correspondente:

```csharp
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link. Action = new LaunchAction(document, dataDir + "CreateApplicationLink.pdf");
page.Annotations.Add(link);
```

## Etapa 5: salve o arquivo atualizado

 Agora vamos salvar o arquivo PDF atualizado usando o`Save` método do`document` objeto. Aqui está o código correspondente:

```csharp
dataDir = dataDir + "CreateApplicationLink_out.pdf";
document. Save(dataDir);
```

### Exemplo de código-fonte para criar link de aplicativo usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document document = new Document( dataDir + "CreateApplicationLink.pdf");
// Criar link
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link.Action = new LaunchAction(document, dataDir + "CreateApplicationLink.pdf");
page.Annotations.Add(link);
dataDir = dataDir + "CreateApplicationLink_out.pdf";
// Salvar documento atualizado
document.Save(dataDir);
Console.WriteLine("\nApplication link created successfully.\nFile saved at " + dataDir);
```

## Conclusão

Parabéns! Agora você tem um guia passo a passo para criar links de aplicativos com Aspose.PDF for .NET. Você pode usar este código para adicionar links para aplicativos externos em seus documentos PDF.

Certifique-se de verificar a documentação oficial do Aspose.PDF para obter mais informações sobre os recursos avançados de links interativos.

### Perguntas frequentes para criar link de aplicativo em arquivo PDF

#### P: O que são links de aplicativos em arquivos PDF?

R: Links de aplicativos em arquivos PDF permitem criar links que abrem aplicativos externos, como arquivos executáveis ou URLs, quando clicados. Esse recurso aprimora a interatividade e fornece uma maneira conveniente de conectar usuários a recursos externos.

#### P: Como o Aspose.PDF for .NET facilita a criação de links de aplicativos?

R: Aspose.PDF for .NET simplifica o processo de criação de links de aplicativos, fornecendo um conjunto abrangente de ferramentas e APIs. O tutorial passo a passo fornecido neste guia demonstra como adicionar links de aplicativos aos seus documentos PDF.

#### P: Posso personalizar a aparência dos links do aplicativo?

R: Absolutamente! Com Aspose.PDF for .NET, você tem controle sobre a aparência dos links do aplicativo. Você pode especificar atributos como cor, estilo e efeitos de foco para garantir uma experiência do usuário visualmente atraente.

#### P: Há alguma restrição quanto aos tipos de aplicativos externos aos quais posso vincular?

R: Aspose.PDF for .NET permite vincular a uma variedade de aplicativos externos, incluindo arquivos executáveis, URLs e documentos. No entanto, é importante considerar a segurança e a compatibilidade do usuário ao vincular arquivos executáveis.

#### P: Como posso verificar se os links do meu aplicativo estão funcionando corretamente?

R: Seguindo as instruções do tutorial e usando o código de exemplo fornecido, você pode criar links de aplicativos funcionais com segurança. Você pode então testar os links abrindo o documento PDF gerado e clicando nos links do aplicativo.

#### P: Posso criar vários links de aplicativos em um único documento PDF?

 R: Sim, você pode criar vários links de aplicativos em um único documento PDF usando o`LinkAnnotation` anotação. Isso permite fornecer aos usuários acesso a diferentes aplicativos externos em várias seções do documento.

#### P: Há alguma consideração de segurança ao usar links de aplicativos?
R: Ao vincular arquivos executáveis, é importante garantir que os aplicativos vinculados sejam seguros e confiáveis. Além disso, considere as permissões do usuário e informe-os sobre o possível lançamento de aplicativos externos.

#### P: Como adiciono links de aplicativos a URLs ou páginas da web?

R: Embora este tutorial se concentre na criação de links para aplicativos externos, o Aspose.PDF for .NET também oferece suporte à criação de hiperlinks para URLs ou páginas da web. Você pode adaptar o código fornecido para criar links da web em seus documentos PDF.

#### P: Posso usar o Aspose.PDF for .NET para extrair informações de aplicativos externos vinculados?

R: Sim, o Aspose.PDF for .NET fornece recursos para extrair e manipular informações de aplicativos externos vinculados. Você pode explorar os amplos recursos da biblioteca para executar diversas tarefas relacionadas ao conteúdo vinculado.