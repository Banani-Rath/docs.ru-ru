---
title: "Пошаговое руководство. Создание и использование динамических объектов (C# и Visual Basic) | Microsoft Docs"
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
  - "динамические объекты"
  - "динамические объекты [C#]"
  - "динамические объекты [Visual Basic]"
ms.assetid: 568f1645-1305-4906-8625-5d77af81e04f
caps.latest.revision: 22
caps.handback.revision: 22
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Пошаговое руководство. Создание и использование динамических объектов (C# и Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Динамические объекты предоставляют такие элементы, как свойства и методы, во время выполнения, а не во время компиляции.  Это позволяет создавать объекты для работы со структурами, не соответствующими статическому типу или формату.  Например, можно использовать динамический объект для ссылки на модель DOM HTML, которая может содержать любую комбинацию допустимых элементов и атрибутов разметки HTML.  Поскольку каждый документ HTML является уникальным, элементы для конкретного документа HTML определяются во время выполнения.  Наиболее распространенный способ ссылки на атрибут элемента HTML состоит в передаче имени этого атрибута в метод `GetProperty` элемента.  Для ссылки на атрибут `id` элемента HTML `<div id="Div1">` следует сначала получить ссылку на элемент `<div>`, а затем указать `divElement.GetProperty("id")`.  При использовании динамического объекта можно сослаться на атрибут `id` в виде `divElement.id`.  
  
 Динамические объекты обеспечивают удобный доступ к динамическим языкам, таким как IronPython и IronRuby.  С помощью динамического объекта можно ссылаться на динамический скрипт, интерпретируемый во время выполнения.  
  
 Ссылка на динамический объект выполняется с помощью позднего связывания.  В C\# тип объектов с поздним связыванием указывается как `dynamic`.  В [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] тип объектов с поздним связыванием указывается как `Object`.  Дополнительные сведения см. в разделах [dynamic](../../../csharp/language-reference/keywords/dynamic.md) и [Раннее и позднее связывание](../../../visual-basic/programming-guide/language-features/early-late-binding/early-and-late-binding.md).  
  
 Существует возможность создания пользовательских динамических объектов с помощью классов в пространстве имен <xref:System.Dynamic?displayProperty=fullName>.  Например, можно создать объект <xref:System.Dynamic.ExpandoObject> и задать элементы этого объекта во время выполнения.  Также можно создать собственный тип, наследующий класс <xref:System.Dynamic.DynamicObject>.  Затем для обеспечения динамических функциональных возможностей во время выполнения можно переопределить элементы класса <xref:System.Dynamic.DynamicObject>.  
  
 В данном пошаговом руководстве демонстрируется выполнение следующих задач:  
  
-   создание пользовательского объекта, который динамически предоставляет содержимое текстового файла в виде свойств объекта;  
  
-   Создайте проект, использующий библиотеку `IronPython`.  
  
## Обязательные компоненты  
 Для выполнения инструкций этого пошагового руководства потребуется установить IronPython 2.6.1 для .NET 4.0.  IronPython 2.6.1 для .NET 4.0 можно загрузить со страницы [CodePlex](http://go.microsoft.com/fwlink/?LinkId=187223).  
  
 [!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
## Создание пользовательского динамического объекта  
 В первом проекте, создаваемом в данном пошаговом руководстве, определяется пользовательский динамический объект, выполняющий поиск по содержимому текстового файла.  Текст для поиска задается именем динамического свойства.  Например, при вызове кода, в котором указано `dynamicFile.Sample`, динамический класс возвращает общий список строк, содержащий все строки файла, начинающиеся со слова "Sample".  При поиске регистр не учитывается.  Динамический класс также поддерживает два дополнительных аргумента.  Первый аргумент — это значение перечисления параметра поиска, задающее, где динамический класс должен искать соответствия: в начале строки, в конце строки или в любом месте строки.  Второй аргумент задает, что динамический класс должен перед поиском отсекать начальные и конечные пробелы в каждой строке.  Например, если в вызывающем коде указано `dynamicFile.Sample(StringSearchOption.Contains)`, то динамический класс выполняет поиск слова "Sample" в любом месте строки.  Если в вызывающем коде указано `dynamicFile.Sample(StringSearchOption.StartsWith, false)`, то динамический класс выполняет поиск слова "Sample" в начале каждой строки и не удаляет начальные и конечные пробелы в строках.  По умолчанию динамический класс выполняет поиск соответствия в начале каждой строки, предварительно удаляя начальные и конечные пробелы.  
  
#### Создание пользовательского динамического класса  
  
1.  Запустите [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)].  
  
2.  В меню **Файл** выберите пункт **Создать**, а затем команду **Проект**.  
  
3.  Убедитесь, что в диалоговом окне **Новый проект** в области **Типы проектов** выбран пункт **Windows**.  В области **Шаблоны** выберите пункт **Консольное приложение**.  В поле **Имя** введите `DynamicSample` и нажмите кнопку **ОК**.  Новый проект создан.  
  
4.  Щелкните правой кнопкой мыши проект DynamicSample, выберите команду **Добавить** и нажмите пункт **Класс**.  В поле **Имя** введите `ReadOnlyFile` и нажмите кнопку **ОК**.  Добавится новый файл, содержащий класс ReadOnlyFile.  
  
5.  Вверху файла ReadOnlyFile.cs или ReadOnlyFile.vb добавьте следующий код для импорта пространств имен <xref:System.IO?displayProperty=fullName> и <xref:System.Dynamic?displayProperty=fullName>.  
  
     [!CODE [VbDynamicWalkthrough#1](../CodeSnippet/VS_Snippets_VBCSharp/vbdynamicwalkthrough#1)]  
  
6.  Пользовательский динамический объект использует перечисление для определения условия поиска.  Перед оператором класса добавьте следующее определение перечисления.  
  
     [!CODE [VbDynamicWalkthrough#2](../CodeSnippet/VS_Snippets_VBCSharp/vbdynamicwalkthrough#2)]  
  
7.  Обновите оператор класса, чтобы он наследовал класс `DynamicObject`, как показано в следующем примере кода.  
  
     [!CODE [VbDynamicWalkthrough#3](../CodeSnippet/VS_Snippets_VBCSharp/vbdynamicwalkthrough#3)]  
  
8.  Добавьте в класс `ReadOnlyFile` следующий код, чтобы задать закрытое поле для пути к файлу и конструктор для класса `ReadOnlyFile`.  
  
     [!CODE [VbDynamicWalkthrough#4](../CodeSnippet/VS_Snippets_VBCSharp/vbdynamicwalkthrough#4)]  
  
9. Добавьте в класс `ReadOnlyFile` следующий метод `GetPropertyValue`.  Метод `GetPropertyValue` принимает в качестве ввода условие поиска и возвращает строки текстового файла, соответствующие этому условию.  Динамический метод, предоставленный классом `ReadOnlyFile`, вызывает метод `GetPropertyValue` для извлечения соответствующих результатов.  
  
     [!CODE [VbDynamicWalkthrough#5](../CodeSnippet/VS_Snippets_VBCSharp/vbdynamicwalkthrough#5)]  
  
10. После метода `GetPropertyValue` добавьте следующий код, чтобы переопределить метод <xref:System.Dynamic.DynamicObject.TryGetMember%2A> класса <xref:System.Dynamic.DynamicObject>.  Метод <xref:System.Dynamic.DynamicObject.TryGetMember%2A> вызывается при запросе элемента динамического класса без указания аргументов.  Аргумент `binder` содержит сведения об элементе, на который делается ссылка, а аргумент `result` ссылается на результат, возвращенный для указанного элемента.  Метод <xref:System.Dynamic.DynamicObject.TryGetMember%2A> возвращает логическое значение `true`, если запрошенный элемент существует, или `false` в другом случае.  
  
     [!CODE [VbDynamicWalkthrough#6](../CodeSnippet/VS_Snippets_VBCSharp/vbdynamicwalkthrough#6)]  
  
11. После метода `TryGetMember` добавьте следующий код, чтобы переопределить метод <xref:System.Dynamic.DynamicObject.TryInvokeMember%2A> класса <xref:System.Dynamic.DynamicObject>.  Метод <xref:System.Dynamic.DynamicObject.TryInvokeMember%2A> вызывается при запросе элемента динамического класса с аргументами.  Аргумент `binder` содержит сведения об элементе, на который делается ссылка, а аргумент `result` ссылается на результат, возвращенный для указанного элемента.  Аргумент `args` содержит массив аргументов, передаваемых в элемент.  Метод <xref:System.Dynamic.DynamicObject.TryInvokeMember%2A> возвращает логическое значение `true`, если запрошенный элемент существует, или `false` в другом случае.  
  
     Данная пользовательская версия метода `TryInvokeMember` ожидает, что первый аргумент будет значением из перечисления `StringSearchOption`, заданного на предыдущем этапе.  Метод `TryInvokeMember` ожидает, что второй аргумент будет логическим значением.  Если один или оба элемента имеют допустимые значения, они передаются в метод `GetPropertyValue` для извлечения результатов.  
  
     [!CODE [VbDynamicWalkthrough#7](../CodeSnippet/VS_Snippets_VBCSharp/vbdynamicwalkthrough#7)]  
  
12. Сохраните и закройте файл.  
  
#### Создание примера текстового файла  
  
1.  Щелкните правой кнопкой мыши проект DynamicSample, выберите команду **Добавить** и нажмите пункт **Создать элемент**.  В области **Установленные шаблоны** выберите **Общие**, а затем выберите шаблон **Текстовый файл**.  В поле **Имя** оставьте имя по умолчанию TextFile1.txt и нажмите кнопку **Добавить**.  В проект добавится новый файл.  
  
2.  Скопируйте в файл TextFile1.txt следующий текст.  
  
    ```  
    List of customers and suppliers  
  
    Supplier: Lucerne Publishing (http://www.lucernepublishing.com/)  
    Customer: Preston, Chris  
    Customer: Hines, Patrick  
    Customer: Cameron, Maria  
    Supplier: Graphic Design Institute (http://www.graphicdesigninstitute.com/)   
    Supplier: Fabrikam, Inc. (http://www.fabrikam.com/)   
    Customer: Seubert, Roxanne  
    Supplier: Proseware, Inc. (http://www.proseware.com/)   
    Customer: Adolphi, Stephan  
    Customer: Koch, Paul  
    ```  
  
3.  Сохраните и закройте файл.  
  
#### Создание примера приложения, в котором применяется пользовательский динамический объект  
  
1.  В **обозревателе решений** дважды щелкните файл Module1.vb, если используется [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], или файл Program.cs, если используется Visual C\#.  
  
2.  Добавьте следующий код в процедуру Main, чтобы создать экземпляр класса `ReadOnlyFile` для файла TextFile1.txt.  В этом коде используется позднее связывание для вызова динамических элементов и извлечения строк текста, содержащих последовательность символов "Customer".  
  
     [!CODE [VbDynamicWalkthrough#8](../CodeSnippet/VS_Snippets_VBCSharp/vbdynamicwalkthrough#8)]  
  
3.  Сохраните файл и нажмите сочетание клавиш CTRL\+F5 для построения и выполнения приложения.  
  
## Вызов библиотеки динамического языка  
 В следующем проекте, создаваемом в ходе данного пошагового руководства, осуществляется доступ к библиотеке, написанной на динамическом языке IronPython.  Перед созданием проекта необходимо установить IronPython 2.6.1 для .NET 4.0.  IronPython 2.6.1 для .NET 4.0 можно загрузить со страницы [CodePlex](http://go.microsoft.com/fwlink/?LinkId=187223).  
  
#### Создание пользовательского динамического класса  
  
1.  В [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] в меню **Файл** последовательно выберите пункты **Создать** и **Проект**.  
  
2.  Убедитесь, что в диалоговом окне **Новый проект** в области **Типы проектов** выбран пункт **Windows**.  В области **Шаблоны** выберите пункт **Консольное приложение**.  В поле **Имя** введите `DynamicIronPythonSample` и нажмите кнопку **ОК**.  Новый проект создан.  
  
3.  Если используется [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], щелкните правой кнопкой мыши проект DynamicIronPythonSample и выберите пункт **Свойства**.  Перейдите на вкладку **Ссылки**.  Нажмите кнопку **Добавить**.  Если используется Visual C\#, в **обозревателе решений** щелкните правой кнопкой мыши папку **Ссылки** и выберите пункт **Добавить ссылку**.  
  
4.  На вкладке **Обзор** перейдите к папке, в которой установлены библиотеки IronPython.  Например, C:\\Program Files\\IronPython 2.6 for .NET 4.0.  Выберите библиотеки **IronPython.dll**, **IronPython.Modules.dll**, **Microsoft.Scripting.dll** и **Microsoft.Dynamic.dll**.  Нажмите кнопку **ОК**.  
  
5.  Если используется [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], отредактируйте файл Module1.vb.  Если используется Visual C\#, отредактируйте файл Program.cs.  
  
6.  В верхней части файла добавьте следующий код для импорта пространств имен `Microsoft.Scripting.Hosting` и `IronPython.Hosting` из библиотек IronPython.  
  
     [!CODE [VbDynamicWalkthroughIronPython#1](../CodeSnippet/VS_Snippets_VBCSharp/vbdynamicwalkthroughironpython#1)]  
  
7.  В методе Main добавьте следующий код, чтобы создать новый объект `Microsoft.Scripting.Hosting.ScriptRuntime`, в котором будут размещены библиотеки IronPython.  Объект `ScriptRuntime` загружает модуль библиотеки IronPython random.py.  
  
     [!CODE [VbDynamicWalkthroughIronPython#2](../CodeSnippet/VS_Snippets_VBCSharp/vbdynamicwalkthroughironpython#2)]  
  
8.  После указания в коде необходимости загрузки модуля random.py добавьте следующий код, чтобы создать массив целых чисел.  Массив передается методу `shuffle` модуля random.py, который произвольно сортирует значения в массиве.  
  
     [!CODE [VbDynamicWalkthroughIronPython#3](../CodeSnippet/VS_Snippets_VBCSharp/vbdynamicwalkthroughironpython#3)]  
  
9. Сохраните файл и нажмите сочетание клавиш CTRL\+F5 для построения и выполнения приложения.  
  
## См. также  
 <xref:System.Dynamic?displayProperty=fullName>   
 <xref:System.Dynamic.DynamicObject?displayProperty=fullName>   
 [Использование типа dynamic](../../../csharp/programming-guide/types/using-type-dynamic.md)   
 [Раннее и позднее связывание](../../../visual-basic/programming-guide/language-features/early-late-binding/early-and-late-binding.md)   
 [dynamic](../../../csharp/language-reference/keywords/dynamic.md)   
 [Реализация динамических интерфейсы \(внешний блог\)](http://go.microsoft.com/fwlink/?LinkId=230895)