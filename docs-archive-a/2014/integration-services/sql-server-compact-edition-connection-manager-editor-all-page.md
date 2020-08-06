---
title: Editor del administrador de conexiones de SQL Server Compact Edition (página todos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sqlmobileconnection.all.f1
helpviewer_keywords:
- SQL Server Compact Connection Manager Editor
ms.assetid: f9fbff4b-c502-44b3-8e7b-398d66e82206
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4f881d63de5435426475c3aed4b666870d706b40
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671585"
---
# <a name="sql-server-compact-edition-connection-manager-editor-all-page"></a><span data-ttu-id="d362a-102">Editor del administrador de conexiones con SQL Server Compact Edition (página Todo)</span><span class="sxs-lookup"><span data-stu-id="d362a-102">SQL Server Compact Edition Connection Manager Editor (All Page)</span></span>
  <span data-ttu-id="d362a-103">Use el cuadro de diálogo **Administrador de conexiones con SQL Server Compact Edition** para especificar las propiedades de conexiones a una base de datos de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="d362a-103">Use the **SQL Server Compact Edition Connection Manager** dialog box to specify properties for connecting to a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact database.</span></span>  
  
 <span data-ttu-id="d362a-104">Para obtener más información acerca del administrador de conexiones con [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact Edition, vea [Administrador de conexiones con SQL Server Compact Edition](connection-manager/sql-server-compact-edition-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="d362a-104">To learn more about the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact Edition connection manager, see [SQL Server Compact Edition Connection Manager](connection-manager/sql-server-compact-edition-connection-manager.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="d362a-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="d362a-105">Options</span></span>  
 <span data-ttu-id="d362a-106">**AutoShrink Threshold**</span><span class="sxs-lookup"><span data-stu-id="d362a-106">**AutoShrink Threshold**</span></span>  
 <span data-ttu-id="d362a-107">Especifique la cantidad de espacio disponible, como porcentaje, permitido en la base de datos de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact antes de que se ejecute el proceso de reducción automática.</span><span class="sxs-lookup"><span data-stu-id="d362a-107">Specify the amount of free space, as a percentage, that is allowed in the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact database before the autoshrink process runs.</span></span>  
  
 <span data-ttu-id="d362a-108">**Extensión de bloqueo predeterminada**</span><span class="sxs-lookup"><span data-stu-id="d362a-108">**Default Lock Escalation**</span></span>  
 <span data-ttu-id="d362a-109">Especifique el número de bloqueos de base de datos que adquiere la base de datos de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact antes de intentar concentrar los bloqueos.</span><span class="sxs-lookup"><span data-stu-id="d362a-109">Specify the number of database locks that the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact database acquires before it tries to escalate locks.</span></span>  
  
 <span data-ttu-id="d362a-110">**Default Lock Timeout**</span><span class="sxs-lookup"><span data-stu-id="d362a-110">**Default Lock Timeout**</span></span>  
 <span data-ttu-id="d362a-111">Especifique el intervalo predeterminado, en milisegundos, que una transacción esperará un bloqueo.</span><span class="sxs-lookup"><span data-stu-id="d362a-111">Specify the default interval, in milliseconds, that a transaction will wait for a lock.</span></span>  
  
 <span data-ttu-id="d362a-112">**Flush Interval**</span><span class="sxs-lookup"><span data-stu-id="d362a-112">**Flush Interval**</span></span>  
 <span data-ttu-id="d362a-113">Especifique el intervalo, en segundos, transcurrido entre que las transacciones confirmadas vacían datos en el disco.</span><span class="sxs-lookup"><span data-stu-id="d362a-113">Specify the interval, in seconds, between committed transactions to flush data to disk.</span></span>  
  
 <span data-ttu-id="d362a-114">**Identificador de configuración regional**</span><span class="sxs-lookup"><span data-stu-id="d362a-114">**Locale Identifier**</span></span>  
 <span data-ttu-id="d362a-115">Especifique el identificador de configuración regional (LCID) de la base de datos de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="d362a-115">Specify the Locale ID (LCID) of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact database.</span></span>  
  
 <span data-ttu-id="d362a-116">**Max Buffer Size**</span><span class="sxs-lookup"><span data-stu-id="d362a-116">**Max Buffer Size**</span></span>  
 <span data-ttu-id="d362a-117">Especifique la cantidad máxima de memoria, en kilobytes, que usará [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact antes del vaciado de datos en el disco.</span><span class="sxs-lookup"><span data-stu-id="d362a-117">Specify the maximum amount of memory, in kilobytes, that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact uses before flushing data to disk.</span></span>  
  
 <span data-ttu-id="d362a-118">**Tamaño máximo de la base de datos**</span><span class="sxs-lookup"><span data-stu-id="d362a-118">**Max Database Size**</span></span>  
 <span data-ttu-id="d362a-119">Especifique el tamaño máximo, en megabytes, de la base de datos de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="d362a-119">Specify the maximum size, in megabytes, of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact database.</span></span>  
  
 <span data-ttu-id="d362a-120">**Modo**</span><span class="sxs-lookup"><span data-stu-id="d362a-120">**Mode**</span></span>  
 <span data-ttu-id="d362a-121">Especifique el modo de archivo en el que se abrirá la base de datos de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="d362a-121">Specify the file mode in which to open the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact database.</span></span> <span data-ttu-id="d362a-122">El valor predeterminado para esta propiedad es **Lectura y escritura**.</span><span class="sxs-lookup"><span data-stu-id="d362a-122">The default value for this property is **Read Write**.</span></span>  
  
 <span data-ttu-id="d362a-123">La opción Modo tiene cuatro valores, tal como se describe en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="d362a-123">The Mode option has four values, as described in the following table.</span></span>  
  
|<span data-ttu-id="d362a-124">Value</span><span class="sxs-lookup"><span data-stu-id="d362a-124">Value</span></span>|<span data-ttu-id="d362a-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="d362a-125">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d362a-126">**Solo lectura**</span><span class="sxs-lookup"><span data-stu-id="d362a-126">**Read Only**</span></span>|<span data-ttu-id="d362a-127">Especifica acceso de solo lectura a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="d362a-127">Specifies read-only access to the database.</span></span>|  
|<span data-ttu-id="d362a-128">**Lectura y escritura**</span><span class="sxs-lookup"><span data-stu-id="d362a-128">**Read Write**</span></span>|<span data-ttu-id="d362a-129">Especifica permiso de lectura/escritura a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="d362a-129">Specifies read/write permission to the database.</span></span>|  
|<span data-ttu-id="d362a-130">**Exclusivo**</span><span class="sxs-lookup"><span data-stu-id="d362a-130">**Exclusive**</span></span>|<span data-ttu-id="d362a-131">Especifica acceso exclusivo a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="d362a-131">Specifies exclusive access to the database.</span></span>|  
|<span data-ttu-id="d362a-132">**Shared Read**</span><span class="sxs-lookup"><span data-stu-id="d362a-132">**Shared Read**</span></span>|<span data-ttu-id="d362a-133">Especifica que otros usuarios pueden leer de la base de datos al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="d362a-133">Specifies that other users can read from the database at the same time.</span></span>|  
  
 <span data-ttu-id="d362a-134">**Persist Security Info**</span><span class="sxs-lookup"><span data-stu-id="d362a-134">**Persist Security Info**</span></span>  
 <span data-ttu-id="d362a-135">Especifique si la información de seguridad será devuelta como parte de la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="d362a-135">Specify whether security information is returned as part of the connection string.</span></span> <span data-ttu-id="d362a-136">El valor predeterminado de esta opción es **false**.</span><span class="sxs-lookup"><span data-stu-id="d362a-136">The default value for this option is **False**.</span></span>  
  
 <span data-ttu-id="d362a-137">**Temp File Directory**</span><span class="sxs-lookup"><span data-stu-id="d362a-137">**Temp File Directory**</span></span>  
 <span data-ttu-id="d362a-138">Especifique la ubicación del archivo de base de datos temporal de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="d362a-138">Specify the location of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact temporary database file.</span></span>  
  
 <span data-ttu-id="d362a-139">**Data Source** (Origen de datos)</span><span class="sxs-lookup"><span data-stu-id="d362a-139">**Data Source**</span></span>  
 <span data-ttu-id="d362a-140">Especifique el nombre de la base de datos de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="d362a-140">Specify the name of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact database.</span></span>  
  
 <span data-ttu-id="d362a-141">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="d362a-141">**Password**</span></span>  
 <span data-ttu-id="d362a-142">Escriba la contraseña de la base de datos de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="d362a-142">Enter the password for the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d362a-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d362a-143">See Also</span></span>  
 <span data-ttu-id="d362a-144">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="d362a-144">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="d362a-145">Editor del administrador de conexiones con SQL Server Compact Edition &#40;página Conexión&#41;</span><span class="sxs-lookup"><span data-stu-id="d362a-145">SQL Server Compact Edition Connection Manager Editor &#40;Connection Page&#41;</span></span>](../../2014/integration-services/sql-server-compact-edition-connection-manager-editor-connection-page.md)  
  
  
