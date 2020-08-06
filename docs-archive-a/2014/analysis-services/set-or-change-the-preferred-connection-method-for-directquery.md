---
title: Establecer o cambiar el método de conexión preferido para DirectQuery | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: f10d5678-d678-4251-8cce-4e30cfe15751
author: minewiskan
ms.author: owend
ms.openlocfilehash: 239c80ace0daa3498c8dafd8fea358ce540931d3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748298"
---
# <a name="set-or-change-the-preferred-connection-method-for-directquery"></a><span data-ttu-id="04c9a-102">Establecer o cambiar el método de conexión preferido para DirectQuery</span><span class="sxs-lookup"><span data-stu-id="04c9a-102">Set or Change the Preferred Connection Method for DirectQuery</span></span>
  <span data-ttu-id="04c9a-103">Al crear un modelo para utilizarlo en el modo DirectQuery, primero debe configurar el entorno de diseño para que admita el uso de DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="04c9a-103">When you create a model for use in DirectQuery mode, you must first configure the design environment to support use of DirectQuery.</span></span> <span data-ttu-id="04c9a-104">Para ello, vea [Habilitar el modo de diseño de DirectQuery &#40;&#41;tabular de SSAS ](tabular-models/enable-directquery-mode-in-ssdt.md).</span><span class="sxs-lookup"><span data-stu-id="04c9a-104">To do this, see [Enable DirectQuery Design Mode &#40;SSAS Tabular&#41;](tabular-models/enable-directquery-mode-in-ssdt.md).</span></span>  
  
 <span data-ttu-id="04c9a-105">Cuando esté en disposición de implementar el modelo, deberá establecer ciertas propiedades adicionales para permitir el acceso de los usuarios al modelo mediante uno de los modos DirectQuery:</span><span class="sxs-lookup"><span data-stu-id="04c9a-105">When you are ready to deploy the model, you must set some additional properties to enable users to access your model using one of the DirectQuery modes:</span></span>  
  
-   <span data-ttu-id="04c9a-106">Debe indicar si las consultas realizadas en el modelo deben utilizar los datos en caché o el origen de datos relacional.</span><span class="sxs-lookup"><span data-stu-id="04c9a-106">You must indicate whether queries against the model should use cached data or the relational data source.</span></span> <span data-ttu-id="04c9a-107">Puede utilizar un modo híbrido o Solo DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="04c9a-107">You can use a hybrid mode or DirectQuery only.</span></span>  
  
-   <span data-ttu-id="04c9a-108">Si utiliza particiones, debe indicar qué partición desea usar como el origen de datos DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="04c9a-108">If you are using partitions, you must indicate which partition to use as the DirectQuery data source.</span></span>  
  
-   <span data-ttu-id="04c9a-109">Debe establecer las opciones de suplantación para los usuarios que van a tener acceso al origen de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="04c9a-109">You must set impersonation options for users who will be accessing the SQL Server data source.</span></span>  
  
 <span data-ttu-id="04c9a-110">En este procedimiento se describe cómo establecer el método de conexión preferido para un modelo DirectQuery en el diseñador.</span><span class="sxs-lookup"><span data-stu-id="04c9a-110">This procedure describes how to set the preferred connection method for a DirectQuery model in the designer.</span></span> <span data-ttu-id="04c9a-111">También se describe cómo cambiar esta propiedad en [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] una vez implementado el modelo.</span><span class="sxs-lookup"><span data-stu-id="04c9a-111">It also describes how you can change this property in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] after the model has been deployed.</span></span>  
  
### <a name="to-set-the-preferred-connection-method-for-a-directquery-model"></a><span data-ttu-id="04c9a-112">Para establecer el método de conexión preferido para un modelo DirectQuery</span><span class="sxs-lookup"><span data-stu-id="04c9a-112">To set the preferred connection method for a DirectQuery model</span></span>  
  
1.  <span data-ttu-id="04c9a-113">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra el archivo de solución para el modelo DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="04c9a-113">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the solution file for the DirectQuery model.</span></span>  
  
2.  <span data-ttu-id="04c9a-114">En el menú **Proyecto** de Visual Studio, seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="04c9a-114">In Visual Studio, from the **Project** menu, select **Properties**.</span></span>  
  
3.  <span data-ttu-id="04c9a-115">En el panel **Propiedades** , cambie la propiedad **DirectQueryMode**a uno de los valores que admita el uso de DirectQuery:</span><span class="sxs-lookup"><span data-stu-id="04c9a-115">In the **Properties** pane, change the property, **DirectQueryMode**, to one of the values that support DirectQuery usage:</span></span>  
  
    -   <span data-ttu-id="04c9a-116">**InMemory con DirectQuery**: si utiliza esta opción, el modelo se implementará, pero deberá procesar la memoria caché para poder ejecutar consultas en él.</span><span class="sxs-lookup"><span data-stu-id="04c9a-116">**InMemory with DirectQuery**: If you use this option, the model is deployed but you must process the cache before you can run queries against the model.</span></span>  
  
    -   <span data-ttu-id="04c9a-117">**DirectQuery con InMemory**: si utiliza esta opción, la caché estará disponible para los clientes si ya se ha procesado.</span><span class="sxs-lookup"><span data-stu-id="04c9a-117">**DirectQuery with InMemory**: If you use this option, the cache will be available for use by clients if it has already been processed.</span></span> <span data-ttu-id="04c9a-118">Si implementa el modelo con esta configuración y no procesa la caché, algunos clientes obtendrán un error al intentar conectarse con el modelo.</span><span class="sxs-lookup"><span data-stu-id="04c9a-118">If you deploy the model with this setting and do not process the cache, some clients must get an error on trying to connect to the model.</span></span>  
  
    -   <span data-ttu-id="04c9a-119">**Solo DirectQuery**: si utiliza esta opción, los metadatos se implementarán pero el modelo no contendrá ningún dato.</span><span class="sxs-lookup"><span data-stu-id="04c9a-119">**DirectQuery only**: If you use this option, the metadata is deployed but the model has no data in it.</span></span> <span data-ttu-id="04c9a-120">Los clientes que intenten conectarse mediante el modo en memoria obtendrán un error que indicará que el modelo no existe o que no se ha procesado.</span><span class="sxs-lookup"><span data-stu-id="04c9a-120">Clients that attempt to connect using In-Memory mode will get an error, indicating that the model does not exist or has not been processed.</span></span>  
  
4.  <span data-ttu-id="04c9a-121">Si hay errores, abra la **Lista de errores** en Visual Studio y solucione los problemas que impiden que el modelo se implemente en el modo DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="04c9a-121">If there are errors, in Visual Studio, open the **Error List** and resolve any problems that would prevent the model from being deployed in DirectQuery mode.</span></span>  
  
### <a name="to-verify-or-change-the-preferred-connection-method-for-a-directquery-model"></a><span data-ttu-id="04c9a-122">Para comprobar o cambiar el método de conexión preferido para un modelo DirectQuery</span><span class="sxs-lookup"><span data-stu-id="04c9a-122">To verify or change the preferred connection method for a DirectQuery model</span></span>  
  
1.  <span data-ttu-id="04c9a-123">En [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], conéctese con la instancia en la que implementó el modelo DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="04c9a-123">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], connect to the instance where you deployed the DirectQuery model.</span></span>  
  
2.  <span data-ttu-id="04c9a-124">Haga clic con el botón secundario del mouse en la base de datos del modelo y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="04c9a-124">Right-click the model database, and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="04c9a-125">En el panel **Propiedades** , cambie la propiedad **DirectQueryMode**a uno de los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="04c9a-125">In the **Properties** pane, change the property, **DirectQueryMode**, to one of these values:</span></span>  
  
    -   <span data-ttu-id="04c9a-126">**Solo DirectQuery**</span><span class="sxs-lookup"><span data-stu-id="04c9a-126">**DirectQuery Only**</span></span>  
  
    -   <span data-ttu-id="04c9a-127">**InMemory con DirectQuery**</span><span class="sxs-lookup"><span data-stu-id="04c9a-127">**InMemory with DirectQuery**</span></span>  
  
    -   <span data-ttu-id="04c9a-128">**DirectQuery con inmemory**</span><span class="sxs-lookup"><span data-stu-id="04c9a-128">**DirectQuery with InMemory**</span></span>  
  
 <span data-ttu-id="04c9a-129">Observe que estas propiedades son las mismas que las que estableció en el proyecto antes de la implementación en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="04c9a-129">Note that these properties are the same as the properties that you set on the project before deployment in Visual Studio.</span></span> <span data-ttu-id="04c9a-130">Puede cambiar el método de conexión preferido para el modelo DirectQuery en cualquier momento, siempre que haya configurado el modelo para que admita el uso de DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="04c9a-130">You can change the preferred connection mode for DirectQuery mode at any time, provided that you have configured the model to support DirectQuery usage.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04c9a-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="04c9a-131">See Also</span></span>  
 <span data-ttu-id="04c9a-132">[Modo DirectQuery &#40;&#41;tabular de SSAS](tabular-models/directquery-mode-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="04c9a-132">[DirectQuery Mode &#40;SSAS Tabular&#41;](tabular-models/directquery-mode-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="04c9a-133">Habilitar el modo de diseño DirectQuery &#40;SSAS tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="04c9a-133">Enable DirectQuery Design Mode &#40;SSAS Tabular&#41;</span></span>](tabular-models/enable-directquery-mode-in-ssdt.md)  
  
  
