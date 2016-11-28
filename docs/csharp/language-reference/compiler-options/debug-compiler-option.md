---
title: "/debug (C# Compiler Options) | Microsoft Docs"
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
  - "/debug"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "debug compiler option [C#]"
  - "-debug compiler option [C#]"
  - "/debug compiler option [C#]"
ms.assetid: e2b48c07-01bc-45cc-a52c-92e9085eb969
caps.latest.revision: 19
caps.handback.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# /debug (C# Compiler Options)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

При заданном параметре **\/debug** компилятор создает отладочную информацию и помещает ее в выходном файле или файлах.  
  
## Синтаксис  
  
```  
/debug[+ | -]  
/debug:{full | pdbonly}  
```  
  
## Аргументы  
 `+` &#124; `-`  
 При задании `+` или только **\/debug** компилятор создает отладочную информацию и помещает ее в базу данных программы \(файл с расширением PDB\).  Если задан параметр `-`, который работает при отсутствии параметра **\/debug**, отладочные данные не создаются.  
  
 `full` &#124; `pdbonly`  
 Определяет тип отладочной информации, создаваемой компилятором.  Аргумент full, действующий при отсутствии параметра **\/debug:pdbonly**, позволяет присоединить отладчик к выполняющейся программе.  Задание параметра pdbonly позволяет выполнять отладку исходного кода при запуске программы в отладчике, но при этом ассемблер отображается только при подключении выполняющейся программы к отладчику.  
  
## Заметки  
 Используйте эту опцию для создания отладочных версий.  Если не задать параметр **\/debug**, **\/debug\+** или **\/debug:full**, то отладка выходного файла программы будет невозможна.  
  
 При использовании параметра **\/debug:full** необходимо учитывать некоторое влияние на скорость и размер оптимизированного кода JIT и незначительное влияние на качество кода с **\/debug:full**.  Для создания кода выпуска рекомендуется использовать параметр **\/debug:pdbonly** либо не использовать PDB.  
  
> [!NOTE]
>  Отличие **\/debug:pdbonly** от **\/debug:full** заключается в том, что компилятор с параметром **\/debug:full** создает <xref:System.Diagnostics.DebuggableAttribute>, сообщающий JIT\-компилятору о доступности отладочных сведений.  Поэтому, если при использовании параметра **\/debug:full** код содержит <xref:System.Diagnostics.DebuggableAttribute> со значением "false", будет выведено сообщение об ошибке.  
  
 Дополнительные сведения о настройке производительности приложения см. в разделе [Способы упрощения отладки изображений](../Topic/Making%20an%20Image%20Easier%20to%20Debug.md).  
  
 Сведения об изменении расположения файла с расширением PDB см. в разделе [\/pdb \(Specify Debug Symbol File\)](../../../csharp/language-reference/compiler-options/pdb-compiler-option.md).  
  
### Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте страницу **Свойства** проекта.  
  
2.  Выберите страницу свойств **Построение**.  
  
3.  Нажмите кнопку **Дополнительно**.  
  
4.  Измените свойство **Отладочная информация**.  
  
 Дополнительные сведения об установке этого параметра компилятора программным путем см. в разделе <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DebugSymbols%2A>.  
  
## Пример  
 Разместите отладочную информацию в выходном файле `app.pdb`.  
  
```  
csc /debug /pdb:app.pdb test.cs  
```  
  
## См. также  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Практическое руководство. Изменение свойств проекта и параметров конфигурации](http://msdn.microsoft.com/ru-ru/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)