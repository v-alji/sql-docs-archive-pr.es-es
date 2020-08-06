---
title: Conector de Microsoft 1,1 para SAP BW | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5281f080-53d5-4679-aa26-f4cd4ac7a2df
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ec5cfe83b201976be0512c54b77bc79f8aa824b3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748177"
---
# <a name="microsoft-connector-11-for-sap-bw"></a><span data-ttu-id="24778-102">Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="24778-102">Microsoft Connector 1.1 for SAP BW</span></span>
  <span data-ttu-id="24778-103">[!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW consta de un conjunto de tres componentes que le permiten tanto extraer datos de un sistema SAP NetWeaver BW versión 7 como cargarlos en él.</span><span class="sxs-lookup"><span data-stu-id="24778-103">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW consists of a set of three components that let you extract data from, or load data into, an SAP Netweaver BW version 7 system.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="24778-104">La documentación de Microsoft Connector 1.1 for SAP BW da por supuesto que se está familiarizado con el entorno SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="24778-104">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="24778-105">Para obtener más información acerca de SAP Netweaver BW, o sobre cómo configurar los objetos y los procesos de SAP Netweaver BW, vea la documentación de SAP.</span><span class="sxs-lookup"><span data-stu-id="24778-105">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="24778-106">La extracción de datos de SAP Netweaver BW requiere una licencia SAP adicional.</span><span class="sxs-lookup"><span data-stu-id="24778-106">Extracting data from SAP Netweaver BW requires additional SAP licensing.</span></span> <span data-ttu-id="24778-107">Póngase en contacto con SAP para comprobar estos requisitos.</span><span class="sxs-lookup"><span data-stu-id="24778-107">Check with SAP to verify these requirements.</span></span>  
  
## <a name="components"></a><span data-ttu-id="24778-108">Componentes</span><span class="sxs-lookup"><span data-stu-id="24778-108">Components</span></span>  
 <span data-ttu-id="24778-109">[!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW tiene los componentes siguientes:</span><span class="sxs-lookup"><span data-stu-id="24778-109">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW has the following components:</span></span>  
  
-   <span data-ttu-id="24778-110">**Origen de SAP BW**: el origen de SAP BW es un componente de origen de flujo de datos que le permite extraer datos de un sistema SAP Netweaver BW versión 7.</span><span class="sxs-lookup"><span data-stu-id="24778-110">**SAP BW Source**-The SAP BW source is a data flow source component that lets you extract data from an SAP Netweaver BW version 7 system.</span></span>  
  
-   <span data-ttu-id="24778-111">**Destino de SAP BW**: el SAP BW destino es un componente de destino de flujo de datos que le permite cargar datos en un sistema SAP Netweaver BW versión 7.</span><span class="sxs-lookup"><span data-stu-id="24778-111">**SAP BW Destination**-The SAP BW destination is a data flow destination component that lets you load data into an SAP Netweaver BW version 7 system.</span></span>  
  
-   <span data-ttu-id="24778-112">**Administrador de conexiones de SAP BW**: el administrador de conexiones de SAP BW conecta un origen de SAP BW o un destino de SAP BW a un sistema SAP Netweaver BW versión 7.</span><span class="sxs-lookup"><span data-stu-id="24778-112">**SAP BW Connection Manager**-The SAP BW connection manager connects either an SAP BW source or SAP BW destination to an SAP Netweaver BW version 7 system.</span></span>  
  
 <span data-ttu-id="24778-113">Para obtener instrucciones sobre cómo configurar y utilizar el administrador de conexiones, el origen y el destino de SAP BW, vea las notas del producto, [Usar SQL Server Integration Services con SAP BI 7.0](https://go.microsoft.com/fwlink/?LinkId=301897).</span><span class="sxs-lookup"><span data-stu-id="24778-113">For a walkthrough that demonstrates how to configure and use the SAP BW connection manager, source, and destination, see the white paper, [Using SQL Server Integration Services with SAP BI 7.0](https://go.microsoft.com/fwlink/?LinkId=301897).</span></span> <span data-ttu-id="24778-114">Estas notas del producto también muestran cómo configurar los objetos necesarios en SAP BW.</span><span class="sxs-lookup"><span data-stu-id="24778-114">This white paper also shows how to configure the required objects in SAP BW.</span></span>  
  
## <a name="documentation"></a><span data-ttu-id="24778-115">Documentación</span><span class="sxs-lookup"><span data-stu-id="24778-115">Documentation</span></span>  
 <span data-ttu-id="24778-116">Este archivo de Ayuda de [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW contiene los temas y las secciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="24778-116">This Help file for the [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW contains the following topics and sections:</span></span>  
  
 [<span data-ttu-id="24778-117">Instalar Microsoft Connector for 1.1 SAP BW</span><span class="sxs-lookup"><span data-stu-id="24778-117">Installing the Microsoft Connector for 1.1 SAP BW</span></span>](installing-the-microsoft-connector-for-sap-bw.md)  
 <span data-ttu-id="24778-118">Describe los requisitos de instalación para [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span><span class="sxs-lookup"><span data-stu-id="24778-118">Describes the installation requirements for the [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span></span>  
  
 [<span data-ttu-id="24778-119">Componentes de Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="24778-119">Microsoft Connector 1.1 for SAP BW Components</span></span>](microsoft-connector-for-sap-bw-components.md)  
 <span data-ttu-id="24778-120">Describe cada uno de los componentes de [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span><span class="sxs-lookup"><span data-stu-id="24778-120">Describes each component of the [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span></span>  
  
 [<span data-ttu-id="24778-121">Ayuda F1 de Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="24778-121">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](microsoft-connector-for-sap-bw-f1-help.md)  
 <span data-ttu-id="24778-122">Describe la interfaz de usuario de cada componente de [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span><span class="sxs-lookup"><span data-stu-id="24778-122">Describes the user interface of each component of the [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span></span>  
  
  
