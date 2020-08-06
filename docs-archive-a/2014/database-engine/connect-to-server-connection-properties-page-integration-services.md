---
title: Conectar al servidor (página Propiedades de conexión) Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.connecttodts.connectionproperties.f1
- sql12.ssiseditserverregistration.connectionproperties.f1
ms.assetid: c2513dab-8415-4e0c-9475-6d4ab97fea7c
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 05f3d370a3f3a299bb90df53538b3fa3e90e28c4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749455"
---
# <a name="connect-to-server-connection-properties-page-integration-services"></a><span data-ttu-id="1891f-102">Conectar al servidor (página Propiedades de conexión de Integration Services)</span><span class="sxs-lookup"><span data-stu-id="1891f-102">Connect to Server (Connection Properties Page) Integration Services</span></span>
  <span data-ttu-id="1891f-103">Use esta pestaña para ver o especificar opciones al conectarse a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] [!INCLUDE[ssIS](../includes/ssis-md.md)] **servidores registrados**o registrarlos en ellos.</span><span class="sxs-lookup"><span data-stu-id="1891f-103">Use this tab to view or specify options when connecting to [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] or registering [!INCLUDE[ssIS](../includes/ssis-md.md)] in **Registered Servers**.</span></span> <span data-ttu-id="1891f-104">**Conectar** y **Opciones** solo aparecen en este cuadro de diálogo al conectar.</span><span class="sxs-lookup"><span data-stu-id="1891f-104">**Connect** and **Options** only appear in this dialog box when connecting.</span></span> <span data-ttu-id="1891f-105">**Probar** y **Guardar** solo aparecen en este cuadro de diálogo al registrar [!INCLUDE[ssIS](../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1891f-105">**Test** and **Save** only appear in this dialog box when registering [!INCLUDE[ssIS](../includes/ssis-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="1891f-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="1891f-106">Options</span></span>  
 <span data-ttu-id="1891f-107">**Número de puerto**</span><span class="sxs-lookup"><span data-stu-id="1891f-107">**Port number**</span></span>  
 <span data-ttu-id="1891f-108">Especifique el número de puerto que utiliza [!INCLUDE[ssIS](../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1891f-108">Enter the port number used by [!INCLUDE[ssIS](../includes/ssis-md.md)].</span></span>  
  
 <span data-ttu-id="1891f-109">**Tiempo de espera de la conexión**</span><span class="sxs-lookup"><span data-stu-id="1891f-109">**Connection time-out**</span></span>  
 <span data-ttu-id="1891f-110">Escriba el número de segundos que se debe esperar para que se establezca una conexión antes de que se agote el tiempo de espera. El valor predeterminado es 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="1891f-110">Enter the number of seconds to wait for a connection to be established before timing out. The default value is 15 seconds.</span></span>  
  
 <span data-ttu-id="1891f-111">**Tiempo de espera de ejecución**</span><span class="sxs-lookup"><span data-stu-id="1891f-111">**Execution time-out**</span></span>  
 <span data-ttu-id="1891f-112">Escriba el intervalo de tiempo (en segundos) que hay que esperar antes de que finalice la ejecución de una tarea en el servidor.</span><span class="sxs-lookup"><span data-stu-id="1891f-112">Enter the amount of time in seconds to wait before execution of a task is completed on the server.</span></span> <span data-ttu-id="1891f-113">El valor predeterminado es de cero segundos, que indica que no hay tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="1891f-113">The default value is zero seconds, which indicates there is no time-out.</span></span>  
  
 <span data-ttu-id="1891f-114">**Restablecer todo**</span><span class="sxs-lookup"><span data-stu-id="1891f-114">**Reset All**</span></span>  
 <span data-ttu-id="1891f-115">Reemplaza todos los valores de las propiedades de conexión especificadas manualmente por los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="1891f-115">Replace all manually entered connection property values with the default values.</span></span>  
  
 <span data-ttu-id="1891f-116">**Conexión**</span><span class="sxs-lookup"><span data-stu-id="1891f-116">**Connect**</span></span>  
 <span data-ttu-id="1891f-117">Intenta establecer una conexión utilizando los valores de la lista.</span><span class="sxs-lookup"><span data-stu-id="1891f-117">Attempt a connection using the listed values.</span></span>  
  
 <span data-ttu-id="1891f-118">**Opciones**</span><span class="sxs-lookup"><span data-stu-id="1891f-118">**Options**</span></span>  
 <span data-ttu-id="1891f-119">Haga clic aquí para modificar el cuadro de diálogo y ocultar las opciones adicionales de conexión al servidor, como recordar la contraseña.</span><span class="sxs-lookup"><span data-stu-id="1891f-119">Click to change the dialog and hide the additional server connection options, such as remembering the password.</span></span>  
  
 <span data-ttu-id="1891f-120">**Test**</span><span class="sxs-lookup"><span data-stu-id="1891f-120">**Test**</span></span>  
 <span data-ttu-id="1891f-121">Al registrar [!INCLUDE[ssIS](../includes/ssis-md.md)] en **Servidores registrados**, haga clic para probar la conexión.</span><span class="sxs-lookup"><span data-stu-id="1891f-121">When registering [!INCLUDE[ssIS](../includes/ssis-md.md)] in **Registered Servers**, click to test the connection.</span></span>  
  
 <span data-ttu-id="1891f-122">**Guardar**</span><span class="sxs-lookup"><span data-stu-id="1891f-122">**Save**</span></span>  
 <span data-ttu-id="1891f-123">Guarda la configuración en **Servidores registrados**.</span><span class="sxs-lookup"><span data-stu-id="1891f-123">Saves the settings in **Registered Servers**.</span></span>  
  
  
