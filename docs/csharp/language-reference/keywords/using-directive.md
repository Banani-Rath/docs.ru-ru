---
title: "Директива using (Справочник по C#) | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "using - директива [C#]"
ms.assetid: b42b8e61-5e7e-439c-bb71-370094b44ae8
caps.latest.revision: 31
caps.handback.revision: 31
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Директива using (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Директива `using` используется в следующих трех целях.  
  
-   Для разрешения использования типов в пространстве имен, чтобы не нужно было квалифицировать использование типа в этом пространстве имен:  
  
    ```c#  
    using System.Text;  
    ```  
  
-   Для разрешения доступа к статическим членам типа без необходимости квалификации доступа с помощью имени типа:  
  
    ```c#  
    using static System.Math;  
    ```  
  
-   Чтобы создать псевдоним для пространства имен или типа.  Это называется *директивой псевдонима using*.  
  
    ```c#  
    using Project = PC.MyCompany.Project;  
    ```  
  
 Ключевое слово `using` также используется для создания *операторов using*, которые помогают обеспечить правильную обработку объектов <xref:System.IDisposable>, таких как файлы и шрифты.  Дополнительные сведения см. в разделе [Оператор using](../../../csharp/language-reference/keywords/using-statement.md).  
  
## Использование статического типа  
 Вы можете обращаться к статическим членам типа без необходимости квалификации доступа с помощью имени типа:  
  
```c#  
using static System.Console;   
using static System.Math;  
class Program   
{   
    static void Main()   
    {   
        WriteLine(Sqrt(3*3 + 4*4));   
    }   
}  
  
```  
  
 `Using static` импортирует только доступные статические члены и вложенные типы, объявленные в указанном типе.  Унаследованные члены не импортируются.  Можно импортировать из любого именованного типа с помощью директивы using static, включая модули Visual Basic.  Если функции F\# верхнего уровня отображаются в метаданных как статические члены именованного типа, чье имя является допустимым идентификатором C\#, то эти функции F\# можно импортировать.  
  
 `Using static` делает методы расширения, объявленные в указанном типе, доступными для поиска метода расширения.  Тем не менее имена методов расширения не импортируются в область для неквалифицированной ссылки в коде.  
  
 Методы с тем же именем, импортированные из различных типов разными директивами using static в том же блоке компиляции или пространстве имен, формируют группу методов.  Разрешение перегрузки в этих группах методов соответствует обычным правилам языка C\#.  
  
## Заметки  
 Область директивы `using` ограничена файлом, в котором она находится.  
  
 Создайте псевдоним `using`, чтобы упростить квалификацию идентификатора для пространства имен или типа.  Правая часть директивы псевдонима using всегда должна быть полным типом независимо от директив using до нее.  
  
 Создайте директиву `using`, чтобы использовать типы в пространстве имен без необходимости указания этого пространства имен.  Директива `using` не предоставляет доступ к пространствам имен, вложенным в указанное пространство имен.  
  
 Пространства имен делятся на две категории: пользовательские и системные.  Пользовательские пространства имен задаются в вашем коде.  Список системных пространств имен см. в разделе [Библиотека классов .NET Framework](http://go.microsoft.com/fwlink/?LinkID=227195).  
  
 Примеры ссылочных методов в других сборках см. в разделе [Создание и использование библиотек DLL C\#](../Topic/How%20to:%20Create%20and%20Use%20Assemblies%20Using%20the%20Command%20Line%20\(C%23%20and%20Visual%20Basic\).md).  
  
## Пример 1  
  
### Описание  
 В следующем примере показано, как задать и использовать псевдоним `using` для пространства имен.  
  
### Код  
 [!CODE [csrefKeywordsNamespace#8](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsNamespace#8)]  
  
### Примечания  
 Псевдоним using не может иметь открытый универсальный тип с правой стороны.  Например, нельзя создать псевдоним using для List\<T\>, но можно создать его для List\<int\>.  
  
## Пример 2  
  
### Описание  
 В следующем примере показано, как задать директиву `using` и псевдоним `using` для класса.  
  
### Код  
 [!CODE [csrefKeywordsNamespace#9](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsNamespace#9)]  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Использование пространств имен](../../../csharp/programming-guide/namespaces/using-namespaces.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Ключевые слова, используемые для пространств имен](../../../csharp/language-reference/keywords/namespace-keywords.md)   
 [Пространства имен](../../../csharp/programming-guide/namespaces/index.md)   
 [Оператор using](../../../csharp/language-reference/keywords/using-statement.md)