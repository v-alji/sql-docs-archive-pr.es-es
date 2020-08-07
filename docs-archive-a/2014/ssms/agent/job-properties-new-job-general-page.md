---
title: Propiedades del trabajo y nuevo trabajo (página general) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.job.general.f1
ms.assetid: b6832840-1c18-4db8-94fc-080db880ae9f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7a5d2ab84ed211a03a3c217bd5f4cd54453a4dc5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745623"
---
# <a name="job-properties-and-new-job-general-page"></a><span data-ttu-id="4d28a-102">Propiedades del trabajo y Nuevo trabajo (página General)</span><span class="sxs-lookup"><span data-stu-id="4d28a-102">Job Properties and New Job (General Page)</span></span>
  <span data-ttu-id="4d28a-103">Utilice esta página para ver y modificar las propiedades generales de un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] trabajo del agente.</span><span class="sxs-lookup"><span data-stu-id="4d28a-103">Use this page to view and modify the general properties of a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job.</span></span>  
  
## <a name="options"></a><span data-ttu-id="4d28a-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="4d28a-104">Options</span></span>  
 <span data-ttu-id="4d28a-105">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="4d28a-105">**Name**</span></span>  
 <span data-ttu-id="4d28a-106">Cambie el nombre del trabajo.</span><span class="sxs-lookup"><span data-stu-id="4d28a-106">Change the name of the job.</span></span>  
  
 <span data-ttu-id="4d28a-107">**Propietario**</span><span class="sxs-lookup"><span data-stu-id="4d28a-107">**Owner**</span></span>  
 <span data-ttu-id="4d28a-108">Seleccione el propietario del trabajo.</span><span class="sxs-lookup"><span data-stu-id="4d28a-108">Select the owner for the job.</span></span>  
  
 <span data-ttu-id="4d28a-109">**Categoría**</span><span class="sxs-lookup"><span data-stu-id="4d28a-109">**Category**</span></span>  
 <span data-ttu-id="4d28a-110">Seleccione la categoría del trabajo.</span><span class="sxs-lookup"><span data-stu-id="4d28a-110">Select the job category for the job.</span></span>  
  
 <span data-ttu-id="4d28a-111">**...**</span><span class="sxs-lookup"><span data-stu-id="4d28a-111">**...**</span></span>  
 <span data-ttu-id="4d28a-112">Muestra los trabajos de la categoría seleccionada.</span><span class="sxs-lookup"><span data-stu-id="4d28a-112">View the jobs in the selected category.</span></span>  
  
 <span data-ttu-id="4d28a-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="4d28a-113">**Description**</span></span>  
 <span data-ttu-id="4d28a-114">Cambie la descripción del trabajo.</span><span class="sxs-lookup"><span data-stu-id="4d28a-114">Change the description of the job.</span></span>  
  
 <span data-ttu-id="4d28a-115">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="4d28a-115">**Enabled**</span></span>  
 <span data-ttu-id="4d28a-116">Habilita el trabajo.</span><span class="sxs-lookup"><span data-stu-id="4d28a-116">Enable the job.</span></span> <span data-ttu-id="4d28a-117">Si el trabajo no está habilitado, no se ejecuta como respuesta a una programación o una alerta; sin embargo, puede iniciarlo con el procedimiento almacenado **sp_start_job** .</span><span class="sxs-lookup"><span data-stu-id="4d28a-117">When the job is not enabled, the job does not run in response to a schedule or an alert, although you can still start the job using the **sp_start_job** stored procedure.</span></span>  
  
 <span data-ttu-id="4d28a-118">**Origen**</span><span class="sxs-lookup"><span data-stu-id="4d28a-118">**Source**</span></span>  
 <span data-ttu-id="4d28a-119">Muestra el servidor maestro del trabajo.</span><span class="sxs-lookup"><span data-stu-id="4d28a-119">Displays the master server for the job.</span></span> <span data-ttu-id="4d28a-120">Solo está disponible en la página **Job PropertiesGeneral** .</span><span class="sxs-lookup"><span data-stu-id="4d28a-120">Only available on the **Job PropertiesGeneral** page.</span></span>  
  
 <span data-ttu-id="4d28a-121">**Creado**</span><span class="sxs-lookup"><span data-stu-id="4d28a-121">**Created**</span></span>  
 <span data-ttu-id="4d28a-122">Muestra la fecha y la hora de creación del trabajo.</span><span class="sxs-lookup"><span data-stu-id="4d28a-122">Displays the date and time that the job was created.</span></span> <span data-ttu-id="4d28a-123">Solo está disponible en la página **Job PropertiesGeneral** .</span><span class="sxs-lookup"><span data-stu-id="4d28a-123">Only available on the **Job PropertiesGeneral** page.</span></span>  
  
 <span data-ttu-id="4d28a-124">**Modificado por última vez**</span><span class="sxs-lookup"><span data-stu-id="4d28a-124">**Last modified**</span></span>  
 <span data-ttu-id="4d28a-125">Muestra la fecha y la hora de la última modificación del trabajo.</span><span class="sxs-lookup"><span data-stu-id="4d28a-125">Displays the date and time that the job was last modified.</span></span> <span data-ttu-id="4d28a-126">Solo está disponible en la página **Job PropertiesGeneral** .</span><span class="sxs-lookup"><span data-stu-id="4d28a-126">Only available on the **Job PropertiesGeneral** page.</span></span>  
  
 <span data-ttu-id="4d28a-127">**Ejecutado por última vez**</span><span class="sxs-lookup"><span data-stu-id="4d28a-127">**Last executed**</span></span>  
 <span data-ttu-id="4d28a-128">Muestra la fecha y la hora del inicio de la última ejecución del trabajo.</span><span class="sxs-lookup"><span data-stu-id="4d28a-128">Displays the date and time that the job last started running.</span></span> <span data-ttu-id="4d28a-129">Solo está disponible en la página **Job PropertiesGeneral** .</span><span class="sxs-lookup"><span data-stu-id="4d28a-129">Only available on the **Job PropertiesGeneral** page.</span></span>  
  
 <span data-ttu-id="4d28a-130">**Ver el historial de trabajos**</span><span class="sxs-lookup"><span data-stu-id="4d28a-130">**View Job History**</span></span>  
 <span data-ttu-id="4d28a-131">Muestra el historial de trabajos.</span><span class="sxs-lookup"><span data-stu-id="4d28a-131">View the job history for the job.</span></span> <span data-ttu-id="4d28a-132">Solo está disponible en la página **Job PropertiesGeneral** .</span><span class="sxs-lookup"><span data-stu-id="4d28a-132">Only available on the **Job PropertiesGeneral** page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d28a-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4d28a-133">See Also</span></span>  
 <span data-ttu-id="4d28a-134">[Implementar trabajos](implement-jobs.md) </span><span class="sxs-lookup"><span data-stu-id="4d28a-134">[Implement Jobs](implement-jobs.md) </span></span>  
 [<span data-ttu-id="4d28a-135">Categorías de trabajos: Administrar categorías de trabajos</span><span class="sxs-lookup"><span data-stu-id="4d28a-135">Job Categories: Manage Job Categories</span></span>](job-categories-manage-job-categories.md)  
  
  
