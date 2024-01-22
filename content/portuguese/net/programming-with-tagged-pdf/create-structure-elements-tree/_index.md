---
title: Criar árvore de elementos estruturais
linktitle: Criar árvore de elementos estruturais
second_title: Referência da API Aspose.PDF para .NET
description: Crie uma estrutura de elementos de árvore usando Aspose.PDF for .NET. Guia passo a passo para criar um documento PDF estruturado.
type: docs
weight: 70
url: /pt/net/programming-with-tagged-pdf/create-structure-elements-tree/
---
Neste guia passo a passo, explicaremos o código-fonte em C# para criar uma estrutura de elementos de árvore usando Aspose.PDF para .NET. Mostraremos como criar um documento PDF com elementos estruturados e como organizá-los hierarquicamente. O uso da biblioteca Aspose.PDF simplifica muito a manipulação de elementos PDF e fornece funcionalidades avançadas para trabalhar com documentos estruturados.

## Passo 1: Configurando o ambiente
 Antes de começar, certifique-se de configurar seu ambiente de desenvolvimento com Aspose.PDF for .NET. Certifique-se também de ter o caminho para o diretório de documentos definido no`dataDir` variável.

## Passo 2: Criando um Documento PDF
 Para começar, criaremos um novo documento PDF usando o`Document` aula fornecida por Aspose.PDF. Aqui está o código para esta etapa:

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Crie um documento PDF
Document document = new Document();
```

## Etapa 3: fazer com que o conteúdo funcione com o TaggedPdf
 A biblioteca Aspose.PDF permite trabalhar com documentos PDF estruturados usando o conceito de Tagged PDF. Para isso, precisamos obter uma referência ao item de conteúdo marcado usando o documento`TaggedContent`propriedade. Aqui está o código para esta etapa:

```csharp
// Faça o conteúdo funcionar com TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;
```

## Etapa 4: definir o título e o idioma do documento
 Antes de começarmos a criar a estrutura dos elementos, precisamos definir o título e o idioma do documento. Isto pode ser feito usando o`SetTitle` e`SetLanguage` métodos do`taggedContent` objeto. Aqui está o código para esta etapa:

```csharp
// Defina o título e o idioma do documento
taggedContent.SetTitle("Structured PDF Document");
taggedContent.SetLanguage("fr-FR");
```

## Etapa 5: Criando Elementos de Estrutura Lógica
Agora que configuramos nosso documento e definimos o título e o idioma, podemos começar a criar elementos de estrutura lógica. Esses elementos serão organizados hierarquicamente para formar a árvore da estrutura. Aqui está o código para esta etapa:

```csharp
// Obtenha o elemento da estrutura raiz (Documento)
StructureElement rootElement = taggedContent.RootElement;

// Crie a estrutura lógica
SectElement sect1 = taggedContent.CreateSectElement();
rootElement.AppendChild(sect1);

SectElement sect2 = taggedContent.CreateSectElement();
rootElement.AppendChild(sect2);

DivElement div11 = taggedContent.CreateDivElement();
sect1.AppendChild(div11);

DivElement div12 = taggedContent.CreateDivElement();
sect1.AppendChild(div12);

ArtElement art21 = taggedContent.CreateArtElement();
sect2.AppendChild(art21);

ArtElement art22

  = taggedContent.CreateArtElement();
sect2.AppendChild(art22);

DivElement div211 = taggedContent.CreateDivElement();
art21.AppendChild(div211);

DivElement div212 = taggedContent.CreateDivElement();
art21.AppendChild(div212);

DivElement div221 = taggedContent.CreateDivElement();
art22.AppendChild(div221);

DivElement div222 = taggedContent.CreateDivElement();
art22.AppendChild(div222);

SectElement sect3 = taggedContent.CreateSectElement();
rootElement.AppendChild(sect3);

DivElement div31 = taggedContent.CreateDivElement();
sect3.AppendChild(div31);
```

## Passo 6: Salvando o documento PDF marcado
 Depois de criar a estrutura do elemento, podemos salvar o documento PDF. Use o`Save` método do`document` objeto para especificar o caminho e o nome do arquivo PDF a ser salvo. Aqui está o código para esta etapa:

```csharp
// Salve o documento PDF marcado
document.Save(dataDir + "StructureElementsTree.pdf");
```

### Exemplo de código-fonte para criar árvore de elementos estruturais usando Aspose.PDF para .NET 
```csharp

// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Criar documento PDF
Document document = new Document();
// Obtenha conteúdo para trabalhar com TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;
// Definir título e idioma para Documnet
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");
// Obtenha o elemento da estrutura raiz (documento)
StructureElement rootElement = taggedContent.RootElement;
// Criar estrutura lógica
SectElement sect1 = taggedContent.CreateSectElement();
rootElement.AppendChild(sect1);
SectElement sect2 = taggedContent.CreateSectElement();
rootElement.AppendChild(sect2);
DivElement div11 = taggedContent.CreateDivElement();
sect1.AppendChild(div11);
DivElement div12 = taggedContent.CreateDivElement();
sect1.AppendChild(div12);
ArtElement art21 = taggedContent.CreateArtElement();
sect2.AppendChild(art21);
ArtElement art22 = taggedContent.CreateArtElement();
sect2.AppendChild(art22);
DivElement div211 = taggedContent.CreateDivElement();
art21.AppendChild(div211);
DivElement div212 = taggedContent.CreateDivElement();
art21.AppendChild(div212);
DivElement div221 = taggedContent.CreateDivElement();
art22.AppendChild(div221);
DivElement div222 = taggedContent.CreateDivElement();
art22.AppendChild(div222);
SectElement sect3 = taggedContent.CreateSectElement();
rootElement.AppendChild(sect3);
DivElement div31 = taggedContent.CreateDivElement();
sect3.AppendChild(div31);
// Salvar documento PDF marcado
document.Save(dataDir + "StructureElementsTree.pdf");

```

## Conclusão
Você aprendeu como criar uma estrutura de elementos de árvore usando Aspose.PDF for .NET. Este guia mostrou as etapas necessárias para configurar um documento PDF, criar elementos de estrutura lógica e salvar o documento final. Ao usar Aspose.PDF, você pode manipular facilmente elementos PDF e criar documentos estruturados.

### Perguntas frequentes

#### P: Qual é o propósito de criar uma estrutura de elementos de árvore em um documento PDF usando Aspose.PDF for .NET?

R: Criar uma estrutura de elementos de árvore em um documento PDF usando Aspose.PDF for .NET permite organizar o conteúdo hierarquicamente. Essa abordagem estruturada melhora a acessibilidade, a navegação e a semântica dos documentos, facilitando a interpretação e a interação dos usuários e das tecnologias assistivas com o conteúdo.

#### P: Como o código C# fornecido cria uma estrutura de elementos de árvore em um documento PDF?

R: O exemplo de código demonstra como criar uma estrutura hierárquica de elementos lógicos usando o`SectElement`, `DivElement` , e`ArtElement` aulas fornecidas por Aspose.PDF. Esses elementos são organizados como nós pai e filho, formando uma estrutura semelhante a uma árvore dentro do documento.

####  P: Como é que`TaggedContent` property of the `Document` class contribute to creating a structured PDF document?

 R: O`TaggedContent` propriedade fornece acesso aos recursos de conteúdo marcado do documento PDF. Isso permite criar e manipular elementos estruturados, definir seus relacionamentos e organizá-los hierarquicamente, melhorando a estrutura e a acessibilidade do documento.

####  P: Por que é importante definir o título e o idioma do documento usando o`SetTitle` and `SetLanguage` methods?

 R: Definir o título e o idioma do documento usando o`SetTitle` e`SetLanguage` métodos aprimora a acessibilidade e a semântica do documento. Ajuda os usuários e as tecnologias assistivas a compreender o propósito e a linguagem do documento.

####  P: Como estão`SectElement`, `DivElement`, and `ArtElement` used to create the structure tree?

 R: Essas classes representam diferentes tipos de elementos estruturais.`SectElement` é usado para criar seções,`DivElement` para divisões dentro de seções, e`ArtElement` para obras de arte ou ilustrações. Ao anexar elementos filhos aos elementos pais, você estabelece uma estrutura hierárquica.

#### P: Quais são os benefícios de organizar elementos hierarquicamente em um documento PDF?

R: A organização hierárquica dos elementos melhora a organização, a navegação e a semântica dos documentos. Ele permite que usuários e tecnologias assistivas compreendam a estrutura e os relacionamentos do conteúdo, melhorando a experiência geral do usuário.

####  P: Como é que`Save` method ensure the preservation of the hierarchical structure in the tagged PDF document?

 R: O`Save` método salva o documento PDF junto com a estrutura hierárquica criada usando o`AppendChild` método. Isso garante que a estrutura permaneça intacta, tornando o documento acessível e bem organizado.

#### P: Posso personalizar ainda mais a árvore de estrutura adicionando outros tipos de elementos lógicos?

R: Sim, você pode personalizar ainda mais a árvore de estrutura adicionando outros tipos de elementos lógicos fornecidos pelo Aspose.PDF, como cabeçalhos, parágrafos, figuras e muito mais. Você pode experimentar diferentes tipos de elementos para criar uma estrutura personalizada.

#### P: Como a árvore estruturada criada pode melhorar a acessibilidade e usabilidade dos documentos?

R: A árvore estruturada melhora a acessibilidade do documento, fornecendo uma hierarquia clara e um significado semântico ao conteúdo. As tecnologias assistivas e os usuários podem navegar, compreender e interpretar a estrutura e os relacionamentos do documento de forma mais eficaz.

#### P: Como posso aplicar esse conhecimento para criar documentos PDF estruturados complexos para vários casos de uso?

R: Você pode desenvolver esse conhecimento combinando diferentes tipos de elementos estruturais e organizando-os hierarquicamente para corresponder à organização de conteúdo desejada. Essa abordagem é valiosa para a criação de documentos complexos, como relatórios, artigos, manuais e muito mais.