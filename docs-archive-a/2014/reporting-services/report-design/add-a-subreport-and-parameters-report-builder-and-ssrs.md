---
title: Agregar un subinforme y parámetros (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10093"
- sql12.rtp.rptdesigner.subreportproperties.general.f1
ms.assetid: 94f960f8-a629-4f1e-8277-c3b8f0680d98
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3aeede343763ea5fc8fbdfde179208f98fa1a2ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662556"
---
# <a name="add-a-subreport-and-parameters-report-builder-and-ssrs"></a><span data-ttu-id="8fc87-102">Agregar un subinforme y parámetros (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="8fc87-102">Add a Subreport and Parameters (Report Builder and SSRS)</span></span>
  <span data-ttu-id="8fc87-103">Agregue subinformes a un informe cuando desee crear un informe principal que actúe como contenedor para varios informes relacionados.</span><span class="sxs-lookup"><span data-stu-id="8fc87-103">Add subreports to a report when you want to create a main report that is a container for multiple related reports.</span></span> <span data-ttu-id="8fc87-104">Un subinforme es una referencia a otro informe.</span><span class="sxs-lookup"><span data-stu-id="8fc87-104">A subreport is a reference to another report.</span></span> <span data-ttu-id="8fc87-105">Para relacionar informes mediante valores de datos (por ejemplo, para que varios informes muestren datos del mismo cliente), debe diseñar un informe con parámetros (por ejemplo, un informe que muestre los detalles de un cliente concreto) como el subinforme.</span><span class="sxs-lookup"><span data-stu-id="8fc87-105">To relate the reports through data values (for example, to have multiple reports show data for the same customer), you must design a parameterized report (for example, a report that shows the details for a specific customer) as the subreport.</span></span> <span data-ttu-id="8fc87-106">Al agregar un subinforme al informe principal, puede especificar los parámetros que se deben pasar al subinforme.</span><span class="sxs-lookup"><span data-stu-id="8fc87-106">When you add a subreport to the main report, you can specify parameters to pass to the subreport.</span></span>  
  
 <span data-ttu-id="8fc87-107">También puede agregar subinformes a filas o columnas dinámicas de una tabla o matriz.</span><span class="sxs-lookup"><span data-stu-id="8fc87-107">You can also add subreports to dynamic rows or columns in a table or matrix.</span></span> <span data-ttu-id="8fc87-108">Cuando se procesa el informe principal, se procesa el subinforme para cada fila.</span><span class="sxs-lookup"><span data-stu-id="8fc87-108">When the main report is processed, the subreport is processed for each row.</span></span> <span data-ttu-id="8fc87-109">En este caso, considere la posibilidad de lograr el efecto deseado usando regiones de datos o regiones de datos anidadas.</span><span class="sxs-lookup"><span data-stu-id="8fc87-109">In this case, consider whether you can achieve the desired effect by using data regions or nested data regions.</span></span>  
  
 <span data-ttu-id="8fc87-110">Para agregar un subinforme a un informe, primero debe crear el informe que actuará como el subinforme.</span><span class="sxs-lookup"><span data-stu-id="8fc87-110">To add a subreport to a report, you must first create the report that will act as the subreport.</span></span> <span data-ttu-id="8fc87-111">Para obtener más información sobre la creación del subinforme, vea [Subinformes &#40;Generador de informes y SSRS&#41;](subreports-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="8fc87-111">For more information on creating the subreport, see [Subreports &#40;Report Builder and SSRS&#41;](subreports-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-subreport"></a><span data-ttu-id="8fc87-112">Agregar un subinforme</span><span class="sxs-lookup"><span data-stu-id="8fc87-112">To add a subreport</span></span>  
  
1.  <span data-ttu-id="8fc87-113">En la pestaña **Insertar** , haga clic en **Subinforme**.</span><span class="sxs-lookup"><span data-stu-id="8fc87-113">On the **Insert** tab, click **Subreport**.</span></span>  
  
2.  <span data-ttu-id="8fc87-114">En la superficie de diseño, haga clic en una ubicación en el informe y, a continuación, arrastre un cuadro hasta que alcance el tamaño deseado para el subinforme.</span><span class="sxs-lookup"><span data-stu-id="8fc87-114">On the design surface, click a location on the report and then drag a box to the desired size of the subreport.</span></span> <span data-ttu-id="8fc87-115">O bien, haga clic en la superficie de diseño para crear un subinforme de tamaño predeterminado.</span><span class="sxs-lookup"><span data-stu-id="8fc87-115">Alternatively, click the design surface to create a subreport of default size.</span></span>  
  
3.  <span data-ttu-id="8fc87-116">Haga clic con el botón derecho en el subinforme y, después, haga clic en **Propiedades del subinforme**.</span><span class="sxs-lookup"><span data-stu-id="8fc87-116">Right-click the subreport, and then click **Subreport Properties**.</span></span>  
  
4.  <span data-ttu-id="8fc87-117">En el cuadro de diálogo **Propiedades del subinforme** , escriba un nombre en el cuadro de texto **Nombre** o acepte el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="8fc87-117">In the **Subreport Properties** dialog box, type a name in the **Name** text box or accept the default.</span></span> <span data-ttu-id="8fc87-118">El nombre debe ser único en el informe.</span><span class="sxs-lookup"><span data-stu-id="8fc87-118">The name must be unique within the report.</span></span> <span data-ttu-id="8fc87-119">De forma predeterminada, se asigna un nombre general como Subreport1 o Subreport2.</span><span class="sxs-lookup"><span data-stu-id="8fc87-119">By default, a general name such as Subreport1 or Subreport2 is assigned.</span></span>  
  
5.  <span data-ttu-id="8fc87-120">En el cuadro **Usar este informe como un subinforme** , escriba el nombre del informe o haga clic en **Examinar**.</span><span class="sxs-lookup"><span data-stu-id="8fc87-120">In the **Use this report as a subreport** box, click **Browse**, or type the name of the report.</span></span> <span data-ttu-id="8fc87-121">Es preferible hacer clic en **Examinar** , porque la ruta de acceso al subinforme se especificará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="8fc87-121">Clicking **Browse** is preferred because the path to the subreport will be specified automatically.</span></span> <span data-ttu-id="8fc87-122">El informe se puede especificar de varias maneras.</span><span class="sxs-lookup"><span data-stu-id="8fc87-122">You can specify the report in the several ways.</span></span> <span data-ttu-id="8fc87-123">Para más información, vea [Especificar las rutas de acceso a los elementos externos &#40;Generador de informes y SSRS&#41;](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="8fc87-123">For more information, see [Specifying Paths to External Items &#40;Report Builder and SSRS&#41;](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span></span>  
  
6.  <span data-ttu-id="8fc87-124">(Opcional) Haga clic en **Sí** para **Omitir borde en el salto de página** , para impedir que un borde se represente en mitad del subinforme si este abarca más de una página.</span><span class="sxs-lookup"><span data-stu-id="8fc87-124">(Optional) Click **Yes** for **Omit border on page break** to prevent a border from being rendered in the middle of the subreport if the subreport spans more than one page.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-specify-parameters-to-pass-to-a-subreport"></a><span data-ttu-id="8fc87-125">Especificar los parámetros que se pasarán a un subinforme</span><span class="sxs-lookup"><span data-stu-id="8fc87-125">To specify parameters to pass to a subreport</span></span>  
  
1.  <span data-ttu-id="8fc87-126">En la vista de diseño, haga clic con el botón derecho en el subinforme y, después, haga clic en **Propiedades del subinforme**.</span><span class="sxs-lookup"><span data-stu-id="8fc87-126">In Design view, right-click the subreport and then click **Subreport Properties**.</span></span>  
  
2.  <span data-ttu-id="8fc87-127">En el cuadro de diálogo **Propiedades del subinforme** , haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="8fc87-127">In the **Subreport Properties** dialog box, click **Parameters**.</span></span>  
  
3.  <span data-ttu-id="8fc87-128">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="8fc87-128">Click **Add**.</span></span> <span data-ttu-id="8fc87-129">Se agrega una nueva fila a la cuadrícula de parámetros.</span><span class="sxs-lookup"><span data-stu-id="8fc87-129">A new row is added to the parameter grid.</span></span>  
  
4.  <span data-ttu-id="8fc87-130">En el cuadro de texto **Nombre** , escriba el nombre de un parámetro en el subinforme o elíjalo del cuadro de lista.</span><span class="sxs-lookup"><span data-stu-id="8fc87-130">In the **Name** text box, type the name of a parameter in the subreport or choose it from the list box.</span></span> <span data-ttu-id="8fc87-131">Este nombre debe coincidir con un parámetro de informe del subinforme, no con un parámetro de consulta.</span><span class="sxs-lookup"><span data-stu-id="8fc87-131">This name must match a report parameter, not a query parameter, in the subreport.</span></span>  
  
5.  <span data-ttu-id="8fc87-132">En el cuadro de lista **Valor** , escriba o seleccione el valor que se pasará al subinforme.</span><span class="sxs-lookup"><span data-stu-id="8fc87-132">In the **Value** list box, type or select a value to pass to the subreport.</span></span> <span data-ttu-id="8fc87-133">Este valor puede ser texto estático o una expresión que haga referencia a un campo o a otro objeto del informe principal.</span><span class="sxs-lookup"><span data-stu-id="8fc87-133">This value can be static text or an expression that references a field or other object in the main report.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8fc87-134">En el Generador de informes, si falta un parámetro de la lista **Parámetros** y se ha definido un valor predeterminado para el subinforme, este se procesará correctamente.</span><span class="sxs-lookup"><span data-stu-id="8fc87-134">In Report Builder, if a parameter is missing from the **Parameters** list and the subreport has a default value defined, the subreport will be processed correctly.</span></span>  
    >   
    >  <span data-ttu-id="8fc87-135">En el Diseñador de informes, todos los parámetros que requiera el subinforme deben incluirse en la lista **Parámetros** .</span><span class="sxs-lookup"><span data-stu-id="8fc87-135">In Report Designer, all parameters that are required by the subreport must be included in the **Parameters** list.</span></span> <span data-ttu-id="8fc87-136">Si falta un parámetro necesario, el subinforme no se muestra correctamente en el informe principal.</span><span class="sxs-lookup"><span data-stu-id="8fc87-136">If a required parameter is missing, the subreport is not displayed correctly in the main report.</span></span>  
  
6.  <span data-ttu-id="8fc87-137">Repita los pasos 3 y 5 para especificar un nombre y un valor para cada parámetro del subinforme.</span><span class="sxs-lookup"><span data-stu-id="8fc87-137">Repeat steps 3-5 to specify a name and value for each subreport parameter.</span></span>  
  
7.  <span data-ttu-id="8fc87-138">Para eliminar un parámetro de subinforme, haga clic en el parámetro en la cuadrícula de parámetros y, a continuación, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="8fc87-138">To delete a subreport parameter, click the parameter in the parameter grid, and then click **Delete**.</span></span>  
  
8.  <span data-ttu-id="8fc87-139">Para cambiar el orden de un parámetro del subinforme, selecciónelo y, después, haga clic en el botón Subir o Bajar.</span><span class="sxs-lookup"><span data-stu-id="8fc87-139">To change the order of a subreport parameter, click the parameter, and then click the up button or the down button.</span></span>  
  
     <span data-ttu-id="8fc87-140">Cambiar el orden de un parámetro de subinforme no afecta al procesamiento del subinforme.</span><span class="sxs-lookup"><span data-stu-id="8fc87-140">Changing the order of a subreport parameter does not affect the processing of the subreport.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fc87-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8fc87-141">See Also</span></span>  
 <span data-ttu-id="8fc87-142">[Subinformes &#40;Generador de informes y SSRS&#41;](subreports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="8fc87-142">[Subreports &#40;Report Builder and SSRS&#41;](subreports-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="8fc87-143">Comportamientos de la representación &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="8fc87-143">Rendering Behaviors &#40;Report Builder  and SSRS&#41;</span></span>](rendering-behaviors-report-builder-and-ssrs.md)  
  
  
