---
title: Crear y publicar una regla de negocios (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- business rules [Master Data Services], creating
- creating business rules [Master Data Services]
ms.assetid: 6961d636-4d69-468e-81f7-8d0be6a4a039
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 4dfca5613a1f328e02b3fd2c7337885a23889207
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676035"
---
# <a name="create-and-publish-a-business-rule-master-data-services"></a><span data-ttu-id="254c1-102">Crear y publicar una regla de negocios (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="254c1-102">Create and Publish a Business Rule (Master Data Services)</span></span>
  <span data-ttu-id="254c1-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], cree una regla de negocios para asegurarse de la exactitud de los datos maestros.</span><span class="sxs-lookup"><span data-stu-id="254c1-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a business rule to ensure the accuracy of your master data.</span></span> <span data-ttu-id="254c1-104">Después de crear una regla, debe publicarla antes de poder aplicarla a los datos.</span><span class="sxs-lookup"><span data-stu-id="254c1-104">After you create a rule, you must publish it before you can apply it to data.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="254c1-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="254c1-105">Prerequisites</span></span>  
 <span data-ttu-id="254c1-106">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="254c1-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="254c1-107">Debe disponer de permiso para tener acceso al área funcional de **Administración del sistema** .</span><span class="sxs-lookup"><span data-stu-id="254c1-107">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="254c1-108">Debe ser administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="254c1-108">You must be a model administrator.</span></span> <span data-ttu-id="254c1-109">Para obtener más información, vea [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="254c1-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-create-and-publish-a-business-rule"></a><span data-ttu-id="254c1-110">Crear y publicar una regla de negocios</span><span class="sxs-lookup"><span data-stu-id="254c1-110">To create and publish a business rule</span></span>  
  
1.  <span data-ttu-id="254c1-111">En [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], haga clic en **Administración del sistema**.</span><span class="sxs-lookup"><span data-stu-id="254c1-111">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="254c1-112">En la barra de menús, seleccione **Administrar** y haga clic en **Reglas de negocios**.</span><span class="sxs-lookup"><span data-stu-id="254c1-112">From the menu bar, point to **Manage** and click **Business Rules**.</span></span>  
  
3.  <span data-ttu-id="254c1-113">En la página **Mantenimiento de reglas de negocios** , en la lista **Modelo** , seleccione un modelo.</span><span class="sxs-lookup"><span data-stu-id="254c1-113">On the **Business Rule Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="254c1-114">En la lista **Entidad** , seleccione una entidad.</span><span class="sxs-lookup"><span data-stu-id="254c1-114">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="254c1-115">En la lista **Tipo de miembro** , seleccione un tipo de miembro al que aplicar la regla de negocios.</span><span class="sxs-lookup"><span data-stu-id="254c1-115">From the **Member Type** list, select a type of member for the business rule to apply to.</span></span>  
  
6.  <span data-ttu-id="254c1-116">En la lista **Atributo** , seleccione un atributo o deje el valor predeterminado de **Todos**.</span><span class="sxs-lookup"><span data-stu-id="254c1-116">From the **Attribute** list, select an attribute or leave the default of **All**.</span></span>  
  
7.  <span data-ttu-id="254c1-117">Haga clic en **Agregar regla de negocios**.</span><span class="sxs-lookup"><span data-stu-id="254c1-117">Click **Add business rule**.</span></span>  
  
8.  <span data-ttu-id="254c1-118">Haga clic en **Editar regla de negocios seleccionada**.</span><span class="sxs-lookup"><span data-stu-id="254c1-118">Click **Edit selected business rule**.</span></span>  
  
9. <span data-ttu-id="254c1-119">En el panel **Componentes** , expanda el nodo **Condiciones** .</span><span class="sxs-lookup"><span data-stu-id="254c1-119">In the **Components** pane, expand the **Conditions** node.</span></span>  
  
10. <span data-ttu-id="254c1-120">Haga clic en una condición y arrástrela hasta la etiqueta **condiciones** del panel **If** .</span><span class="sxs-lookup"><span data-stu-id="254c1-120">Click a condition and drag it to the **IF** pane's **Conditions** label.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="254c1-121">Puede eliminar elementos de la regla de negocio si hace clic con el botón secundario y elige **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="254c1-121">You can delete items from your business rule by right-clicking and choosing **Delete**.</span></span>  
  
11. <span data-ttu-id="254c1-122">En el panel **atributos** , haga clic en un atributo y arrástrelo hasta la etiqueta **seleccionar atributo** del panel **Editar condición** .</span><span class="sxs-lookup"><span data-stu-id="254c1-122">In the **Attributes** pane, click an attribute and drag it to the **Edit Condition** pane's **Select attribute** label.</span></span>  
  
12. <span data-ttu-id="254c1-123">En el panel **Editar condición** , complete los campos obligatorios.</span><span class="sxs-lookup"><span data-stu-id="254c1-123">In the **Edit Condition** pane, complete any required fields.</span></span>  
  
13. <span data-ttu-id="254c1-124">En el panel **Editar acción** , haga clic en **Guardar elemento**.</span><span class="sxs-lookup"><span data-stu-id="254c1-124">In the **Edit Condition** pane, click **Save item**.</span></span>  
  
14. <span data-ttu-id="254c1-125">En el panel **Componentes** , expanda el nodo **Acciones** .</span><span class="sxs-lookup"><span data-stu-id="254c1-125">In the **Components** pane, expand the **Actions** node.</span></span>  
  
15. <span data-ttu-id="254c1-126">Haga clic en una acción y arrástrela hasta la etiqueta **Acción** del panel **THEN** .</span><span class="sxs-lookup"><span data-stu-id="254c1-126">Click an action and drag it to the **THEN** pane's **Action** label.</span></span>  
  
16. <span data-ttu-id="254c1-127">En el panel **Atributos** , haga clic en un atributo y arrástrelo hasta la etiqueta **Seleccionar atributo** del panel **Editar acción** .</span><span class="sxs-lookup"><span data-stu-id="254c1-127">In the **Attributes** pane, click an attribute and drag it to the **Edit Action** pane's **Select attribute** label.</span></span>  
  
17. <span data-ttu-id="254c1-128">En el panel **Editar acción** , complete los campos obligatorios.</span><span class="sxs-lookup"><span data-stu-id="254c1-128">In the **Edit Action** pane, complete any required fields.</span></span>  
  
18. <span data-ttu-id="254c1-129">En el panel **Editar acción** , haga clic en **Guardar elemento**.</span><span class="sxs-lookup"><span data-stu-id="254c1-129">In the **Edit Action** pane, click **Save item**.</span></span>  
  
19. <span data-ttu-id="254c1-130">Opcionalmente, agregue varias condiciones a la regla.</span><span class="sxs-lookup"><span data-stu-id="254c1-130">Optionally, add multiple conditions to the rule.</span></span> <span data-ttu-id="254c1-131">Para obtener más información, vea [Agregar varias condiciones a una regla de negocios &#40;Master Data Services&#41;](../../2014/master-data-services/add-multiple-conditions-to-a-business-rule-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="254c1-131">For more information, see [Add Multiple Conditions to a Business Rule &#40;Master Data Services&#41;](../../2014/master-data-services/add-multiple-conditions-to-a-business-rule-master-data-services.md).</span></span>  
  
20. <span data-ttu-id="254c1-132">Haga clic en **Atrás**.</span><span class="sxs-lookup"><span data-stu-id="254c1-132">Click **Back**.</span></span>  
  
21. <span data-ttu-id="254c1-133">Opcionalmente, en la página **Business Rules Maintenance** (Mantenimiento de las reglas de negocios), en la fila que contiene la regla de negocio, haga doble clic en una celda de las columnas **Nombre**, **Descripción**o **Notificación** para actualizar el valor.</span><span class="sxs-lookup"><span data-stu-id="254c1-133">Optionally, on the **Business Rules Maintenance** page, for the row that contains your business rule, double-click a cell in the **Name**, **Description**, or **Notification** column to update the value.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="254c1-134">Las notificaciones solo se envían para las reglas que incluyen una acción de validación.</span><span class="sxs-lookup"><span data-stu-id="254c1-134">Notifications are sent only for rules that include a validation action.</span></span>  
  
22. <span data-ttu-id="254c1-135">Haga clic en **Publicar reglas de negocios**.</span><span class="sxs-lookup"><span data-stu-id="254c1-135">Click **Publish business rules**.</span></span>  
  
23. <span data-ttu-id="254c1-136">En el cuadro de diálogo de confirmación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="254c1-136">On the confirmation dialog box, click **OK**.</span></span> <span data-ttu-id="254c1-137">El estado de la regla cambia a **Activo**.</span><span class="sxs-lookup"><span data-stu-id="254c1-137">The rule's status changes to **Active**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="254c1-138">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="254c1-138">Next Steps</span></span>  
  
-   <span data-ttu-id="254c1-139">Aplique las reglas de negocios a los datos siguiendo uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="254c1-139">Apply business rules to data by following one of these procedures:</span></span>  
  
    -   [<span data-ttu-id="254c1-140">Validar miembros específicos con las reglas de negocios &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="254c1-140">Validate Specific Members against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-specific-members-against-business-rules-master-data-services.md)  
  
    -   [<span data-ttu-id="254c1-141">Validar una versión con las reglas de negocios &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="254c1-141">Validate a Version against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-a-version-against-business-rules-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="254c1-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="254c1-142">See Also</span></span>  
 <span data-ttu-id="254c1-143">[Configurar reglas de negocios para enviar notificaciones &#40;Master Data Services&#41;](../../2014/master-data-services/configure-business-rules-to-send-notifications-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="254c1-143">[Configure Business Rules to Send Notifications &#40;Master Data Services&#41;](../../2014/master-data-services/configure-business-rules-to-send-notifications-master-data-services.md) </span></span>  
 <span data-ttu-id="254c1-144">[Cambiar el nombre de una regla de negocios &#40;Master Data Services&#41;](../../2014/master-data-services/change-a-business-rule-name-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="254c1-144">[Change a Business Rule Name &#40;Master Data Services&#41;](../../2014/master-data-services/change-a-business-rule-name-master-data-services.md) </span></span>  
 [<span data-ttu-id="254c1-145">Agregar varias condiciones a una regla de negocios &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="254c1-145">Add Multiple Conditions to a Business Rule &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/add-multiple-conditions-to-a-business-rule-master-data-services.md)  
  
  
