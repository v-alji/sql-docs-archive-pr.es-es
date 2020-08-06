---
title: Asignar columnas a dominios compuestos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: d9422412-8a3d-45ae-af7f-072c902a09ba
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6a665b2096579c9da35a1b69be46c4ba6103610f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676088"
---
# <a name="map-columns-to-composite-domains"></a><span data-ttu-id="3698e-102">Asignar columnas a dominios compuestos</span><span class="sxs-lookup"><span data-stu-id="3698e-102">Map Columns to Composite Domains</span></span>
  <span data-ttu-id="3698e-103">Un dominio compuesto consta de dos o más dominios individuales.</span><span class="sxs-lookup"><span data-stu-id="3698e-103">A composite domain consists of two or more single domains.</span></span> <span data-ttu-id="3698e-104">Es posible asignar varias columnas, o una sola con valores delimitados, al dominio.</span><span class="sxs-lookup"><span data-stu-id="3698e-104">You can map multiple columns to the domain, or you can map a single column with delimited values to the domain.</span></span>  
  
 <span data-ttu-id="3698e-105">Si opta por varias columnas, deberá asignar una columna a cada dominio individual del dominio compuesto para aplicar las reglas de este último para la limpieza de datos.</span><span class="sxs-lookup"><span data-stu-id="3698e-105">When you have multiple columns, you must map a column to each single domain in the composite domain to apply the composite domain rules to data cleansing.</span></span> <span data-ttu-id="3698e-106">Para seleccionar los dominios individuales incluidos en el dominio compuesto, utilice Data Quality Client.</span><span class="sxs-lookup"><span data-stu-id="3698e-106">You select the single domains contained in the composite domain, in the Data Quality Client.</span></span> <span data-ttu-id="3698e-107">Para más información, consulte [Crear un dominio compuesto](../../../data-quality-services/create-a-composite-domain.md).</span><span class="sxs-lookup"><span data-stu-id="3698e-107">For more information, see [Create a Composite Domain](../../../data-quality-services/create-a-composite-domain.md).</span></span>  
  
 <span data-ttu-id="3698e-108">Si dispone de una sola columna con valores delimitados, deberá asignarla al dominio compuesto.</span><span class="sxs-lookup"><span data-stu-id="3698e-108">When you have a single column with delimited values, you must map the single column to the composite domain.</span></span> <span data-ttu-id="3698e-109">Los valores deben aparecer en el mismo orden en el que aparecen los dominios individuales en el dominio compuesto.</span><span class="sxs-lookup"><span data-stu-id="3698e-109">The values must appear in the same order as the single domains appear in the composite domain.</span></span> <span data-ttu-id="3698e-110">El delimitador del origen de datos debe coincidir con el delimitador utilizado para analizar los valores del dominio compuesto.</span><span class="sxs-lookup"><span data-stu-id="3698e-110">The delimiter in the data source must match the delimiter that is used to parse the composite domain values.</span></span> <span data-ttu-id="3698e-111">Para seleccionar el delimitador para el dominio compuesto, así como para establecer otras propiedades, utilice Data Quality Client.</span><span class="sxs-lookup"><span data-stu-id="3698e-111">You select the delimiter for the composite domain, as well as set other properties, in the Data Quality Client.</span></span> <span data-ttu-id="3698e-112">Para más información, consulte [Crear un dominio compuesto](../../../data-quality-services/create-a-composite-domain.md).</span><span class="sxs-lookup"><span data-stu-id="3698e-112">For more information, see [Create a Composite Domain](../../../data-quality-services/create-a-composite-domain.md).</span></span>  
  
### <a name="to-map-multiple-columns-to-a-composite-domain"></a><span data-ttu-id="3698e-113">Para asignar varias columnas a un dominio compuesto</span><span class="sxs-lookup"><span data-stu-id="3698e-113">To map multiple columns to a composite domain</span></span>  
  
1.  <span data-ttu-id="3698e-114">Haga clic con el botón derecho en la transformación Limpieza de DQS y, después, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="3698e-114">Right-click the DQS Cleansing transformation, and then click **Edit**.</span></span>  
  
2.  <span data-ttu-id="3698e-115">En la pestaña **Administrador de conexiones** , asegúrese de que el dominio compuesto aparece en la lista de dominios disponibles.</span><span class="sxs-lookup"><span data-stu-id="3698e-115">On the **Connection Manager** tab, confirm that the composite domain appears in the list of available domains.</span></span>  
  
3.  <span data-ttu-id="3698e-116">En la pestaña **Asignación** , seleccione las columnas en el área **Columnas de entrada disponibles** .</span><span class="sxs-lookup"><span data-stu-id="3698e-116">On the **Mapping** tab, select the columns in the **Available Input Columns** area.</span></span>  
  
4.  <span data-ttu-id="3698e-117">Para cada columna que aparezca en el campo **Columna de entrada** , seleccione un dominio individual en el campo **Dominio** .</span><span class="sxs-lookup"><span data-stu-id="3698e-117">For each column listed in the **Input Column** field, select a single domain in the **Domain** field.</span></span> <span data-ttu-id="3698e-118">Seleccione solo dominios individuales que estén incluidos en el dominio compuesto.</span><span class="sxs-lookup"><span data-stu-id="3698e-118">Select only single domains that are in the composite domain.</span></span>  
  
5.  <span data-ttu-id="3698e-119">Si fuera necesario, modifique los nombres que aparecen en los campos **Alias de origen**, **Alias de salida**y **Alias de estado** .</span><span class="sxs-lookup"><span data-stu-id="3698e-119">As needed, modify the names that appear in the **Source Alias**, **Output Alias**, and **Status Alias** fields.</span></span>  
  
6.  <span data-ttu-id="3698e-120">Si fuera necesario, establezca propiedades en la pestaña **Avanzadas** . Para obtener más información acerca de las propiedades, vea [DQS Cleansing Transformation Editor Dialog Box](../../dqs-cleansing-transformation-editor-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="3698e-120">As needed, set properties on the **Advanced** tab. For more information about the properties, see [DQS Cleansing Transformation Editor Dialog Box](../../dqs-cleansing-transformation-editor-dialog-box.md).</span></span>  
  
### <a name="to-map-a-column-with-delimited-values-to-a-composite-domain"></a><span data-ttu-id="3698e-121">Para asignar una columna con valores delimitados a un dominio compuesto</span><span class="sxs-lookup"><span data-stu-id="3698e-121">To map a column with delimited values to a composite domain</span></span>  
  
1.  <span data-ttu-id="3698e-122">Haga clic con el botón derecho en la transformación Limpieza de DQS y, después, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="3698e-122">Right-click the DQS Cleansing transformation, and then click **Edit**.</span></span>  
  
2.  <span data-ttu-id="3698e-123">En la pestaña **Administrador de conexiones** , asegúrese de que el dominio compuesto aparece en la lista de dominios disponibles.</span><span class="sxs-lookup"><span data-stu-id="3698e-123">On the **Connection Manager** tab, confirm that the composite domain appears in the list of available domains.</span></span>  
  
3.  <span data-ttu-id="3698e-124">En la pestaña **Asignación** , seleccione la columna en el área **Columnas de entrada disponibles** .</span><span class="sxs-lookup"><span data-stu-id="3698e-124">On the **Mapping** tab, select the column in the **Available Input Columns** area.</span></span>  
  
4.  <span data-ttu-id="3698e-125">Para la columna que aparece en el campo **Columna de entrada** , seleccione el dominio compuesto en el campo **Dominio** .</span><span class="sxs-lookup"><span data-stu-id="3698e-125">For the column listed in the **Input Column** field, select the composite domain in the **Domain** field.</span></span>  
  
5.  <span data-ttu-id="3698e-126">Si fuera necesario, modifique los nombres que aparecen en los campos **Alias de origen**, **Alias de salida**y **Alias de estado** .</span><span class="sxs-lookup"><span data-stu-id="3698e-126">As needed, modify the names that appear in the **Source Alias**, **Output Alias**, and **Status Alias** fields.</span></span>  
  
6.  <span data-ttu-id="3698e-127">Si fuera necesario, establezca propiedades en la pestaña **Avanzadas** . Para obtener más información acerca de las propiedades, vea [DQS Cleansing Transformation Editor Dialog Box](../../dqs-cleansing-transformation-editor-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="3698e-127">As needed, set properties on the **Advanced** tab. For more information about the properties, see [DQS Cleansing Transformation Editor Dialog Box](../../dqs-cleansing-transformation-editor-dialog-box.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3698e-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3698e-128">See Also</span></span>  
 [<span data-ttu-id="3698e-129">Transformación Limpieza de DQS</span><span class="sxs-lookup"><span data-stu-id="3698e-129">DQS Cleansing Transformation</span></span>](dqs-cleansing-transformation.md)  
  
  
