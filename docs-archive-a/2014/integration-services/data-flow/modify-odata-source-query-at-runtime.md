---
title: Modificar consulta de origen OData en tiempo de ejecución | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: bcbba7f4-6e5d-46e6-a73a-3f17d3ff376a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b3dbc4d27f2d11537a9d66980ef6ca59b80811b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750042"
---
# <a name="modify-odata-source-query-at-runtime"></a><span data-ttu-id="cfcb1-102">Modificar una consulta de origen OData en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="cfcb1-102">Modify OData Source Query at Runtime</span></span>
  <span data-ttu-id="cfcb1-103">Puede modificar la consulta de origen OData en tiempo de ejecución si agrega una expresión a la propiedad **[OData Source].[Query]** de la tarea Flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="cfcb1-103">You can modify the OData Source query at runtime by adding an expression to the **[OData Source].[Query]** property of the Data Flow task.</span></span>  
  
 <span data-ttu-id="cfcb1-104">Tenga en cuenta que las columnas deben seguir siendo iguales que las que se usaron en tiempo de diseño; de lo contrario, obtendrá un error cuando se ejecute el paquete.</span><span class="sxs-lookup"><span data-stu-id="cfcb1-104">Note that the columns must remain the same as what was used at design time; otherwise you will get an error when the package is executed.</span></span> <span data-ttu-id="cfcb1-105">Asegúrese de especificar las mismas columnas (en el mismo orden) cuando use la opción de consulta $select.</span><span class="sxs-lookup"><span data-stu-id="cfcb1-105">Be sure to specify the same columns (in the same order) when using the $select query option.</span></span> <span data-ttu-id="cfcb1-106">Una alternativa más segura a la opción $select consiste en anular la selección de las columnas que no quiera usar directamente desde la interfaz de usuario del componente de origen.</span><span class="sxs-lookup"><span data-stu-id="cfcb1-106">A safer alternative to using the $select option is to deselect the columns you don't want directly from the Source Component UI.</span></span>  
  
 <span data-ttu-id="cfcb1-107">Hay varias maneras de establecer de forma dinámica el valor de consulta en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="cfcb1-107">There are a few different ways of dynamically setting the query value at runtime.</span></span> <span data-ttu-id="cfcb1-108">A continuación se muestran algunos de los métodos más frecuentes.</span><span class="sxs-lookup"><span data-stu-id="cfcb1-108">Below are some of the more common methods.</span></span>  
  
## <a name="exposing-the-query-as-a-parameter"></a><span data-ttu-id="cfcb1-109">Exponer la consulta como un parámetro</span><span class="sxs-lookup"><span data-stu-id="cfcb1-109">Exposing the Query as a Parameter</span></span>  
 <span data-ttu-id="cfcb1-110">El procedimiento siguiente tiene pasos para exponer la consulta usada por un componente de origen OData como un parámetro del paquete.</span><span class="sxs-lookup"><span data-stu-id="cfcb1-110">The following procedure has steps to expose query used by an OData Source component as a parameter to the package.</span></span>  
  
1.  <span data-ttu-id="cfcb1-111">Haga clic con el botón derecho en **Tarea Flujo de datos** y seleccione la opción **Parametrizar…** .</span><span class="sxs-lookup"><span data-stu-id="cfcb1-111">Right click on the **Data Flow task** and select the **Parameterize...** option.</span></span>  
  
2.  <span data-ttu-id="cfcb1-112">En el cuadro de diálogo **Parametrizar**, seleccione **[\<Name of the OData Source Component>].[Query]** para **Propiedad**.</span><span class="sxs-lookup"><span data-stu-id="cfcb1-112">In the **Parameterize** dialog, select **[\<Name of the OData Source Component>].[Query]** for **Property**.</span></span>  
  
3.  <span data-ttu-id="cfcb1-113">Elija si se va a **Crear nuevo parámetro** o **Usar un parámetro existente**.</span><span class="sxs-lookup"><span data-stu-id="cfcb1-113">Choose whether to **create new parameter** or **use an existing parameter**.</span></span>  
  
4.  <span data-ttu-id="cfcb1-114">Si selecciona **Crear nuevo parámetro**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="cfcb1-114">If you select **Create new parameter**, do the following:</span></span>  
  
    1.  <span data-ttu-id="cfcb1-115">Escriba el **nombre** y la **descripción** del parámetro.</span><span class="sxs-lookup"><span data-stu-id="cfcb1-115">Enter **name** and **description** for the parameter.</span></span>  
  
    2.  <span data-ttu-id="cfcb1-116">Especifique el **valor** predeterminado del parámetro.</span><span class="sxs-lookup"><span data-stu-id="cfcb1-116">Specify default **value** for the parameter.</span></span>  
  
    3.  <span data-ttu-id="cfcb1-117">Especifique el **ámbito** (**paquete** o **proyecto**) del parámetro.</span><span class="sxs-lookup"><span data-stu-id="cfcb1-117">Specify the **scope** (**package** or **project**) for the parameter.</span></span>  
  
    4.  <span data-ttu-id="cfcb1-118">Especifique si el parámetro es **obligatorio** o no</span><span class="sxs-lookup"><span data-stu-id="cfcb1-118">Specify whether the parameter is **required** or not</span></span>  
  
5.  <span data-ttu-id="cfcb1-119">Haga clic en **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="cfcb1-119">Click **OK** to close the dialog box.</span></span>  
  
## <a name="using-an-expression"></a><span data-ttu-id="cfcb1-120">Usar una expresión</span><span class="sxs-lookup"><span data-stu-id="cfcb1-120">Using an Expression</span></span>  
 <span data-ttu-id="cfcb1-121">Este método resulta útil si desea crear dinámicamente la cadena de consulta en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="cfcb1-121">This method is useful when you want to dynamically construct query string at runtime.</span></span> <span data-ttu-id="cfcb1-122">En este ejemplo, la variable MaxRows se establecerá mediante otros medios (script, parámetros, etc.).</span><span class="sxs-lookup"><span data-stu-id="cfcb1-122">In this example, MaxRows variable will be set through other means (script, parameter, etc).</span></span>  
  
1.  <span data-ttu-id="cfcb1-123">Seleccione la **Tarea Flujo de datos** que contiene el **Origen OData**.</span><span class="sxs-lookup"><span data-stu-id="cfcb1-123">Select the **Data Flow Task** which contains your **OData Source**.</span></span>  
  
2.  <span data-ttu-id="cfcb1-124">En la ventana **Propiedades** , resalte la propiedad **Expresiones** .</span><span class="sxs-lookup"><span data-stu-id="cfcb1-124">In the **Properties** window, highlight the **Expressions** property.</span></span>  
  
3.  <span data-ttu-id="cfcb1-125">Haga clic en... (puntos suspensivos) para abrir el editor de **expresiones de propiedad**.</span><span class="sxs-lookup"><span data-stu-id="cfcb1-125">Click the ... (ellipses) button to bring up the **Property Expressions Editor**.</span></span>  
  
4.  <span data-ttu-id="cfcb1-126">Seleccione la propiedad **[OData Source].[Query]** .</span><span class="sxs-lookup"><span data-stu-id="cfcb1-126">Select the **[OData Source].[Query]** property.</span></span>  
  
5.  <span data-ttu-id="cfcb1-127">Haga clic en... botón (puntos suspensivos) para **expresión**.</span><span class="sxs-lookup"><span data-stu-id="cfcb1-127">Click the ... (ellipses) button for **Expression**.</span></span>  
  
6.  <span data-ttu-id="cfcb1-128">Escriba la **expresión**.</span><span class="sxs-lookup"><span data-stu-id="cfcb1-128">Enter the **expression**.</span></span>  
  
7.  <span data-ttu-id="cfcb1-129">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="cfcb1-129">Click **OK**.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="cfcb1-130">Tenga en cuenta que cuando se usa este enfoque debe asegurarse de que los valores establecidos están codificados correctamente como una dirección URL.</span><span class="sxs-lookup"><span data-stu-id="cfcb1-130">Note that when using this approach you need to ensure that the values set are properly URL encoded.</span></span> <span data-ttu-id="cfcb1-131">Cuando reciba valores de datos proporcionados por el usuario (por ejemplo, al establecer valores de opción de consulta individuales de un parámetro), debe asegurarse de que los valores se validan para impedir posibles ataques de inyección de código SQL.</span><span class="sxs-lookup"><span data-stu-id="cfcb1-131">When receiving values from user input (for example, setting individual query option values from a parameter), you must ensure that the values are validated to avoid potential SQL injection-type attacks.</span></span>  
  
  
