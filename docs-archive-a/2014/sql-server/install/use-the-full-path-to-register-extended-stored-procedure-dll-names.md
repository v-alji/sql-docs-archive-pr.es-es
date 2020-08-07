---
title: Usar la ruta de acceso completa para registrar nombres de archivos DLL de procedimientos almacenados extendidos | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- registering DLL names
- extended stored procedures [SQL Server], registering
- DLL names [SQL Server]
- full path DLL name registration [SQL Server]
ms.assetid: f648d57c-af32-4c71-9882-47b6766f3c2b
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 5ec4ef3fc2e0f2c4834ffa7479a00562ae15d07f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746089"
---
# <a name="use-the-full-path-to-register-extended-stored-procedure-dll-names"></a><span data-ttu-id="d9ba2-102">Utilizar la ruta de acceso completa para registrar nombres de DLL de procedimiento almacenado extendido</span><span class="sxs-lookup"><span data-stu-id="d9ba2-102">Use the full path to register extended stored procedure DLL names</span></span>
  <span data-ttu-id="d9ba2-103">Es posible que los procedimientos almacenados extendidos registrados anteriormente sin la ruta de acceso completa para el nombre de DLL no funcionen en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d9ba2-103">Extended stored procedures that were previously registered without the full path for the DLL name may not work in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
## <a name="component"></a><span data-ttu-id="d9ba2-104">Componente</span><span class="sxs-lookup"><span data-stu-id="d9ba2-104">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="d9ba2-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="d9ba2-105">Description</span></span>  
 <span data-ttu-id="d9ba2-106">Es posible que los procedimientos almacenados extendidos registrados anteriormente sin la ruta de acceso completa para el nombre de DLL no funcionen después de realizar la actualización.</span><span class="sxs-lookup"><span data-stu-id="d9ba2-106">Extended stored procedures that were previously registered without the full path for the DLL name may not work after you upgrade.</span></span> <span data-ttu-id="d9ba2-107">Esto se debe a que, durante el proceso de actualización, no se agrega el antiguo directorio BINN a la nueva ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="d9ba2-107">This is because the old BINN directory is not added to the new path during the upgrade process.</span></span> <span data-ttu-id="d9ba2-108">Es posible que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no pueda encontrar los procedimientos almacenados extendidos.</span><span class="sxs-lookup"><span data-stu-id="d9ba2-108">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] may not be able to locate the extended stored procedures.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="d9ba2-109">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="d9ba2-109">Corrective Action</span></span>  
 <span data-ttu-id="d9ba2-110">Antes de actualizar, siga estos pasos para cada procedimiento almacenado extendido que no se haya registrado con un nombre completo de ruta de acceso:</span><span class="sxs-lookup"><span data-stu-id="d9ba2-110">Before you upgrade, follow these steps for each extended stored procedure that was not registered with a full path name:</span></span>  
  
1.  <span data-ttu-id="d9ba2-111">Ejecute sp_dropextendedproc para quitar el procedimiento almacenado extendido.</span><span class="sxs-lookup"><span data-stu-id="d9ba2-111">Run sp_dropextendedproc to remove the extended stored procedure.</span></span>  
  
2.  <span data-ttu-id="d9ba2-112">Ejecute sp_addextendedproc para registrar el procedimiento almacenado extendido con el nombre completo de ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="d9ba2-112">Run sp_addextendedproc to register the extended stored procedure with the full path name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9ba2-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d9ba2-113">See Also</span></span>  
 <span data-ttu-id="d9ba2-114">[Problemas de actualización Motor de base de datos](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="d9ba2-114">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="d9ba2-115">SQL Server el asesor de actualizaciones de 2014 &#91;nuevo&#93;</span><span class="sxs-lookup"><span data-stu-id="d9ba2-115">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
