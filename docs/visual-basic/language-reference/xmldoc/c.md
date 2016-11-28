---
title: "&lt;c&gt; (Visual&#160;Basic) | Microsoft Docs"
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
  - "<c> - XML-тег"
  - "c - XML-тег"
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# &lt;c&gt; (Visual&#160;Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Указывает, что текст в описании — это код.  
  
## Синтаксис  
  
```  
<c>text</c>  
```  
  
#### Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|`text`|Текст, который нужно было бы представить как код.|  
  
## Заметки  
 Тег `<c>` дает возможность указать, что текст в описании должен быть помечен как код.  Используйте [\<code\>](../../../visual-basic/language-reference/xmldoc/code.md) для указания нескольких строк в качестве кода.  
  
 Чтобы выделить документирующие комментарии в отдельный файл, необходимо использовать при компиляции параметр [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
## Пример  
 Этот пример использует тег `<c>` в сводном разделе для указания, что `Counter` — это код.  
  
 [!CODE [VbVbcnXmlDocComments#1](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnXmlDocComments#1)]  
  
## См. также  
 [XML\-теги для комментариев](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)