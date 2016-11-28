---
title: "Функция &lt;имяФункции&gt; возвращает значение не для всех путей выполнения | Microsoft Docs"
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
  - "bc42105"
  - "vbc42105"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC42105"
ms.assetid: b6929bf4-a365-4a70-8dc9-6b0fc09e1468
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Функция &lt;имяФункции&gt; возвращает значение не для всех путей выполнения
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Функция '\<имя\_функции\>' не возвращает значения для всех путей кода.У вас нет оператора возврата?  
  
 Процедура `Function` имеет, по крайней мере, один возможный путь во всем коде, который не возвращает значения.  
  
 Значение можно получить из процедуры `Function` любым из следующих способов:  
  
-   Включите значение в оператор [Оператор Return](../../../visual-basic/language-reference/statements/return-statement.md).  
  
-   Присвойте значение имени процедуры `Function` и выполните оператор `Exit Function`.  
  
-   Присвойте значение имени процедуры`Function` и выполните оператор `End Function`.  
  
 Если элемент управление передается в `Exit Function` или `End Function` и вы не присвоили никаких значений имени процедуры, то процедура вернет значение, установленное по умолчанию для типа данных.  Дополнительные сведения см. в разделе "Поведение" раздела [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md).  
  
 По умолчанию это сообщение является предупреждающим.  Дополнительные сведения о скрытии предупреждений и их обработке как ошибок см. в разделе [Настройка предупреждений в Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки**: BC42105  
  
### Чтобы исправить эту ошибку  
  
-   Проверьте логику потока управления и убедитесь, что значение присваивается перед каждым оператором, вызывающим возврат.  
  
     Если всегда используется оператор `Return`, то проще обеспечить возврат значения при каждом возврате из процедуры.  В этом случае последним оператором перед `End Function` должен быть оператор `Return`.  
  
## См. также  
 [Процедуры Function](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)   
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Страница "Компиляция" в конструкторе проектов \(Visual Basic\)](/visual-studio/ide/reference/compile-page-project-designer-visual-basic)