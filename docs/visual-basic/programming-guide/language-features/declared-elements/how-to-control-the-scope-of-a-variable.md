---
title: "Практическое руководство. Управление областью действия переменной (Visual Basic) | Microsoft Docs"
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
  - "объявленные элементы, область действия"
  - "объявленные элементы, видимость"
  - "область действия, объявленные элементы"
  - "область действия, переменные"
  - "область действия, Visual Basic"
  - "переменные [Visual Basic], область действия"
  - "переменные [Visual Basic], видимость"
  - "видимость, объявленные элементы"
  - "видимость, переменные"
ms.assetid: 44b7f62a-cb5c-4d50-bce9-60ae68f87072
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Практическое руководство. Управление областью действия переменной (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Обычно переменная находится в *области доступа* \(или доступна для ссылки\) в том блоке, где она объявляется.  В некоторых случаях *уровень доступа* переменной может повлиять на ее область действия.  
  
 Дополнительные сведения см. в разделе [Область видимости в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).  
  
## Область действия на уровне блока или процедуры  
  
#### Отображение переменной только внутри блока  
  
-   Поместите [Оператор Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) для переменной между начальными и конечными операторами объявления блока, например между операторами `For` и `Next` цикла `For`.  
  
     Обратиться к переменной можно только из блока.  
  
#### Отображение переменной только в процедуре  
  
-   Поместите оператор `Dim` для переменной внутри процедуры, но вне любого блока \(например блока `With`... `End With`\).  
  
     Можно обращаться к переменной только внутри процедуры, в том числе внутри любого блока, содержащегося в процедуре.  
  
## Область действия на уровне модуля или пространства имен  
 Для удобства один и тот же термин *уровень модуля* применяется в отношении модулей, классов и структур.  Уровень доступа переменной уровня модуля определяет область ее действия.  На эту область также влияет пространство имен, которому принадлежит модуль, класс или структура.  
  
#### Отображение переменной внутри модуля, класса или структуры  
  
1.  Поместите оператор `Dim` для переменной внутри модуля, класса или структуры, но вне любой процедуры.  
  
2.  Включите в оператор `Dim` ключевое слово [Private](../../../../visual-basic/language-reference/modifiers/private.md).  
  
3.  Обращаться к переменной можно из любого места внутри модуля, класса или структуры, но не из\-за их пределов.  
  
#### Отображение переменной внутри пространства имен  
  
1.  Поместите оператор `Dim` для переменной внутри модуля, класса или структуры, но вне любой процедуры.  
  
2.  Включите в оператор `Dim` ключевое слово [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) или [Public](../../../../visual-basic/language-reference/modifiers/public.md).  
  
3.  Обращаться к переменной можно из любого места внутри пространства имен, содержащего модули, классы или структуры.  
  
## Пример  
 В следующем примере объявляется переменная на уровне модуля и ее видимость ограничивается модулем.  
  
```  
Module demonstrateScope  
    Private strMsg As String  
    Sub initializePrivateVariable()  
        strMsg = "This variable cannot be used outside this module."  
    End Sub  
    Sub usePrivateVariable()  
        MsgBox(strMsg)  
    End Sub  
End Module  
```  
  
 В предыдущем примере все процедуры, определенные в модуле `demonstrateScope`, могут ссылаться на переменную `strMsg` типа `String`.  При вызове процедуры `usePrivateVariable` содержимое строковой переменной `strMsg` отображается в диалоговом окне.  
  
 Учитывая следующие изменения в предыдущем примере, обращаться к строковой переменной `strMsg` по коду можно из любого места в пространстве имен ее объявления.  
  
```  
Public strMsg As String  
```  
  
## Отказоустойчивость  
 Чем уже область действия переменной, тем меньше возможность случайной ссылки на нее вместо другой переменной с тем же именем.  Кроме того, можно сократить проблемы, связанные с соответствием ссылки.  
  
## Безопасность платформы .NET Framework  
 Чем уже область действия переменной, тем меньше вероятность неправильного использования этой переменной злонамеренным кодом.  
  
## См. также  
 [Область видимости в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)   
 [Время существования в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)   
 [Уровни доступа в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)   
 [Переменные](../../../../visual-basic/programming-guide/language-features/variables/index.md)   
 [Объявление переменной](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [Оператор Dim](../../../../visual-basic/language-reference/statements/dim-statement.md)