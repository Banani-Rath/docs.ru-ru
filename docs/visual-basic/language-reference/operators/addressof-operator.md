---
title: "Оператор AddressOf (Visual Basic) | Microsoft Docs"
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
  - "AddressOf"
  - "vb.AddressOf"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "адреса, передача API-процедурам"
  - "AddressOf - оператор"
ms.assetid: 8105a59d-60d8-4ab5-b221-5899cdfacbf4
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Оператор AddressOf (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Создает экземпляр делегата процедуры, ссылающийся на указанную процедуру.  
  
## Синтаксис  
  
```  
  
AddressOf procedurename  
```  
  
## Части  
 `procedurename`  
 Обязательный.  Указывает процедуру, на которую указывает созданный делегат процедуры.  
  
## Заметки  
 Оператор `AddressOf` создает делегат функции, указывая на функцию, заданную при помощи `procedurename`.  Если указанная процедура является методом экземпляра, то делегат функции ссылается и на экземпляр, и на метод.  Затем при вызове указанного делегата функции вызывается указанный метод или экземпляр.  
  
 Оператор `AddressOf` используется как операнд конструктора делегата, либо его можно использовать в контексте, в котором тип делегата определяется компилятором.  
  
## Пример  
 В данном примере оператор `AddressOf` применяется, чтобы назначить делегат для обработки события `Click` кнопки.  
  
 [!CODE [VbVbalrDelegates#8](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrDelegates#8)]  
  
## Пример  
 В следующем примере оператор `AddressOf` используется, чтобы назначить функцию запуска для потока.  
  
 [!CODE [VbVbalrDelegates#9](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrDelegates#9)]  
  
## См. также  
 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)   
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Делегаты](../../../visual-basic/programming-guide/language-features/delegates/delegates.md)