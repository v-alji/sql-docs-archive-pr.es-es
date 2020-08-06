---
title: Iniciar acciones según los cambios de valores de atributos (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- business rules [Master Data Services], tracking attribute changes
- change tracking groups [Master Data Services], initiating actions
ms.assetid: 5e4402ce-31db-4774-a2a1-552335f87693
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 50931b9f9c4bd5d08596d485ba695143b9c6594e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744734"
---
# <a name="initiate-actions-based-on-attribute-value-changes-master-data-services"></a><span data-ttu-id="e28b4-102">Iniciar acciones según los cambios de valores de atributos (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="e28b4-102">Initiate Actions Based on Attribute Value Changes (Master Data Services)</span></span>
  <span data-ttu-id="e28b4-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], cree una regla de negocios para iniciar acciones según los cambios de los valores de atributos.</span><span class="sxs-lookup"><span data-stu-id="e28b4-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a business rule to initiate actions based on changes to attribute values.</span></span> <span data-ttu-id="e28b4-104">Por ejemplo, cuando un valor de atributo concreto cambia, quizás desee cambiar un valor, enviar una notificación o iniciar un flujo de trabajo externo.</span><span class="sxs-lookup"><span data-stu-id="e28b4-104">For example, when a specific attribute value changes, you may want to change a value, send a notification, or start an external workflow.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e28b4-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="e28b4-105">Prerequisites</span></span>  
 <span data-ttu-id="e28b4-106">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="e28b4-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="e28b4-107">Debe disponer de permiso para tener acceso al área funcional de **Administración del sistema** .</span><span class="sxs-lookup"><span data-stu-id="e28b4-107">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="e28b4-108">Debe ser administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="e28b4-108">You must be a model administrator.</span></span> <span data-ttu-id="e28b4-109">Para obtener más información, vea [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="e28b4-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="e28b4-110">Los atributos deben estar en un grupo de seguimiento de cambios.</span><span class="sxs-lookup"><span data-stu-id="e28b4-110">Your attributes must be in a change tracking group.</span></span> <span data-ttu-id="e28b4-111">Consulte [Agregar atributos a un grupo de seguimiento de cambios &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="e28b4-111">See [Add Attributes to a Change Tracking Group &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md) for more information.</span></span>  
  
### <a name="to-create-a-business-rule-to-initiate-actions-based-on-attribute-value-changes"></a><span data-ttu-id="e28b4-112">Crear una regla de negocios para iniciar acciones según los cambios de los valores de atributos</span><span class="sxs-lookup"><span data-stu-id="e28b4-112">To create a business rule to initiate actions based on attribute value changes</span></span>  
  
1.  <span data-ttu-id="e28b4-113">En [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], haga clic en **Administración del sistema**.</span><span class="sxs-lookup"><span data-stu-id="e28b4-113">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="e28b4-114">En la barra de menús, seleccione **Administrar** y haga clic en **Reglas de negocios**.</span><span class="sxs-lookup"><span data-stu-id="e28b4-114">From the menu bar, point to **Manage** and click **Business Rules**.</span></span>  
  
3.  <span data-ttu-id="e28b4-115">En la página **Mantenimiento de reglas de negocios** , en la lista **Modelo** , seleccione un modelo.</span><span class="sxs-lookup"><span data-stu-id="e28b4-115">On the **Business Rule Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="e28b4-116">En la lista **Entidad** , seleccione una entidad.</span><span class="sxs-lookup"><span data-stu-id="e28b4-116">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="e28b4-117">En la lista **Tipo de miembro** , seleccione un tipo de miembro al que aplicar la regla de negocios.</span><span class="sxs-lookup"><span data-stu-id="e28b4-117">From the **Member Type** list, select a type of member for the business rule to apply to.</span></span>  
  
6.  <span data-ttu-id="e28b4-118">En la lista **Atributo** , seleccione un atributo o deje el valor predeterminado de **Todos**.</span><span class="sxs-lookup"><span data-stu-id="e28b4-118">From the **Attribute** list, select an attribute or leave the default of **All**.</span></span>  
  
7.  <span data-ttu-id="e28b4-119">Haga clic en **Agregar regla de negocios**.</span><span class="sxs-lookup"><span data-stu-id="e28b4-119">Click **Add business rule**.</span></span>  
  
8.  <span data-ttu-id="e28b4-120">Haga clic en **Editar regla de negocios seleccionada**.</span><span class="sxs-lookup"><span data-stu-id="e28b4-120">Click **Edit selected business rule**.</span></span>  
  
9. <span data-ttu-id="e28b4-121">En el panel **Componentes** , expanda el nodo **Condiciones** .</span><span class="sxs-lookup"><span data-stu-id="e28b4-121">In the **Components** pane, expand the **Conditions** node.</span></span>  
  
10. <span data-ttu-id="e28b4-122">En el nodo **Comparación de valor** , arrastre **ha cambiado** hasta la etiqueta **Condiciones** del panel **IF** .</span><span class="sxs-lookup"><span data-stu-id="e28b4-122">Under the **Value comparison** node, drag **has changed** to the **IF** pane's **Conditions** label.</span></span>  
  
11. <span data-ttu-id="e28b4-123">En el panel **atributos** , haga clic en un atributo y arrástrelo hasta la etiqueta **seleccionar atributo** del panel **Editar condición** .</span><span class="sxs-lookup"><span data-stu-id="e28b4-123">In the **Attributes** pane, click an attribute and drag it to the **Edit Condition** pane's **Select attribute** label.</span></span> <span data-ttu-id="e28b4-124">Este atributo no tiene ningún efecto en la regla, así que seleccione cualquiera disponible.</span><span class="sxs-lookup"><span data-stu-id="e28b4-124">This attribute has no effect on the rule, so select any available attribute.</span></span>  
  
12. <span data-ttu-id="e28b4-125">En el panel **Editar condición** , en el cuadro **Grupo de seguimientos de cambios** , escriba el número del grupo de seguimiento de cambios que asignó como parte de los requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="e28b4-125">In the **Edit Condition** pane, in the **Change tracking group** box, type the number of the change tracking group that you assigned as part of the prerequisites.</span></span>  
  
13. <span data-ttu-id="e28b4-126">En el panel **Editar acción** , haga clic en **Guardar elemento**.</span><span class="sxs-lookup"><span data-stu-id="e28b4-126">In the **Edit Condition** pane, click **Save item**.</span></span>  
  
14. <span data-ttu-id="e28b4-127">En el panel **Componentes** , expanda el nodo **Acciones** .</span><span class="sxs-lookup"><span data-stu-id="e28b4-127">In the **Components** pane, expand the **Actions** node.</span></span>  
  
15. <span data-ttu-id="e28b4-128">Haga clic en una acción y arrástrela hasta la etiqueta **Acción** del panel **THEN** .</span><span class="sxs-lookup"><span data-stu-id="e28b4-128">Click an action and drag it to the **THEN** pane's **Action** label.</span></span>  
  
16. <span data-ttu-id="e28b4-129">En el panel **Atributos** , haga clic en un atributo y arrástrelo hasta la etiqueta **Seleccionar atributo** del panel **Editar acción** .</span><span class="sxs-lookup"><span data-stu-id="e28b4-129">In the **Attributes** pane, click an attribute and drag it to the **Edit Action** pane's **Select attribute** label.</span></span>  
  
17. <span data-ttu-id="e28b4-130">En el panel **Editar acción** , complete los campos obligatorios.</span><span class="sxs-lookup"><span data-stu-id="e28b4-130">In the **Edit Action** pane, complete any required fields.</span></span>  
  
18. <span data-ttu-id="e28b4-131">En el panel **Editar acción** , haga clic en **Guardar elemento**.</span><span class="sxs-lookup"><span data-stu-id="e28b4-131">In the **Edit Action** pane, click **Save item**.</span></span>  
  
19. <span data-ttu-id="e28b4-132">Haga clic en **Atrás**.</span><span class="sxs-lookup"><span data-stu-id="e28b4-132">Click **Back**.</span></span>  
  
20. <span data-ttu-id="e28b4-133">Opcionalmente, en la página **Business Rules Maintenance** (Mantenimiento de las reglas de negocios), en la fila que contiene la regla de negocio, haga doble clic en una celda de las columnas **Nombre**, **Descripción**o **Notificación** para actualizar el valor.</span><span class="sxs-lookup"><span data-stu-id="e28b4-133">Optionally, on the **Business Rules Maintenance** page, for the row that contains your business rule, double-click a cell in the **Name**, **Description**, or **Notification** column to update the value.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e28b4-134">Las notificaciones solo se envían para las reglas que incluyen una acción de validación.</span><span class="sxs-lookup"><span data-stu-id="e28b4-134">Notifications are sent only for rules that include a validation action.</span></span>  
  
21. <span data-ttu-id="e28b4-135">Haga clic en **Publicar reglas de negocios**.</span><span class="sxs-lookup"><span data-stu-id="e28b4-135">Click **Publish business rules**.</span></span>  
  
22. <span data-ttu-id="e28b4-136">En el cuadro de diálogo de confirmación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e28b4-136">On the confirmation dialog box, click **OK**.</span></span> <span data-ttu-id="e28b4-137">El estado de la regla cambia a **Activo**.</span><span class="sxs-lookup"><span data-stu-id="e28b4-137">The rule's status changes to **Active**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="e28b4-138">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="e28b4-138">Next Steps</span></span>  
  
-   <span data-ttu-id="e28b4-139">Aplique las reglas de negocios a los datos siguiendo uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="e28b4-139">Apply business rules to data by following one of these procedures:</span></span>  
  
    -   [<span data-ttu-id="e28b4-140">Validar miembros específicos con las reglas de negocios &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="e28b4-140">Validate Specific Members against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-specific-members-against-business-rules-master-data-services.md)  
  
    -   [<span data-ttu-id="e28b4-141">Validar una versión con las reglas de negocios &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="e28b4-141">Validate a Version against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-a-version-against-business-rules-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="e28b4-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e28b4-142">See Also</span></span>  
 <span data-ttu-id="e28b4-143">[Agregar atributos a un grupo de Change Tracking &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="e28b4-143">[Add Attributes to a Change Tracking Group &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md) </span></span>  
 [<span data-ttu-id="e28b4-144">Reglas de negocios &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="e28b4-144">Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/business-rules-master-data-services.md)  
  
  
