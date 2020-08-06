---
title: Ver o cambiar las ubicaciones predeterminadas de los archivos de datos y de registro (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- log files [SQL Server], changing default location
- data files [SQL Server], changing default location
ms.assetid: 70a57fda-fcfe-490f-9cf6-5df620e32b2a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: def6be137aecbab7f2730fa4c2bf210b374a3a7a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744852"
---
# <a name="view-or-change-the-default-locations-for-data-and-log-files-sql-server-management-studio"></a><span data-ttu-id="a4051-102">Ver o cambiar las ubicaciones predeterminadas de los archivos de datos y registro (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="a4051-102">View or Change the Default Locations for Data and Log Files (SQL Server Management Studio)</span></span>
  <span data-ttu-id="a4051-103">En este tema se describe cómo ver y cambiar las ubicaciones predeterminadas de los archivos de datos y registro nuevos en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a4051-103">This topic describes how to view and change the default locations of new data and log files in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="a4051-104">La ruta de acceso predeterminada se obtiene del Registro.</span><span class="sxs-lookup"><span data-stu-id="a4051-104">The default path is obtained from the registry.</span></span> <span data-ttu-id="a4051-105">Después de cambiar la ubicación todas las nuevas bases de datos creadas en la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , utilizará dicha ubicación si no se ha especificado otra.</span><span class="sxs-lookup"><span data-stu-id="a4051-105">After you change the location all new databases created in the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will use that location if a different location is not specified.</span></span>  
  
 <span data-ttu-id="a4051-106">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="a4051-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a4051-107">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="a4051-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a4051-108">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="a4051-108">Recommendations</span></span>](#Recommendations)  
  
-   <span data-ttu-id="a4051-109">**Para ver o cambiar las ubicaciones predeterminadas de los archivos de datos y de registro, use:**</span><span class="sxs-lookup"><span data-stu-id="a4051-109">**To view or change the data and log file default locations, using:**</span></span>  
  
     [<span data-ttu-id="a4051-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a4051-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   <span data-ttu-id="a4051-111">**Seguimiento:**  [Cambiar las ubicaciones predeterminadas](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="a4051-111">**Follow Up:**  [Changing the Default Locations](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a4051-112">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="a4051-112">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="a4051-113">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="a4051-113">Recommendations</span></span>  
 <span data-ttu-id="a4051-114">El mejor procedimiento para proteger los archivos de datos y de registro es asegurarse de que estén protegidos mediante listas de control de acceso (ACL).</span><span class="sxs-lookup"><span data-stu-id="a4051-114">The best practice for protecting your data files and log files is to ensure that they are protected by access control lists (ACLs).</span></span> <span data-ttu-id="a4051-115">Las listas de control de acceso se deben establecer en el directorio raíz en el que se crean los archivos.</span><span class="sxs-lookup"><span data-stu-id="a4051-115">The ACLs should be set on the directory root under which the files are created.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a4051-116">Seguridad</span><span class="sxs-lookup"><span data-stu-id="a4051-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a4051-117">Permisos</span><span class="sxs-lookup"><span data-stu-id="a4051-117">Permissions</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a4051-118">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a4051-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-or-change-the-default-locations-for-database-files"></a><span data-ttu-id="a4051-119">Para ver o cambiar las ubicaciones predeterminadas de los archivos de base de datos</span><span class="sxs-lookup"><span data-stu-id="a4051-119">To view or change the default locations for database files</span></span>  
  
1.  <span data-ttu-id="a4051-120">En el Explorador de objetos, haga clic con el botón derecho en un servidor y haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="a4051-120">In Object Explorer, right-click a server and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="a4051-121">En el panel izquierdo, haga clic en la página **Configuración de base de datos** .</span><span class="sxs-lookup"><span data-stu-id="a4051-121">In the left panel, click the **Database settings** page.</span></span>  
  
3.  <span data-ttu-id="a4051-122">En **Ubicaciones predeterminadas de la base de datos**, vea las ubicaciones predeterminadas actuales de los archivos de datos y de registro nuevos.</span><span class="sxs-lookup"><span data-stu-id="a4051-122">In **Database default locations**, view the current default locations for new data files and new log files.</span></span> <span data-ttu-id="a4051-123">Para cambiar una ubicación predeterminada, escriba una nueva ruta de acceso predeterminada en el campo **Datos** o **Registro** , o haga clic en el botón Examinar para buscar y seleccionar una ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="a4051-123">To change a default location, enter a new default pathname in the **Data** or **Log** field, or click the browse button to find and select a pathname.</span></span>  
  
##  <a name="follow-up-after-changing-the-default-locations"></a><a name="FollowUp"></a><span data-ttu-id="a4051-124">Seguimiento: después de cambiar las ubicaciones predeterminadas</span><span class="sxs-lookup"><span data-stu-id="a4051-124">Follow Up: After Changing the Default Locations</span></span>  
 <span data-ttu-id="a4051-125">Debe detener e iniciar el servicio SQL Server para completar el cambio.</span><span class="sxs-lookup"><span data-stu-id="a4051-125">You must stop and start the SQL Server service to complete the change.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4051-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a4051-126">See Also</span></span>  
 <span data-ttu-id="a4051-127">[CREATE DATABASE &#40;Transact-SQL de SQL Server&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a4051-127">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 [<span data-ttu-id="a4051-128">Crear una base de datos</span><span class="sxs-lookup"><span data-stu-id="a4051-128">Create a Database</span></span>](../../relational-databases/databases/create-a-database.md)  
  
  
