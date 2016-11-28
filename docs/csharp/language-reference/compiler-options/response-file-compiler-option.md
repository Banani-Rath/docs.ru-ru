---
title: "@ (C# Compiler Options) | Microsoft Docs"
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
  - "@"
dev_langs: 
  - "CSharp"
  - "CSharp"
helpviewer_keywords: 
  - "response files, specifying for compilation [C#]"
  - "@ compiler option"
ms.assetid: dda4fa9f-a02c-400f-8b6a-d58834e13d7f
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# @ (C# Compiler Options)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Параметр @ позволяет указать файл, содержащий параметры компилятора и файлы исходного кода для компиляции.  
  
## Синтаксис  
  
```  
@response_file  
```  
  
## Аргументы  
 `response_file`  
 Файл, содержащий параметры компилятора и файлы исходного кода для компиляции.  
  
## Заметки  
 Компилятор обрабатывает параметры компилятора и файлы исходного кода, как если бы они были указаны в командной строке.  
  
 Чтобы задать несколько файлов ответов для компиляции следует использовать этот параметр несколько раз.  Примеры.  
  
```  
@file1.rsp @file2.rsp  
```  
  
 В файле ответов в одной строке можно указать несколько параметров компилятора и файлов исходного кода.  Каждый параметр компилятора должен записываться только в одной строке \(его нельзя переносить на другую строку\).  В файл ответов можно включать примечания, начинающиеся с символа \#.  
  
 Указание параметров компилятора в файле ответов подобно выполнению таких команд в командной строке.  Дополнительные сведения см. в разделе [Построение из командной строки](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md).  
  
 Компилятор обрабатывает параметры команд по мере их обнаружения.  Таким образом, параметры командной строки могут переопределять параметры, указанные в файле ответа.  Таким же образом параметры в файле ответа могут переопределять ранее указанные параметры командной строки или параметры из других файлов ответа.  
  
 Язык C\# предоставляет файл csc.rsp, расположенный в том же каталоге, что и файл csc.exe.  Дополнительные сведения о csc.rsp см. в разделе [\/noconfig](../../../csharp/language-reference/compiler-options/noconfig-compiler-option.md).  
  
 Этот параметр не может быть установлен в среде разработки Visual Studio и его нельзя изменить программным способом.  
  
## Пример  
 Вот несколько строк из возможного файла ответов:  
  
```  
# build the first output file  
/target:exe /out:MyExe.exe source1.cs source2.cs  
```  
  
## См. также  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)