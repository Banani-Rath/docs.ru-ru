---
title: "Недопустимый порядковый номер | Microsoft Docs"
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
  - "vbrID452"
dev_langs: 
  - "VB"
ms.assetid: 7459562b-cd4f-4590-95e0-6126ae3589a5
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Недопустимый порядковый номер
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

При вызове динамически подключаемой библиотеки \(DLL\) использовался номер, а не имя процедуры, указываемый с помощью синтаксиса `#num`.  Причиной возникновения данной ошибки может быть:  
  
-   Отказ при преобразовании выражения `#num` в порядковый номер.  
  
-   Указанный `#num` не соответствует ни одной функции из библиотеки DLL.  
  
-   Недопустимое объявление библиотеки типов, что явилось причиной внутреннего использования недопустимого порядкового номера.  
  
### Чтобы исправить эту ошибку  
  
1.  Убедитесь, что выражение содержит допустимый номер или вызовите процедуру по имени.  
  
2.  Убедитесь, что выражение `#num` определяет допустимую функцию из библиотеки DLL.  
  
3.  Изолируйте вызов процедуры, вызывающей ошибку путем преобразования кода в комментарий.  Напишите для процедуры оператор `Declare` и сообщите об ошибке разработчику библиотеки типов.  
  
## См. также  
 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)