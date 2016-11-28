---
title: "/filealign | Microsoft Docs"
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
  - "/filealign - параметр компилятора [Visual Basic]"
  - "alignment - параметр компилятора [Visual Basic]"
  - "filealign - параметр компилятора [Visual Basic]"
  - "-filealign - параметр компилятора [Visual Basic]"
  - "выравнивание разделов"
  - "sections - параметр компилятора [Visual Basic]"
ms.assetid: cc61ec3d-ad38-4b28-9659-099d73cad099
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# /filealign
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Определяет, где выравнивать разделы выходного файла.  
  
## Синтаксис  
  
```  
/filealign:number  
```  
  
## Аргументы  
 `number`  
 Обязательный.  Значение, в котором указано выравнивание разделов выходного файла.  Допустимыми значениями являются 512, 1024, 2048, 4096 и 8192.  Эти значения задаются в байтах.  
  
## Заметки  
 Чтобы задать выравнивание разделов в выходном файле можно использовать параметр `/filealign`.  Разделы являются блоками непрерывной памяти в переносимом исполняемом файле \(PE\), который содержит код или данные.  Параметр `/filealign` позволяет скомпилировать приложение с нестандартным выравниванием; большинству разработчиков не требуется использовать этот параметр.  
  
 Каждый раздел выравнивается по границе, кратной значению `/filealign`.  Фиксированного значения по умолчанию нет.  Если `/filealign` не указан, компилятор выбирает значение по умолчанию во время компиляции.  
  
 Указав размер раздела, можно изменить размер выходного файла.  Изменение размера раздела может применяться для программ, выполняющихся на небольших устройствах.  
  
> [!NOTE]
>  Параметр `/filealign` недоступен из среды разработки Visual Studio; он доступен только при выполнении компиляции из командной строки.  
  
## См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)