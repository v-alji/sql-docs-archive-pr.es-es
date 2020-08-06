---
title: Agregar varias condiciones a una regla de negocios (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- business rules [Master Data Services], multiple conditions
ms.assetid: 5f0f6958-6cf2-444b-bdcd-05b887637a0b
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c62b8dfa4f459958d12bd384b85aa74bef382b21
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674889"
---
# <a name="add-multiple-conditions-to-a-business-rule-master-data-services"></a><span data-ttu-id="2a4ce-102">Agregar varias condiciones a una regla de negocios (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="2a4ce-102">Add Multiple Conditions to a Business Rule (Master Data Services)</span></span>
  <span data-ttu-id="2a4ce-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], agregue varias condiciones **AND** u **OR** a una regla de negocio cuando quiera una regla más compleja.</span><span class="sxs-lookup"><span data-stu-id="2a4ce-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], add multiple **AND** or **OR** conditions to a business rule when you want a more complex rule.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2a4ce-104">Si crea una regla de negocio que usa el operador **OR** , considere crear una regla distinta para cada instrucción condicional que se pueda evaluar de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="2a4ce-104">If you create a business rule that uses the **OR** operator, consider creating a separate rule for each conditional statement that can be evaluated independently.</span></span> <span data-ttu-id="2a4ce-105">A continuación, puede excluir las reglas según sea necesario, proporcionando más flexibilidad y facilitando la solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="2a4ce-105">You can then exclude rules as needed, providing more flexibility and easier troubleshooting.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2a4ce-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="2a4ce-106">Prerequisites</span></span>  
 <span data-ttu-id="2a4ce-107">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="2a4ce-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="2a4ce-108">Debe disponer de permiso para tener acceso al área funcional de **Administración del sistema** .</span><span class="sxs-lookup"><span data-stu-id="2a4ce-108">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="2a4ce-109">Debe ser administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="2a4ce-109">You must be a model administrator.</span></span> <span data-ttu-id="2a4ce-110">Para obtener más información, vea [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="2a4ce-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="2a4ce-111">Una regla de negocios debe existir.</span><span class="sxs-lookup"><span data-stu-id="2a4ce-111">A business rule must exist.</span></span> <span data-ttu-id="2a4ce-112">Para obtener más información, consulte [Crear y publicar una regla de negocios &#40;Master Data Services&#41;](../../2014/master-data-services/create-and-publish-a-business-rule-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="2a4ce-112">For more information, see [Create and Publish a Business Rule &#40;Master Data Services&#41;](../../2014/master-data-services/create-and-publish-a-business-rule-master-data-services.md).</span></span>  
  
### <a name="to-add-multiple-conditions-to-a-business-rule"></a><span data-ttu-id="2a4ce-113">Para agregar varias condiciones a una regla de negocios</span><span class="sxs-lookup"><span data-stu-id="2a4ce-113">To add multiple conditions to a business rule</span></span>  
  
1.  <span data-ttu-id="2a4ce-114">En [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], haga clic en **Administración del sistema**.</span><span class="sxs-lookup"><span data-stu-id="2a4ce-114">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="2a4ce-115">En la barra de menús, seleccione **Administrar** y haga clic en **Reglas de negocios**.</span><span class="sxs-lookup"><span data-stu-id="2a4ce-115">From the menu bar, point to **Manage** and click **Business Rules**.</span></span>  
  
3.  <span data-ttu-id="2a4ce-116">En la página **Mantenimiento de reglas de negocios** , en la lista **Modelo** , seleccione un modelo.</span><span class="sxs-lookup"><span data-stu-id="2a4ce-116">On the **Business Rule Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="2a4ce-117">En la lista **Entidad** , seleccione una entidad.</span><span class="sxs-lookup"><span data-stu-id="2a4ce-117">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="2a4ce-118">En la lista **tipo de miembro** , seleccione un tipo de miembro.</span><span class="sxs-lookup"><span data-stu-id="2a4ce-118">From the **Member Type** list, select a type of member.</span></span>  
  
6.  <span data-ttu-id="2a4ce-119">En la lista **Atributo** , seleccione un atributo o deje el valor predeterminado de **Todos**.</span><span class="sxs-lookup"><span data-stu-id="2a4ce-119">From the **Attribute** list, select an attribute or leave the default of **All**.</span></span>  
  
7.  <span data-ttu-id="2a4ce-120">Haga clic en la fila de la regla de negocios que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="2a4ce-120">Click the row for the business rule you want to edit.</span></span>  
  
8.  <span data-ttu-id="2a4ce-121">Haga clic en **Editar regla de negocios seleccionada**.</span><span class="sxs-lookup"><span data-stu-id="2a4ce-121">Click **Edit selected business rule**.</span></span>  
  
9. <span data-ttu-id="2a4ce-122">En el panel **componentes** , expanda el nodo **operadores lógicos** .</span><span class="sxs-lookup"><span data-stu-id="2a4ce-122">In the **Components** pane, expand the **Logical Operators** node.</span></span>  
  
10. <span data-ttu-id="2a4ce-123">Haga clic en **and** u **or** y arrástrelo a la etiqueta **y** del panel **If** .</span><span class="sxs-lookup"><span data-stu-id="2a4ce-123">Click **AND** or **OR** and drag it to the **IF** pane's **AND** label.</span></span>  
  
11. <span data-ttu-id="2a4ce-124">En el panel **Componentes** , expanda el nodo **Condiciones** .</span><span class="sxs-lookup"><span data-stu-id="2a4ce-124">In the **Components** pane, expand the **Conditions** node.</span></span>  
  
12. <span data-ttu-id="2a4ce-125">Haga clic en una condición y arrástrela **hasta la** etiqueta **y** o **o** desde el paso 10.</span><span class="sxs-lookup"><span data-stu-id="2a4ce-125">Click a condition and drag it to **IF** pane, to the **AND** or **OR** label from step 10.</span></span>  
  
13. <span data-ttu-id="2a4ce-126">En el panel **atributos** , haga clic en un atributo y arrástrelo hasta la etiqueta **seleccionar atributo** del panel **Editar condición** .</span><span class="sxs-lookup"><span data-stu-id="2a4ce-126">In the **Attributes** pane, click an attribute and drag it to the **Edit Condition** pane's **Select attribute** label.</span></span>  
  
14. <span data-ttu-id="2a4ce-127">En el panel **Editar condición** , complete los campos obligatorios.</span><span class="sxs-lookup"><span data-stu-id="2a4ce-127">In the **Edit Condition** pane, complete any required fields.</span></span>  
  
15. <span data-ttu-id="2a4ce-128">En el panel **Editar acción** , haga clic en **Guardar elemento**.</span><span class="sxs-lookup"><span data-stu-id="2a4ce-128">In the **Edit Condition** pane, click **Save item**.</span></span>  
  
16. <span data-ttu-id="2a4ce-129">Opcionalmente, para agregar más condiciones, en el panel **componentes** , arrastre **and** u **or** a **and** u or **en el** panel **If** .</span><span class="sxs-lookup"><span data-stu-id="2a4ce-129">Optionally, to add more conditions, from the **Components** pane, drag **AND** or **OR** to any **AND** or **OR** in the **IF** pane.</span></span> <span data-ttu-id="2a4ce-130">A continuación, siga los pasos 13-15.</span><span class="sxs-lookup"><span data-stu-id="2a4ce-130">Then follow steps 13-15.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="2a4ce-131">Para eliminar una condición, haga clic en el nombre de la condición y, en el panel **Editar condición** , haga clic en **Eliminar elemento**.</span><span class="sxs-lookup"><span data-stu-id="2a4ce-131">To delete a condition, click the name of the condition and in the **Edit Condition** pane, click **Delete item**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a4ce-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2a4ce-132">See Also</span></span>  
 <span data-ttu-id="2a4ce-133">[Reglas de negocios &#40;Master Data Services&#41;](../../2014/master-data-services/business-rules-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="2a4ce-133">[Business Rules &#40;Master Data Services&#41;](../../2014/master-data-services/business-rules-master-data-services.md) </span></span>  
 <span data-ttu-id="2a4ce-134">[Cambiar el nombre de una regla de negocios &#40;Master Data Services&#41;](../../2014/master-data-services/change-a-business-rule-name-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="2a4ce-134">[Change a Business Rule Name &#40;Master Data Services&#41;](../../2014/master-data-services/change-a-business-rule-name-master-data-services.md) </span></span>  
 [<span data-ttu-id="2a4ce-135">Configurar reglas de negocios para enviar notificaciones &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="2a4ce-135">Configure Business Rules to Send Notifications &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/configure-business-rules-to-send-notifications-master-data-services.md)  
  
  
