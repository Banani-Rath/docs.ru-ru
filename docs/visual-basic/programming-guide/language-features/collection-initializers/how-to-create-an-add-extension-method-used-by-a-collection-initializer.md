---
title: "Практическое руководство. Создание метода расширения Add, используемого инициализатором набора (Visual Basic) | Microsoft Docs"
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
  - "инициализаторы коллекций [Visual Basic]"
ms.assetid: f64b52c7-8b11-4410-93a6-cb3aeebcc772
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Практическое руководство. Создание метода расширения Add, используемого инициализатором набора (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

При использовании инициализатора набора для создания коллекции компилятор Visual Basic выполняет поиск метода `Add` типа коллекции, у которого параметры метода `Add` соответствуют типам значений в инициализаторе набора.  Этот метод `Add` служит для наполнения коллекции значениями из инициализатора набора.  
  
 Если подходящий метод `Add` не существует, а код коллекции изменить нельзя, то можно добавить метод расширения `Add` с параметрами, необходимыми для инициализатора набора.  Такие действия обычно необходимы при использовании инициализаторов наборов для создания универсальных коллекций.  
  
## Пример  
 В следующем примере показано, как добавить метод расширения к универсальному типу <xref:System.Collections.Generic.List%601>, чтобы инициализатор набора можно было использовать для добавления объектов типа `Employee`.  Метод расширения позволяет использовать сокращенный синтаксис инициализатора набора.  
  
 [!CODE [VbVbalrCollectionInitializersHowTo1#1](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1#1)]  
  
 [!CODE [VbVbalrCollectionInitializersHowTo1#2](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1#2)]  
  
 [!CODE [VbVbalrCollectionInitializersHowTo1#3](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1#3)]  
  
## См. также  
 [Инициализаторы коллекций](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)   
 [Практическое руководство. Создание коллекции, используемой инициализатором набора](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-a-collection-used-by-a-collection-initializer.md)