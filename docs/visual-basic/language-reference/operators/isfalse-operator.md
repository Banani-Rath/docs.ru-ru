---
title: "Оператор IsFalse (Visual Basic) | Microsoft Docs"
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
  - "vb.isfalse"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "AndAlso - оператор"
  - "IsFalse - оператор"
ms.assetid: 37fc9dbf-e5cc-4570-b93f-7213447974df
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Оператор IsFalse (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Определяет, является ли выражение `False`.  
  
 Нельзя вызывать `IsFalse` явно в коде, но компилятор Visual Basic может использовать это для создания кода из предложений `AndAlso`.  Если определяется класс или структура, а затем используется переменная этого типа в предложении `AndAlso`, необходимо определить `IsFalse` на этом классе или структуре.  
  
 Компилятор рассматривает операторы `IsFalse` и `IsTrue` как  *соответствующие пары* .  Это означает, что если определить один из них, необходимо также определить другой.  
  
> [!NOTE]
>  Оператор `IsFalse` может быть  *перегруженным* , это означает, что класс или структура может переопределить его поведение, если его операнд имеет тип этого класса или структуры.  Если в коде используется этот оператор для такого класса или структуры, убедитесь, что его переопределенное поведение вам понятно.  Дополнительные сведения см. в разделе [Процедуры операторов](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Пример  
 В следующем примере кода определяется контур структуры, содержащей определения для операторов `IsFalse` и `IsTrue`.  
  
 [!CODE [VbVbalrOperators#28](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOperators#28)]  
  
## См. также  
 [Оператор IsTrue](../../../visual-basic/language-reference/operators/istrue-operator.md)   
 [Практическое руководство. Определение оператора](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)   
 [Оператор AndAlso](../../../visual-basic/language-reference/operators/andalso-operator.md)