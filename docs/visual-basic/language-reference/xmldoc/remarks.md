---
title: "&lt;remarks&gt; (Visual Basic) | Microsoft Docs"
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
  - "<remarks> - XML-тег"
  - "remarks - XML-тег"
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# &lt;remarks&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Задает раздел примечаний для члена.  
  
## Синтаксис  
  
```  
<remarks>description</remarks>  
```  
  
#### Параметры  
 `description`  
 Описание члена.  
  
## Заметки  
 Используйте тег `<remarks>`, чтобы добавить сведения о типе, дополняя сведения, указанные в [\<summary\>](../../../visual-basic/language-reference/xmldoc/summary.md) .  
  
 Эта информация отображается в обозревателе объектов.  Дополнительные сведения об обозревателе объектов см. в разделе [Просмотр структуры кода](/visual-studio/ide/viewing-the-structure-of-code).  
  
 Чтобы выделить документирующие комментарии в отдельный файл, необходимо использовать при компиляции параметр [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
## Пример  
 В этом примере используется тег `<remarks>`, чтобы объяснить, что делает метод `UpdateRecord`.  
  
 [!CODE [VbVbcnXmlDocComments#6](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnXmlDocComments#6)]  
  
## См. также  
 [XML\-теги для комментариев](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)