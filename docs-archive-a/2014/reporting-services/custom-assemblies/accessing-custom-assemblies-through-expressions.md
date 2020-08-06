---
title: Acceso a los ensamblados personalizados a través de expresiones | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- expressions [Reporting Services], custom assemblies
- static member calls
- instance member calls [Reporting Services]
- calling class members
- custom assemblies [Reporting Services], expressions
ms.assetid: 917c4d47-1a95-4f54-98b1-e8cb2165d90f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 99497de0456d90fd522ce27c62fd5aa1b812059f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87661807"
---
# <a name="accessing-custom-assemblies-through-expressions"></a><span data-ttu-id="e32a5-102">Acceso a los ensamblados personalizados a través de expresiones</span><span class="sxs-lookup"><span data-stu-id="e32a5-102">Accessing Custom Assemblies Through Expressions</span></span>
  <span data-ttu-id="e32a5-103">Cuando haya creado un ensamblado personalizado, lo haya puesto a disposición del Diseñador de informes o del servidor de informes, y haya agregado la directiva de seguridad adecuada y una referencia al ensamblado personalizado en la definición de informe, podrá tener acceso a los miembros de las clases en el ensamblado mediante expresiones de informe.</span><span class="sxs-lookup"><span data-stu-id="e32a5-103">Once you have created a custom assembly, made it available to Report Designer or the report server, added the appropriate security policy, and added a reference to your custom assembly in your report definition, you can access the members of the classes in your assembly using report expressions.</span></span> <span data-ttu-id="e32a5-104">Para incluir en una expresión una referencia a código personalizado, debe llamar al miembro de una clase dentro del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e32a5-104">To refer to custom code in an expression, you must call the member of a class within the assembly.</span></span> <span data-ttu-id="e32a5-105">La manera de hacerlo depende de si el método es estático o se basa en instancias.</span><span class="sxs-lookup"><span data-stu-id="e32a5-105">How you do this depends on whether the method is static or instance-based.</span></span>  
  
## <a name="calling-static-members-from-a-report-definition-file"></a><span data-ttu-id="e32a5-106">Llamar a miembros estáticos desde un archivo de definición de informe</span><span class="sxs-lookup"><span data-stu-id="e32a5-106">Calling Static Members from a Report Definition File</span></span>  
 <span data-ttu-id="e32a5-107">Los miembros estáticos pertenecen a la clase o al propio tipo, y no a un objeto con instancias.</span><span class="sxs-lookup"><span data-stu-id="e32a5-107">Static members belong to the class or type itself and not to an instantiated object.</span></span> <span data-ttu-id="e32a5-108">Se puede tener acceso a estos miembros llamándoles directamente desde la clase.</span><span class="sxs-lookup"><span data-stu-id="e32a5-108">These members can be accessed by directly calling them from the class.</span></span> <span data-ttu-id="e32a5-109">Debería utilizar miembros estáticos para llamar a las funciones personalizadas en un informe siempre que sea posible, porque se comportan mejor.</span><span class="sxs-lookup"><span data-stu-id="e32a5-109">You should use static members to call custom functions in a report whenever possible, because static members perform best.</span></span> <span data-ttu-id="e32a5-110">Para llamar a un miembro estático, tiene que hacer referencia a él como expresión con el formato =*EspacioDeNombres.Clase.Método*.</span><span class="sxs-lookup"><span data-stu-id="e32a5-110">To call a static member, you need to reference it as an expression that takes the form =*Namespace.Class.Method*.</span></span>  
  
#### <a name="to-call-static-members"></a><span data-ttu-id="e32a5-111">Para llamar a los miembros estáticos</span><span class="sxs-lookup"><span data-stu-id="e32a5-111">To call static members</span></span>  
  
-   <span data-ttu-id="e32a5-112">Para llamar a un miembro estático, establezca la expresión igual al nombre completo del miembro, lo que incluye el espacio de nombres, el nombre de la clase y el nombre del miembro.</span><span class="sxs-lookup"><span data-stu-id="e32a5-112">To call a static member, set your expression equal to the fully qualified name of the member, which includes the namespace, class name, and member name.</span></span> <span data-ttu-id="e32a5-113">En el ejemplo siguiente se llama al método **ToGBP**, que convierte el valor de campo **StandardCost** de dólares a libras esterlinas y lo presenta en un informe:</span><span class="sxs-lookup"><span data-stu-id="e32a5-113">The following example calls the **ToGBP** method, which converts the **StandardCost** field value from dollars to pounds sterling and displays it in a report:</span></span>  
  
    ```  
    =CurrencyConversion.DollarCurrencyConversion.ToGBP(Fields!StandardCost.Value)  
    ```  
  
### <a name="important-information-regarding-static-fields-and-properties"></a><span data-ttu-id="e32a5-114">Información importante con respecto a los campos estáticos y propiedades</span><span class="sxs-lookup"><span data-stu-id="e32a5-114">Important Information Regarding Static Fields and Properties</span></span>  
 <span data-ttu-id="e32a5-115">Actualmente, todos los informes se ejecutan en el mismo dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="e32a5-115">Currently, all reports are executed in the same application domain.</span></span> <span data-ttu-id="e32a5-116">Esto significa que los informes con datos estáticos específicos del usuario exponen estos datos a otras instancias del mismo informe.</span><span class="sxs-lookup"><span data-stu-id="e32a5-116">This means that reports with user-specific, static data expose this data to other instances of the same report.</span></span> <span data-ttu-id="e32a5-117">Esta condición podría permitir que los datos estáticos de un usuario estuvieran disponibles para todos los usuarios que ejecutaran actualmente un informe determinado.</span><span class="sxs-lookup"><span data-stu-id="e32a5-117">This condition might make it possible for the static data of one user to be available to all users currently running a particular report.</span></span> <span data-ttu-id="e32a5-118">Por esta razón, es muy aconsejable no usar campos estáticos ni propiedades en ensamblados personalizados ni en el elemento **Code**. En su lugar, utilice campos de instancia o propiedades en los informes.</span><span class="sxs-lookup"><span data-stu-id="e32a5-118">For this reason, it is highly recommended that you not use static fields or properties in custom assemblies or in the **Code** element; instead, use instance fields or properties in your reports.</span></span> <span data-ttu-id="e32a5-119">Se pueden seguir utilizando los métodos estáticos, porque no almacenan el estado ni los datos.</span><span class="sxs-lookup"><span data-stu-id="e32a5-119">Static methods can still be used, because they do not store state or data.</span></span>  
  
## <a name="calling-instance-members-from-a-report-definition-file"></a><span data-ttu-id="e32a5-120">Llamar a miembros de instancia desde un archivo de definición de informe</span><span class="sxs-lookup"><span data-stu-id="e32a5-120">Calling Instance Members from a Report Definition File</span></span>  
 <span data-ttu-id="e32a5-121">Si un ensamblado personalizado contiene miembros de instancia a los que debe obtener acceso en una definición de informe, debe agregar al informe un nombre de instancia para la clase.</span><span class="sxs-lookup"><span data-stu-id="e32a5-121">If your custom assembly contains instance members that you need to access in a report definition, you must add an instance name for your class to the report.</span></span> <span data-ttu-id="e32a5-122">Puede agregar un nombre de instancia para una clase utilizando la pestaña **Código** del cuadro de diálogo **Propiedades del informe**.</span><span class="sxs-lookup"><span data-stu-id="e32a5-122">You can add an instance name for a class using the **Code** tab of the **Report Properties** dialog.</span></span> <span data-ttu-id="e32a5-123">Para obtener más información sobre cómo agregar instancias de clases a un informe, vea [Referencias a ensamblados y código personalizado en expresiones en el Diseñador de informes &#40;SSRS&#41;](../report-design/custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e32a5-123">For more information about adding instances of classes to a report, see [Custom Code and Assembly References in Expressions in Report Designer &#40;SSRS&#41;](../report-design/custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span></span>  
  
 <span data-ttu-id="e32a5-124">Para llamar a un miembro estático, debe hacer referencia a él como una expresión que toma el formato = code *. NombreDeInstancia. Method*.</span><span class="sxs-lookup"><span data-stu-id="e32a5-124">To call a static member, you need to reference it as an expression that takes the form = Code *.InstanceName.Method*.</span></span>  
  
#### <a name="to-call-instance-members"></a><span data-ttu-id="e32a5-125">Para llamar a los miembros de instancia</span><span class="sxs-lookup"><span data-stu-id="e32a5-125">To call instance members</span></span>  
  
-   <span data-ttu-id="e32a5-126">Para llamar a un miembro de instancia de un ensamblado personalizado, debe hacer referencia a la palabra clave **Code** seguida del nombre de instancia y el método.</span><span class="sxs-lookup"><span data-stu-id="e32a5-126">To call an instance member of a custom assembly, you must reference the **Code** keyword followed by the instance name and the method.</span></span> <span data-ttu-id="e32a5-127">En el ejemplo siguiente se llama a un método de instancia **ToEUR** que convierte el valor del campo **StandardCost** de dólares a euros y los muestra en un informe:</span><span class="sxs-lookup"><span data-stu-id="e32a5-127">The following example calls an instance method **ToEUR** which converts the **StandardCost** field value from dollars to euros and displays it in a report:</span></span>  
  
    ```  
    =Code.m_myDollarCoversion.ToEUR(Fields!StandardCost.Value)  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e32a5-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e32a5-128">See Also</span></span>  
 [<span data-ttu-id="e32a5-129">Usar ensamblados personalizados con informes</span><span class="sxs-lookup"><span data-stu-id="e32a5-129">Using Custom Assemblies with Reports</span></span>](using-custom-assemblies-with-reports.md)  
  
  
