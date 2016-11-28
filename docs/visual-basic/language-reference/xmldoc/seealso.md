---
title: "&lt;seealso&gt; (Visual Basic) | Microsoft Docs"
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
  - "<seealso> - XML-тег"
  - "seealso - XML-тег"
ms.assetid: 36050c95-1af2-4284-b9b6-1a70691ed978
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# &lt;seealso&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Указывает ссылку, которая отображается в разделе "Cм. также".  
  
## Синтаксис  
  
```  
<seealso cref="member"/>  
```  
  
#### Параметры  
 `member`  
 Ссылка на член или поле, которое может вызываться из текущей среды компиляции.  Компилятор проверяет, существует ли данный элемент кода и передает ли он `member` имени элемента в выходных XML\-данных.  `member` необходимо заключать в двойные кавычки \(" "\).  
  
## Заметки  
 Используйте тег `<seealso>`, чтобы указать текст, который должен отображаться в разделе "См. также".  Используйте [\<see\>](../../../visual-basic/language-reference/xmldoc/see.md), чтобы указать ссылку в тексте  
  
 Чтобы выделить документирующие комментарии в отдельный файл, необходимо использовать при компиляции параметр [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
## Пример  
 Этот пример использует тег `<seealso>` в разделе примечаний `DoesRecordExist` для ссылки на метод `UpdateRecord`.  
  
 [!CODE [VbVbcnXmlDocComments#6](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnXmlDocComments#6)]  
  
## См. также  
 [XML\-теги для комментариев](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)