---
title: "Оператор Const (Visual Basic) | Microsoft Docs"
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
  - "vb.Const"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Const - оператор [Visual Basic]"
ms.assetid: 495b318d-b7c5-4198-94f8-0790a541b07a
caps.latest.revision: 28
caps.handback.revision: 28
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Оператор Const (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Объявляет и определяет одну или несколько констант.  
  
## Синтаксис  
  
```  
[ <attributelist> ] [ accessmodifier ] [ Shadows ]   
Const constantlist  
```  
  
## Части  
 `attributelist`  
 Необязательный.  Список атрибутов, применяемых ко всем константам, объявленным в данном операторе.  См. [Список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md) в угловых скобках \("`<`" и "`>`"\).  
  
 `accessmodifier`  
 Необязательный.  Позволяет указать, какой код может получить доступ к этим константам.  Может быть [Public](../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../visual-basic/language-reference/modifiers/friend.md), `Protected Friend` или [Private](../../../visual-basic/language-reference/modifiers/private.md).  
  
 `Shadows`  
 Необязательный.  Используется для переобъявления и скрытия программного элемента в базовом классе.  См. раздел [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).  
  
 `constantlist`  
 Обязательный.  Список констант, объявляемых в этом операторе.  
  
 `constant` `[ ,` `constant` `... ]`  
  
 Каждая процедура `constant` имеет следующий синтаксис и составляющие:  
  
 `constantname` `[ As` `datatype` `] =` `initializer`  
  
|Часть|Описание|  
|-----------|--------------|  
|`constantname`|Обязательный.  Имя константы.  Дополнительные сведения см. в разделе [Имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`datatype`|Требуется, если для `Option Strict` установлено значение `On`.  Тип данных константы.|  
|`initializer`|Обязательный.  Выражение, вычисляемое во время компиляции и присваиваемое константе.|  
  
## Заметки  
 Если в приложении имеется значение, которое никогда не изменяется, можно определить именованную константу и использовать ее вместо исходного значения.  Имя проще запомнить, чем значение.  Можно определить константу только один раз и использовать ее в коде.  Если в более поздней версии требуется переопределить значение, оператор `Const` является единственным местом, где необходимо внести изменения.  
  
 `Const` можно использовать только на уровне модуля или процедуры.  Это означает, что *контекст объявления* для переменной должен быть классом, структурой, модулем, процедурой или блоком и не может быть исходным файлом, пространством имен или интерфейсом.  Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Локальные константы \(внутри процедуры\) по умолчанию имеют общий уровень доступа и в них нельзя использовать никакие модификаторы доступа.  Константы\-члены класса и модуля \(вне любых процедур\) по умолчанию имеют закрытый доступ, а константы\-члены структуры по умолчанию имеют общий доступ.  Уровни доступа можно настроить с помощью модификаторов доступа.  
  
## Правила  
  
-   **Контекст объявления.** Константа, объявленная на уровне модуля, вне любой процедуры, представляет собой *константу\-член*; она является членом класса, структуры или модуля, объявляющего его.  
  
     Константа, объявленная на процедурном уровне является *локальной константой*; она является локальной для процедуры или блока, объявляющего ее.  
  
-   **Атрибуты.** Можно применить атрибуты только к константам\-членам, но не к локальным константам.  Атрибут вносит сведения для метаданных сборки, которая не имеет смысла для временного хранения таких констант, как локальные.  
  
-   **Модификаторы.** По умолчанию, все константы являются `Shared`, `Static` и `ReadOnly`.  При объявлении констант эти ключевые слова использовать нельзя.  
  
     На уровне процедур нельзя использовать `Shadows` и все модификаторы доступа для объявления локальных констант.  
  
-   **Множественные константы.** В одном операторе объявления можно объявить несколько констант, указав компонент `constantname` для каждого из них.  Несколько констант разделяются запятыми.  
  
## Правила типов данных  
  
-   **Типы данных.** Оператор `Const` может объявлять тип данных переменной.  Можно указать любой тип данных или имя перечисления.  
  
-   **Тип по умолчанию.** Если не определен элемент `datatype`, переменная принимает тип данных элемента `initializer`.  Если задан и `datatype` и `initializer`, тип данных `initializer` должен быть преобразован к `datatype`.  Если отсутствует и `datatype`, и `initializer`, по умолчанию типом данных является `Object`.  
  
-   **Различные типы.** Можно указать различные типы для разных констант с помощью отдельных предложений `As` для каждой объявляемой переменной.  Однако с помощью общего предложения `As` нельзя объявить несколько констант одного и того же типа.  
  
-   **Инициализация.** Необходимо инициализировать значение каждой константы в `constantlist`.  `initializer` позволяет указать выражение, которое необходимо назначить константе.  Выражение может быть любым сочетанием литералов, других констант и членов перечислений, которые уже определены.  Для комбинирования этих элементов можно использовать арифметические и логические операторы.  
  
     Нельзя использовать переменные или функции в `initializer`.  Однако можно использовать ключевые слова преобразования, такие как `CByte` и `CShort`.  Также можно использовать функцию `AscW` для вызова с постоянными аргументами типа `String` или `Char`, поскольку ее значение может быть вычислено во время компиляции.  
  
## Поведение  
  
-   **Область действия.** Локальные константы доступны только в пределах их процедуры или блока.  Константы\-члены доступны из любого места в пределах их класса, структуры или модуля.  
  
-   **Квалификация.** Код вне класса, модуля или структуры должен предварять имя константы\-члена именем этого класса, структуры или модуля.  Код за пределами процедуры или блока не может ссылаться на любые локальные константы в пределах этой процедуры или блока.  
  
## Пример  
 В следующем примере оператор `Const` используется для объявления констант, заменяющих литералы.  
  
 [!CODE [VbVbalrStatements#13](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStatements#13)]  
  
## Пример  
 При определении константы с типом данных `Object` компилятор Visual Basic предоставляет ей тип `initializer` вместо `Object`.  В следующем примере константа `naturalLogBase` имеет тип времени выполнения `Decimal`.  
  
 [!CODE [VbVbalrStatements#87](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStatements#87)]  
  
 Вышеприведенный пример использует метод <xref:System.Type.ToString%2A> в объекте <xref:System.Type>, возвращенном оператором [Оператор GetType](../../../visual-basic/language-reference/operators/gettype-operator.md), поскольку <xref:System.Type> не может быть преобразован к `String` с помощью `CStr`.  
  
## См. также  
 <xref:Microsoft.VisualBasic.Strings.Asc%2A>   
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>   
 [Оператор Enum](../../../visual-basic/language-reference/statements/enum-statement.md)   
 [Директива \#Const](../../../visual-basic/language-reference/directives/const-directive.md)   
 [Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md)   
 [Оператор ReDim](../../../visual-basic/language-reference/statements/redim-statement.md)   
 [Явные и неявные преобразования](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)   
 [Константы и перечисления](../../../visual-basic/programming-guide/language-features/constants-enums/index.md)   
 [Константы и перечисления](../../../visual-basic/language-reference/constants-and-enumerations.md)   
 [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)