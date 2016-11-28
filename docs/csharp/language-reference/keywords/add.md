---
title: "add (Справочник по C#) | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "add_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "add - метод доступа события [C#]"
ms.assetid: faf30b99-10e8-45cd-ab9a-57585d4d1d8d
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# add (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Контекстно\-зависимое ключевое слово `add` используется для определения пользовательского метода доступа к событию, вызываемому при подписке клиентского кода к [событию](../../../csharp/language-reference/keywords/event.md).  Если указан пользовательский метод доступа `add`, то необходимо также указать метод доступа [remove](../../../csharp/language-reference/keywords/remove.md).  
  
## Пример  
 В следующем примере показано событие, имеющее пользовательские методы доступа `add` и [remove](../../../csharp/language-reference/keywords/remove.md).  Полный пример см. в разделе [Практическое руководство. Реализация событий интерфейса](../../../csharp/programming-guide/events/how-to-implement-interface-events.md).  
  
 [!CODE [csrefKeywordsContextual#15](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsContextual#15)]  
  
 Обычно не требуется предоставлять свои собственные пользовательские методы доступа к событиям.  Для большинства сценариев достаточны методы доступа, которые автоматически создаются компилятором при объявлении события.  
  
## См. также  
 [События](../../../csharp/programming-guide/events/index.md)