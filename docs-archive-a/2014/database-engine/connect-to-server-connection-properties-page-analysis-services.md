---
title: Conectar al servidor (página Propiedades de conexión de Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.connecttoas.connectionproperties.f1
ms.assetid: 26cf53e3-3bcb-4697-8a88-53e93bc68b56
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 04706671ea8b0a50f2bf72cd7b73db88dce34d89
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743627"
---
# <a name="connect-to-server-connection-properties-page-analysis-services"></a><span data-ttu-id="64ece-102">Conectar al servidor (página Propiedades de conexión de Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="64ece-102">Connect to Server (Connection Properties Page) Analysis Services</span></span>
  <span data-ttu-id="64ece-103">Use esta pestaña para ver o especificar opciones al conectarse a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] [!INCLUDE[ssAS](../includes/ssas-md.md)] **servidores registrados**o registrarlos en ellos.</span><span class="sxs-lookup"><span data-stu-id="64ece-103">Use this tab to view or specify options when connecting to [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] or registering [!INCLUDE[ssAS](../includes/ssas-md.md)] in **Registered Servers**.</span></span> <span data-ttu-id="64ece-104">**Conectar** y **Opciones** solo aparecen en este cuadro de diálogo al conectar.</span><span class="sxs-lookup"><span data-stu-id="64ece-104">**Connect** and **Options** only appear in this dialog box when connecting.</span></span> <span data-ttu-id="64ece-105">**Probar** y **Guardar** solo aparecen en este cuadro de diálogo al registrar [!INCLUDE[ssAS](../includes/ssas-md.md)].</span><span class="sxs-lookup"><span data-stu-id="64ece-105">**Test** and **Save** only appear in this dialog box when registering [!INCLUDE[ssAS](../includes/ssas-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="64ece-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="64ece-106">Options</span></span>  
 <span data-ttu-id="64ece-107">**Conexión a la base de datos**</span><span class="sxs-lookup"><span data-stu-id="64ece-107">**Connect to database**</span></span>  
 <span data-ttu-id="64ece-108">Seleccione en la lista una base de datos a la que conectarse.</span><span class="sxs-lookup"><span data-stu-id="64ece-108">Select a database to connect to from the list.</span></span> <span data-ttu-id="64ece-109">Si selecciona **\<default>** , se conectará a la base de datos predeterminada del servidor.</span><span class="sxs-lookup"><span data-stu-id="64ece-109">If you select **\<default>**, you will be connected to the default database for the server.</span></span> <span data-ttu-id="64ece-110">Si selecciona **\<Browse server>** , puede examinar el servidor de la base de datos a la que le gustaría conectarse.</span><span class="sxs-lookup"><span data-stu-id="64ece-110">If you select **\<Browse server>**, you can browse the server for the database you would like to connect to.</span></span>  
  
 <span data-ttu-id="64ece-111">**Tiempo de espera de conexión**</span><span class="sxs-lookup"><span data-stu-id="64ece-111">**Connection timeout**</span></span>  
 <span data-ttu-id="64ece-112">Escriba el número de segundos que se debe esperar para que se establezca una conexión antes de que se agote el tiempo de espera. El valor predeterminado es 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="64ece-112">Enter the number of seconds to wait for a connection to be established before timing out. The default value is 15 seconds.</span></span>  
  
 <span data-ttu-id="64ece-113">**Tiempo de espera de ejecución**</span><span class="sxs-lookup"><span data-stu-id="64ece-113">**Execution timeout**</span></span>  
 <span data-ttu-id="64ece-114">Escriba el intervalo de tiempo (en segundos) que hay que esperar antes de que finalice la ejecución de una tarea en el servidor.</span><span class="sxs-lookup"><span data-stu-id="64ece-114">Enter the amount of time in seconds to wait before execution of a task is completed on the server.</span></span> <span data-ttu-id="64ece-115">El valor predeterminado es de cero segundos, que indica que no hay tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="64ece-115">The default value is zero seconds, which indicates there is no time-out.</span></span>  
  
 <span data-ttu-id="64ece-116">**Cifrar conexión**</span><span class="sxs-lookup"><span data-stu-id="64ece-116">**Encrypt connection**</span></span>  
 <span data-ttu-id="64ece-117">Fuerza el cifrado de la conexión.</span><span class="sxs-lookup"><span data-stu-id="64ece-117">Forces encryption of the connection.</span></span>  
  
 <span data-ttu-id="64ece-118">**Restablecer todo**</span><span class="sxs-lookup"><span data-stu-id="64ece-118">**Reset All**</span></span>  
 <span data-ttu-id="64ece-119">Reemplaza todos los valores de las propiedades de conexión especificadas manualmente por los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="64ece-119">Replace all manually entered connection property values with the default values.</span></span>  
  
 <span data-ttu-id="64ece-120">**Conexión**</span><span class="sxs-lookup"><span data-stu-id="64ece-120">**Connect**</span></span>  
 <span data-ttu-id="64ece-121">Intenta establecer una conexión utilizando los valores de la lista.</span><span class="sxs-lookup"><span data-stu-id="64ece-121">Attempt a connection using the listed values.</span></span>  
  
 <span data-ttu-id="64ece-122">**Opciones**</span><span class="sxs-lookup"><span data-stu-id="64ece-122">**Options**</span></span>  
 <span data-ttu-id="64ece-123">Haga clic aquí para modificar el cuadro de diálogo y ocultar las opciones adicionales de conexión al servidor, como recordar la contraseña.</span><span class="sxs-lookup"><span data-stu-id="64ece-123">Click to change the dialog and hide the additional server connection options, such as remembering the password.</span></span>  
  
 <span data-ttu-id="64ece-124">**Test**</span><span class="sxs-lookup"><span data-stu-id="64ece-124">**Test**</span></span>  
 <span data-ttu-id="64ece-125">Al registrar [!INCLUDE[ssAS](../includes/ssas-md.md)] en **Servidores registrados**, haga clic para probar la conexión.</span><span class="sxs-lookup"><span data-stu-id="64ece-125">When registering [!INCLUDE[ssAS](../includes/ssas-md.md)] in **Registered Servers**, click to test the connection.</span></span>  
  
 <span data-ttu-id="64ece-126">**Guardar**</span><span class="sxs-lookup"><span data-stu-id="64ece-126">**Save**</span></span>  
 <span data-ttu-id="64ece-127">Guarda la configuración en **Servidores registrados**.</span><span class="sxs-lookup"><span data-stu-id="64ece-127">Saves the settings in **Registered Servers**.</span></span>  
  
  
