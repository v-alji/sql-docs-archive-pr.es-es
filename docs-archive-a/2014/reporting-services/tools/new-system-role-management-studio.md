---
title: Nuevo rol del sistema (Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.newsystemrole.f1
ms.assetid: 7b4a0b98-975b-478a-8359-7db39ccbb347
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a744fc78bdd5ae6ef3a37f96ff5ae8cd10f71a80
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746126"
---
# <a name="new-system-role-management-studio"></a><span data-ttu-id="2fc6e-102">Nuevo rol del sistema (Management Studio)</span><span class="sxs-lookup"><span data-stu-id="2fc6e-102">New System Role (Management Studio)</span></span>
  <span data-ttu-id="2fc6e-103">Utilice esta página para crear una definición de roles de nivel del sistema.</span><span class="sxs-lookup"><span data-stu-id="2fc6e-103">Use this page to create a system-level role definition.</span></span> <span data-ttu-id="2fc6e-104">Una definición de roles del sistema especifica un conjunto de tareas de nivel de sistema que se aplican a un servidor de informes como un conjunto.</span><span class="sxs-lookup"><span data-stu-id="2fc6e-104">A system role definition specifies a set of system-level tasks that apply to a report server as whole.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2fc6e-105">Las definiciones de roles solo se utilizan en un servidor de informes que se ejecute en modo nativo.</span><span class="sxs-lookup"><span data-stu-id="2fc6e-105">Role definitions are used only on a report server that runs in native mode.</span></span> <span data-ttu-id="2fc6e-106">Si el servidor de informes está configurado para la integración con SharePoint, esta página no está disponible.</span><span class="sxs-lookup"><span data-stu-id="2fc6e-106">If the report server is configured for SharePoint integration, this page is not available.</span></span>  
  
## <a name="options"></a><span data-ttu-id="2fc6e-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="2fc6e-107">Options</span></span>  
 <span data-ttu-id="2fc6e-108">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="2fc6e-108">**Name**</span></span>  
 <span data-ttu-id="2fc6e-109">Escriba el nombre de la definición de roles.</span><span class="sxs-lookup"><span data-stu-id="2fc6e-109">Type the name of the role definition.</span></span> <span data-ttu-id="2fc6e-110">Un nombre de definición de roles debe ser único en el espacio de nombres del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="2fc6e-110">A role definition name must be unique within the report server namespace.</span></span> <span data-ttu-id="2fc6e-111">El nombre debe incluir al menos un carácter alfanumérico.</span><span class="sxs-lookup"><span data-stu-id="2fc6e-111">A name must contain at least one alphanumeric character.</span></span> <span data-ttu-id="2fc6e-112">También puede incluir espacios y algunos símbolos.</span><span class="sxs-lookup"><span data-stu-id="2fc6e-112">It can also include spaces and some symbols.</span></span> <span data-ttu-id="2fc6e-113">No utilice los caracteres siguientes al especificar un nombre:</span><span class="sxs-lookup"><span data-stu-id="2fc6e-113">Do not use the following characters when specifying a name:</span></span>  
  
 <span data-ttu-id="2fc6e-114">; ?</span><span class="sxs-lookup"><span data-stu-id="2fc6e-114">; ?</span></span> <span data-ttu-id="2fc6e-115">: \@ & = +, $/\*\< ></span><span class="sxs-lookup"><span data-stu-id="2fc6e-115">: \@ & = + , $ / \* \< ></span></span>  
  
 <span data-ttu-id="2fc6e-116">" /</span><span class="sxs-lookup"><span data-stu-id="2fc6e-116">" /</span></span>  
  
 <span data-ttu-id="2fc6e-117">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="2fc6e-117">**Description**</span></span>  
 <span data-ttu-id="2fc6e-118">Proporcione una descripción que explique cómo usar el rol y que indique lo que admite.</span><span class="sxs-lookup"><span data-stu-id="2fc6e-118">Provide a description that explains how to use the role and enumerates what the role supports.</span></span>  
  
 <span data-ttu-id="2fc6e-119">**Task**</span><span class="sxs-lookup"><span data-stu-id="2fc6e-119">**Task**</span></span>  
 <span data-ttu-id="2fc6e-120">Seleccione las tareas de nivel de sistema que se pueden realizar mediante este rol.</span><span class="sxs-lookup"><span data-stu-id="2fc6e-120">Select the system-level tasks that can be performed through this role.</span></span> <span data-ttu-id="2fc6e-121">No puede crear nuevas tareas ni modificar las tareas existentes que admite [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2fc6e-121">You cannot create new tasks or modify the existing tasks that are supported by [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="2fc6e-122">No puede elegir tareas de nivel de elemento para una definición de rol del sistema.</span><span class="sxs-lookup"><span data-stu-id="2fc6e-122">You cannot choose item-level tasks for a system role definition.</span></span>  
  
 <span data-ttu-id="2fc6e-123">**Descripción de la tarea**</span><span class="sxs-lookup"><span data-stu-id="2fc6e-123">**Task Description**</span></span>  
 <span data-ttu-id="2fc6e-124">Muestra una descripción de la tarea con las operaciones o los permisos que ésta admite.</span><span class="sxs-lookup"><span data-stu-id="2fc6e-124">Shows a description of the task that enumerates the operations or permissions that the task supports.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fc6e-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2fc6e-125">See Also</span></span>  
 <span data-ttu-id="2fc6e-126">[Servidor de informes en Management Studio ayuda F1](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="2fc6e-126">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 [<span data-ttu-id="2fc6e-127">Definiciones de roles</span><span class="sxs-lookup"><span data-stu-id="2fc6e-127">Role Definitions</span></span>](../security/role-definitions.md)  
  
  
