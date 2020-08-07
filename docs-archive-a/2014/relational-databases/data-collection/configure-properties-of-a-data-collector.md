---
title: Configuración de las propiedades de un recopilador de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.dc.datacollectionprop.advanced.f1
- sql12.swb.dc.datacollectionprop.general.f1
ms.assetid: cf98f57d-5a6d-4bc3-bf10-783e460fc63d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 05172c2c831ec649269512a625be069cdc67047a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747029"
---
# <a name="configure-properties-of-a-data-collector"></a><span data-ttu-id="f3da0-102">Configurar las propiedades de un recopilador de datos</span><span class="sxs-lookup"><span data-stu-id="f3da0-102">Configure Properties of a Data Collector</span></span>
  <span data-ttu-id="f3da0-103">En este tema se describe cómo puede configurar las propiedades de un recopilador de datos.</span><span class="sxs-lookup"><span data-stu-id="f3da0-103">This topic discusses how you can configure the properties of a data collector.</span></span>  
  
## <a name="data-collection-properties-general-tab"></a><span data-ttu-id="f3da0-104">Propiedades de Recopilación de datos (pestaña General)</span><span class="sxs-lookup"><span data-stu-id="f3da0-104">Data Collection Properties (General Tab)</span></span>  
 <span data-ttu-id="f3da0-105">Utilice esta página para configurar las opciones para el almacén de administración de datos y especificar dónde se deben almacenar los datos recopilados antes de cargarse en el almacenamiento de datos.</span><span class="sxs-lookup"><span data-stu-id="f3da0-105">Use this page to configure settings for the management data warehouse and specify where collected data should be stored before it is uploaded to the data warehouse.</span></span>  
  
 <span data-ttu-id="f3da0-106">**Habilitar recopilación de datos**</span><span class="sxs-lookup"><span data-stu-id="f3da0-106">**Enable Data Collection**</span></span>  
 <span data-ttu-id="f3da0-107">Seleccione esta opción para habilitar la recopilación de datos.</span><span class="sxs-lookup"><span data-stu-id="f3da0-107">Select to enable data collection.</span></span> <span data-ttu-id="f3da0-108">Esto tiene el mismo efecto que ejecutar el procedimiento almacenado sp_syscollector_enable_collector.</span><span class="sxs-lookup"><span data-stu-id="f3da0-108">This has the same effect as running the sp_syscollector_enable_collector stored procedure.</span></span> <span data-ttu-id="f3da0-109">Si se desactiva esta casilla, se deshabilitará la recopilación de datos y tiene el mismo efecto que ejecutar el procedimiento almacenado del sp_syscollector_disable_collector.</span><span class="sxs-lookup"><span data-stu-id="f3da0-109">Clearing this check box disables data collection and has the same effect as running the sp_syscollector_disable_collector stored procedure.</span></span>  
  
 <span data-ttu-id="f3da0-110">**Server**</span><span class="sxs-lookup"><span data-stu-id="f3da0-110">**Server**</span></span>  
 <span data-ttu-id="f3da0-111">Muestra el nombre del servidor que hospedará el almacén de administración de datos.</span><span class="sxs-lookup"><span data-stu-id="f3da0-111">Displays the name of the server that will host the management data warehouse</span></span>  
  
 <span data-ttu-id="f3da0-112">**Nombre de la base de datos**</span><span class="sxs-lookup"><span data-stu-id="f3da0-112">**Database name**</span></span>  
 <span data-ttu-id="f3da0-113">Muestra el nombre de la base de datos relacional que se utiliza para el almacén de administración de datos.</span><span class="sxs-lookup"><span data-stu-id="f3da0-113">Displays the name of the relational database that is used for the management data warehouse.</span></span>  
  
 <span data-ttu-id="f3da0-114">**Probar conexión**</span><span class="sxs-lookup"><span data-stu-id="f3da0-114">**Test Connection**</span></span>  
 <span data-ttu-id="f3da0-115">Pruebe la conexión con el **Servidor** especificado usando la información proporcionada al configurar la recopilación de datos.</span><span class="sxs-lookup"><span data-stu-id="f3da0-115">Test the connection to the specified **Server** using information provided when data collection is configured.</span></span>  
  
 <span data-ttu-id="f3da0-116">**Directorio de caché**</span><span class="sxs-lookup"><span data-stu-id="f3da0-116">**Cache directory**</span></span>  
 <span data-ttu-id="f3da0-117">Especifica el directorio del sistema en el que se almacenan los datos recopilados antes de cargarlos en el almacén de administración de datos.</span><span class="sxs-lookup"><span data-stu-id="f3da0-117">Specifies the directory where collected data is stored on the system collecting the data before it is uploaded to the management data warehouse.</span></span> <span data-ttu-id="f3da0-118">Si no se especifica **Directorio de caché** , el recopilador de datos intenta buscar las variables de entorno %TEMP% y %TMP% y utilizar una de estas ubicaciones como la ubicación predeterminada para el almacenamiento temporal.</span><span class="sxs-lookup"><span data-stu-id="f3da0-118">If **Cache directory** is not specified, the data collector attempts to locate the %TEMP% and %TMP% environment variables and use one these locations as the default location for temporary storage.</span></span> <span data-ttu-id="f3da0-119">Si no se configuran estas variables de entorno, se produce un error y se le pedirá que cree un directorio de caché.</span><span class="sxs-lookup"><span data-stu-id="f3da0-119">If these environment variables are not configured, an error occurs and you are prompted to create a cache directory.</span></span>  
  
## <a name="data-collection-properties-advanced-tab"></a><span data-ttu-id="f3da0-120">Propiedades de Recopilación de datos (pestaña Avanzadas)</span><span class="sxs-lookup"><span data-stu-id="f3da0-120">Data Collection Properties (Advanced Tab)</span></span>  
 <span data-ttu-id="f3da0-121">Utilice esta página para configurar las opciones de reintentos para la conexión con el almacén de administración de datos.</span><span class="sxs-lookup"><span data-stu-id="f3da0-121">Use this page to configure the retry settings for the connection to the management data warehouse.</span></span>  
  
 <span data-ttu-id="f3da0-122">**Número de reintentos si no se puede realizar la carga**</span><span class="sxs-lookup"><span data-stu-id="f3da0-122">**Number of times to retry if upload fails**</span></span>  
 <span data-ttu-id="f3da0-123">Especifica el número de reintentos de carga en el almacén de administración de datos si no se puede realizar una carga.</span><span class="sxs-lookup"><span data-stu-id="f3da0-123">Specifies the number of times to retry an upload to the management data warehouse if an upload fails.</span></span> <span data-ttu-id="f3da0-124">El valor predeterminado es 1.</span><span class="sxs-lookup"><span data-stu-id="f3da0-124">The default is 1.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3da0-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f3da0-125">See Also</span></span>  
 <span data-ttu-id="f3da0-126">[Administrar la recopilación de datos](data-collection.md) </span><span class="sxs-lookup"><span data-stu-id="f3da0-126">[Manage Data Collection](data-collection.md) </span></span>  
 [<span data-ttu-id="f3da0-127">Configurar el almacén de administración de datos &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="f3da0-127">Configure the Management Data Warehouse &#40;SQL Server Management Studio&#41;</span></span>](configure-the-management-data-warehouse-sql-server-management-studio.md)  
  
  
