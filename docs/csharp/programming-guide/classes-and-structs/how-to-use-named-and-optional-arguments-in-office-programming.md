---
title: "Практическое руководство. Использование именованных и необязательных аргументов в программировании приложений Office (Руководство по программированию на C#) | Microsoft Docs"
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
  - "именованные и необязательные аргументы [C#], программирование для Office"
  - "именованные аргументы [C#], программирование для Office"
  - "необязательные аргументы [C#], программирование для Office"
ms.assetid: 65b8a222-bcd8-454c-845f-84adff5a356f
caps.latest.revision: 34
caps.handback.revision: 34
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Практическое руководство. Использование именованных и необязательных аргументов в программировании приложений Office (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Появившиеся в [!INCLUDE[csharp_dev10_long](../../../csharp/programming-guide/classes-and-structs/includes/csharp_dev10_long_md.md)] именованные и необязательные аргументы повышают удобство, гибкость и удобочитаемость программирования на C\#. Кроме этого, данные функции значительно упрощают доступ к COM\-интерфейсам, таким как интерфейсы API автоматизации Microsoft Office.  
  
 В следующем примере у метода [ConvertToTable](http://go.microsoft.com/fwlink/?LinkId=145378) имеется шестнадцать параметров, представляющих характеристики таблицы, например число столбцов и строк, форматирование, границы и цвета.  Все шестнадцать параметров являются необязательными, поскольку в большинстве случаев не требуется задавать конкретные значения для всех этих параметров.  Однако без именованных и необязательных параметров приходилось указывать значение или значение\-заполнитель для каждого из параметров.  Именованные и необязательные параметры позволяют задавать значения только для тех параметров, которые требуются в конкретном проекте.  
  
 Для выполнения этих процедур на компьютере должен быть установлен Microsoft Office Word.  
  
 [!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### Создание нового консольного приложения  
  
1.  Запустите Visual Studio.  
  
2.  В меню **Файл** последовательно выберите пункты **Создать** и **Проект**.  
  
3.  В области **Категории шаблонов** откройте **Visual C\#**, а затем щелкните **Windows**.  
  
4.  В верхней части области **Шаблоны** значение **.NET Framework 4** должно отображаться в поле **Требуемая версия .NET Framework**.  
  
5.  В области **Шаблоны** щелкните **Консольное приложение**.  
  
6.  Введите имя проекта в поле **Имя**.  
  
7.  Нажмите кнопку **ОК**.  
  
     В **обозревателе решений** появится новый проект.  
  
### Добавление ссылки  
  
1.  В **обозревателе решений** щелкните имя проекта правой кнопкой мыши и выберите **Добавить ссылку**.  Откроется диалоговое окно **Добавление ссылки**.  
  
2.  На странице **.NET** выберите в списке **Имя компонента** элемент **Microsoft.Office.Interop.Word**.  
  
3.  Нажмите кнопку **ОК**.  
  
### Добавление необходимых директив Using  
  
1.  В **обозревателе решений** щелкните правой кнопкой мыши файл **Program.cs** и выберите пункт **Просмотр кода**.  
  
2.  Добавьте следующие директивы `using` в начало файла кода.  
  
     [!CODE [csProgGuideNamedAndOptional#4](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidenamedandoptional#4)]  
  
### Отображение текста в документе Word  
  
1.  В класс `Program` в файле Program.cs добавьте следующий метод для создания приложения Word и документа Word.  У метода [Add](http://go.microsoft.com/fwlink/?LinkId=145381) имеется четыре необязательных параметра.  В этом примере используются значения по умолчанию.  Поэтому в инструкции вызова указывать аргументы не требуется.  
  
     [!CODE [csProgGuideNamedAndOptional#6](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidenamedandoptional#6)]  
  
2.  Добавьте в конец метода следующий код, чтобы определить место отображения текста в документе и текст для отображения.  
  
     [!CODE [csProgGuideNamedAndOptional#7](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidenamedandoptional#7)]  
  
### Запуск приложения  
  
1.  Добавьте в метод Main следующую инструкцию.  
  
     [!CODE [csProgGuideNamedAndOptional#8](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidenamedandoptional#8)]  
  
2.  Нажмите сочетание клавиш CTRL\+F5, чтобы запустить проект.  Появится документ Word, содержащий указанный текст.  
  
### Замена текста на таблицу  
  
1.  Метод `ConvertToTable` служит для преобразования текста в таблицу.  У метода имеется шестнадцать необязательных параметров.  IntelliSense заключает необязательные параметры в квадратные скобки, как показано на следующем рисунке.  
  
     ![Список параметров для метода ConvertToTable.](../../../csharp/programming-guide/classes-and-structs/media/convert_tableparameters.png "Convert\_TableParameters")  
Параметры ConvertToTable  
  
     Именованные и необязательные аргументы позволяют задавать значения только для тех параметров, которые требуется изменить.  Добавьте в конец метода `DisplayInWord` следующий код, чтобы создать простую таблицу.  Аргумент указывает, что запятые в текстовой строке в `range` разделяют ячейки таблицы.  
  
     [!CODE [csProgGuideNamedAndOptional#9](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidenamedandoptional#9)]  
  
     В предыдущих версиях C\# для вызова `ConvertToTable` каждому параметру требовался ссылочный аргумент, как показано в следующем коде.  
  
     [!CODE [csProgGuideNamedAndOptional#14](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidenamedandoptional#14)]  
  
2.  Нажмите сочетание клавиш CTRL\+F5, чтобы запустить проект.  
  
### Экспериментирование с другими параметрами  
  
1.  Для изменения таблицы, чтобы она содержала один столбец и три строки, замените последнюю строку метода `DisplayInWord` следующей инструкцией и нажмите сочетание клавиш CTRL\+F5.  
  
     [!CODE [csProgGuideNamedAndOptional#10](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidenamedandoptional#10)]  
  
2.  Чтобы использовать заранее определенный формат таблицы, замените последнюю строку метода `DisplayInWord` следующей инструкцией и нажмите сочетание клавиш CTRL\+F5.  В качестве формата можно использовать любую из констант [WdTableFormat](http://go.microsoft.com/fwlink/?LinkId=145382).  
  
     [!CODE [csProgGuideNamedAndOptional#11](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidenamedandoptional#11)]  
  
## Пример  
 Следующий код включает полный пример.  
  
 [!CODE [csProgGuideNamedAndOptional#12](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidenamedandoptional#12)]  
  
## См. также  
 [Именованные и необязательные аргументы](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md)