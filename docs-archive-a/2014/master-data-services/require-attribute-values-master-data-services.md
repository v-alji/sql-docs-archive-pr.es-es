---
title: Requerir valores de atributo (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- business rules [Master Data Services], requiring attribute values
- attributes [Master Data Services], requiring values
ms.assetid: a360ef13-0c34-43b8-a87e-2f5d8732d30e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 42b412fc42138c5e186c6c7ad42373f20e35f3cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670415"
---
# <a name="require-attribute-values-master-data-services"></a><span data-ttu-id="afecf-102">Requerir valores de atributo (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="afecf-102">Require Attribute Values (Master Data Services)</span></span>
  <span data-ttu-id="afecf-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], requiera valores de atributo cuando desee asegurarse de que los datos maestros están completos.</span><span class="sxs-lookup"><span data-stu-id="afecf-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], require attribute values when you want to ensure your master data is complete.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="afecf-104">Los miembros que sean valores de atributos basados en dominio y que falten no se muestran en las jerarquías derivadas que se basen en esas relaciones.</span><span class="sxs-lookup"><span data-stu-id="afecf-104">Members that are missing domain-based attribute values are not displayed in derived hierarchies that are based on those relationships.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="afecf-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="afecf-105">Prerequisites</span></span>  
 <span data-ttu-id="afecf-106">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="afecf-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="afecf-107">Debe disponer de permiso para tener acceso al área funcional de **Administración del sistema** .</span><span class="sxs-lookup"><span data-stu-id="afecf-107">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="afecf-108">Debe ser administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="afecf-108">You must be a model administrator.</span></span> <span data-ttu-id="afecf-109">Para obtener más información, vea [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="afecf-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-require-attribute-values"></a><span data-ttu-id="afecf-110">Requerir los valores de atributo</span><span class="sxs-lookup"><span data-stu-id="afecf-110">To require attribute values</span></span>  
  
1.  <span data-ttu-id="afecf-111">En [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], haga clic en **Administración del sistema**.</span><span class="sxs-lookup"><span data-stu-id="afecf-111">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="afecf-112">En la barra de menús, seleccione **Administrar** y haga clic en **Reglas de negocios**.</span><span class="sxs-lookup"><span data-stu-id="afecf-112">From the menu bar, point to **Manage** and click **Business Rules**.</span></span>  
  
3.  <span data-ttu-id="afecf-113">En la página **Mantenimiento de reglas de negocios** , en la lista **Modelo** , seleccione un modelo.</span><span class="sxs-lookup"><span data-stu-id="afecf-113">On the **Business Rule Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="afecf-114">En la lista **Entidad** , seleccione una entidad.</span><span class="sxs-lookup"><span data-stu-id="afecf-114">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="afecf-115">En la lista **Tipo de miembro** , seleccione un tipo de miembro al que aplicar la regla de negocios.</span><span class="sxs-lookup"><span data-stu-id="afecf-115">From the **Member Type** list, select a type of member for the business rule to apply to.</span></span>  
  
6.  <span data-ttu-id="afecf-116">En la lista **Atributo** , seleccione un atributo o deje el valor predeterminado de **Todos**.</span><span class="sxs-lookup"><span data-stu-id="afecf-116">From the **Attribute** list, select an attribute or leave the default of **All**.</span></span>  
  
7.  <span data-ttu-id="afecf-117">Haga clic en **Agregar regla de negocios**.</span><span class="sxs-lookup"><span data-stu-id="afecf-117">Click **Add business rule**.</span></span>  
  
8.  <span data-ttu-id="afecf-118">Haga clic en **Editar regla de negocios seleccionada**.</span><span class="sxs-lookup"><span data-stu-id="afecf-118">Click **Edit selected business rule**.</span></span>  
  
9. <span data-ttu-id="afecf-119">En el panel **Componentes** , expanda el nodo **Acciones** .</span><span class="sxs-lookup"><span data-stu-id="afecf-119">In the **Components** pane, expand the **Actions** node.</span></span>  
  
10. <span data-ttu-id="afecf-120">Haga clic en **es obligatorio** y arrástrelo hasta la etiqueta de **acción** del panel **then** .</span><span class="sxs-lookup"><span data-stu-id="afecf-120">Click **is required** and drag it to the **THEN** pane's **Action** label.</span></span>  
  
11. <span data-ttu-id="afecf-121">En el panel **Atributos** , haga clic en un atributo y arrástrelo hasta la etiqueta **Seleccionar atributo** del panel **Editar acción** .</span><span class="sxs-lookup"><span data-stu-id="afecf-121">In the **Attributes** pane, click an attribute and drag it to the **Edit Action** pane's **Select attribute** label.</span></span>  
  
12. <span data-ttu-id="afecf-122">En el panel **Editar acción** , haga clic en **Guardar elemento**.</span><span class="sxs-lookup"><span data-stu-id="afecf-122">In the **Edit Action** pane, click **Save item**.</span></span>  
  
13. <span data-ttu-id="afecf-123">Haga clic en **Atrás**.</span><span class="sxs-lookup"><span data-stu-id="afecf-123">Click **Back**.</span></span>  
  
14. <span data-ttu-id="afecf-124">Opcionalmente, en la página **Business Rules Maintenance** (Mantenimiento de las reglas de negocios), en la fila que contiene la regla de negocio, haga doble clic en una celda de las columnas **Nombre**, **Descripción**o **Notificación** para actualizar el valor.</span><span class="sxs-lookup"><span data-stu-id="afecf-124">Optionally, on the **Business Rules Maintenance** page, for the row that contains your business rule, double-click a cell in the **Name**, **Description**, or **Notification** column to update the value.</span></span>  
  
15. <span data-ttu-id="afecf-125">Haga clic en **Publicar reglas de negocios**.</span><span class="sxs-lookup"><span data-stu-id="afecf-125">Click **Publish business rules**.</span></span>  
  
16. <span data-ttu-id="afecf-126">En el cuadro de diálogo de confirmación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="afecf-126">On the confirmation dialog box, click **OK**.</span></span> <span data-ttu-id="afecf-127">El estado de la regla cambia a **Activo**.</span><span class="sxs-lookup"><span data-stu-id="afecf-127">The rule's status changes to **Active**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="afecf-128">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="afecf-128">Next Steps</span></span>  
  
-   <span data-ttu-id="afecf-129">Aplique las reglas de negocios a los datos siguiendo uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="afecf-129">Apply business rules to data by following one of these procedures:</span></span>  
  
    -   [<span data-ttu-id="afecf-130">Validar miembros específicos con las reglas de negocios &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="afecf-130">Validate Specific Members against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-specific-members-against-business-rules-master-data-services.md)  
  
    -   [<span data-ttu-id="afecf-131">Validar una versión con las reglas de negocios &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="afecf-131">Validate a Version against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-a-version-against-business-rules-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="afecf-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="afecf-132">See Also</span></span>  
 <span data-ttu-id="afecf-133">[Reglas de negocios &#40;Master Data Services&#41;](../../2014/master-data-services/business-rules-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="afecf-133">[Business Rules &#40;Master Data Services&#41;](../../2014/master-data-services/business-rules-master-data-services.md) </span></span>  
 [<span data-ttu-id="afecf-134">Jerarquías derivadas &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="afecf-134">Derived Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/derived-hierarchies-master-data-services.md)  
  
  
