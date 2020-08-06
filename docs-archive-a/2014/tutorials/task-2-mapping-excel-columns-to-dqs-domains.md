---
title: 'Tarea 2: asignar columnas de Excel a dominios de DQS | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: f347cc92-950f-4021-b7af-393640dfe821
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 293b035ff52845959e2c8b70c63df643ae6e3e55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676282"
---
# <a name="task-2-mapping-excel-columns-to-dqs-domains"></a><span data-ttu-id="362d3-102">Tarea 2: Asignación de columnas de Excel a dominios de DQS</span><span class="sxs-lookup"><span data-stu-id="362d3-102">Task 2: Mapping Excel Columns to DQS Domains</span></span>
    
1.  <span data-ttu-id="362d3-103">En la página **Asignación** , seleccione **Archivo de Excel** en **Origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="362d3-103">In the **Map** page, select **Excel File** for **Data Source**.</span></span>  
  
2.  <span data-ttu-id="362d3-104">Haga clic en **examinar**, seleccione **Suppliers.xlsx**y haga clic en **abrir**.</span><span class="sxs-lookup"><span data-stu-id="362d3-104">Click **Browse**, select **Suppliers.xlsx**, and click **Open**.</span></span>  
  
3.  <span data-ttu-id="362d3-105">Seleccione **IncomingSuppliers $** en la **hoja de cálculo**.</span><span class="sxs-lookup"><span data-stu-id="362d3-105">Select **IncomingSuppliers$** for the **Worksheet**.</span></span>  
  
4.  <span data-ttu-id="362d3-106">Asigne las columnas como se muestra en la tabla y en la captura de pantalla siguientes.</span><span class="sxs-lookup"><span data-stu-id="362d3-106">Map columns as shown in the following table and screenshot.</span></span> <span data-ttu-id="362d3-107">Al crear asignaciones para el dominio de **Estado** , haga clic en el botón **Agregar una asignación de columna** en la barra de herramientas situada justo encima de la lista.</span><span class="sxs-lookup"><span data-stu-id="362d3-107">When creating mappings for the **State** domain, click **Add a column mapping** button on the toolbar located just above the list.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="362d3-108">No se usa la columna o el dominio de ID. de **proveedor** para la limpieza.</span><span class="sxs-lookup"><span data-stu-id="362d3-108">You are not using **Supplier ID** column/domain for cleansing.</span></span> <span data-ttu-id="362d3-109">Usará el dominio ID. de **proveedor** más adelante en la actividad de búsqueda de coincidencias.</span><span class="sxs-lookup"><span data-stu-id="362d3-109">You will use the **Supplier ID** domain later in the matching activity.</span></span>  
  
    |<span data-ttu-id="362d3-110">Columna de Excel</span><span class="sxs-lookup"><span data-stu-id="362d3-110">Excel column</span></span>|<span data-ttu-id="362d3-111">Dominio de DQS</span><span class="sxs-lookup"><span data-stu-id="362d3-111">DQS Domain</span></span>|  
    |------------------|----------------|  
    |<span data-ttu-id="362d3-112">Nombre del proveedor</span><span class="sxs-lookup"><span data-stu-id="362d3-112">Supplier Name</span></span>|<span data-ttu-id="362d3-113">Nombre del proveedor</span><span class="sxs-lookup"><span data-stu-id="362d3-113">Supplier Name</span></span>|  
    |<span data-ttu-id="362d3-114">ContactEmailAddress</span><span class="sxs-lookup"><span data-stu-id="362d3-114">ContactEmailAddress</span></span>|<span data-ttu-id="362d3-115">Dirección de correo electrónico de contacto</span><span class="sxs-lookup"><span data-stu-id="362d3-115">Contact Email</span></span>|  
    |<span data-ttu-id="362d3-116">Address Line</span><span class="sxs-lookup"><span data-stu-id="362d3-116">Address Line</span></span>|<span data-ttu-id="362d3-117">Address Line</span><span class="sxs-lookup"><span data-stu-id="362d3-117">Address Line</span></span>|  
    |<span data-ttu-id="362d3-118">City</span><span class="sxs-lookup"><span data-stu-id="362d3-118">City</span></span>|<span data-ttu-id="362d3-119">City</span><span class="sxs-lookup"><span data-stu-id="362d3-119">City</span></span>|  
    |<span data-ttu-id="362d3-120">State</span><span class="sxs-lookup"><span data-stu-id="362d3-120">State</span></span>|<span data-ttu-id="362d3-121">State</span><span class="sxs-lookup"><span data-stu-id="362d3-121">State</span></span>|  
    |<span data-ttu-id="362d3-122">País (haga clic en **+ (agregar una asignación de columnas)** barra de herramientas para agregar una fila</span><span class="sxs-lookup"><span data-stu-id="362d3-122">Country (Click **+(Add a column mapping)** toolbar to add a row)</span></span>|<span data-ttu-id="362d3-123">Country</span><span class="sxs-lookup"><span data-stu-id="362d3-123">Country</span></span>|  
    |<span data-ttu-id="362d3-124">Zip Code</span><span class="sxs-lookup"><span data-stu-id="362d3-124">Zip Code</span></span>|<span data-ttu-id="362d3-125">Zip</span><span class="sxs-lookup"><span data-stu-id="362d3-125">Zip</span></span>|  
  
     <span data-ttu-id="362d3-126">![Asignaciones de columnas de Excel a dominios](../../2014/tutorials/media/et-mappingexcelcolumnstodqsdomains-01.jpg "Asignaciones de columnas de Excel a dominios")</span><span class="sxs-lookup"><span data-stu-id="362d3-126">![Mappings of Excel Columns to Domains](../../2014/tutorials/media/et-mappingexcelcolumnstodqsdomains-01.jpg "Mappings of Excel Columns to Domains")</span></span>  
  
5.  <span data-ttu-id="362d3-127">Como ha asignado todos los dominios individuales dentro del dominio compuesto **validación de direcciones** , el dominio compuesto participa automáticamente en el proceso de limpieza.</span><span class="sxs-lookup"><span data-stu-id="362d3-127">As you have mapped all the individual domains within the **Address Validation** composite domain, the composite domain automatically participates in the cleansing process.</span></span> <span data-ttu-id="362d3-128">Haga clic en el botón **Ver/seleccionar dominios compuestos** para ver que el dominio compuesto **validación de direcciones** se selecciona automáticamente y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="362d3-128">Click **View/Select Composite Domains** button to see that the **Address Validation** composite domain is automatically selected, and then click **OK**.</span></span>  
  
     <span data-ttu-id="362d3-129">![Cuadro de diálogo Ver o seleccionar dominios compuestos](../../2014/tutorials/media/et-mappingexcelcolumnstodqsdomains-02.jpg "Cuadro de diálogo Ver o seleccionar dominios compuestos")</span><span class="sxs-lookup"><span data-stu-id="362d3-129">![View/Select Composite Domains Dialog Box](../../2014/tutorials/media/et-mappingexcelcolumnstodqsdomains-02.jpg "View/Select Composite Domains Dialog Box")</span></span>  
  
6.  <span data-ttu-id="362d3-130">Haga clic en **siguiente** para cambiar a la página **limpieza** .</span><span class="sxs-lookup"><span data-stu-id="362d3-130">Click **Next** to switch to the **Cleanse** page.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="362d3-131">siguiente paso</span><span class="sxs-lookup"><span data-stu-id="362d3-131">Next Step</span></span>  
 [<span data-ttu-id="362d3-132">Tarea 3: Limpieza de datos en la base de conocimiento Proveedores</span><span class="sxs-lookup"><span data-stu-id="362d3-132">Task 3: Cleansing Data against the Suppliers Knowledge Base</span></span>](../../2014/tutorials/task-3-cleansing-data-against-the-suppliers-knowledge-base.md)  
  
  
