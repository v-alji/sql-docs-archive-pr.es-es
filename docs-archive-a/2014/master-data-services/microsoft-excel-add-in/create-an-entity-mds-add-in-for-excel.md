---
title: Crear una entidad (Complemento MDS para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: d354abb3-88fe-4b40-a374-f6256b84ffae
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 87ad67f7347da87c67afc11590df6775af4cf3d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662137"
---
# <a name="create-an-entity-mds-add-in-for-excel"></a><span data-ttu-id="844aa-102">Crear una entidad (Complemento MDS para Excel)</span><span class="sxs-lookup"><span data-stu-id="844aa-102">Create an Entity (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="844aa-103">En [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], los administradores pueden crear nuevas entidades para almacenar datos.</span><span class="sxs-lookup"><span data-stu-id="844aa-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], administrators can create new entities to store data.</span></span> <span data-ttu-id="844aa-104">Cuando crea una entidad, debe cargar al menos una muestra de los datos que desea almacenar.</span><span class="sxs-lookup"><span data-stu-id="844aa-104">When you create an entity you should load at least a sampling of the data you want to store.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="844aa-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="844aa-105">Prerequisites</span></span>  
 <span data-ttu-id="844aa-106">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="844aa-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="844aa-107">Debe disponer del permiso para tener acceso a las áreas funcionales del **Explorador** y de **Administración del sistema** .</span><span class="sxs-lookup"><span data-stu-id="844aa-107">You must have permission to access the **System Administration** and **Explorer** functional areas.</span></span>  
  
-   <span data-ttu-id="844aa-108">Debe ser administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="844aa-108">You must be a model administrator.</span></span> <span data-ttu-id="844aa-109">Para obtener más información, vea [administradores &#40;Master Data Services&#41;](../administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="844aa-109">For more information, see [Administrators &#40;Master Data Services&#41;](../administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="844aa-110">Debe tener un modelo existente en el que crear la entidad.</span><span class="sxs-lookup"><span data-stu-id="844aa-110">You must have an existing model to create the entity in.</span></span> <span data-ttu-id="844aa-111">Para obtener más información, consulte [Crear un modelo &#40;Master Data Services&#41;](../create-a-model-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="844aa-111">For more information, see [Create a Model &#40;Master Data Services&#41;](../create-a-model-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="844aa-112">Asegúrese de que los datos cumplen los siguientes requisitos:</span><span class="sxs-lookup"><span data-stu-id="844aa-112">Ensure that your data meets the following requirements:</span></span>  
  
    -   <span data-ttu-id="844aa-113">Los datos deben tener una fila de encabezado.</span><span class="sxs-lookup"><span data-stu-id="844aa-113">The data should have a header row.</span></span>  
  
    -   <span data-ttu-id="844aa-114">Resulta útil tener las columnas **Nombre** y **Código** .</span><span class="sxs-lookup"><span data-stu-id="844aa-114">It is helpful to have **Name** and **Code** columns.</span></span> <span data-ttu-id="844aa-115">**Código** es un identificador único para cada fila.</span><span class="sxs-lookup"><span data-stu-id="844aa-115">**Code** is a unique identifier for each row.</span></span>  
  
    -   <span data-ttu-id="844aa-116">Debe tener al menos una fila de datos distinta del encabezado.</span><span class="sxs-lookup"><span data-stu-id="844aa-116">You should have at least one row of data other than the header.</span></span> <span data-ttu-id="844aa-117">Todas las columnas no necesitan valores, pero los datos deben ser representativos de los que estarán en la entidad.</span><span class="sxs-lookup"><span data-stu-id="844aa-117">All columns do not need values, but the data should be representative of the data that will be in the entity.</span></span>  
  
    -   <span data-ttu-id="844aa-118">Si tiene una columna que contiene un identificador único (conocido en MDS como **Código**), asegúrese de que los valores sean únicos.</span><span class="sxs-lookup"><span data-stu-id="844aa-118">If you have a column that contains a unique identifier (known in MDS as **Code**), ensure that the values are unique.</span></span> <span data-ttu-id="844aa-119">Si ninguna columna contiene identificadores, puede hacer que se generen automáticamente cuando se cree la entidad.</span><span class="sxs-lookup"><span data-stu-id="844aa-119">If no column contains identifiers, you can have them generated automatically when you create the entity.</span></span>  
  
    -   <span data-ttu-id="844aa-120">Asegúrese de que las celdas contienen fórmulas.</span><span class="sxs-lookup"><span data-stu-id="844aa-120">Ensure that no cells contain formulas.</span></span>  
  
    -   <span data-ttu-id="844aa-121">Asegúrese de que las celdas contienen valores de hora.</span><span class="sxs-lookup"><span data-stu-id="844aa-121">Ensure that no cells contain time values.</span></span> <span data-ttu-id="844aa-122">Los valores de fecha se pueden guardar en MDS pero los valores de hora no.</span><span class="sxs-lookup"><span data-stu-id="844aa-122">Date values can be saved in MDS but time values cannot.</span></span>  
  
### <a name="to-create-an-entity-and-load-data"></a><span data-ttu-id="844aa-123">Para crear una entidad y cargar datos</span><span class="sxs-lookup"><span data-stu-id="844aa-123">To create an entity and load data</span></span>  
  
1.  <span data-ttu-id="844aa-124">Abra o cree una hoja de cálculo de Excel que contenga los datos que desea cargar.</span><span class="sxs-lookup"><span data-stu-id="844aa-124">Open or create an Excel worksheet that contains data you want to load.</span></span>  
  
2.  <span data-ttu-id="844aa-125">Seleccione las celdas que desea cargar en la entidad nueva.</span><span class="sxs-lookup"><span data-stu-id="844aa-125">Select the cells you want to load into the new entity.</span></span>  
  
3.  <span data-ttu-id="844aa-126">En la pestaña **Datos maestros** , en el grupo **Generar modelo** , haga clic en **Crear entidad**.</span><span class="sxs-lookup"><span data-stu-id="844aa-126">On the **Master Data** tab, in the **Build Model** group, click **Create Entity**.</span></span>  
  
4.  <span data-ttu-id="844aa-127">Si se le solicita conectarse a un repositorio MDS, conéctese.</span><span class="sxs-lookup"><span data-stu-id="844aa-127">If you are prompted to connect to an MDS repository, connect.</span></span>  
  
5.  <span data-ttu-id="844aa-128">En el cuadro de diálogo **Crear entidad** , deje el intervalo predeterminado o cámbielo para aplicarlo a los datos que desea cargar.</span><span class="sxs-lookup"><span data-stu-id="844aa-128">In the **Create Entity** dialog box, leave the default range or change it to apply to the data you want to load.</span></span>  
  
6.  <span data-ttu-id="844aa-129">No desactive la casilla **Mis tablas tienen encabezados** .</span><span class="sxs-lookup"><span data-stu-id="844aa-129">Do not clear the **My data has headers** check box.</span></span>  
  
7.  <span data-ttu-id="844aa-130">En la lista **Modelo** , seleccione un modelo.</span><span class="sxs-lookup"><span data-stu-id="844aa-130">From the **Model** list, select a model.</span></span>  
  
8.  <span data-ttu-id="844aa-131">En la lista **Versión** , seleccione una versión.</span><span class="sxs-lookup"><span data-stu-id="844aa-131">From the **Version** list, select a version.</span></span>  
  
9. <span data-ttu-id="844aa-132">En el cuadro **Nuevo nombre de entidad** , escriba un nombre para la entidad.</span><span class="sxs-lookup"><span data-stu-id="844aa-132">In the **New entity name** box, type a name for the entity.</span></span>  
  
10. <span data-ttu-id="844aa-133">En la lista **Código** , seleccione la columna que contiene identificadores únicos o haga que los códigos se generen automáticamente.</span><span class="sxs-lookup"><span data-stu-id="844aa-133">From the **Code** list, select the column that contains unique identifiers or have codes generated automatically.</span></span>  
  
11. <span data-ttu-id="844aa-134">Opcional.</span><span class="sxs-lookup"><span data-stu-id="844aa-134">Optional.</span></span> <span data-ttu-id="844aa-135">En la lista **Nombre** , seleccione una columna que contenga los nombres de cada miembro.</span><span class="sxs-lookup"><span data-stu-id="844aa-135">From the **Name** list, select a column that contains names for each member.</span></span>  
  
12. <span data-ttu-id="844aa-136">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="844aa-136">Click **OK**.</span></span> <span data-ttu-id="844aa-137">Cuando haya creado la entidad correctamente, aparecerá una nueva fila de encabezado, las celdas se resaltarán y el nombre de la hoja se actualizará para coincidir con el nombre de la entidad.</span><span class="sxs-lookup"><span data-stu-id="844aa-137">When the entity has been created successfully, a new header row is displayed, the cells are highlighted, and the sheet name is updated to match the entity name.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="844aa-138">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="844aa-138">Next Steps</span></span>  
  
-   <span data-ttu-id="844aa-139">Para ver los errores producidos, en el grupo **Publicar y validar** , haga clic en **Mostrar estado**.</span><span class="sxs-lookup"><span data-stu-id="844aa-139">To view errors that occurred, in the **Publish and Validate** group, click **Show Status**.</span></span> <span data-ttu-id="844aa-140">Se muestran las columnas ValidationStatus e InputStatus.</span><span class="sxs-lookup"><span data-stu-id="844aa-140">ValidationStatus and InputStatus columns are displayed.</span></span> <span data-ttu-id="844aa-141">Para obtener más información, consulte [Validar datos &#40;complemento MDS para Excel&#41;](validating-data-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="844aa-141">For more information, see [Validating Data &#40;MDS Add-in for Excel&#41;](validating-data-mds-add-in-for-excel.md).</span></span>  
  
-   <span data-ttu-id="844aa-142">Confirme que los atributos se crearon con el tipo de datos que esperaba.</span><span class="sxs-lookup"><span data-stu-id="844aa-142">Confirm that the attributes were created as the data type you expected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="844aa-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="844aa-143">See Also</span></span>  
 [<span data-ttu-id="844aa-144">Crear un atributo basado en dominio &#40;complemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="844aa-144">Create a Domain-based Attribute &#40;MDS Add-in for Excel&#41;</span></span>](create-a-domain-based-attribute-mds-add-in-for-excel.md)  
  
  
