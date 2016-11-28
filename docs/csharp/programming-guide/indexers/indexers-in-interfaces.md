---
title: "Индексаторы в интерфейсах (Руководство по программированию в C#) | Microsoft Docs"
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
  - "методы доступа [C#], индексаторы"
  - "индексаторы [C#], в интерфейсах"
ms.assetid: e16b54bd-4a83-4f52-bd75-65819fca79e8
caps.latest.revision: 18
caps.handback.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Индексаторы в интерфейсах (Руководство по программированию в C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Индексаторы можно объявлять на [интерфейс](../../../csharp/language-reference/keywords/interface.md).  Между методами доступа индексаторов интерфейса и методами доступа индексаторов [класса](../../../csharp/language-reference/keywords/class.md) существуют следующие отличия:  
  
-   Методы доступа интерфейсов не используют модификаторы.  
  
-   Метод доступа интерфейса не имеет тела.  
  
 Поэтому метод доступа предназначен для того, чтобы указывать, доступен ли индексатор для чтения и записи, только для чтения или только для записи.  
  
 Ниже приведен пример метода доступа индексатора интерфейса:  
  
 [!CODE [csProgGuideIndexers#3](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideIndexers#3)]  
  
 Сигнатура индексатора должна отличаться от сигнатур всех других индексаторов, объявленных в том же интерфейсе.  
  
## Пример  
 В следующем примере показана реализация индексаторов интерфейса.  
  
 [!CODE [csProgGuideIndexers#4](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideIndexers#4)]  
  
 В предыдущем пример можно использовать явную реализацию члена интерфейса с помощью полного имени члена интерфейса.  Примеры.  
  
```  
public string ISomeInterface.this   
{   
}   
```  
  
 Однако, полное имя требуется для исключения неоднозначности только тогда, когда класс реализует более одного интерфейса с одинаковой сигнатурой индексатора.  Например, если класс `Employee` реализует два интерфейса `ICitizen` и `IEmployee` с одинаковой сигнатурой индексатора, требуется явная реализация члена интерфейса.  Поэтому следующее объявление индексатора:  
  
```  
public string IEmployee.this   
{   
}   
```  
  
 реализует индексатор для интерфейса `IEmployee`, а следующее объявление:  
  
```  
public string ICitizen.this   
{   
}   
```  
  
 реализует индексатор для интерфейса `ICitizen`.  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Индексаторы](../../../csharp/programming-guide/indexers/index.md)   
 [Свойства](../../../csharp/programming-guide/classes-and-structs/properties.md)   
 [Интерфейсы](../../../csharp/programming-guide/interfaces/index.md)