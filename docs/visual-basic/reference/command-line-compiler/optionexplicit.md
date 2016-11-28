---
title: "/optionexplicit | Microsoft Docs"
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
  - "/optionexplicit"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "/optionexplicit - параметр компилятора [Visual Basic]"
  - "optionexplicit - параметр компилятора [Visual Basic]"
  - "-optionexplicit - параметр компилятора [Visual Basic]"
ms.assetid: 5d296ab3-bafe-4c4d-9887-78f162ed86c7
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# /optionexplicit
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Указывает компилятору сообщать об ошибках, если используются необъявленные переменные.  
  
## Синтаксис  
  
```  
/optionexplicit[+ | -]  
```  
  
## Аргументы  
 `+` &#124; `-`  
 Необязательный.  Для указания необходимости явного объявления переменных задайте `/optionexplicit+`.  Параметр `/optionexplicit+` является параметром по умолчанию и совпадает с `/optionexplicit`.  Параметр `/optionexplicit-` разрешает неявное объявление переменных.  
  
## Заметки  
 Если файл исходного кода содержит[Оператор Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md), оператор переопределяет параметр командной строки компилятора`/optionexplicit`.  
  
### Установка параметра \/optionexplicit в интегрированной среде разработки Visual Studio  
  
1.  Выберите проект в **обозревателе решений**.  В меню **Проект** выберите пункт **Свойства**.  Дополнительные сведения см. в разделе [Introduction to the Project Designer](http://msdn.microsoft.com/ru-ru/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  Перейдите на вкладку **Compile**.  
  
3.  Измените значение в поле **Option Explicit**.  
  
## Пример  
 Следующий код компилируется при использовании `/optionexplicit-`.  
  
 [!CODE [VbVbalrCompiler#5](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrCompiler#5)]  
  
## См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)   
 [\/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)   
 [\/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Оператор Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md)   
 [Страница "Параметры Visual Basic по умолчанию", папка "Проекты", диалоговое окно "Параметры"](/visual-studio/ide/reference/visual-basic-defaults-projects-options-dialog-box)