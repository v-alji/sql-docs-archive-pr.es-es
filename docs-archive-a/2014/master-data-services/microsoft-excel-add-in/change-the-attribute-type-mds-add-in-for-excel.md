---
title: Cambar el tipo de atributo (complemento MDS para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 9d3001d9-8d0f-4e4a-8e04-4f666bf0df69
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: a55ca53fcf6923957e2196840aea2fb5914e1746
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745358"
---
# <a name="change-the-attribute-type-mds-add-in-for-excel"></a><span data-ttu-id="c7aa5-102">Cambar el tipo de atributo (complemento MDS para Excel)</span><span class="sxs-lookup"><span data-stu-id="c7aa5-102">Change the Attribute Type (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="c7aa5-103">En el [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], los administradores pueden cambiar el tipo de atributo cuando el tipo de datos o el número de caracteres permitido sea incorrecto.</span><span class="sxs-lookup"><span data-stu-id="c7aa5-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], administrators can change the attribute type when the data type or number of allowed characters is incorrect.</span></span>  
  
 <span data-ttu-id="c7aa5-104">Si quiere cambiar el tipo de atributo para crear una lista restringida (atributo basado en dominios), consulte [Crear un atributo basado en dominio &#40;complemento MDS para Excel&#41;](create-a-domain-based-attribute-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="c7aa5-104">If you want to change the attribute type to create a constrained list (domain-based attribute), see [Create a Domain-based Attribute &#40;MDS Add-in for Excel&#41;](create-a-domain-based-attribute-mds-add-in-for-excel.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c7aa5-105"> No se puede actualizar el tipo o la longitud de las columnas **Nombre** o **Código** .</span><span class="sxs-lookup"><span data-stu-id="c7aa5-105">You cannot update the type or length of the **Name** or **Code** columns.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c7aa5-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="c7aa5-106">Prerequisites</span></span>  
 <span data-ttu-id="c7aa5-107">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="c7aa5-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="c7aa5-108">Debe disponer del permiso para tener acceso a las áreas funcionales del **Explorador** y de **Administración del sistema** .</span><span class="sxs-lookup"><span data-stu-id="c7aa5-108">You must have permission to access the **System Administration** and **Explorer** functional areas.</span></span>  
  
-   <span data-ttu-id="c7aa5-109">Debe ser administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="c7aa5-109">You must be a model administrator.</span></span> <span data-ttu-id="c7aa5-110">Para obtener más información, vea [administradores &#40;Master Data Services&#41;](../administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="c7aa5-110">For more information, see [Administrators &#40;Master Data Services&#41;](../administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="c7aa5-111">Debe haber un modelo, una entidad y un atributo existentes.</span><span class="sxs-lookup"><span data-stu-id="c7aa5-111">There must be an existing model, entity, and attribute.</span></span>  
  
### <a name="to-change-the-attribute-type"></a><span data-ttu-id="c7aa5-112">Para cambiar el tipo de atributo</span><span class="sxs-lookup"><span data-stu-id="c7aa5-112">To change the attribute type</span></span>  
  
1.  <span data-ttu-id="c7aa5-113">En Excel, cargue la entidad que contenga la columna (atributo) que desee cambiar.</span><span class="sxs-lookup"><span data-stu-id="c7aa5-113">In Excel, load the entity that contains the column (attribute) you want to change.</span></span> <span data-ttu-id="c7aa5-114">Para obtener más información, consulte [carga de datos de MDS en Excel](export-data-to-excel-from-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="c7aa5-114">For more information, see [Load Data from MDS into Excel](export-data-to-excel-from-master-data-services.md).</span></span>  
  
2.  <span data-ttu-id="c7aa5-115">Haga clic en cualquier celda en la columna que desee cambiar.</span><span class="sxs-lookup"><span data-stu-id="c7aa5-115">Click any cell in the column you want to change.</span></span>  
  
3.  <span data-ttu-id="c7aa5-116">En el grupo **Compilar modelo** , haga clic en **Propiedades de atributo**.</span><span class="sxs-lookup"><span data-stu-id="c7aa5-116">In the **Build Model** group, click **Attribute Properties**.</span></span>  
  
4.  <span data-ttu-id="c7aa5-117">En el cuadro de diálogo **Propiedades de atributo** , actualice los valores según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="c7aa5-117">In the **Attribute Properties** dialog box, update settings as needed.</span></span>  
  
5.  <span data-ttu-id="c7aa5-118">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="c7aa5-118">Click **OK**.</span></span>  
  
## <a name="what-happens-when-you-change-the-attribute-type"></a><span data-ttu-id="c7aa5-119">¿Qué ocurre cuando se cambia el tipo de atributo?</span><span class="sxs-lookup"><span data-stu-id="c7aa5-119">What happens when you change the attribute type?</span></span>  
 <span data-ttu-id="c7aa5-120">Si hay alguna dependencia en el atributo, como si una regla de negocios de MDS hace referencia al atributo o si el atributo se incluye en una vista de suscripción, y cambia el tipo de datos de un atributo, MDS hará lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c7aa5-120">If there is any dependency on the attribute, such as the attribute is referenced by any MDS business rule or the attribute is included in a subscription view, and you change the data type of an attribute, MDS will:</span></span>  
  
-   <span data-ttu-id="c7aa5-121">Cambiar el tipo de datos del atributo.</span><span class="sxs-lookup"><span data-stu-id="c7aa5-121">Change the data type of the attribute.</span></span>  
  
-   <span data-ttu-id="c7aa5-122">Genere una copia del atributo con el sufijo "_old" que no contenga ningún valor.</span><span class="sxs-lookup"><span data-stu-id="c7aa5-122">Generate a copy of the attribute with the suffix "_old" that does not contain any value.</span></span> <span data-ttu-id="c7aa5-123">Esto se denomina atributo **desusado** .</span><span class="sxs-lookup"><span data-stu-id="c7aa5-123">This is called a **deprecated** attribute.</span></span>  
  
 <span data-ttu-id="c7aa5-124">Sin embargo, todas las dependencias existentes en el atributo original apuntarán al atributo desusado, no al modificado.</span><span class="sxs-lookup"><span data-stu-id="c7aa5-124">However, all the existing dependencies on the original attribute will point to the deprecated attribute, and not to the changed one.</span></span>  
  
 <span data-ttu-id="c7aa5-125">Esto implica lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c7aa5-125">This implies that:</span></span>  
  
-   <span data-ttu-id="c7aa5-126">Debe actualizar las reglas de negocios para que apunten al atributo modificado, ya que la lógica puede no ser la misma dado el nuevo tipo de datos del atributo.</span><span class="sxs-lookup"><span data-stu-id="c7aa5-126">You must refresh the business rules to point to the changed attribute because the logic may not be the same given the new data type of the attribute.</span></span> <span data-ttu-id="c7aa5-127">Tendrá que editar todas las reglas afectadas y hacer que las expresiones que apuntan a referencias quitadas del atributo desusado (_old) apunten al atributo actualizado.</span><span class="sxs-lookup"><span data-stu-id="c7aa5-127">You will have to edit each affected rule, and then rework the expressions to point to remove references from the deprecated attribute (_old) to point to the updated attribute.</span></span>  
  
-   <span data-ttu-id="c7aa5-128">Debe abrir cualquier vista de suscripción en la selección de administración de integración, seleccionar la fila de la vista, abrirla para su edición haciendo clic en el icono de lápiz y, a continuación, hacer clic en el icono **Guardar disco** para actualizar la definición de la vista.</span><span class="sxs-lookup"><span data-stu-id="c7aa5-128">You must open any subscription views under the Integration Management selection, select the view row, open it for editing by clicking the pencil icon, and then click the **Save disk** icon to refresh the view definition.</span></span> <span data-ttu-id="c7aa5-129">No es necesario hacer ningún otro cambio para regenerar la sintaxis de la vista.</span><span class="sxs-lookup"><span data-stu-id="c7aa5-129">No other change is needed to regenerate the view syntax.</span></span>  
  
-   <span data-ttu-id="c7aa5-130">En las tablas de ensayo que incluyen el atributo se agregará una columna de atributo desusado, lo que significa que el código de ensayo se verá afectado.</span><span class="sxs-lookup"><span data-stu-id="c7aa5-130">Staging tables that include the attribute will have a deprecated attribute column added to them, which means that your staging code will be affected.</span></span> <span data-ttu-id="c7aa5-131">Para deshacerse del atributo desusado, puede eliminarlo después de haber actualizado las reglas de negocios y las vistas de suscripción.</span><span class="sxs-lookup"><span data-stu-id="c7aa5-131">To get rid of the deprecated attribute, you can delete it after you have updated the business rules and subscription views.</span></span>  
  
 <span data-ttu-id="c7aa5-132">**Eliminar el atributo desusado**</span><span class="sxs-lookup"><span data-stu-id="c7aa5-132">**Deleting the deprecated attribute**</span></span>  
  
 <span data-ttu-id="c7aa5-133">Antes de eliminar cualquier atributo desusado, debe quitar las referencias al mismo, como corregir las reglas de negocios y regenerar las vistas de suscripción como se ha descrito anteriormente.</span><span class="sxs-lookup"><span data-stu-id="c7aa5-133">Before you delete any deprecated attribute, you must remove any references to the attribute such as fixing the business rules and regenerating subscription views as described earlier.</span></span> <span data-ttu-id="c7aa5-134">De lo contrario, cuando intente eliminar el atributo desusado obtendrá un error en la página web Administración del sistema que indica que no se puede eliminar el atributo porque un objeto hace referencia a él.</span><span class="sxs-lookup"><span data-stu-id="c7aa5-134">Otherwise, you will get an error in the System Administration web page when you attempt to delete the deprecated attribute stating that the attribute cannot be deleted because it is referenced by an object.</span></span>  
  
 <span data-ttu-id="c7aa5-135">Para eliminar un atributo, consulte [eliminar un atributo &#40;Master Data Services&#41;](../delete-an-attribute-master-data-services.md)</span><span class="sxs-lookup"><span data-stu-id="c7aa5-135">To delete an attribute, see [Delete an Attribute &#40;Master Data Services&#41;](../delete-an-attribute-master-data-services.md)</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="c7aa5-136">Es tedioso cambiar los tipos de datos de los atributos de MDS que tienen datos y entidades relacionadas existentes, especialmente si se ha declarado una regla de negocios o una vista de suscripción que depende de la entidad.</span><span class="sxs-lookup"><span data-stu-id="c7aa5-136">It is cumbersome to change data types for MDS attributes that have existing data and related entities, especially if there is a business rule or subscription view declared which depends on the entity.</span></span> <span data-ttu-id="c7aa5-137">La práctica recomendada es empezar con un tipo de datos que sea suficientemente flexible como para contener los valores necesarios.</span><span class="sxs-lookup"><span data-stu-id="c7aa5-137">The best practice is to start with a data type that is flexible enough to hold the necessary values.</span></span> <span data-ttu-id="c7aa5-138">Por ejemplo, las cadenas pueden ser pequeñas al principio, pero quizás haya que agrandarlas con el tiempo, por lo que debe considerar los escenarios de caso peor.</span><span class="sxs-lookup"><span data-stu-id="c7aa5-138">For example, strings may start small, but may need to be lengthened over time, so consider the worst case scenarios.</span></span> <span data-ttu-id="c7aa5-139">La longitud adicional de las cadenas de texto puede ser molesta (por ejemplo, es difícil encajar en la pantalla cuadros de texto anchos de la GUI), por lo que debe evitar una longitud grande de las cadenas.</span><span class="sxs-lookup"><span data-stu-id="c7aa5-139">Extra text string length can be burdensome (for example, wide GUI text boxes are hard to fit on the screen), so avoid too long string length.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7aa5-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c7aa5-140">See Also</span></span>  
 <span data-ttu-id="c7aa5-141">[Atributos &#40;Master Data Services&#41;](../attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="c7aa5-141">[Attributes &#40;Master Data Services&#41;](../attributes-master-data-services.md) </span></span>  
 [<span data-ttu-id="c7aa5-142">Generar un modelo &#40;complemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="c7aa5-142">Building a Model &#40;MDS Add-in for Excel&#41;</span></span>](building-a-model-mds-add-in-for-excel.md)  
  
  
