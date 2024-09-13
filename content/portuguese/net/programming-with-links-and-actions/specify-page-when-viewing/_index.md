---
title: Especificar página ao visualizar
linktitle: Especificar página ao visualizar
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda como especificar uma página para visualizar em um PDF usando Aspose.PDF para .NET. Melhore a navegação do usuário com este guia simples.
type: docs
weight: 110
url: /pt/net/programming-with-links-and-actions/specify-page-when-viewing/
---
## Introdução

Você está procurando aprimorar seus aplicativos PDF direcionando usuários para páginas específicas ao abrir um documento? Você veio ao lugar certo! Neste guia, vamos nos aprofundar nos detalhes do uso do Aspose.PDF para .NET para especificar a página que deve ser exibida quando um PDF é aberto. Essa funcionalidade pode melhorar significativamente a experiência do usuário, especialmente quando você precisa chamar a atenção para seções críticas do seu documento.

## Pré-requisitos

Antes de mergulhar na codificação, vamos garantir que você tenha tudo o que precisa para começar. Aqui está o que você vai precisar:

1. Conhecimento básico de .NET: Familiaridade com o framework .NET é essencial. Se você se sente confortável com C# e tem um entendimento básico de programação orientada a objetos, você está pronto!

2.  Aspose.PDF para .NET: Você precisará ter a biblioteca Aspose.PDF instalada em seu projeto. Se você ainda não a instalou, você pode baixá-la[aqui](https://releases.aspose.com/pdf/net/).

3. Visual Studio: Este tutorial pressupõe que você esteja usando o Visual Studio como seu IDE. Certifique-se de tê-lo instalado em sua máquina.

4. Um arquivo PDF: Você precisará de um arquivo PDF existente com o qual trabalhará. Se não tiver um, você pode criar um documento de amostra ou usar qualquer PDF de sua escolha.

Depois de cumprir esses pré-requisitos, podemos arregaçar as mangas e começar a programar!

## Pacotes de importação

Agora que estamos todos configurados, vamos importar os pacotes necessários para o nosso projeto. Siga estes passos:

### Iniciar o Visual Studio

Abra o Visual Studio e crie um novo projeto ou carregue um existente onde você deseja implementar a funcionalidade de visualização de páginas em PDF.

### Referência Aspose.PDF

Para usar a biblioteca Aspose.PDF, você precisa adicionar uma referência a ela:

1. Clique com o botão direito do mouse no seu projeto no Solution Explorer.
2. Selecione 'Gerenciar pacotes NuGet'.
3.  Procurar`Aspose.PDF` e instale o pacote.

### Importar namespaces

Adicione a seguinte diretiva using no topo do seu arquivo de código:

```csharp
using System;
using System.IO;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
```

Agora, você está pronto para começar a criar a lógica de navegação da sua página em PDF!

Vamos dividir nossa tarefa em etapas gerenciáveis. Escreveremos um código que abre um documento PDF, especifica uma página específica a ser exibida na visualização e salva o documento atualizado. 

## Etapa 1: Defina o diretório de documentos

Primeiro, você precisa definir o caminho para seus documentos:

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Substitua pelo seu diretório
```

 Esta linha é essencialmente seu roteiro. Você está dizendo ao seu código onde encontrar o arquivo PDF. Certifique-se de substituir`YOUR DOCUMENT DIRECTORY` com o caminho real na sua máquina.

## Etapa 2: Carregue o arquivo PDF

Em seguida, você carregará o arquivo PDF em seu aplicativo:

```csharp
// Carregue o arquivo PDF
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
```

 O que está acontecendo aqui é que você está criando uma nova instância de um`Document`objeto ao especificar o caminho para seu arquivo PDF. Você pode pensar nisso como abrir o livro que você acabou de colocar na mesa.

## Etapa 3: Acesse a página desejada

Agora, vamos acessar a página que você deseja exibir quando o documento for aberto:

```csharp
// Obter a instância da segunda página do documento
Page page2 = doc.Pages[2]; // Lembre-se, a indexação começa em 1
```

Aqui, estamos acessando a segunda página do seu documento. Vale a pena notar que a numeração de páginas começa em 1 neste contexto, então se você está pensando na página 2, precisa usar um índice de 2.

## Etapa 4: Defina o fator de zoom

Você pode ajustar o nível de zoom da página que será exibida:

```csharp
// Crie a variável para definir o fator de zoom da página de destino
double zoom = 1; // 1 significa zoom de 100%
```

Definir um fator de zoom ajuda a determinar quanto da página o usuário vê imediatamente ao abrir. Um valor de 1 significa que a página será exibida com zoom de 100%, o que geralmente é um bom padrão.

## Etapa 5: Crie a instância GoToAction

Vamos colocar os recursos de navegação em ação:

```csharp
// Criar instância GoToAction
GoToAction action = new GoToAction(doc.Pages[2]); 
```

 Nesta etapa, você está criando uma instância de`GoToAction` que representa essencialmente a ação de navegar até um ponto específico no PDF – neste caso, a segunda página.

## Etapa 6: Defina o destino

Agora, você precisa definir para onde a ação deve levar:

```csharp
// Ir para a página 2
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
```

Esta linha é como definir um destino de GPS para o GoToAction. Você está dizendo para ele ir para a página 2 no topo da página (altura) e no nível de zoom especificado.

## Etapa 7: Defina a ação aberta

Vamos garantir que esta ação ocorra quando o documento for aberto:

```csharp
// Defina a ação de abertura do documento
doc.OpenAction = action;
```

Com isso, você declarou que quando seu PDF for aberto, a ação de navegação que acabamos de definir será ativada. É como se você tivesse colocado o capacho de boas-vindas na porta da frente do seu documento.

## Etapa 8: Salve o documento atualizado

Por fim, vamos salvar o documento com as alterações feitas:

```csharp
// Salvar documento atualizado
doc.Save(dataDir + "goto2page_out.pdf");
```

Esta etapa finaliza seu trabalho! Você terá um novo arquivo PDF chamado`goto2page_out.pdf` que abre diretamente para a página que você especificou.

Com isso, a parte de codificação está completa! Você programou com sucesso o Aspose.PDF para mostrar uma página específica quando um PDF é aberto. 

## Conclusão

Neste guia, adotamos uma abordagem passo a passo para entender como especificar uma página em um arquivo PDF usando o Aspose.PDF para .NET. Essa funcionalidade não apenas melhora a navegação para seus usuários, mas também simplifica a interação deles com conteúdo crucial em seus documentos. Ao adotar esses recursos, você está criando uma experiência mais amigável que pode diferenciar seus aplicativos PDF.

## Perguntas frequentes

### O que é Aspose.PDF para .NET?
Aspose.PDF para .NET é uma biblioteca que permite aos desenvolvedores criar, modificar e gerenciar documentos PDF em aplicativos .NET.

### Posso especificar várias páginas para serem visualizadas?
Não, você só pode definir o documento para abrir em uma página específica. No entanto, você pode criar documentos diferentes para páginas iniciais diferentes.

### se eu quiser visualizar uma página em um nível de zoom diferente?
 Você pode alterar o nível de zoom ajustando o`zoom` variável antes de salvar o documento.

### Onde posso encontrar mais exemplos de uso do Aspose.PDF?
 Você pode verificar o[documentação](https://reference.aspose.com/pdf/net/) para mais exemplos e funcionalidades.

### Existe uma versão de avaliação gratuita disponível para o Aspose.PDF para .NET?
 Sim! Você pode baixar uma versão de teste gratuita do Aspose.PDF[aqui](https://releases.aspose.com/).