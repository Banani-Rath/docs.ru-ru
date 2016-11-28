---
title: "&lt;значение&gt; (Visual Basic) | Microsoft Docs"
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
  - "<value> - XML-тег"
  - "value - XML-тег"
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# &lt;значение&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Указывает описание свойства.  
  
## Синтаксис  
  
```  
<value>property-description</value>  
```  
  
#### Параметры  
 `property-description`  
 Описание свойства.  
  
## Заметки  
 Используйте тег `<value>` для описания свойства.  Обратите внимание, что при добавлении свойства с помощью мастера создания кода в среде разработки Visual Studio для нового свойства будет добавлен тег [\<summary\>](../../../visual-basic/language-reference/xmldoc/summary.md).  Следует затем вручную добавить тег `<value>` для описания значения, которое представляет свойство.  
  
 Чтобы выделить документирующие комментарии в отдельный файл, необходимо использовать при компиляции параметр [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
## Пример  
 В данном примере используется тег `<value>` для описания того, какое значение содержится в свойстве `Counter`.  
  
 [!CODE [VbVbcnXmlDocComments#1](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnXmlDocComments#1)]  
  
## См. также  
 [XML\-теги для комментариев](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)