---
title: "Ограничение доступности методов доступа (Руководство по программированию на C#) | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "методы доступа [C#]"
  - "асимметричные методы доступа [C#]"
  - "индексаторы [C#], только для чтения"
  - "свойства [C#], только для чтения"
  - "индексаторы только для чтения [C#]"
  - "свойства только для чтения [C#]"
ms.assetid: 6e655798-e112-4301-a680-6310a6e012e1
caps.latest.revision: 26
caps.handback.revision: 26
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Ограничение доступности методов доступа (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Части свойства [get](../../../csharp/language-reference/keywords/get.md) и [set](../../../csharp/language-reference/keywords/set.md) или индексатора называются *методами доступа*.  По умолчанию эти методы доступа обладают той же видимостью или уровнем доступа, присущим свойству или индексатору, которому они принадлежат.  Дополнительные сведения см. в разделе [уровни доступности](../../../csharp/language-reference/keywords/accessibility-levels.md).  Однако иногда имеет смысл ограничить доступ к одному из этих методов доступа.  Как правило, для этого ограничивается доступность метода доступа `set` и сохраняется открытая доступность метода доступа `get`.  Примеры.  
  
 [!CODE [csProgGuideIndexers#6](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideIndexers#6)]  
  
 В этом примере свойство с именем `Name` определяет метод доступа `get` и `set`.  Метод доступа `get` получает уровень доступности самого свойства – в этом случае это `public`, а метод доступа `set` ограничивается явным образом путем применения модификатора доступа [protected](../../../csharp/language-reference/keywords/protected.md) к самому методу доступа.  
  
## Ограничения модификаторов доступа в методах доступа  
 Использование модификаторов доступа для свойств или индексаторов подчиняется следующим условиям:  
  
-   Модификаторы доступа нельзя использовать в интерфейсе или в явной реализации члена [интерфейса](../../../csharp/language-reference/keywords/interface.md).  
  
-   Модификаторы доступа можно использовать только в том случае, если как свойство, так и индексатор имеют модификаторы доступа `set` и `get`.  В этом случае, модификатор разрешен в одном из двух методов доступа.  
  
-   Если свойство или индексатор имеет модификатор [override](../../../csharp/language-reference/keywords/override.md), модификатор доступа должен соответствовать методу доступа переопределенного метода доступа, если он существует.  
  
-   Уровень доступности в методе доступа должен быть более ограничивающим, чем уровень доступности в самом свойстве или индексаторе.  
  
## Модификаторы доступа в переопределяющих методах доступа  
 При переопределении свойства или индексатора переопределенные методы доступа должны быть доступны переопределяющему коду.  Кроме того, уровень доступности свойства\/индексатора, а также методов доступа должен перехватывать соответствующее свойство\/индексатор и методы доступа.  Примеры.  
  
 [!CODE [csProgGuideIndexers#7](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideIndexers#7)]  
  
## Реализация интерфейсов  
 При использовании метода доступа для реализации интерфейса, метод доступа не может иметь модификатор доступа.  Однако если интерфейс реализуется при помощи одного метода доступа, такого как `get`, другой метод доступа может иметь модификатор доступа, как в следующем примере:  
  
 [!CODE [csProgGuideIndexers#8](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideIndexers#8)]  
  
## Домен доступности к методу доступа  
 При использовании модификатора доступа в методе доступа, этот модификатор определяет [домен доступности](../../../csharp/language-reference/keywords/accessibility-domain.md) метода доступа.  
  
 Если модификатор доступа в методе доступа не используется, домен доступности метода доступа определяется уровнем доступности свойства или индексатора.  
  
## Пример  
 В следующем примере содержатся три класса: `BaseClass`, `DerivedClass` и `MainClass`.  В `BaseClass`, `Name` и `Id` для обоих классов имеется два свойства.  Пример демонстрирует, как свойство `Id` в `DerivedClass` можно скрыть при помощи свойства `Id` в `BaseClass`, если используется ограничивающий модификатор доступа, такой как [protected](../../../csharp/language-reference/keywords/protected.md) или [private](../../../csharp/language-reference/keywords/private.md).  Таким образом, при присвоении значений этому свойству, вместо этого вызывается свойство `BaseClass`.  Замена модификатора доступа модификатором [public](../../../csharp/language-reference/keywords/public.md) сделает свойство доступным.  
  
 Пример также демонстрирует, что ограничивающий модификатор доступа, такой как `private` или `protected`, в методе доступа `set` свойства `Name` в `DerivedClass` запрещает доступ к методу доступа и создает ошибку при его присвоении.  
  
 [!CODE [csProgGuideIndexers#5](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideIndexers#5)]  
  
## Комментарии  
 Обратите внимание, что при замене объявления `new private string Id` `new public string Id`, результат будет следующим:  
  
 `Name and ID in the base class: Name-BaseClass, ID-BaseClass`  
  
 `Name and ID in the derived class: John, John123`  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Свойства](../../../csharp/programming-guide/classes-and-structs/properties.md)   
 [Индексаторы](../../../csharp/programming-guide/indexers/index.md)   
 [Модификаторы доступа](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)