---
title: "Исключение комментария XML должно иметь атрибут cref | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc42319"
  - "vbc42319"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC42319"
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Исключение комментария XML должно иметь атрибут cref
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Тег \<exception\> позволяет документировать исключения, которые могут быть созданы методом.  Обязательный атрибут `cref` обозначает имя элемента, которое проверяется генератором документации.  Если элемент существует, его символы переводятся в каноническое имя элемента в файле документации.  
  
 **Идентификатор ошибки:** BC42319  
  
### Чтобы исправить эту ошибку  
  
-   Добавьте атрибут `cref` к исключению следующим образом:  
  
    ```  
    '''<exception cref="member">description</exception>  
    ```  
  
## См. также  
 [\<exception\>](../../../visual-basic/language-reference/xmldoc/exception.md)   
 [Практическое руководство. Создание XML\-документации](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)   
 [XML\-теги для комментариев](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)