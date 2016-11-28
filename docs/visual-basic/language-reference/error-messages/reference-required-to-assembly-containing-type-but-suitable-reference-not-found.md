---
title: "Для сборки &quot;&lt;удостоверение_сборки&gt;&quot;, содержащей тип &quot;&lt;имя_типа&gt;&quot;, требуется ссылка, но подходящая ссылка не может быть найдена из-за неоднозначности между проектами &quot;&lt;имя_проекта1&gt;&quot; и &quot;&lt;имя_проекта2&gt;&quot;. | Microsoft Docs"
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
  - "bc30969"
  - "vbc30969"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30969"
ms.assetid: 1b29dbc5-8268-45fe-bfc2-b2070a5c845c
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Для сборки &quot;&lt;удостоверение_сборки&gt;&quot;, содержащей тип &quot;&lt;имя_типа&gt;&quot;, требуется ссылка, но подходящая ссылка не может быть найдена из-за неоднозначности между проектами &quot;&lt;имя_проекта1&gt;&quot; и &quot;&lt;имя_проекта2&gt;&quot;.
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Выражение использует тип, например класс, структуру, интерфейс, перечисление или делегат, который определен за пределами проекта. Однако имеются ссылки проекта на несколько сборок, определяющих этот тип.  
  
 Названные проекты создают сборки с тем же именем. Поэтому компилятор не может определить, какую сборку следует использовать для типа, к которому осуществляется доступ.  
  
 Для доступа к типу, определенному в другой сборке, компилятор [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] должен иметь ссылку на эту сборку. Это должна быть одна однозначная ссылка, не вызывающая циклических ссылок между проектами.  
  
 **Идентификатор ошибки:** BC30969  
  
### Исправление ошибки  
  
1.  Определите, какой проект создает наиболее подходящую сборку для проекта, чтобы ссылаться на нее в дальнейшем. Для этого можно использовать такие критерии, как простота доступа к файлам и частота обновления.  
  
2.  В свойствах проекта добавьте ссылку на файл, содержащий сборку, определяющую используемый тип.  
  
## См. также  
 [Управление ссылками в проекте](/visual-studio/ide/managing-references-in-a-project)   
 [Ссылки на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [NIB. Практическое руководство. Добавление и удаление ссылок с помощью диалогового окна "Добавление ссылок"](http://msdn.microsoft.com/ru-ru/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)   
 [NIB. Практическое руководство. Изменение свойств проекта и параметров конфигурации](http://msdn.microsoft.com/ru-ru/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)   
 [Диагностика неработающих ссылок](/visual-studio/ide/troubleshooting-broken-references)