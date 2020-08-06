---
title: Inicializar objetos de ensamblados personalizados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- initializing custom assemblies [Reporting Services]
- custom assemblies [Reporting Services], initializing
- OnInit method
ms.assetid: 26fd74dc-d02f-40f7-aeb3-50ce05e9e6b9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2aba0bd8b71b26651067a2370728dcdff521ceaa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672788"
---
# <a name="initializing-custom-assembly-objects"></a><span data-ttu-id="b2387-102">Inicializar objetos de ensamblados personalizados</span><span class="sxs-lookup"><span data-stu-id="b2387-102">Initializing Custom Assembly Objects</span></span>
  <span data-ttu-id="b2387-103">En algunos casos, puede que tenga que inicializar valores de campos y propiedades en las clases de ensamblados personalizados al crear instancias de ellos.</span><span class="sxs-lookup"><span data-stu-id="b2387-103">In some cases, you may need to initialize property and field values in your custom assembly classes when you instantiate them.</span></span> <span data-ttu-id="b2387-104">Probablemente tendrá que inicializar las clases personalizadas con los valores de que disponga en las colecciones de objetos globales del informe.</span><span class="sxs-lookup"><span data-stu-id="b2387-104">You will most likely need to initialize your custom classes with values available to you from the report's global object collections.</span></span> <span data-ttu-id="b2387-105">Para ello, se reemplaza el método **OnInit** del objeto **Code** de un informe.</span><span class="sxs-lookup"><span data-stu-id="b2387-105">You do this by overriding the **OnInit** method of the **Code** object of a report.</span></span> <span data-ttu-id="b2387-106">Para acceder a **OnInit**, use el elemento **Code** de la definición de informe.</span><span class="sxs-lookup"><span data-stu-id="b2387-106">To access **OnInit**, use the **Code** element of the report definition.</span></span> <span data-ttu-id="b2387-107">Hay dos técnicas para inicializar valores de propiedad o campo de las clases de un ensamblado personalizado que se piensa usar en el informe: puede declarar y crear una instancia nueva de la clase mediante **OnInit** o puede llamar a un método disponible públicamente con **OnInit**.</span><span class="sxs-lookup"><span data-stu-id="b2387-107">There are two techniques for initializing property or field values of the classes in a custom assembly that you plan to use in your report: You can either declare and create a new instance of your class using **OnInit**, or you can call a publicly available method using **OnInit**.</span></span>  
  
## <a name="global-object-collections-and-initialization"></a><span data-ttu-id="b2387-108">Colecciones de objetos globales e inicialización</span><span class="sxs-lookup"><span data-stu-id="b2387-108">Global Object Collections and Initialization</span></span>  
 <span data-ttu-id="b2387-109">Hay varias colecciones disponibles para inicializar las variables de clases personalizadas.</span><span class="sxs-lookup"><span data-stu-id="b2387-109">Several collections are available to you for initializing your custom class variables.</span></span> <span data-ttu-id="b2387-110">Puede usar las colecciones **Globals** y **User**.</span><span class="sxs-lookup"><span data-stu-id="b2387-110">You can use the **Globals** and **User** collections.</span></span> <span data-ttu-id="b2387-111">Las colecciones **Parameters**, **Fields** y **ReportItems** no están disponibles cuando se invoca al método **OnInit** en el ciclo de vida del informe.</span><span class="sxs-lookup"><span data-stu-id="b2387-111">The **Parameters**, **Fields** and **ReportItems** collections are not available to you at the point in the report lifecycle when the **OnInit** method is invoked.</span></span> <span data-ttu-id="b2387-112">Para usar las colecciones compartidas, **Globals** o **User**, tiene que incluir la referencia al objeto **Report**.</span><span class="sxs-lookup"><span data-stu-id="b2387-112">To use the shared collections, **Globals** or **User**, you need to include the **Report** object reference.</span></span> <span data-ttu-id="b2387-113">Por ejemplo, para inicializar la clase base en función del idioma actual del usuario que accede al informe, el elemento **Code** podría ser similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="b2387-113">For example, to initialize your custom class based on the current language of the user accessing the report, your **Code** element might look like the following:</span></span>  
  
```  
<Code>  
   Dim m_myClass As MyClass  
  
   Protected Overrides Sub OnInit()  
      m_myClass = new MyClass(Report.User!Language, _  
         Report.Globals!ExecutionTime)  
   End Sub  
</Code>  
```  
  
 <span data-ttu-id="b2387-114">Una manera de inicializar los valores de los campos y propiedades de una clase según se ha mostrado anteriormente es declarar la clase y crear una instancia nueva de ella llamando a un constructor invalidado.</span><span class="sxs-lookup"><span data-stu-id="b2387-114">One way to initialize the property and field values of a class as shown previously is to declare your class and create a new instance of it by calling an overridden constructor.</span></span>  
  
 <span data-ttu-id="b2387-115">Otra manera de inicializar los valores de campo y propiedad de las clases de los ensamblados personalizados es llamar a un método disponible públicamente que se define a partir del método **OnInit**.</span><span class="sxs-lookup"><span data-stu-id="b2387-115">Another way to initialize the property and field values of the classes in your custom assemblies is to call a publicly available method that you define from the **OnInit** method.</span></span> <span data-ttu-id="b2387-116">Primero es necesario agregar un nombre de instancia para la clase en el archivo de definición de informe.</span><span class="sxs-lookup"><span data-stu-id="b2387-116">You first need to add an instance name for your class in the report definition file.</span></span> <span data-ttu-id="b2387-117">Cuando haya agregado la referencia de ensamblado y el nombre de instancia adecuados, podrá llamar al método de inicialización para inicializar los valores de las propiedades y campos para la clase.</span><span class="sxs-lookup"><span data-stu-id="b2387-117">Once you have added the appropriate assembly reference and instance name, you can call your initialization method to initialize property and field values for your class.</span></span> <span data-ttu-id="b2387-118">El método **OnInit** podría ser similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="b2387-118">Your **OnInit** method might look like the following:</span></span>  
  
```  
<Code>  
   Protected Overrides Sub OnInit()  
      m_myClass.MyInitializationMethod(Report.User!Language, _  
         Report.Globals!ExecutionTime)  
   End Sub  
</Code>  
```  
  
 <span data-ttu-id="b2387-119">Para más información sobre cómo agregar una referencia de ensamblado y un nombre de instancia para la clase personalizada, vea [Agregar una referencia de ensamblado a un informe &#40;SSRS&#41;](../report-design/add-an-assembly-reference-to-a-report-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="b2387-119">For more information about adding an assembly reference and instance name for your custom class, see [Add an Assembly Reference to a Report &#40;SSRS&#41;](../report-design/add-an-assembly-reference-to-a-report-ssrs.md).</span></span>  
  
 <span data-ttu-id="b2387-120">Para más información sobre las colecciones de objetos globales, vea [Colecciones integradas en expresiones &#40;Generador de informes y SSRS&#41;](../report-design/built-in-collections-in-expressions-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="b2387-120">For more information about the global object collections, see [Built-in Collections in Expressions &#40;Report Builder and SSRS&#41;](../report-design/built-in-collections-in-expressions-report-builder.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2387-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b2387-121">See Also</span></span>  
 [<span data-ttu-id="b2387-122">Usar ensamblados personalizados con informes</span><span class="sxs-lookup"><span data-stu-id="b2387-122">Using Custom Assemblies with Reports</span></span>](using-custom-assemblies-with-reports.md)  
  
  
