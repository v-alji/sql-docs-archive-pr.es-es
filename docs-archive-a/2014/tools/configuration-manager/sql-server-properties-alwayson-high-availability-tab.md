---
title: Propiedades de SQL Server (pestaña alta disponibilidad de AlwaysOn) | Microsoft Docs
description: Obtenga información acerca de cómo activar o desactivar la característica Grupos de disponibilidad AlwaysOn en SQL Server 2014. Ver los requisitos previos que debe cumplir la instancia de servidor para esta característica.
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: d8630923-a600-4f1c-aca1-027453a3ec82
author: mikeraymsft
ms.author: mikeray
ms.openlocfilehash: 3939b40a334746e9ee96441338e2e50791987103
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747371"
---
# <a name="sql-server-properties-alwayson-high-availability-tab"></a><span data-ttu-id="17727-104">Propiedades de SQL Server (pestaña Alta disponibilidad de AlwaysOn)</span><span class="sxs-lookup"><span data-stu-id="17727-104">SQL Server Properties (AlwaysOn High Availability Tab)</span></span>
  <span data-ttu-id="17727-105">Use la pestaña **Alta disponibilidad de AlwaysOn** del cuadro de diálogo **Propiedades de SQL Server** del Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para habilitar o deshabilitar la característica Grupos de disponibilidad de AlwaysOn de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="17727-105">Use the **AlwaysOn High Availability** tab of the **SQL Server Properties** dialog box in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager to enable or disable the AlwaysOn Availability Groups feature in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="17727-106">La habilitación de los Grupos de disponibilidad de AlwaysOn es un requisito previo para que una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] use los grupos de disponibilidad como solución de alta disponibilidad y recuperación ante desastres.</span><span class="sxs-lookup"><span data-stu-id="17727-106">Enabling AlwaysOn Availability Groups is a prerequisite for an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to use availability groups as a high availability and disaster recovery solution.</span></span>  
  
##  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="17727-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="17727-107">Prerequisites</span></span>  
 <span data-ttu-id="17727-108">Para tener habilitados los Grupos de disponibilidad de AlwaysOn, una instancia del servidor debe cumplir los requisitos previos siguientes.</span><span class="sxs-lookup"><span data-stu-id="17727-108">To be enabled for AlwaysOn Availability Groups, a server instance must meet the following prerequisites:</span></span>  
  
-   <span data-ttu-id="17727-109">La instancia de servidor debe residir en un nodo de clústeres de conmutación por error de Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="17727-109">The server instance must reside on a Windows Server Failover Clustering (WSFC) node.</span></span>  
  
-   <span data-ttu-id="17727-110">Para pertenecer al mismo grupo de disponibilidad, las instancias deben estar en el mismo clúster de WSFC.</span><span class="sxs-lookup"><span data-stu-id="17727-110">To be in the same availability group, instances must be in the same WSFC cluster.</span></span> <span data-ttu-id="17727-111">Un grupo de disponibilidad no puede abarcar varios clústeres de WSFC.</span><span class="sxs-lookup"><span data-stu-id="17727-111">An availability group cannot span WSFC clusters.</span></span>  
  
-   <span data-ttu-id="17727-112">La instancia del servidor debe ejecutar una edición de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que admita [!INCLUDE[ssHADR](../../includes/sshadr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="17727-112">The server instance must be running an edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that supports [!INCLUDE[ssHADR](../../includes/sshadr-md.md)].</span></span>  
  
-   <span data-ttu-id="17727-113">Habilite los Grupos de disponibilidad de AlwaysOn para las distintas instancias del servidor de una en una.</span><span class="sxs-lookup"><span data-stu-id="17727-113">Enable AlwaysOn Availability Groups for only one server instance at a time.</span></span> <span data-ttu-id="17727-114">Después de habilitar los Grupos de disponibilidad de AlwaysOn, espere hasta que se haya reiniciado el servicio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] antes de habilitar la instancia del servidor siguiente.</span><span class="sxs-lookup"><span data-stu-id="17727-114">After enabling AlwaysOn Availability Groups, wait until the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service has restarted before you enable the next server instance.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="17727-115">Para más información sobre las características admitidas y sobre los requisitos previos, restricciones y recomendaciones adicionales para [!INCLUDE[ssHADR](../../includes/sshadr-md.md)], vea los Libros en pantalla de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="17727-115">For information about feature support and for information about additional prerequisites, restrictions, and recommendations for [!INCLUDE[ssHADR](../../includes/sshadr-md.md)], see [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Books Online.</span></span>  
  
## <a name="dialog-options"></a><span data-ttu-id="17727-116">Opciones del cuadro de diálogo</span><span class="sxs-lookup"><span data-stu-id="17727-116">Dialog Options</span></span>  
 <span data-ttu-id="17727-117">**Nombre del clúster de conmutación por error de Windows**</span><span class="sxs-lookup"><span data-stu-id="17727-117">**Windows failover cluster name**</span></span>  
 <span data-ttu-id="17727-118">Muestra el nombre del clúster de WSFC en el que el equipo local es un nodo.</span><span class="sxs-lookup"><span data-stu-id="17727-118">Displays the name of the WSFC cluster in which the local computer is a node.</span></span>  
  
 <span data-ttu-id="17727-119">**Habilitar Grupos de disponibilidad AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="17727-119">**Enable AlwaysOn Availability Groups**</span></span>  
 <span data-ttu-id="17727-120">Use esta casilla para habilitar o deshabilitar los Grupos de disponibilidad de AlwaysOn en esta instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="17727-120">Use this check box to enable or disable AlwaysOn Availability Groups on this instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], as follows:</span></span>  
  
-   <span data-ttu-id="17727-121">Si esta casilla está los vacía, los Grupos de disponibilidad de AlwaysOn estarán deshabilitados.</span><span class="sxs-lookup"><span data-stu-id="17727-121">If this check box is empty, AlwaysOn Availability Groups is currently disabled.</span></span> <span data-ttu-id="17727-122">Para habilitar los Grupos de disponibilidad de AlwaysOn, seleccione esta casilla, haga clic en **Aceptar**y reinicie manualmente el servicio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="17727-122">To enable AlwaysOn Availability Groups, select this check box, click **OK**, and manually restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  
-   <span data-ttu-id="17727-123">Si esta casilla ya está seleccionada, los Grupos de disponibilidad de AlwaysOn ya están habilitados.</span><span class="sxs-lookup"><span data-stu-id="17727-123">If this check box is already selected, AlwaysOn Availability Groups is currently enabled.</span></span> <span data-ttu-id="17727-124">Para deshabilitar los Grupos de disponibilidad de AlwaysOn, desactive la casilla y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="17727-124">To disable AlwaysOn Availability Groups, uncheck the check box and click **OK**.</span></span> <span data-ttu-id="17727-125">Esto hace que se reinicie la instancia del servidor.</span><span class="sxs-lookup"><span data-stu-id="17727-125">This causes the server instance to restart.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="17727-126">Después de deshabilitar los Grupos de disponibilidad de AlwaysOn, debe quitar todas las réplicas disponibilidad locales de la instancia del servidor.</span><span class="sxs-lookup"><span data-stu-id="17727-126">After disabling AlwaysOn Availability Groups, you should remove any local availability replicas from the server instance.</span></span> <span data-ttu-id="17727-127">Si quita la última réplica de un grupo de disponibilidad determinado, también debe quitar el grupo.</span><span class="sxs-lookup"><span data-stu-id="17727-127">If you remove the last replica of a given availability group, you should also remove the group.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="17727-128">Lista de elementos de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="17727-128">UI element list</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="17727-129">Para obtener más información sobre los pasos que se deben seguir después de deshabilitar los Grupos de disponibilidad de AlwaysOn y para obtener información sobre cómo crear y configurar grupos de disponibilidad, vea los Libros en pantalla de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="17727-129">For more information about follow up after you disable AlwaysOn Availability Groups and for information about how to create and configure availability groups, see [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Books Online.</span></span>  
  
  
