---
title: Seleccionar un paquete | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.selectapackage.f1
helpviewer_keywords:
- Select a Package dialog box
ms.assetid: 92b47a2b-21b5-460a-885d-6cc4bb567249
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b35276791b004a011a1c2656057046be05ed6770
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662193"
---
# <a name="select-a-package"></a><span data-ttu-id="43199-102">Seleccionar un paquete</span><span class="sxs-lookup"><span data-stu-id="43199-102">Select a Package</span></span>
  <span data-ttu-id="43199-103">Utilice el cuadro de diálogo **Seleccionar un paquete** para especificar el paquete desde el que la tarea Cola de mensajes puede recibir mensajes.</span><span class="sxs-lookup"><span data-stu-id="43199-103">Use the **Select a Package** dialog box to specify the package from which the Message Queue task can receive messages.</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="43199-104">Opciones estáticas</span><span class="sxs-lookup"><span data-stu-id="43199-104">Static Options</span></span>  
 <span data-ttu-id="43199-105">**Ubicación**</span><span class="sxs-lookup"><span data-stu-id="43199-105">**Location**</span></span>  
 <span data-ttu-id="43199-106">Especifique la ubicación del paquete.</span><span class="sxs-lookup"><span data-stu-id="43199-106">Specify the location of the package.</span></span> <span data-ttu-id="43199-107">Esta propiedad presenta las opciones indicadas en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="43199-107">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="43199-108">Value</span><span class="sxs-lookup"><span data-stu-id="43199-108">Value</span></span>|<span data-ttu-id="43199-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="43199-109">Description</span></span>|  
|-----------|-----------------|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<span data-ttu-id="43199-110">Establezca la ubicación de una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="43199-110">Set the location to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="43199-111">La selección de este valor muestra las opciones dinámicas, **Servidor**, **Utilizar autenticación de Windows**, **Utilizar autenticación de SQL Server**, **Nombre de usuario**y **Contraseña**.</span><span class="sxs-lookup"><span data-stu-id="43199-111">Selecting this value displays the dynamic options, **Server**, **Use Windows Authentication**, **Use SQL Server Authentication**, **User name**, and **Password**.</span></span>|  
|<span data-ttu-id="43199-112">Archivo DTSX</span><span class="sxs-lookup"><span data-stu-id="43199-112">DTSX file</span></span>|<span data-ttu-id="43199-113">Establezca la ubicación de un archivo DTSX.</span><span class="sxs-lookup"><span data-stu-id="43199-113">Set the location to a DTSX file.</span></span> <span data-ttu-id="43199-114">La selección de este valor muestra la opción dinámica **Nombre de archivo**.</span><span class="sxs-lookup"><span data-stu-id="43199-114">Selecting this value displays the dynamic option, **File name**.</span></span>|  
  
## <a name="location-dynamic-options"></a><span data-ttu-id="43199-115">Opciones dinámicas de ubicación</span><span class="sxs-lookup"><span data-stu-id="43199-115">Location Dynamic Options</span></span>  
  
### <a name="location--sql-server"></a><span data-ttu-id="43199-116">Ubicación = SQL Server</span><span class="sxs-lookup"><span data-stu-id="43199-116">Location = SQL Server</span></span>  
 <span data-ttu-id="43199-117">**Nombre del paquete**</span><span class="sxs-lookup"><span data-stu-id="43199-117">**Package name**</span></span>  
 <span data-ttu-id="43199-118">Seleccione un paquete que esté almacenado en el servidor especificado.</span><span class="sxs-lookup"><span data-stu-id="43199-118">Select a package that is stored on the specified server.</span></span>  
  
 <span data-ttu-id="43199-119">**Server**</span><span class="sxs-lookup"><span data-stu-id="43199-119">**Server**</span></span>  
 <span data-ttu-id="43199-120">Proporcione un nombre de servidor o seleccione un servidor de la lista.</span><span class="sxs-lookup"><span data-stu-id="43199-120">Provide a server name or select a server from the list.</span></span>  
  
 <span data-ttu-id="43199-121">**Utilizar autenticación de Windows**</span><span class="sxs-lookup"><span data-stu-id="43199-121">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="43199-122">Haga clic en esta opción para utilizar la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="43199-122">Click to use Windows Authentication.</span></span>  
  
 <span data-ttu-id="43199-123">**Utilizar autenticación de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="43199-123">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="43199-124">Haga clic en esta opción para usar la autenticación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="43199-124">Click to use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="43199-125">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="43199-125">**User name**</span></span>  
 <span data-ttu-id="43199-126">Si está usando la autenticación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , proporcione un nombre de usuario para usarlo cuando inicie sesión en el servidor.</span><span class="sxs-lookup"><span data-stu-id="43199-126">If using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, provide a user name to use when logging on to the server.</span></span>  
  
 <span data-ttu-id="43199-127">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="43199-127">**Password**</span></span>  
 <span data-ttu-id="43199-128">Si está usando la autenticación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , proporcione una contraseña.</span><span class="sxs-lookup"><span data-stu-id="43199-128">If using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, provide a password.</span></span>  
  
### <a name="location--dtsx-file"></a><span data-ttu-id="43199-129">Ubicación = archivo DTSX</span><span class="sxs-lookup"><span data-stu-id="43199-129">Location = DTSX file</span></span>  
 <span data-ttu-id="43199-130">**Nombre de archivo**</span><span class="sxs-lookup"><span data-stu-id="43199-130">**File name**</span></span>  
 <span data-ttu-id="43199-131">Proporcione la ruta de acceso a un paquete, o bien haga clic en el botón Examinar **(…)** y busque el paquete.</span><span class="sxs-lookup"><span data-stu-id="43199-131">Provide the path of a package or click the browse button **(...)** and locate the package.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43199-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="43199-132">See Also</span></span>  
 [<span data-ttu-id="43199-133">Tarea Cola de mensajes</span><span class="sxs-lookup"><span data-stu-id="43199-133">Message Queue Task</span></span>](message-queue-task.md)  
  
  
