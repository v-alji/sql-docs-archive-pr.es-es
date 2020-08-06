---
title: Generar automáticamente valores de atributo que no sean Code (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: b82f6f81-6e9c-4918-9ea9-4ab5f5d11b15
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 8db6c89bdce2a11a5a54ed3a763a7bc41bd7f1be
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676043"
---
# <a name="automatically-generate-attribute-values-other-than-code-master-data-services"></a><span data-ttu-id="fcf5f-102">Generar automáticamente valores de atributo que no sean Code (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="fcf5f-102">Automatically Generate Attribute Values Other Than Code (Master Data Services)</span></span>
  <span data-ttu-id="fcf5f-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], genere de forma automática los valores de atributo de una entidad si quiere que se asigne automáticamente un entero como valor cada vez que se apliquen reglas de negocio.</span><span class="sxs-lookup"><span data-stu-id="fcf5f-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], automatically generate values for an entity's attribute values when you want an integer to be automatically assigned as the value each time business rules are applied.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="fcf5f-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="fcf5f-104">Prerequisites</span></span>  
 <span data-ttu-id="fcf5f-105">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="fcf5f-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="fcf5f-106">Debe disponer de permiso para tener acceso al área funcional de **Administración del sistema** .</span><span class="sxs-lookup"><span data-stu-id="fcf5f-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="fcf5f-107">Debe ser administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="fcf5f-107">You must be a model administrator.</span></span> <span data-ttu-id="fcf5f-108">Para obtener más información, vea [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="fcf5f-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="fcf5f-109">Debe existir un atributo numérico.</span><span class="sxs-lookup"><span data-stu-id="fcf5f-109">A numeric attribute must exist.</span></span> <span data-ttu-id="fcf5f-110">Para obtener más información, consulte [Crear un atributo numérico &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-numeric-attribute-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="fcf5f-110">For more information, see [Create a Numeric Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-numeric-attribute-master-data-services.md).</span></span>  
  
### <a name="to-automatically-generate-an-attribute-value"></a><span data-ttu-id="fcf5f-111">Para generar automáticamente un valor de atributo</span><span class="sxs-lookup"><span data-stu-id="fcf5f-111">To automatically generate an attribute value</span></span>  
  
1.  <span data-ttu-id="fcf5f-112">En [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], haga clic en **Administración del sistema**.</span><span class="sxs-lookup"><span data-stu-id="fcf5f-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="fcf5f-113">En la barra de menús, seleccione **Administrar** y haga clic en **Reglas de negocios**.</span><span class="sxs-lookup"><span data-stu-id="fcf5f-113">From the menu bar, point to **Manage** and click **Business Rules**.</span></span>  
  
3.  <span data-ttu-id="fcf5f-114">En la página **Mantenimiento de reglas de negocios** , en la lista **Modelo** , seleccione un modelo.</span><span class="sxs-lookup"><span data-stu-id="fcf5f-114">On the **Business Rule Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="fcf5f-115">En la lista **Entidad** , seleccione una entidad.</span><span class="sxs-lookup"><span data-stu-id="fcf5f-115">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="fcf5f-116">En la lista **Tipo de miembro** , seleccione un tipo de miembro al que aplicar la regla de negocios.</span><span class="sxs-lookup"><span data-stu-id="fcf5f-116">From the **Member Type** list, select a type of member for the business rule to apply to.</span></span>  
  
6.  <span data-ttu-id="fcf5f-117">En la lista **Atributo** , deje el valor predeterminado **Todos**.</span><span class="sxs-lookup"><span data-stu-id="fcf5f-117">From the **Attribute** list, leave the default of **All**.</span></span>  
  
7.  <span data-ttu-id="fcf5f-118">Haga clic en **Agregar regla de negocios**.</span><span class="sxs-lookup"><span data-stu-id="fcf5f-118">Click **Add business rule**.</span></span>  
  
8.  <span data-ttu-id="fcf5f-119">Haga clic en **Editar regla de negocios seleccionada**.</span><span class="sxs-lookup"><span data-stu-id="fcf5f-119">Click **Edit selected business rule**.</span></span>  
  
9. <span data-ttu-id="fcf5f-120">En el panel **Componentes** , expanda el nodo **Acciones** .</span><span class="sxs-lookup"><span data-stu-id="fcf5f-120">In the **Components** pane, expand the **Actions** node.</span></span>  
  
10. <span data-ttu-id="fcf5f-121">En el nodo de valor predeterminado, haga clic en **tiene como valor predeterminado un valor generado** y arrástrelo hasta la etiqueta de **Acciones** del panel **THEN**.</span><span class="sxs-lookup"><span data-stu-id="fcf5f-121">In the Default Value node, click **defaults to a generated value** and drag it to the **THEN** pane's **Actions** label.</span></span>  
  
11. <span data-ttu-id="fcf5f-122">En el panel **Atributos** , haga clic en un atributo que desea generar y arrástrelo hasta la etiqueta **Seleccionar atributo** del panel **Editar acción** .</span><span class="sxs-lookup"><span data-stu-id="fcf5f-122">In the **Attributes** pane, click the attribute with the value you want to generated and drag it to the **Edit Action** pane's **Select attribute** label.</span></span>  
  
12. <span data-ttu-id="fcf5f-123">Escriba un valor en los cuadros **Empezar con** e **Incrementar en** .</span><span class="sxs-lookup"><span data-stu-id="fcf5f-123">Type a value in the **Start with** and **Increment by** boxes.</span></span> <span data-ttu-id="fcf5f-124">Si ya existen miembros, el valor se establece según el mayor valor existente.</span><span class="sxs-lookup"><span data-stu-id="fcf5f-124">If members already exist, the value will be set based on the highest existing value.</span></span> <span data-ttu-id="fcf5f-125">Por ejemplo, si el mayor valor existente es 299 e **Incrementar en** se ha establecido en **1**, el valor del miembro siguiente se establecerá en 300.</span><span class="sxs-lookup"><span data-stu-id="fcf5f-125">For example, if the highest existing value is 299 and you set **Increment by** to **1**, the next member's value will be set to 300.</span></span>  
  
13. <span data-ttu-id="fcf5f-126">En el panel **Editar acción** , haga clic en **Guardar elemento**.</span><span class="sxs-lookup"><span data-stu-id="fcf5f-126">In the **Edit Action** pane, click **Save item**.</span></span>  
  
14. <span data-ttu-id="fcf5f-127">Haga clic en **Atrás**.</span><span class="sxs-lookup"><span data-stu-id="fcf5f-127">Click **Back**.</span></span>  
  
15. <span data-ttu-id="fcf5f-128">Opcionalmente, en la página **Business Rules Maintenance** (Mantenimiento de las reglas de negocios), en la fila que contiene la regla de negocio, haga doble clic en una celda de las columnas **Nombre**, **Descripción**o **Notificación** para actualizar el valor.</span><span class="sxs-lookup"><span data-stu-id="fcf5f-128">Optionally, on the **Business Rules Maintenance** page, for the row that contains your business rule, double-click a cell in the **Name**, **Description**, or **Notification** column to update the value.</span></span>  
  
16. <span data-ttu-id="fcf5f-129">Haga clic en **Publicar reglas de negocios**.</span><span class="sxs-lookup"><span data-stu-id="fcf5f-129">Click **Publish business rules**.</span></span>  
  
17. <span data-ttu-id="fcf5f-130">En el cuadro de diálogo de confirmación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fcf5f-130">On the confirmation dialog box, click **OK**.</span></span> <span data-ttu-id="fcf5f-131">El estado de la regla cambia a **Activo**.</span><span class="sxs-lookup"><span data-stu-id="fcf5f-131">The rule's status changes to **Active**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="fcf5f-132">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="fcf5f-132">Next Steps</span></span>  
  
-   [<span data-ttu-id="fcf5f-133">Validar miembros específicos con las reglas de negocios &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="fcf5f-133">Validate Specific Members against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-specific-members-against-business-rules-master-data-services.md)  
  
-   [<span data-ttu-id="fcf5f-134">Validar una versión con las reglas de negocios &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="fcf5f-134">Validate a Version against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-a-version-against-business-rules-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="fcf5f-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fcf5f-135">See Also</span></span>  
 <span data-ttu-id="fcf5f-136">[Creación automática de código &#40;Master Data Services&#41;](../../2014/master-data-services/automatic-code-creation-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="fcf5f-136">[Automatic Code Creation &#40;Master Data Services&#41;](../../2014/master-data-services/automatic-code-creation-master-data-services.md) </span></span>  
 <span data-ttu-id="fcf5f-137">[Reglas de negocios &#40;Master Data Services&#41;](../../2014/master-data-services/business-rules-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="fcf5f-137">[Business Rules &#40;Master Data Services&#41;](../../2014/master-data-services/business-rules-master-data-services.md) </span></span>  
 [<span data-ttu-id="fcf5f-138">Validación &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="fcf5f-138">Validation &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validation-master-data-services.md)  
  
  
