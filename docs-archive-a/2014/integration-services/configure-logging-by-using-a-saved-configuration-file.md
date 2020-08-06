---
title: Configurar el registro mediante un archivo de configuración guardado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- containers [Integration Services], logs
- logs [Integration Services], containers
ms.assetid: e5fdbbcb-94ca-4912-aa7c-0d89cebbd308
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8eb517462d9e932906f739678fbd46c1004fb84d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674268"
---
# <a name="configure-logging-by-using-a-saved-configuration-file"></a><span data-ttu-id="730f1-102">Configurar el registro utilizando un archivo de configuración guardado</span><span class="sxs-lookup"><span data-stu-id="730f1-102">Configure Logging by Using a Saved Configuration File</span></span>
  <span data-ttu-id="730f1-103">Este procedimiento describe cómo configurar el registro para los contenedores nuevos de un paquete, cargando un archivo de configuración de registro previamente guardado.</span><span class="sxs-lookup"><span data-stu-id="730f1-103">This procedure describes how to configure logging for new containers in a package by loading a previously saved logging configuration file.</span></span>  
  
 <span data-ttu-id="730f1-104">De manera predeterminada, todos los contenedores de un paquete utilizan la misma configuración de registro que el contenedor principal.</span><span class="sxs-lookup"><span data-stu-id="730f1-104">By default, all containers in a package use the same logging configuration as their parent container.</span></span> <span data-ttu-id="730f1-105">Por ejemplo, las tareas de un bucle ForEach utilizan la misma configuración de registro que el bucle ForEach.</span><span class="sxs-lookup"><span data-stu-id="730f1-105">For example, the tasks in a Foreach Loop use the same logging configuration as the Foreach Loop.</span></span>  
  
### <a name="to-configure-logging-for-a-container"></a><span data-ttu-id="730f1-106">Para configurar el registro para un contenedor</span><span class="sxs-lookup"><span data-stu-id="730f1-106">To configure logging for a container</span></span>  
  
1.  <span data-ttu-id="730f1-107">En [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contiene el paquete que desea.</span><span class="sxs-lookup"><span data-stu-id="730f1-107">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="730f1-108">En el menú **SSIS** , haga clic en **Registro**.</span><span class="sxs-lookup"><span data-stu-id="730f1-108">On the **SSIS** menu, click **Logging**.</span></span>  
  
3.  <span data-ttu-id="730f1-109">Expanda la vista de árbol del paquete y seleccione el contenedor que desee configurar.</span><span class="sxs-lookup"><span data-stu-id="730f1-109">Expand the package tree view and select the container to configure.</span></span>  
  
4.  <span data-ttu-id="730f1-110">En la pestaña **Proveedores y registros** , seleccione los registros que desee utilizar para el contenedor.</span><span class="sxs-lookup"><span data-stu-id="730f1-110">On the **Providers and Logs** tab, select the logs to use for the container.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="730f1-111">Solo puede crear registros en el nivel de paquete.</span><span class="sxs-lookup"><span data-stu-id="730f1-111">You can create logs only at the package level.</span></span> <span data-ttu-id="730f1-112">Para más información, vea [Habilitar el registro de paquetes en SQL Server Data Tools](../../2014/integration-services/enable-package-logging-in-sql-server-data-tools.md).</span><span class="sxs-lookup"><span data-stu-id="730f1-112">For more information, see [Enable Package Logging in SQL Server Data Tools](../../2014/integration-services/enable-package-logging-in-sql-server-data-tools.md).</span></span>  
  
5.  <span data-ttu-id="730f1-113">Haga clic en la pestaña **Detalles** y, a continuación, en **Cargar**.</span><span class="sxs-lookup"><span data-stu-id="730f1-113">Click the **Details** tab and click **Load**.</span></span>  
  
6.  <span data-ttu-id="730f1-114">Localice el archivo de configuración del registro que desee utilizar y haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="730f1-114">Locate the logging configuration file you want to use and click **Open**.</span></span>  
  
7.  <span data-ttu-id="730f1-115">También puede seleccionar una entrada diferente del registro al activar la casilla correspondiente en la columna **Eventos** .</span><span class="sxs-lookup"><span data-stu-id="730f1-115">Optionally, select a different log entry to log by selecting its check box in the **Events** column.</span></span> <span data-ttu-id="730f1-116">Haga clic en **Avanzadas** para seleccionar el tipo de información que se debe registrar para esta entrada.</span><span class="sxs-lookup"><span data-stu-id="730f1-116">Click **Advanced** to select the type of information to log for this entry.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="730f1-117">El nuevo contenedor puede incluir entradas de registro adicionales que no estén disponibles para el contenedor utilizado originalmente para crear la configuración del registro.</span><span class="sxs-lookup"><span data-stu-id="730f1-117">The new container may include additional log entries that are not available for the container originally used to create the logging configuration.</span></span> <span data-ttu-id="730f1-118">Es necesario seleccionar manualmente estas entradas adicionales para que se registren.</span><span class="sxs-lookup"><span data-stu-id="730f1-118">These additional log entries must be selected manually if you want them to be logged.</span></span>  
  
8.  <span data-ttu-id="730f1-119">Para guardar la versión actualizada de la configuración de registro, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="730f1-119">To save the updated version of the logging configuration, click **Save**.</span></span>  
  
9. <span data-ttu-id="730f1-120">Para guardar el paquete actualizado, haga clic en **Guardar los elementos seleccionados**, en el menú **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="730f1-120">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="730f1-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="730f1-121">See Also</span></span>  
 [<span data-ttu-id="730f1-122">Registro de Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="730f1-122">Integration Services &#40;SSIS&#41; Logging</span></span>](performance/integration-services-ssis-logging.md)  
  
  
