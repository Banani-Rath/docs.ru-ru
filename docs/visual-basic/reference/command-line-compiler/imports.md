---
title: "/imports (Visual Basic) | Microsoft Docs"
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
  - "/imports - параметр компилятора [Visual Basic]"
  - "imports - параметр компилятора [Visual Basic]"
  - "-imports - параметр компилятора [Visual Basic]"
ms.assetid: 9a93fb53-c080-497b-bf9b-441022dbbc39
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# /imports (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Импортирует пространство имен из указанной сборки.  
  
## Синтаксис  
  
```  
/imports:namespaceList  
```  
  
## Аргументы  
  
|||  
|-|-|  
|Термин|Определение|  
|`namespaceList`|Обязательный.  Список с разделенными запятыми пространствами имен для импорта.|  
  
## Заметки  
 Параметр `/imports` импортирует любое пространство имен, определенное в текущем наборе исходных файлов или в сборках, на которые имеются ссылки.  
  
 Члены пространства имен, указанные в параметре `/imports`, доступны для всех файлов компилируемых исходных кодов.  Используйте [Оператор Imports \(пространство имен .NET и тип\)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) для использования пространства имен в одном файле исходного кода.  
  
||  
|-|  
|Установка\/импорт в интегрированной среде разработки Visual Studio|  
|1.  Выберите проект в **обозревателе решений**.  В меню **Проект** выберите пункт **Свойства**.  Дополнительные сведения см. в разделе [Introduction to the Project Designer](http://msdn.microsoft.com/ru-ru/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Перейдите на вкладку **Ссылки**.<br />3.  Введите имя пространства имен в поле рядом с кнопкой **Добавить пользовательский импорт**.<br />4.  Нажмите кнопку  **Добавить пользовательский импорт** .|  
  
## Пример  
 Следующий код компилируется при указании `/imports:system`.  
  
 [!CODE [VbVbalrCompiler#21](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrCompiler#21)]  
  
## См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Ссылки и оператор Imports](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)