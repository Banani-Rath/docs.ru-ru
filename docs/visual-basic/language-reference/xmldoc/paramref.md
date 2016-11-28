---
title: "&lt;paramref&gt; (Visual Basic) | Microsoft Docs"
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
  - "<paramref> - XML-тег"
  - "paramref - XML-тег"
ms.assetid: 8979d53b-beb1-41b7-b41e-6bbea1c17a03
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# &lt;paramref&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Форматирует слово как параметр.  
  
## Синтаксис  
  
```  
<paramref name="name"/>  
```  
  
#### Параметры  
 `name`  
 Имя параметра, на который нужна ссылка.  Заключите имя в двойные кавычки \(" "\).  
  
## Заметки  
 Тег `<paramref>` дает возможность указать, что слово — это параметр.  Чтобы форматировать этот параметр некоторым конкретным образом, может быть обработан XML\-файл.  
  
 Чтобы выделить документирующие комментарии в отдельный файл, необходимо использовать при компиляции параметр [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
## Пример  
 В этом примере тег `<paramref>` используется для ссылки на параметр `id`.  
  
 [!CODE [VbVbcnXmlDocComments#6](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnXmlDocComments#6)]  
  
## См. также  
 [XML\-теги для комментариев](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)