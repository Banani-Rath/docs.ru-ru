---
title: "Практическое руководство. Преобразование объекта к другому типу в Visual Basic | Microsoft Docs"
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
  - "объекты [Visual Basic], преобразование"
ms.assetid: 60cb5fc7-7ba4-4ab5-9c24-480fa12ddcdc
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Практическое руководство. Преобразование объекта к другому типу в Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Преобразование переменной `Object` в другой тип данных с помощью ключевого слова преобразования, например [Функция CType](../../../../visual-basic/language-reference/functions/ctype-function.md).  
  
## Пример  
 В следующем примере преобразуется переменная `Object` в `Integer` и `String`.  
  
```  
Public Sub objectConversion(ByVal anObject As Object)  
    Dim anInteger As Integer  
    Dim aString As String  
    anInteger = CType(anObject, Integer)  
    aString = CType(anObject, String)  
End Sub  
```  
  
 Если известно, что содержимое переменной `Object` имеет определенный тип данных, желательно преобразовать переменную в этот тип данных.  Если продолжать использовать переменную `Object`, то это вызовет либо *упаковку* и *распаковку* \(для типа значения\), либо *позднюю привязку* \(для ссылочного типа\).  Эти операции требуют большего времени для выполнения и снижают производительность.  
  
## Компиляция кода  
 Для этого примера необходимо следующее.  
  
-   Ссылка на пространство имен <xref:System?displayProperty=fullName>.  
  
## См. также  
 <xref:System.Object>   
 [Преобразование типов в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Расширяющие и сужающие преобразования](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)   
 [Явные и неявные преобразования](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)   
 [Преобразование значений между строковыми и другими типами](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)   
 [Преобразования массивов](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)   
 [Структуры](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Типы данных](../../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Функции преобразования типов](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)