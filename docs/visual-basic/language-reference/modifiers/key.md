---
title: "Key (Visual Basic) | Microsoft Docs"
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
  - "vb.AnonymousKey"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "анонимные типы [Visual Basic], клавиша"
  - "Key [Visual Basic]"
  - "Key - ключевое слово [Visual Basic]"
ms.assetid: 7697a928-7d14-4430-a72a-c9e96e8d6c11
caps.latest.revision: 22
caps.handback.revision: 22
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Key (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Ключевое слово `Key` позволяет указать поведение свойств анонимных типов.  Только свойства, указанные как ключевые свойства, участвуют в проверке равенства между экземплярами анонимных типов или в вычислении значений хэш\-кода.  Значения ключевых свойств не могут быть изменены.  
  
 Укажите свойство анонимного типа в качестве ключевого свойства, установив ключевое слово `Key` в начале объявления в списке инициализации.  В следующем примере `Airline` и `FlightNo` являются ключевыми свойствами, а `Gate` — нет.  
  
 [!CODE [VbVbalrAnonymousTypes#26](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes#26)]  
  
 При создании нового анонимного типа он наследуется непосредственно от <xref:System.Object>.  Компилятор переопределяет три унаследованных члена: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A> и <xref:System.Object.ToString%2A>.  Перегруженный код, созданный для <xref:System.Object.Equals%2A> и <xref:System.Object.GetHashCode%2A> основан на основных свойствах.  Если нет ключевых свойств в типе, то <xref:System.Object.GetHashCode%2A> и <xref:System.Object.Equals%2A> не переопределяются.  
  
## Равенство  
 Два экземпляра одинаковых анонимных типов равны, если они являются экземплярами одного типа и значения их ключевых свойств равны.  В следующих примерах `flight2` равно `flight1` из предыдущего примера, поскольку они являются экземплярами одного и того же анонимного типа и значения их ключевых свойств совпадают.  Однако, `flight3` не равно `flight1` поскольку значения их основных свойств различны, `FlightNo`.  Экземпляр `flight4` имеет другой тип, нежели `flight1`, так как у них разные свойства назначены ключевыми.  
  
 [!CODE [VbVbalrAnonymousTypes#27](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes#27)]  
  
 Если два экземпляра объявлены только с неключевыми свойствами, идентичными по имени, типу, порядку и значению, они не равны.  Экземпляр без ключевого свойства равен только самому себе.  
  
 Дополнительные сведения об условиях, при которых два экземпляра анонимных типов являются экземплярами одного и того же анонимного типа, см. в разделе [Анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
## Вычисление хэш\-кода  
 Как и <xref:System.Object.Equals%2A>, хэш\-функция, определенная в <xref:System.Object.GetHashCode%2A> для анонимного типа, основана на ключевых свойствах типа.  В следующем примере показано взаимодействие между ключевыми свойствами и значениями хэш\-кода.  
  
 Экземпляры анонимного типа, имеющие те же значения для всех ключевых свойств, имеют такие же значения хэш\-кода, даже если их неключевые свойства не имеют совпадающих значений.  Следующий оператор возвращает `True`.  
  
 [!CODE [VbVbalrAnonymousTypes#37](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes#37)]  
  
 Экземпляры анонимного типа, имеющие различные значения для одного или более ключевых свойств, имеют различные значения хэш\-кода.  Следующий оператор возвращает `False`.  
  
 [!CODE [VbVbalrAnonymousTypes#38](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes#38)]  
  
 Экземпляры анонимных типов, определяющие различные свойства в качестве ключевых, не являются экземплярами одного типа.  Они имеют различные значения хэш\-кода, даже когда имена и значения всех их свойств одинаковы.  Следующий оператор возвращает `False`.  
  
 [!CODE [VbVbalrAnonymousTypes#39](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes#39)]  
  
## Значения, доступные только для чтения  
 Значения ключевых свойств не могут быть изменены.  Например в предыдущих примерах в `flight1` поля `Airline` и `FlightNo` являются доступными только для чтения, а `Gate` можно изменять.  
  
 [!CODE [VbVbalrAnonymousTypes#28](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes#28)]  
  
## См. также  
 [Определение анонимного типа](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md)   
 [Практическое руководство. Выведение имен свойств и типов в объявлениях анонимных типов](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)   
 [Анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)