---
title: "Практическое руководство. Запись текста в файлы в каталоге &quot;Мои документы&quot; в Visual Basic | Microsoft Docs"
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
  - "примеры [Visual Basic], текстовые файлы"
  - "файлы, запись в"
  - "текст, запись в файлы"
  - "запись в файлы, в папке "Мои документы""
ms.assetid: 1c726124-781d-4976-9baa-ed46814ff3fe
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Практическое руководство. Запись текста в файлы в каталоге &quot;Мои документы&quot; в Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Объект `My.Computer.FileSystem.SpecialDirectories` позволяет получать доступ к специальным каталогам, таким как каталог **Мои документы**.  
  
## Процедура  
  
#### Чтобы записать новые текстовые файлы в каталог "Мои документы"  
  
1.  Укажите путь в свойстве `My.Computer.FileSystem.SpecialDirectories.MyDocuments`.  
  
     [!CODE [VbFileIOWrite#1](../CodeSnippet/VS_Snippets_VBCSharp/VbFileIOWrite#1)]  
  
2.  Используйте метод `WriteAllText` для записи текста в указанный файл.  
  
     [!CODE [VbVbcnMyFileSystem#14](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnMyFileSystem#14)]  
  
## Пример  
 [!CODE [VbFileIOWrite#2](../CodeSnippet/VS_Snippets_VBCSharp/VbFileIOWrite#2)]  
  
## Компиляция кода  
 Замените имя `test.txt` на имя файла, в который требуется выполнить запись.  
  
## Отказоустойчивость  
 Этот код возвращает все исключения, которые могут произойти при записи текста в файл.  Можно уменьшить вероятность возникновения исключений, используя элементы управления Windows Forms, такие как компоненты [OpenFileDialog](../Topic/OpenFileDialog%20Component%20\(Windows%20Forms\).md) и [SaveFileDialog](../Topic/SaveFileDialog%20Component%20\(Windows%20Forms\).md), которые позволяют пользователям выбирать только допустимые имена файлов.  Однако использование этих элементов управления не гарантирует полную надежность.  В период между моментом выбора пользователем файла и моментом выполнения кода файловая система может измениться.  Таким образом, при работе с файлами обработка исключений почти всегда является необходимой.  
  
## Безопасность платформы .NET Framework  
 Если код выполняется в контексте частичного доверия, исключение может возникнуть из\-за недостатка прав доступа.  Дополнительные сведения см. в разделе [Code Access Security Basics](../Topic/Code%20Access%20Security%20Basics.md).  
  
 В этом примере создается новый файл.  Если приложение создает файл, оно должно иметь разрешение на создание файла в соответствующем каталоге.  Для задания разрешений используется список управления доступом.  Если файл уже существует, приложению требуется лишь разрешение на запись.  Для повышения безопасности рекомендуется по возможности создавать файлы во время развертывания и предоставлять доступ на чтение только к одному файлу, а не доступ к каталогу с разрешением на создание.  По тем же соображениям рекомендуется сохранять данные в пользовательских каталогах, а не в корневом каталоге или каталоге **Program Files**.  Дополнительные сведения см. в разделе [ACL Technology Overview](http://msdn.microsoft.com/ru-ru/06fbf66d-6f02-4378-b863-b2f12e349045).  
  
## См. также  
 <xref:System.IO.Path.Combine%2A?displayProperty=fullName>   
 <xref:Microsoft.VisualBasic.Devices.Computer>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>   
 <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories>