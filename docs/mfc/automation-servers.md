---
title: 自动化服务器
ms.date: 11/04/2016
helpviewer_keywords:
- Automation servers
- COM components, Automation servers
- dispatch maps [MFC], Automation servers
- servers, Automation
ms.assetid: 523fd155-51ce-4f91-b986-b74bdbdd7d92
ms.openlocfilehash: 391cb2f6ff5673296f40e21113e3a6510f71d475
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370842"
---
# <a name="automation-servers"></a>自动化服务器

利用自动化，您的应用程序可以操作在其他应用程序中实现的对象，或者公开对象以便让它们能够被操作。 自动化服务器是一个应用程序，它向其他应用程序（称为[自动化客户端](../mfc/automation-clients.md)）公开可编程对象（称为自动化对象）。 自动化服务器有时称为自动化组件。

通过公开自动化对象，客户端可以通过直接访问对象和服务器提供的功能来自动执行某些过程。 当应用程序提供对其他应用程序有用的功能时，以这种方式公开对象有很大好处。 例如，字处理器可能公开其拼写检查器功能以便让其他程序使用它。 公开对象后，供应商便能使用其他应用程序的现成功能改进其应用程序的功能。

这些自动化对象将属性和方法作为其外部接口。 属性是自动化对象的命名特性。 属性与 C++ 类的数据成员类似。 方法是处理自动化对象的函数。 方法与 C++ 类的公共成员函数类似。

> [!NOTE]
> 尽管属性与 C++ 数据成员类似，但前者不可直接访问。 若要提供透明访问，请使用一对 get/set 成员函数在自动化对象中设置一个内部变量来访问这些属性。

通过定义完善的常用接口公开应用程序功能后，自动化实现了在单个通用编程语言（如 Microsoft Visual Basic）中（而不是在各种特定于应用程序的宏语言中）生成应用程序。

## <a name="support-for-automation-servers"></a><a name="_core_support_for_automation_servers"></a>支持自动化服务器

Visual C++ 和 MFC 框架为自动化服务器提供了广泛的支持。 它们处理了创建自动化服务器所涉及的大部分工作，从而让您将精力放在应用程序的功能上。

用于支持自动化的框架的主要机制是调度映射，即扩展到公开 OLE 的方法和属性所需的声明和调用中的一组宏。 典型的调度映射如下所示：

[!code-cpp[NVC_MFCAutomation#1](../mfc/codesnippet/cpp/automation-servers_1.cpp)]

[类向导](reference/mfc-class-wizard.md)和类视图有助于维护调度映射。 向类添加新方法或属性时，Visual Studio 会添加一个相应的`DISP_FUNCTION`或`DISP_PROPERTY`宏，其中参数指示类名称、方法或属性的外部和内部名称以及数据类型。

**"添加类"** 对话框还简化了自动化类的声明及其属性和操作的管理。 当您使用“添加类”对话框向您的项目添加类时，应指定其基类。 如果基类允许自动化，则“添加类”对话框将显示一些控件，您可使用这些控件指定新类是否应支持自动化、新类是否是“OLE 可创建的”（即，类的对象是否可以应来自 COM 客户端的请求而创建）以及 COM 客户端要使用的外部名称。

然后，"**添加类"** 对话框将创建类声明，包括指定 OLE 功能的相应宏。 它还会为你的类的成员函数的实现添加主干代码。

MFC 应用程序向导简化了让自动化服务器应用程序起作用所涉及的步骤。 如果从 **"高级功能"** 页面中选择`InitInstance`**"自动化**"复选框，则 MFC 应用程序向导会向应用程序的功能添加注册自动化对象并将应用程序作为自动化服务器运行所需的调用。

### <a name="what-do-you-want-to-do"></a>你想做什么

- [了解自动化客户端](../mfc/automation-clients.md)

- [详细了解类 CCmdTarget](../mfc/reference/ccmdtarget-class.md)

- [详细了解类 COleDispatchDriver](../mfc/reference/coledispatchdriver-class.md)

## <a name="see-also"></a>另请参阅

[自动化](../mfc/automation.md)<br/>
[MFC 应用程序向导](../mfc/reference/mfc-application-wizard.md)
