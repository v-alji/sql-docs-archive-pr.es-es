---
title: Actualización de datos PowerPivot | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- unattended data refresh [Analysis Services with SharePoint]
- scheduled data refresh [Analysis Services with SharePoint]
- data refresh [Analysis Services with SharePoint]
ms.assetid: ac8358a3-ee71-44c7-8ee6-ac7afe3ebaa4
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6f7d5ed5c2f8882cbc0c47a1c711748d26e0193c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673324"
---
# <a name="powerpivot-data-refresh"></a><span data-ttu-id="22b01-102">Actualización de datos PowerPivot</span><span class="sxs-lookup"><span data-stu-id="22b01-102">PowerPivot Data Refresh</span></span>
  <span data-ttu-id="22b01-103">Después de crear un libro que contiene datos PowerPivot, puede que desee actualizar los datos volviendo a ejecutar una consulta o comando periódicamente para conseguir información actualizada de los orígenes que se usaron originalmente para crear el libro.</span><span class="sxs-lookup"><span data-stu-id="22b01-103">After you create a workbook that contains PowerPivot data, you might want to periodically refresh the data by rerunning a query or command to get updated information from the sources you used originally to create the workbook.</span></span> <span data-ttu-id="22b01-104">Este proceso se denomina `data refresh` y permite actualizar datos a petición en [!INCLUDE[ssGeminiClient](../../includes/ssgeminiclient-md.md)] o como una operación programada que se ejecuta como un proceso de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] en un servidor de aplicaciones de una granja de servidores de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="22b01-104">This process is called `data refresh`, and you can refresh data on demand in [!INCLUDE[ssGeminiClient](../../includes/ssgeminiclient-md.md)], or as a scheduled operation that runs as an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] process on an application server in a SharePoint farm.</span></span> <span data-ttu-id="22b01-105">Para más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="22b01-105">For more information, see:</span></span>  
  
-   [<span data-ttu-id="22b01-106">Actualización de datos PowerPivot con SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="22b01-106">PowerPivot Data Refresh with SharePoint 2010</span></span>](../powerpivot-data-refresh-with-sharepoint-2010.md)  
  
-   [<span data-ttu-id="22b01-107">Configurar la cuenta de actualización de datos desatendida de PowerPivot &#40;PowerPivot para SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="22b01-107">Configure the PowerPivot Unattended Data Refresh Account &#40;PowerPivot for SharePoint&#41;</span></span>](../configure-unattended-data-refresh-account-powerpivot-sharepoint.md)  
  
-   [<span data-ttu-id="22b01-108">Configurar credenciales almacenadas para la actualización de datos PowerPivot &#40;PowerPivot para SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="22b01-108">Configure Stored Credentials for PowerPivot Data Refresh &#40;PowerPivot for SharePoint&#41;</span></span>](../configure-stored-credentials-data-refresh-powerpivot-sharepoint.md)  
  
-   [<span data-ttu-id="22b01-109">Programar una actualización de datos &#40;PowerPivot para SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="22b01-109">Schedule a Data Refresh &#40;PowerPivot for SharePoint&#41;</span></span>](../schedule-a-data-refresh-powerpivot-for-sharepoint.md)  
  
-   [<span data-ttu-id="22b01-110">Ver el historial de actualización de datos &#40;PowerPivot para SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="22b01-110">View Data Refresh History &#40;PowerPivot for SharePoint&#41;</span></span>](view-data-refresh-history-power-pivot-for-sharepoint.md)  
  
> [!NOTE]
>  [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="22b01-111">y SharePoint Server 2013 Excel Services usan una arquitectura diferente para la actualización de datos de modelos de datos de PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="22b01-111">and SharePoint Server 2013 Excel Services use a different architecture for data refresh of PowerPivot data models.</span></span> <span data-ttu-id="22b01-112">La arquitectura admitida de SharePoint 2013 emplea Excel Services como componente principal para cargar modelos de datos de PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="22b01-112">The SharePoint 2013 supported architecture utilizes Excel Services as the primary component to load PowerPivot data models.</span></span> <span data-ttu-id="22b01-113">La arquitectura usada anteriormente para la actualización de datos se basaba en un servidor que ejecutaba el Servicio de sistema de PowerPivot y [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] en modo de SharePoint para cargar los modelos de datos.</span><span class="sxs-lookup"><span data-stu-id="22b01-113">The previous data refresh architecture used relied on a server running PowerPivot System Service and [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] in SharePoint mode to load data models.</span></span> <span data-ttu-id="22b01-114">Para obtener más información, vea lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="22b01-114">For more information, see the following:</span></span>  
> 
>  -   [<span data-ttu-id="22b01-115">Actualización de datos PowerPivot con SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="22b01-115">PowerPivot Data Refresh with SharePoint 2013</span></span>](power-pivot-data-refresh-with-sharepoint-2013.md)  
> -   [<span data-ttu-id="22b01-116">Actualizar libros y actualización de datos programada &#40;SharePoint 2013&#41;</span><span class="sxs-lookup"><span data-stu-id="22b01-116">Upgrade Workbooks and Scheduled Data Refresh &#40;SharePoint 2013&#41;</span></span>](../instances/install-windows/upgrade-workbooks-and-scheduled-data-refresh-sharepoint-2013.md)  
  
  
