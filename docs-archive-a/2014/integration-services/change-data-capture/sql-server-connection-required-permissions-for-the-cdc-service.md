---
title: Permisos de conexión con SQL Server necesarios para CDC Service | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: d9e968f9-180c-4fa0-a849-98f2b1942330
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e63b98ffd0371bd5b70ecc0ac843ad40a4a5d03e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671630"
---
# <a name="sql-server-connection-required-permissions-for-the-cdc-service"></a><span data-ttu-id="dbcba-102">Permisos de conexión con SQL Server necesarios para el servicio CDC</span><span class="sxs-lookup"><span data-stu-id="dbcba-102">SQL Server Connection Required Permissions for the CDC Service</span></span>
  <span data-ttu-id="dbcba-103">La Consola de configuración del servicio CDC necesita información de conexión con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para realizar sus tareas.</span><span class="sxs-lookup"><span data-stu-id="dbcba-103">The CDC Service Configuration Console requires connection information to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to perform their tasks.</span></span> <span data-ttu-id="dbcba-104">En este tema se describe la información que se puede proporcionar en el cuadro de diálogo Conectar con SQL Server para configurar la conexión con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dbcba-104">This topic describes the information that can be provided in the Connect to SQL Server dialog box for setting up the connection to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="dbcba-105">El cuadro de diálogo Conectar con SQL Server se abre cuando es necesario, como cuando la información de conexión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no está disponible o si existe la información pero la conexión no tiene los permisos necesarios.</span><span class="sxs-lookup"><span data-stu-id="dbcba-105">The Connect to SQL Server dialog box opens when necessary, such as when the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connection information is not available or when the information exists but the connection does not have the required permissions.</span></span>  
  
 <span data-ttu-id="dbcba-106">En la tabla siguiente se describen las diversas tareas en las que se necesita una conexión con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y los permisos que necesita el inicio de sesión o el usuario de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dbcba-106">The following table describes the various tasks where a connection to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is required and the required permissions from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login/user.</span></span>  
  
|<span data-ttu-id="dbcba-107">Tarea</span><span class="sxs-lookup"><span data-stu-id="dbcba-107">Task</span></span>|<span data-ttu-id="dbcba-108">Permisos mínimos</span><span class="sxs-lookup"><span data-stu-id="dbcba-108">Minimum Permissions</span></span>|  
|----------|-------------------------|  
|<span data-ttu-id="dbcba-109">Preparar la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dbcba-109">Prepare [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Instance.</span></span>|<span data-ttu-id="dbcba-110">`dbcreator` Rol fijo de servidor</span><span class="sxs-lookup"><span data-stu-id="dbcba-110">`dbcreator` fixed-server role</span></span>|  
|<span data-ttu-id="dbcba-111">Crear un inicio de sesión del servicio CDC de Oracle de SQL Server para su uso por parte del servicio CDC de Oracle.</span><span class="sxs-lookup"><span data-stu-id="dbcba-111">Create an Oracle CDC Service-SQL Server login for use by the Oracle CDC service.</span></span>|<span data-ttu-id="dbcba-112">`public` Rol fijo de servidor</span><span class="sxs-lookup"><span data-stu-id="dbcba-112">`public` fixed-server role</span></span>|  
|<span data-ttu-id="dbcba-113">Crear un inicio de sesión del servicio CDC de Oracle que se usará para registrar el nuevo servicio en MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="dbcba-113">Create an Oracle CDC Service-login to use for registering the new service in MSXDBCDC.</span></span>|<span data-ttu-id="dbcba-114">`db_datareader` y `db_datawriter` en MSXDBCDC</span><span class="sxs-lookup"><span data-stu-id="dbcba-114">`db_datareader` and `db_datawriter` roles on MSXDBCDC</span></span>|  
|<span data-ttu-id="dbcba-115">Editar un inicio de sesión del servicio CDC de Oracle que se usará para actualizar el registro del servicio en MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="dbcba-115">Edit an Oracle CDC Service-login to use for updating the registration of the service in MSXDBCDC.</span></span>|<span data-ttu-id="dbcba-116">`db_datareader` y `db_datawriter` en MSXDBCDC</span><span class="sxs-lookup"><span data-stu-id="dbcba-116">`db_datareader` and `db_datawriter` roles on MSXDBCDC</span></span>|  
|<span data-ttu-id="dbcba-117">Eliminar un inicio de sesión del servicio CDC de Oracle que se usará para actualizar el registro del servicio en MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="dbcba-117">Delete an Oracle CDC Service-login to use for updating the registration of the service in MSXDBCDC.</span></span>|<span data-ttu-id="dbcba-118">`db_datareader` y `db_datawriter` en MSXDBCDC</span><span class="sxs-lookup"><span data-stu-id="dbcba-118">`db_datareader` and `db_datawriter` roles on MSXDBCDC</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dbcba-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dbcba-119">See Also</span></span>  
 <span data-ttu-id="dbcba-120">[Conexión con SQL Server](connection-to-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="dbcba-120">[Connection to SQL Server](connection-to-sql-server.md) </span></span>  
 [<span data-ttu-id="dbcba-121">Conexión con SQL Server para eliminación</span><span class="sxs-lookup"><span data-stu-id="dbcba-121">Connection to SQL Server for Delete</span></span>](connection-to-sql-server-for-delete.md)  
  
  
