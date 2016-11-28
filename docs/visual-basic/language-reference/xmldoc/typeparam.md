---
title: "&lt;typeparam&gt; (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "<typeparam> - XML-тег"
  - "typeparam - XML-тег"
ms.assetid: 1bb5ba78-f060-478c-905c-77a2e43639af
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# &lt;typeparam&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Определяет имя и описание параметра типа.  
  
## Синтаксис  
  
```  
<typeparam name="name">description</typeparam>  
```  
  
#### Параметры  
 `name`  
 Имя параметра типа.  Заключите имя в двойные кавычки \(" "\).  
  
 `description`  
 Описание параметра типа.  
  
## Заметки  
 Используйте тег `<typeparam>` в комментарии для базового типа или объявления универсального члена для описания одного из параметров типа.  
  
 Чтобы выделить документирующие комментарии в отдельный файл, необходимо использовать при компиляции параметр [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
## Пример  
 В этом примере тег `<typeparam>` используется для описания параметра `id`.  
  
 [!CODE [VbVbcnXmlDocComments#8](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnXmlDocComments#8)]  
  
## См. также  
 [XML\-теги для комментариев](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)